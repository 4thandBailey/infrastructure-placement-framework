# Module 8 — Business Impact Analysis

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

*This document must be completed before the BCP or DRP can be written. RTO and RPO are business decisions — not IT estimates.*

---

**Organisation:** _______________________________________________

**BIA completed by:** _______________________________________________

**Business sponsor (leadership signoff required):** _______________________________________________

**Date:** _______________________________________________

**Review date:** _______________________________________________ (annually minimum)

---

## Part 1 — Critical business function inventory

List every function the organisation must be able to perform to remain operational. Include people, not just systems.

| Function | Business unit | Function owner | Tier | Maximum tolerable downtime | Impact if unavailable |
|---|---|---|---|---|---|
| | | | 0 / 1 / 2 / 3 | | Financial / Operational / Regulatory / Reputational |
| | | | | | |
| | | | | | |

---

## Part 2 — RTO and RPO by workload

For each critical system, leadership must define the RTO and RPO. These are business decisions that must be signed off by the appropriate business owner — not estimated by IT.

| System / workload | Tier | Depends on (other systems) | Business-defined RTO | Business-defined RPO | Current recovery capability | Gap? |
|---|---|---|---|---|---|---|
| Domain Controllers | 0 | Network, DNS | | | | Yes / No |
| DNS infrastructure | 0 | Network | | | | Yes / No |
| Identity / Entra ID / Google IdP | 0 | | | | | Yes / No |
| Email (Exchange / Gmail) | 1 | Identity | | | | Yes / No |
| ERP / financial system | 1 | Identity, DB | | | | Yes / No |
| Line-of-business application | 1 | Identity, DB | | | | Yes / No |
| CRM | 2 | Identity | | | | Yes / No |
| Collaboration (Teams / Workspace) | 2 | Identity | | | | Yes / No |
| File storage (SharePoint / Drive) | 2 | Identity | | | | Yes / No |
| HR system | 2 | Identity | | | | Yes / No |
| Archives | 3 | Storage | | | | Yes / No |
| Development environments | 3 | | | | | Yes / No |

*Add rows for all systems in scope.*

**RTO/RPO approval:** Signed by _____________________________ Title _____________________________ Date _____________

---

## Part 3 — Dependency map

Map the dependencies between systems to identify the correct restoration sequence:

**Tier 0 must be restored before Tier 1 can be restored. Tier 1 must be restored before Tier 2 can function.**

| System | Depends on | Cannot restore until these are up |
|---|---|---|
| Email | Identity (Entra/Google), DNS | Domain Controllers, DNS, Identity |
| ERP | Database, Identity | Tier 0 systems |
| CRM | ERP (in some configurations), Identity | Tier 0 + ERP |

*Complete this map for your environment — the dependency chain must be understood before the DRP is written.*

---

## Part 4 — Financial impact quantification

For leadership sign-off, quantify the financial impact of downtime at each tier:

| Tier | System examples | Estimated cost per hour of downtime | Estimated cost per day | Regulatory penalty risk |
|---|---|---|---|---|
| Tier 0 | Payments, domain, identity | $ | $ | Yes / No |
| Tier 1 | Email, ERP, financial | $ | $ | Yes / No |
| Tier 2 | CRM, HR, collaboration | $ | $ | Yes / No |
| Tier 3 | Archives, dev | $ | $ | Yes / No |

---

## Part 5 — Regulatory notification obligations

For each data type processed, document the notification timeline if that data is compromised:

| Data type | Regulation | Notification deadline | Who must be notified | Template exists? |
|---|---|---|---|---|
| PHI (health data) | HIPAA | 60 days of discovery | HHS + affected individuals | Yes / No |
| Texas resident PII | Texas HB 3834 | 60 days | Affected individuals + AG (if > 500 Texans) | Yes / No |
| Cardholder data | PCI-DSS | Immediately | Card brands (Visa, Mastercard, etc.) | Yes / No |
| Financial customer data | GLBA Safeguards Rule | 30 days | FTC (or regulator) | Yes / No |
| Student data | FERPA | Without unreasonable delay | ED / parents | Yes / No |
| Other: | | | | |

*Note: Notification templates must be drafted by legal counsel before an incident occurs, not during.*

---

## Part 6 — BIA summary and sign-off

**Systems with unacceptable recovery gaps (current capability does not meet business-defined RTO/RPO):**

| System | Business-defined RTO | Current capability | Gap | Priority action |
|---|---|---|---|---|
| | | | | |

**Leadership approval:**

This Business Impact Analysis has been reviewed and the RTO/RPO targets represent business decisions made with full awareness of the cost and operational implications.

| Name | Title | Signature | Date |
|---|---|---|---|
| | | | |
| | | | |

---

*Infrastructure Placement Framework · Module 8 Business Impact Analysis · 4th and Bailey · v1.0.0*
*This document should be treated as confidential — it describes recovery priorities and dependencies that could be exploited if disclosed.*
