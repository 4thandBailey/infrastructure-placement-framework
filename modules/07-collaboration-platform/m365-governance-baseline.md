# Module 7 — Microsoft 365 Governance Baseline

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

**Assessment date:** _______________________________________________

---

## Section A — Identity and access (Entra ID)

| # | Control | Status | Notes |
|---|---|---|---|
| A1 | All global administrators use dedicated admin accounts (not daily-use accounts) | ✅ / ⚠️ / ❌ | |
| A2 | Global admin count is 2–4 (no more) | ✅ / ⚠️ / ❌ | |
| A3 | MFA enforced for all users via Conditional Access (not just per-user MFA) | ✅ / ⚠️ / ❌ | |
| A4 | Phishing-resistant MFA (FIDO2 or authenticator app) for all admins | ✅ / ⚠️ / ❌ | |
| A5 | Legacy authentication protocols blocked (Basic Auth, SMTP AUTH where not needed) | ✅ / ⚠️ / ❌ | |
| A6 | Privileged Identity Management (PIM) enabled for admin roles (E3/E5) | ✅ / ⚠️ / ❌ | |
| A7 | Guest access reviewed in last 90 days; stale guests removed | ✅ / ⚠️ / ❌ | |
| A8 | External collaboration settings restrict domains to approved list | ✅ / ⚠️ / ❌ | |

**Section A score:** _____ / 8 = _____%

---

## Section B — Email security (Exchange Online)

| # | Control | Status | Notes |
|---|---|---|---|
| B1 | SPF record published and valid | ✅ / ⚠️ / ❌ | |
| B2 | DKIM signing enabled for all sending domains | ✅ / ⚠️ / ❌ | |
| B3 | DMARC record published with at minimum p=quarantine | ✅ / ⚠️ / ❌ | |
| B4 | Defender for Office 365 — Safe Links enabled | ✅ / ⚠️ / ❌ | |
| B5 | Defender for Office 365 — Safe Attachments enabled | ✅ / ⚠️ / ❌ | |
| B6 | Anti-phishing policies configured for impersonation protection | ✅ / ⚠️ / ❌ | |
| B7 | Audit logging enabled for mailboxes | ✅ / ⚠️ / ❌ | |
| B8 | Email retention policies configured to meet compliance requirements | ✅ / ⚠️ / ❌ | |

**Section B score:** _____ / 8 = _____%

---

## Section C — SharePoint and OneDrive

| # | Control | Status | Notes |
|---|---|---|---|
| C1 | External sharing policy set to organisation-appropriate level (not "Anyone") | ✅ / ⚠️ / ❌ | |
| C2 | Site-level external sharing reviewed and documented | ✅ / ⚠️ / ❌ | |
| C3 | Sensitivity labels applied to confidential sites and libraries | ✅ / ⚠️ / ❌ | |
| C4 | DLP policies configured for sensitive data types | ✅ / ⚠️ / ❌ | |
| C5 | Inactive sites reviewed in last 6 months | ✅ / ⚠️ / ❌ | |
| C6 | Guest access expiry policies configured | ✅ / ⚠️ / ❌ | |

**Section C score:** _____ / 6 = _____%

---

## Section D — Microsoft Teams

| # | Control | Status | Notes |
|---|---|---|---|
| D1 | Team creation rights restricted (not all users can create Teams) | ✅ / ⚠️ / ❌ | |
| D2 | Guest access reviewed; guests limited to necessary Teams only | ✅ / ⚠️ / ❌ | |
| D3 | External access (federation) restricted to known partner domains | ✅ / ⚠️ / ❌ | |
| D4 | Teams meeting recording storage policy defined | ✅ / ⚠️ / ❌ | |
| D5 | Inactive Teams reviewed and archived in last 6 months | ✅ / ⚠️ / ❌ | |

**Section D score:** _____ / 5 = _____%

---

## Section E — Licensing and cost

| # | Control | Status | Notes |
|---|---|---|---|
| E1 | Licence utilisation reviewed in last 30 days | ✅ / ⚠️ / ❌ | |
| E2 | Inactive user licences reclaimed (users not logged in > 90 days) | ✅ / ⚠️ / ❌ | |
| E3 | Licence assignment matches actual plan tier needed (no over-provisioning) | ✅ / ⚠️ / ❌ | |
| E4 | Copilot licences assigned only to active, trained users | ✅ / ⚠️ / ❌ | |

**Section E score:** _____ / 4 = _____%

---

## Section F — Microsoft 365 Copilot governance

*Complete only if Copilot is licensed or under evaluation.*

| # | Control | Status | Notes |
|---|---|---|---|
| F1 | Copilot data handling terms reviewed and accepted by legal/security | ✅ / ⚠️ / ❌ | |
| F2 | Sensitivity labels applied to data that should NOT be accessible to Copilot | ✅ / ⚠️ / ❌ | |
| F3 | Over-sharing audit completed — confidential data accessible to all staff reviewed | ✅ / ⚠️ / ❌ | |
| F4 | Copilot acceptable use guidance communicated to users | ✅ / ⚠️ / ❌ | |
| F5 | Copilot interaction logs retained and reviewable | ✅ / ⚠️ / ❌ | |

**Section F score:** _____ / 5 = _____%

---

## M365 governance scorecard

| Section | Controls | Score |
|---|---|---|
| A — Identity and access | 8 | ____% |
| B — Email security | 8 | ____% |
| C — SharePoint / OneDrive | 6 | ____% |
| D — Microsoft Teams | 5 | ____% |
| E — Licensing | 4 | ____% |
| F — Copilot governance | 5 | ____% |
| **Overall** | **36** | ____% |

**Next review date:** _______________________________________________

---

*Infrastructure Placement Framework · Module 7 M365 Governance Baseline · 4th and Bailey · v1.0.0*
