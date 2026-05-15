# Module 8 — Backup Validation Checklist

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Why backup validation matters

A backup job showing "completed successfully" in a console is not evidence that the backup is restorable. The most common discovery organisations make during an actual incident is that backup jobs were completing but producing unrestorable files. By the time this is discovered, it is too late.

This checklist mandates actual restoration tests — not completion log reviews.

**Core principle: A backup that has never been restored is not a backup. It is an assumption.**

---

## Validation schedule

| Tier | System | Backup restore test frequency | Last tested | Next due | Tested by |
|---|---|---|---|---|---|
| Tier 0 | Domain Controllers | Monthly | | | |
| Tier 0 | DNS / DHCP | Monthly | | | |
| Tier 0 | Identity / IdP | Monthly | | | |
| Tier 0 | Payment infrastructure | Monthly | | | |
| Tier 1 | Email platform | Quarterly | | | |
| Tier 1 | ERP / financial system | Quarterly | | | |
| Tier 1 | Core LoB applications | Quarterly | | | |
| Tier 2 | CRM | Semi-annually | | | |
| Tier 2 | Collaboration / SharePoint | Semi-annually | | | |
| Tier 2 | HR system | Semi-annually | | | |
| Tier 3 | Archives | Annually | | | |
| Tier 3 | Dev environments | Annually | | | |

---

## Per-system validation checklist

Complete this checklist for each system tested. File completed checklists for audit purposes.

---

**System:** _______________________________________________

**Backup date/time being tested:** _______________________________________________

**Test date:** _______________________________________________

**Tested by:** _______________________________________________

**Test environment:** Production / Isolated test environment *(circle one — Tier 0/1 tests should use isolated environment)*

### Section A — Backup integrity verification

| Check | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|
| Backup job completed without errors on scheduled date | | | |
| Backup file size is consistent with prior backups (within 10% variance) | | | |
| Backup file is not corrupted (hash verification or tool integrity check) | | | |
| Backup encryption is applied (if required) | | | |
| Backup is stored in the expected location (primary + offsite if required) | | | |
| Backup age is within the required RPO window | | | |

### Section B — Restoration test

| Check | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|
| Restore initiated from backup (not from live system) | | | |
| Restore completed without errors | | | |
| Restored system/data boots or opens successfully | | | |
| Data contents are as expected — spot check 5–10 records or files | | | |
| Application functions correctly post-restore (not just OS-level) | | | |
| Restore completed within the defined RTO window | | | Time taken: _______ |
| Data loss (gap between backup and test) is within RPO window | | | Data loss: _______ |

### Section C — Ransomware resilience check

*(Complete for all Tier 0 and Tier 1 systems)*

| Check | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|
| Immutable backup exists (vault lock or equivalent — cannot be encrypted or deleted by ransomware) | | | |
| Immutable backup is stored in a separate account/subscription (not accessible via same credentials as production) | | | |
| Backup of this system predates any potential dormant ransomware infection (test backup age ≥ 30 days old, not just last night's backup) | | | |

### Section D — SaaS platform backup check

*(For M365, Google Workspace, Salesforce, and other SaaS where backup is customer responsibility)*

| Check | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|
| Third-party backup tool is actively backing up this SaaS platform | | | |
| Backup covers all required data types (email, calendar, contacts, files, chat) | | | |
| Restore of individual item tested (e.g., single email or single file) | | | |
| Restore of mailbox/site-level tested (full mailbox or SharePoint site) | | | |

---

### Test result summary

| Category | Checks | Passed | Failed |
|---|---|---|---|
| A — Backup integrity | 6 | | |
| B — Restoration test | 6 | | |
| C — Ransomware resilience | 3 | | |
| D — SaaS (if applicable) | 4 | | |

**Overall result:** PASS / FAIL

**Failures requiring remediation:**

| Failure | Remediation action | Owner | Target date |
|---|---|---|---|
| | | | |

**Tester sign-off:** _____________________________ Date: _____________________________

---

## Quarterly backup environment summary

Use this summary to track the overall backup posture across all systems each quarter:

| Quarter | Systems tested | Pass rate | Critical failures | Action taken |
|---|---|---|---|---|
| Q1 | | | | |
| Q2 | | | | |
| Q3 | | | | |
| Q4 | | | | |

---

*Infrastructure Placement Framework · Module 8 Backup Validation Checklist · 4th and Bailey · v1.0.0*
*github.com/4thandBailey/infrastructure-placement-framework*
