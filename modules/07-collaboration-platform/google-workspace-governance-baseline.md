# Module 7 — Google Workspace Governance Baseline

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

**Assessment date:** _______________________________________________

---

## Section A — Admin and identity

| # | Control | Status | Notes |
|---|---|---|---|
| A1 | Super admin accounts are dedicated accounts (not daily-use accounts) | ✅ / ⚠️ / ❌ | |
| A2 | Super admin count is 2–4; all require hardware security key (FIDO2) | ✅ / ⚠️ / ❌ | |
| A3 | 2-Step Verification enforced for all users via Admin policy | ✅ / ⚠️ / ❌ | |
| A4 | Admin activity audit logs reviewed regularly | ✅ / ⚠️ / ❌ | |
| A5 | External guest users reviewed in last 90 days | ✅ / ⚠️ / ❌ | |
| A6 | Context-Aware Access policies configured for sensitive apps | ✅ / ⚠️ / ❌ | |

**Section A score:** _____ / 6 = _____%

---

## Section B — Gmail security

| # | Control | Status | Notes |
|---|---|---|---|
| B1 | SPF, DKIM, and DMARC configured for all sending domains | ✅ / ⚠️ / ❌ | |
| B2 | Email security sandbox (Advanced Protection) enabled | ✅ / ⚠️ / ❌ | |
| B3 | Anti-phishing enhanced pre-delivery message scanning enabled | ✅ / ⚠️ / ❌ | |
| B4 | Gmail confidential mode governance policy defined | ✅ / ⚠️ / ❌ | |
| B5 | Email retention policies configured to meet compliance requirements | ✅ / ⚠️ / ❌ | |
| B6 | Vault (Google Workspace Vault) configured for legal hold and eDiscovery | ✅ / ⚠️ / ❌ | |

**Section B score:** _____ / 6 = _____%

---

## Section C — Drive and sharing

| # | Control | Status | Notes |
|---|---|---|---|
| C1 | External sharing restricted to approved domains or organization-level policy | ✅ / ⚠️ / ❌ | |
| C2 | "Anyone with the link" sharing disabled or restricted to internal only | ✅ / ⚠️ / ❌ | |
| C3 | Drive audit logs reviewed for anomalous sharing | ✅ / ⚠️ / ❌ | |
| C4 | Shared drives (formerly Team Drives) ownership reviewed | ✅ / ⚠️ / ❌ | |
| C5 | DLP rules configured for sensitive data types (SSNs, credit card numbers) | ✅ / ⚠️ / ❌ | |

**Section C score:** _____ / 5 = _____%

---

## Section D — Third-party app access (OAuth)

One of the highest-risk areas in Google Workspace: employees granting OAuth access to third-party apps.

| # | Control | Status | Notes |
|---|---|---|---|
| D1 | Third-party app access policy restricts which apps users can install | ✅ / ⚠️ / ❌ | |
| D2 | OAuth app consent audit completed in last 90 days | ✅ / ⚠️ / ❌ | |
| D3 | High-risk OAuth grants (apps with access to email/Drive/contacts) reviewed | ✅ / ⚠️ / ❌ | |
| D4 | AI-embedded apps accessing Workspace data are reviewed under Module 5 | ✅ / ⚠️ / ❌ | |

**Section D score:** _____ / 4 = _____%

---

## Section E — Gemini for Workspace governance

*Complete only if Gemini is licensed or under evaluation.*

| # | Control | Status | Notes |
|---|---|---|---|
| E1 | Gemini data handling and training terms reviewed by legal/security | ✅ / ⚠️ / ❌ | |
| E2 | Gemini access restricted to appropriate user groups | ✅ / ⚠️ / ❌ | |
| E3 | AI acceptable use policy addresses Gemini features specifically | ✅ / ⚠️ / ❌ | |
| E4 | Gemini interaction logging enabled and retained | ✅ / ⚠️ / ❌ | |

**Section E score:** _____ / 4 = _____%

---

## Section F — Licensing

| # | Control | Status | Notes |
|---|---|---|---|
| F1 | License utilisation reviewed in last 30 days | ✅ / ⚠️ / ❌ | |
| F2 | Inactive users suspended or removed | ✅ / ⚠️ / ❌ | |
| F3 | License tier right-sized per role (Frontline Starter vs Business vs Enterprise) | ✅ / ⚠️ / ❌ | |

**Section F score:** _____ / 3 = _____%

---

## Google Workspace governance scorecard

| Section | Controls | Score |
|---|---|---|
| A — Admin and identity | 6 | ____% |
| B — Gmail security | 6 | ____% |
| C — Drive and sharing | 5 | ____% |
| D — Third-party app access | 4 | ____% |
| E — Gemini governance | 4 | ____% |
| F — Licensing | 3 | ____% |
| **Overall** | **28** | ____% |

**Next review date:** _______________________________________________

---

*Infrastructure Placement Framework · Module 7 Google Workspace Governance Baseline · 4th and Bailey · v1.0.0*
