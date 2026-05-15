# Module 3 — Hybrid Estate Governance Checklist

**Ongoing governance controls for hybrid infrastructure**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## How to use this checklist

This checklist supports the quarterly governance review cadence established in Module 3. Run through the applicable sections each quarter. Items marked ❌ require a documented remediation action with an assigned owner and target date.

**Review date:** _______________________________________________

**Reviewed by:** _______________________________________________

---

## Section A — Cost governance

| # | Control | Status | Notes |
|---|---|---|---|
| A1 | All cloud resources tagged according to the tagging policy | ✅ / ⚠️ / ❌ | |
| A2 | Cloud spend allocated to business units and cost centres | ✅ / ⚠️ / ❌ | |
| A3 | Budget alerts are configured and active for all cloud accounts | ✅ / ⚠️ / ❌ | |
| A4 | Anomaly alerts reviewed and actioned since last review | ✅ / ⚠️ / ❌ | |
| A5 | No idle or orphaned resources identified (or remediation in progress) | ✅ / ⚠️ / ❌ | |
| A6 | Reserved instances/savings plans utilisation above 85% | ✅ / ⚠️ / ❌ | |
| A7 | SaaS licence utilisation reviewed; unused licences flagged for reclamation | ✅ / ⚠️ / ❌ | |
| A8 | Monthly cloud cost report distributed to business owners | ✅ / ⚠️ / ❌ | |

**Section A score:** _____ / 8 = _____%

---

## Section B — Access and identity governance

| # | Control | Status | Notes |
|---|---|---|---|
| B1 | Cloud IAM roles reviewed; no over-privileged accounts identified | ✅ / ⚠️ / ❌ | |
| B2 | Privileged/admin accounts inventoried and justified | ✅ / ⚠️ / ❌ | |
| B3 | Service accounts and API keys inventoried; unused keys revoked | ✅ / ⚠️ / ❌ | |
| B4 | MFA enforced for all cloud management console access | ✅ / ⚠️ / ❌ | |
| B5 | Guest and external access reviewed; no unexplained external access | ✅ / ⚠️ / ❌ | |
| B6 | Stale user accounts (departed employees) removed from all cloud platforms | ✅ / ⚠️ / ❌ | |
| B7 | Shared credentials not in use (each user has individual credentials) | ✅ / ⚠️ / ❌ | |
| B8 | Break-glass accounts documented, credentials secured, last-use verified | ✅ / ⚠️ / ❌ | |

**Section B score:** _____ / 8 = _____%

---

## Section C — Workload placement governance

| # | Control | Status | Notes |
|---|---|---|---|
| C1 | Workload inventory is current (new workloads documented since last review) | ✅ / ⚠️ / ❌ | |
| C2 | New workloads deployed since last review were assessed under Module 1 before deployment | ✅ / ⚠️ / ❌ | |
| C3 | Architecture Decision Records exist for all production workloads | ✅ / ⚠️ / ❌ | |
| C4 | Workloads flagged for placement review in previous quarter have been actioned | ✅ / ⚠️ / ❌ | |
| C5 | Data classification is current for sensitive workloads | ✅ / ⚠️ / ❌ | |

**Section C score:** _____ / 5 = _____%

---

## Section D — Change management and documentation

| # | Control | Status | Notes |
|---|---|---|---|
| D1 | Network architecture diagram updated since last major change | ✅ / ⚠️ / ❌ | |
| D2 | Infrastructure changes since last review were processed through change management | ✅ / ⚠️ / ❌ | |
| D3 | No unauthorised infrastructure changes identified in audit logs | ✅ / ⚠️ / ❌ | |
| D4 | Runbooks are current for all critical workloads | ✅ / ⚠️ / ❌ | |
| D5 | Vendor contracts reviewed for renewal dates and pricing changes due | ✅ / ⚠️ / ❌ | |

**Section D score:** _____ / 5 = _____%

---

## Section E — Security baseline

| # | Control | Status | Notes |
|---|---|---|---|
| E1 | Security posture score reviewed in cloud security tools (Defender, Security Hub, etc.) | ✅ / ⚠️ / ❌ | |
| E2 | Open ports and security groups reviewed; no unexplained exposure | ✅ / ⚠️ / ❌ | |
| E3 | Encryption at rest confirmed for all sensitive data stores | ✅ / ⚠️ / ❌ | |
| E4 | Encryption in transit (TLS) confirmed for all data movement | ✅ / ⚠️ / ❌ | |
| E5 | Cloud audit logging (CloudTrail, Activity Log, Cloud Audit) is active and retained | ✅ / ⚠️ / ❌ | |
| E6 | Backup jobs validated — backups are completing and restoration has been tested | ✅ / ⚠️ / ❌ | |

**Section E score:** _____ / 6 = _____%

---

## Quarterly scorecard summary

| Section | Controls | Passing | Score |
|---|---|---|---|
| A — Cost governance | 8 | | ____% |
| B — Access and identity | 8 | | ____% |
| C — Workload placement | 5 | | ____% |
| D — Change management | 5 | | ____% |
| E — Security baseline | 6 | | ____% |
| **Overall** | **32** | | ____% |

---

## Remediation actions from this review

| Control | Issue | Owner | Target date | Status |
|---|---|---|---|---|
| | | | | |
| | | | | |

**Next review date:** _______________________________________________

---

*Infrastructure Placement Framework · Module 3 Governance Checklist · 4th and Bailey · v1.0.0*
