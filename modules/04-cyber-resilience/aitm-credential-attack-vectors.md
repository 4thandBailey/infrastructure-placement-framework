---
title: "AiTM Phishing and Public Authentication Endpoint Abuse — Microsoft 365 Attack Analysis"
description: "How adversary-in-the-middle (AiTM) phishing bypasses MFA to compromise Microsoft 365 accounts via Azure CLI and PowerShell. Includes anonymized case study, detection indicators, defensive controls, and remediation sequence."
keywords: ["AiTM phishing", "adversary in the middle", "Microsoft 365 account compromise", "MFA bypass", "Azure CLI attack", "Entra ID sign-in logs", "session token hijacking", "FIDO2 security keys", "Token Protection Conditional Access", "cyber resilience"]
module: "04-cyber-resilience"
document_type: "threat-intelligence-supplement"
source: "confirmed-incident-anonymized"
date: "2026-05-15"
author: "4th and Bailey | Information Technology Consulting"
license: "CC BY 4.0"
mitre: ["T1557", "T1098.005", "T1564.008"]
---

# AiTM Phishing and Public Authentication Endpoint Abuse

> **Module 04 — Cyber Resilience and Business Continuity**
> Threat intelligence supplement · Derived from a confirmed incident · May 2026

Adversary-in-the-middle (AiTM) phishing is one of the most operationally dangerous attack techniques targeting Microsoft 365 environments because it defeats multi-factor authentication entirely — not by cracking it, but by capturing the authenticated session token in real time. This document explains how the attack works, what the sign-in and audit logs reveal, which controls actually stop it, and how to remediate a confirmed compromise.

---

## Contents

1. [Attack Mind Map](#attack-mind-map)
2. [How Azure CLI and PowerShell Are Used in Attacks](#how-azure-cli-and-powershell-authentication-works-against-a-target-tenant)
3. [Anonymized Case Study — Three-Phase Attack Pattern](#confirmed-incident-pattern--anonymized-case-study)
4. [Why Standard MFA Does Not Stop AiTM](#why-standard-mfa-does-not-stop-aitm-attacks)
5. [What Actually Stops These Attacks](#what-actually-stops-these-attacks)
6. [Inbox Rule Persistence](#inbox-rule-persistence--a-frequently-overlooked-artifact)
7. [Remediation Sequence](#remediation-sequence-for-confirmed-aitm-compromise)
8. [Relationship to Framework Controls](#relationship-to-framework-controls)
9. [Frequently Asked Questions](#frequently-asked-questions)
10. [References](#references)

---

## Attack Mind Map

The diagram below maps the full AiTM attack pattern across three color-coded branches: the attack chain (left), the defensive controls that address each phase (right), and the post-compromise remediation sequence (bottom). Use it as a quick reference during incident response or client briefings.

![AiTM phishing attack mind map — three-branch diagram showing credential spray, PowerShell probing, AiTM breach, and persistence on the left; FIDO2 MFA, Token Protection, Safe Links, and Identity Protection on the right; five-step remediation sequence across the bottom.](../../assets/aitm-attack-mind-map.svg)

*Figure 1: AiTM phishing attack mind map. Left branch = attack chain (credential spray → PowerShell probing → AiTM breach → persistence). Right branch = defensive controls (FIDO2 MFA, Token Protection, Defender Safe Links/Attachments, Identity Protection). Bottom band = five-step remediation sequence. Color coding: red = attacker actions, green = defensive controls, blue = remediation steps. Derived from a confirmed Microsoft 365 account compromise. All identifying details anonymized.*

---

## How Azure CLI and PowerShell Authentication Works Against a Target Tenant

A common question after a Microsoft 365 account compromise involving Azure CLI or PowerShell is:

> *"Did the attacker use another account inside our tenant, or did they need access to another Microsoft cloud environment to launch the attack?"*

The answer to both is **no** — and understanding why is essential to building controls that actually match the threat.

Azure CLI (`az`) and Azure AD PowerShell are **freely available client tools** that anyone can download and install on any machine, anywhere in the world. They are not privileged utilities — they are the same tools your IT team uses, redistributed by Microsoft publicly.

When a threat actor executes a command such as:

```bash
az login --username user@yourdomain.com --password <credential>
```

That request travels directly to Microsoft's **public authentication endpoint** at `login.microsoftonline.com`. Microsoft's identity platform has no way to determine — and does not require — that the request originates from inside the target organization's network, from a trusted device, or from any Microsoft infrastructure associated with the target tenant. It receives credentials and evaluates them.

This means:

- **No access to the target tenant is required to attack it.** The attacker operates from their own machines entirely.
- **No access to a second Microsoft tenant is required.** The public endpoint is available to the entire internet.
- **The attacker's infrastructure is their own** — virtual servers, residential proxies, or cloud instances they rent or control.

The `Client App` field in Microsoft Entra ID sign-in logs (`Microsoft Azure CLI`, `Mobile Apps and Desktop clients`) records **what software was used to make the authentication request**, not where the attacker authenticated from within any organizational boundary.

---

## Confirmed Incident Pattern — Anonymized Case Study

The following pattern was observed in a confirmed Microsoft 365 account compromise affecting a mid-market organization. All identifying details have been anonymized.

### Phase 1 — Credential Spray Campaign (Days 1–6)

A threat actor operating through **ASN 53667** (a single hosting provider) rotated across dozens of IPv6 addresses resolving to three geographic regions: Luxembourg, Las Vegas (NV), and Cheyenne (WY).

Every attempt used **Microsoft Azure CLI** as the authentication client. The campaign targeted a single user account, producing **96 failed sign-in attempts** across a 6-day window. Each burst of 2–5 attempts in rapid succession triggered an account lockout (Entra error code `50053`), followed by a pause of several hours before the next wave.

**This campaign never succeeded.** Standard account lockout policy prevented credential validation. The geographic dispersion of source IPs — all resolving to the same upstream ASN — is a characteristic signature of a single actor rotating through a proxy pool, not multiple independent attackers.

> **Key takeaway:** The spray campaign tells us the attacker had the username and a credential list, but not the current password. It also tells us they were persistent, organized, and operating from infrastructure they controlled — not from inside the target organization or any affiliated tenant.

### Phase 2 — PowerShell Administrative Probing

On day 7, two authentication attempts were recorded from a separate IP block (different provider, different geography) using **Azure Active Directory PowerShell** rather than Azure CLI.

This distinction matters. Azure CLI is a general-purpose tool for interacting with Azure resources. **Azure AD PowerShell is specifically used to manage directory objects** — users, groups, roles, licenses, and conditional access policies. Its use as an attack tool signals that the actor was not merely testing for mailbox access; they were probing for **directory-level and administrative access**.

Both attempts failed. However, organizations should treat unexpected Azure AD PowerShell authentication attempts — especially on accounts that have recently experienced failed sign-ins — as a distinct, elevated-severity indicator.

### Phase 3 — AiTM Phishing Breach

The actual account compromise did not come through the credential spray. It came through an **adversary-in-the-middle (AiTM) phishing attack** — a technique that defeats standard multi-factor authentication entirely.

The critical indicator in the sign-in log was:

```
Multifactor authentication result: MFA requirement satisfied by claim in the token
```

This phrase means **no interactive MFA challenge occurred at the point of the attacker's sign-in.** A pre-captured, already-authenticated session token was presented. The attacker had obtained this token by proxying the victim's real Microsoft authentication session — capturing the password, the completed MFA approval, and the resulting session cookie simultaneously.

Within 3 hours of the initial breach, the attacker:

1. Completed a live MFA challenge from their own device (now using the captured credentials plus MFA push)
2. Registered a new Authenticator device to the account — providing independent, durable MFA persistence
3. Created an inbox rule named `"."` (single period) to silently route incoming messages, concealing their activity from the legitimate account holder
4. Maintained persistent mailbox access for approximately 26 hours before remediation

---

## Why Standard MFA Does Not Stop AiTM Attacks

This is the most operationally important concept in this document.

Standard MFA — SMS codes, authenticator app push notifications, TOTP — protects against an attacker who has the **password but not the second factor**. AiTM phishing defeats this model entirely because it captures all three elements at the same time:

| What AiTM captures | What it enables |
|---|---|
| The victim's password | Credential reuse across services |
| The victim's completed MFA approval | Full authenticated session |
| The resulting session token (cookie) | Replay without further MFA |

The attack works because the session token — issued by Microsoft after successful authentication — is not bound to the device or network that originally authenticated. An attacker who captures that token can present it from any device, anywhere, and Microsoft's identity platform will honor it.

This is not a vulnerability in Microsoft's implementation — it is an architectural characteristic of web-based authentication that AiTM toolkits are specifically designed to exploit. Known toolkits include Evilginx, Modlishka, and variants documented in Microsoft Threat Intelligence advisories.

---

## What Actually Stops These Attacks

### Phishing-Resistant MFA (Addresses Phase 3)

**FIDO2 hardware security keys** (e.g., YubiKey, Feitian) are cryptographically bound to the specific domain being authenticated against. A FIDO2 key will refuse to authenticate to a domain that is not the legitimate Microsoft login endpoint — the AiTM proxy's domain will not match, and the authentication will fail regardless of how convincing the phishing page looks.

**Microsoft Authenticator with number matching** raises the bar significantly for AiTM attacks as an interim measure. The attacker must relay the correct number shown on the victim's screen in real time — harder to automate, more visible to the victim.

### Conditional Access Token Protection (Addresses Phase 3)

Microsoft's **Token Protection** feature cryptographically binds session tokens to the device they were issued to. A token captured via AiTM cannot be used from a different device — even if the attacker possesses it. This directly eliminates the mechanism that allowed session token replay in the confirmed incident above.

Available in Entra ID P1 licensing. Pilot with privileged accounts and IT staff before tenant-wide rollout.

### Conditional Access — Geographic and ASN-Based Restrictions (Addresses Phase 1)

If the organization's user population does not legitimately authenticate from overseas locations or unexpected IPv6 ranges, a Conditional Access Named Location policy can block or require step-up authentication from those ranges. This would not have stopped the AiTM breach (which used a domestic IP), but it would have eliminated the majority of the spray campaign attempts before they were logged.

### Entra ID Identity Protection — Risk-Based Conditional Access (Addresses Phase 1 and 3)

Identity Protection can automatically require re-authentication or block sign-ins when a risk signal is detected. The Phase 1 spray pattern — burst attempts from rotating IPs at irregular hours — is precisely the pattern that risk-based policies are designed to catch. Enabling automatic remediation (rather than just flagging) for high-risk sign-ins closes the gap between detection and response.

### Alerting on MFA Device Registration Events (Addresses Phase 3 persistence)

In the confirmed incident, the attacker registered a rogue Authenticator device to the compromised account within 3 hours of the initial breach. This event was visible in the Azure audit log — but no automated alert was generated for it.

A custom alert rule targeting MFA device registration events — particularly on accounts with recent failed sign-in history — would have triggered immediate response and significantly shortened the attacker's dwell time. This can be implemented in Microsoft Sentinel or Defender XDR without additional licensing beyond what most Entra ID P1 deployments include.

### Defender for Office 365 — Safe Links and Safe Attachments (Addresses AiTM delivery)

AiTM phishing requires delivering a convincing link or attachment to the victim. **Safe Links** rewrites and validates every URL in email at click time. **Safe Attachments** detonates attachments in a sandbox before delivery. Either control, if active, would have intercepted the phishing delivery mechanism before the victim could interact with it — preventing the AiTM session capture entirely.

---

## Inbox Rule Persistence — A Frequently Overlooked Artifact

After gaining access, threat actors frequently create inbox rules to:

- **Conceal security alert emails** from the legitimate account holder (password reset confirmations, MFA registration notifications, Microsoft security alerts)
- **Support Business Email Compromise (BEC)** by hiding reply threads from fraudulent emails sent in the victim's name
- **Intercept communications** from colleagues or systems that might reveal the breach

In the confirmed incident, the attacker created a rule named `"."` (a single period) — a deliberate obfuscation technique designed to be visually inconspicuous in the rules list. The rule was active but had not yet been used to divert messages at the time of discovery.

**Critical operational note:** Password reset, token invalidation, and MFA device removal — the standard remediation steps — do **not** automatically remove inbox rules. Rules persist on the mailbox object independently of the user account's authentication state. A mailbox audit is always required as part of any account compromise remediation.

Post-compromise mailbox audit checklist:

- [ ] Inbox rules — check for unexpected, obfuscated, or unnamed rules
- [ ] Forwarding settings — check Outlook Settings > Mail > Forwarding for external forwarding addresses
- [ ] OAuth app grants — check Entra ID > Users > [account] > Applications for unexpected third-party app permissions
- [ ] Sent Items — review the breach window for emails sent by the attacker impersonating the account holder
- [ ] Delegate access — confirm no mailbox delegation was granted to an external or unexpected account

---

## Remediation Sequence for Confirmed AiTM Compromise

The following sequence was validated in the confirmed incident. All steps should be executed in a single session to minimize the window between partial and complete remediation.

1. **Remove all MFA device registrations** from the compromised account (Entra ID > Users > Authentication methods). This revokes the attacker's independently registered authenticator device.
2. **Delete attacker-registered security info** — phone number and email address added during the compromise window.
3. **Reset the account password** and set `ForceChangePassword = True`.
4. **Invalidate all STS refresh tokens** (Entra ID > Users > Revoke sessions, or via PowerShell: `Revoke-MgUserSignInSession`). This terminates all active authenticated sessions regardless of how they were established.
5. **Review and remove inbox rules** in Outlook Web.
6. **Check Forwarding settings** for external forwarding addresses.
7. **Audit OAuth app grants** on the user object.
8. **Review Sent Items** for the breach window.
9. **Document the incident** — note the STS token invalidation timestamp as the confirmed end of unauthorized access.

For organizations with confirmed deep compromise, provisioning a **new account and migrating email** to a clean mailbox eliminates any risk of persistence mechanisms that were not detected during the audit. This approach is more conservative than remediation in place and is appropriate when the dwell time was extended, the account held administrative privileges, or the audit scope is uncertain.

---

## Relationship to Framework Controls

| Attack phase | Framework module | Control |
|---|---|---|
| Public endpoint credential spray | Module 04 — Identity resilience | Entra ID Identity Protection, Conditional Access Named Locations |
| AiTM session token capture | Module 04 — Identity resilience | FIDO2 MFA, Token Protection |
| AiTM phishing delivery | Module 04 — Email security | Defender for Office 365 Safe Links / Safe Attachments |
| Rogue MFA device registration | Module 04 — Monitoring | Sentinel / Defender XDR alert on registration events |
| Inbox rule persistence | Module 04 — Incident response | Post-compromise mailbox audit checklist |
| Administrative PowerShell probing | Module 04 — Identity resilience | Privileged Identity Management, Conditional Access for admin roles |

---

## Frequently Asked Questions

**Does the attacker need to be inside our Microsoft tenant to use Azure CLI against us?**
No. Azure CLI and Azure AD PowerShell are publicly available tools that authenticate against Microsoft's public `login.microsoftonline.com` endpoint. Any attacker on the internet can target any tenant — no internal access is required.

**If MFA is enabled, how did the attacker get in?**
AiTM phishing captures the authenticated session token — the result of a successful MFA challenge — not the MFA code itself. The victim completes their own legitimate MFA; the proxy intercepts the resulting session cookie before it reaches the browser. Standard push-notification MFA does not prevent this.

**What is the single highest-impact control to deploy against AiTM phishing?**
FIDO2 hardware security keys. They are cryptographically bound to the legitimate login domain and will refuse to authenticate to any AiTM proxy, regardless of how convincing the phishing page appears. As an interim step with no additional licensing cost, enabling number matching in Microsoft Authenticator significantly raises the bar.

**Do standard remediation steps remove inbox rules?**
No. Password resets, token revocation, and MFA device removal do not touch inbox rules. Rules persist on the mailbox object and must be audited and removed separately.

---

## References

- Microsoft Identity Platform — Sign-in logs and error codes: `50053` (account locked), `50126` (invalid credentials)
- Microsoft Threat Intelligence — AiTM phishing campaigns targeting Microsoft 365
- NIST SP 800-63B — Digital Identity Guidelines, Authenticator Assurance Levels
- MITRE ATT&CK T1557 — Adversary-in-the-Middle
- MITRE ATT&CK T1098.005 — Account Manipulation: Device Registration
- MITRE ATT&CK T1564.008 — Hide Artifacts: Email Hiding Rules

---

*Infrastructure Placement Framework — Module 04 Supplement*
*4th and Bailey | Information Technology Consulting · Houston, TX*
*github.com/4thandBailey/infrastructure-placement-framework · CC BY 4.0*
