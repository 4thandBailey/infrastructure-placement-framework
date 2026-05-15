# Module 8 — Business Continuity and Disaster Recovery (BCDR)

**Pillar:** Survive and recover · **Framework:** Infrastructure Placement Framework v1.0.0

---

## The question

When something goes wrong — a ransomware attack, a data breach, a vendor failure, a natural disaster, an accidental deletion — exactly how does your organisation recover, in what order, by whom, and how fast?

---

## Why this module exists

This is the most overlooked module in enterprise IT planning. Plans exist on paper in most organisations. Tested, current, role-specific plans that the team has actually rehearsed are rare.

- **76%** of organisations needed more than 100 days to fully recover from a cyberattack (IBM Cost of a Data Breach Report, 2025)
- **40%** of small businesses never reopen after a disaster (FEMA)
- **25%** fail within one year (FEMA)
- **44%** of data breaches involved ransomware (Verizon DBIR 2025)

The gap between having a plan on paper and having a plan that works is measured in days of downtime and the survival of the business.

---

## The critical distinction

A **Business Continuity Plan (BCP)** and a **Disaster Recovery Plan (DRP)** are not the same document.

- **BCP** — Strategic. Keeps the entire organisation operating across all functions during and after any disruption: people, processes, communications, alternate work locations, manual workarounds.
- **DRP** — Tactical. Restores IT systems, data, and infrastructure after a technical failure. A component of the BCP, not a replacement.

Most organisations have a version of a DRP. Almost none have a genuine BCP.

---

## RTO and RPO tiers

| Tier | Examples | Target RTO | Target RPO |
|---|---|---|---|
| Tier 0 — Critical | Domain Controllers, DNS, EHR, payment systems | < 1 hour | < 15 minutes |
| Tier 1 — Mission-critical | Email, ERP, financial systems | 1 – 4 hours | < 1 hour |
| Tier 2 — Business-important | CRM, collaboration, HR | 4 – 24 hours | 4 hours |
| Tier 3 — Non-critical | Archives, dev environments | 24 – 72 hours | 24 hours |

---

## The six scenarios

Every plan must explicitly address:
1. Ransomware attack
2. Data breach and exfiltration
3. Third-party vendor failure (CrowdStrike-informed)
4. Natural disaster / physical infrastructure loss
5. Insider threat and accidental data loss
6. Supply chain compromise (SolarWinds-informed)

---

## Files in this module

| File | Purpose |
|---|---|
| `README.md` | This file |
| `business-impact-analysis.md` | BIA template: RTO/RPO per workload, critical function inventory |
| `bcp-template.md` | Business Continuity Plan template |
| `drp-template.md` | Disaster Recovery Plan template |
| `ransomware-playbook.md` | Step-by-step ransomware response playbook |
| `breach-notification-guide.md` | Data breach notification guide with regulatory timelines |
| `vendor-failure-playbook.md` | Vendor failure response playbook |
| `backup-validation-checklist.md` | Backup integrity and restoration validation checklist |
| `tabletop-exercise-guide.md` | Tabletop exercise scripts for all six scenarios |
| `bcdr-assessment.md` | BCDR readiness scored assessment |

---

## Testing requirement

| Test type | Frequency | What it tests |
|---|---|---|
| Tabletop exercise | Quarterly | Walk-through of scenario — no systems touched |
| Component test | Semi-annually | Actual backup restore, specific system failover |
| Full simulation | Annually | Complete Tier 0/Tier 1 failover under realistic conditions |

**The plan that has never been tested is not a plan.**

---

*Infrastructure Placement Framework · Module 8 · 4th and Bailey · github.com/4thandBailey/infrastructure-placement-framework*
