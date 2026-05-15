# Module 4 — Data Protection Assessment

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

**Assessment date:** _______________________________________________

**Assessed by:** _______________________________________________

---

## Section 1 — Data classification baseline

Before assessing protection controls, establish what data exists and how sensitive it is.

| Data category | Location(s) | Classification | Regulatory obligation | Owner |
|---|---|---|---|---|
| | | Public / Internal / Confidential / Restricted | | |
| | | Public / Internal / Confidential / Restricted | | |
| | | Public / Internal / Confidential / Restricted | | |

---

## Section 2 — Backup coverage (3-2-1 rule)

The 3-2-1 backup rule: **three** copies of data, on **two** different media types, with **one** copy stored offsite.

| System / data store | Backup frequency | Backup location 1 | Backup location 2 | Offsite copy? | Meets 3-2-1? |
|---|---|---|---|---|---|
| | | | | Yes / No | ✅ / ❌ |
| | | | | Yes / No | ✅ / ❌ |
| | | | | Yes / No | ✅ / ❌ |

### 2.1 IaaS backup controls

| Control | Status | Notes |
|---|---|---|
| VM-level snapshots scheduled for all production VMs | ✅ / ⚠️ / ❌ | |
| Database backups scheduled and tested | ✅ / ⚠️ / ❌ | |
| Backup retention period meets regulatory requirements | ✅ / ⚠️ / ❌ | |
| Backups stored in a separate account/subscription (not same account as production) | ✅ / ⚠️ / ❌ | |
| Immutable/vault-locked backups in place for critical data | ✅ / ⚠️ / ❌ | |

### 2.2 SaaS backup controls

*Note: SaaS vendors back up their platforms, not your data. Microsoft 365 and Google Workspace data is your responsibility.*

| SaaS platform | Third-party backup tool in use | Last restore test | Meets RPO? |
|---|---|---|---|
| Microsoft 365 (Exchange, SharePoint, Teams, OneDrive) | | | Yes / No |
| Google Workspace | | | Yes / No |
| Salesforce / CRM | | | Yes / No |
| Other SaaS (list) | | | Yes / No |

### 2.3 Backup validation

| Control | Status | Last tested | Notes |
|---|---|---|---|
| Backup restore tested in last 30 days for Tier 0 systems | ✅ / ⚠️ / ❌ | | |
| Backup restore tested in last 90 days for Tier 1 systems | ✅ / ⚠️ / ❌ | | |
| Backup integrity verified (backup jobs completing; not just "green" in console) | ✅ / ⚠️ / ❌ | | |
| Ransomware-resilient backups: immutable or air-gapped copies in place | ✅ / ⚠️ / ❌ | | |

---

## Section 3 — Encryption controls

| Data state | Control | Status | Notes |
|---|---|---|---|
| At rest | Encryption enabled for all cloud storage | ✅ / ⚠️ / ❌ | |
| At rest | Encryption enabled for on-premises data stores | ✅ / ⚠️ / ❌ | |
| At rest | Encryption keys managed by organisation (not vendor-managed only) | ✅ / ⚠️ / ❌ | |
| At rest | Laptop/endpoint full-disk encryption enforced | ✅ / ⚠️ / ❌ | |
| In transit | TLS enforced for all data in transit | ✅ / ⚠️ / ❌ | |
| In transit | No unencrypted protocols in use (HTTP, FTP, Telnet) for sensitive data | ✅ / ⚠️ / ❌ | |
| Key management | Encryption key rotation schedule exists | ✅ / ⚠️ / ❌ | |
| Key management | Key access is audited | ✅ / ⚠️ / ❌ | |

---

## Section 4 — RTO and RPO targets

Recovery Time Objective (RTO): maximum acceptable downtime before consequences are unacceptable.
Recovery Point Objective (RPO): maximum acceptable data loss measured in time.

| Workload | Tier | Business-defined RTO | Business-defined RPO | Current capability meets RTO? | Current capability meets RPO? |
|---|---|---|---|---|---|
| | Tier 0 | < 1 hour | < 15 min | Yes / No | Yes / No |
| | Tier 1 | 1–4 hours | < 1 hour | Yes / No | Yes / No |
| | Tier 2 | 4–24 hours | 4 hours | Yes / No | Yes / No |
| | Tier 3 | 24–72 hours | 24 hours | Yes / No | Yes / No |

*RTO and RPO are business decisions, not IT estimates. The targets above should be validated by business leadership.*

---

## Section 5 — Data protection gap summary

| Gap identified | Severity | Recommended action | Owner | Target date |
|---|---|---|---|---|
| | Critical / High / Medium / Low | | | |

---

*Infrastructure Placement Framework · Module 4 Data Protection Assessment · 4th and Bailey · v1.0.0*
