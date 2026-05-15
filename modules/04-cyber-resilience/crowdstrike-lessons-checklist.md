# Module 4 — CrowdStrike Lessons Checklist

**Vendor Update Governance Controls**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Background

On July 19, 2024, a faulty content update from CrowdStrike Falcon caused 8.5 million Windows systems globally to enter a boot loop. The root cause was not a cyberattack. It was a trusted, widely deployed security vendor pushing an update that had not been sufficiently tested against production configurations.

The organisations that recovered in hours had specific controls in place. The organisations that took days did not.

This checklist documents the controls that the CrowdStrike incident demonstrated were essential. It is scored as a binary pass/fail. A score below 80% requires an immediate remediation programme.

**Assessment date:** _______________________________________________

**Assessed by:** _______________________________________________

---

## Section A — Staged update rollout policy

The single most impactful control: do not allow any vendor to simultaneously update all systems.

| # | Control | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|---|
| A1 | A written staged rollout policy exists for security tool updates | | | |
| A2 | Policy covers all security vendors, not just EDR/AV | | | |
| A3 | Staged rings are defined: pilot (5%) → early adopter (20%) → broad (75%) | | | |
| A4 | Minimum soak time between stages is defined (minimum: 24 hours for security tools) | | | |
| A5 | Pilot ring includes non-critical systems only (not domain controllers, not payment systems) | | | |
| A6 | Rollout pause trigger is defined: if X% of systems in a ring fail, rollout auto-pauses | | | |
| A7 | Policy is enforced technically (not just documented) | | | |

**Section A score:** _____ / 7 = _____%

---

## Section B — Vendor update testing environment

| # | Control | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|---|
| B1 | A non-production test environment exists that mirrors production configuration | | | |
| B2 | Security tool updates are deployed to the test environment before production | | | |
| B3 | Test environment includes the same OS versions and configurations as production | | | |
| B4 | Minimum test period before production promotion is documented (recommended: 24 hours) | | | |
| B5 | Test environment coverage includes all critical workload types (servers, endpoints, DCs) | | | |

**Section B score:** _____ / 5 = _____%

---

## Section C — Vendor dependency and concentration

| # | Control | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|---|
| C1 | A vendor concentration risk threshold is defined (e.g., no single vendor on > 80% of systems) | | | |
| C2 | Third-party risk register exists and includes all security vendors | | | |
| C3 | Security vendor contracts include SLA for incident response time | | | |
| C4 | Security vendor's update and testing process has been reviewed as part of vendor evaluation | | | |
| C5 | Alternative or manual controls are documented for critical functions if primary security tool fails | | | |

**Section C score:** _____ / 5 = _____%

---

## Section D — Manual operational fallbacks

The organisations that kept operating during the CrowdStrike outage had manual fallbacks. Those that didn't had no way to function when their systems were offline.

| # | Control | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|---|
| D1 | Manual fallback procedures are documented for each critical business function | | | |
| D2 | Fallback procedures are printed and accessible without a working computer | | | |
| D3 | Staff have been trained on manual fallbacks (at least one exercise in last 12 months) | | | |
| D4 | Fallback procedures cover: accepting payments, processing orders, communicating with customers | | | |
| D5 | Key contact information (vendors, staff, customers) is available offline | | | |
| D6 | Manual fallbacks have been tested within the last 12 months | | | |

**Section D score:** _____ / 6 = _____%

---

## Section E — Recovery capability

| # | Control | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|---|
| E1 | Recovery procedure is documented for a mass system failure event (not just single-system failure) | | | |
| E2 | Recovery procedure includes step-by-step instructions to restore from a boot loop | | | |
| E3 | BitLocker recovery keys are stored outside the affected systems (not only in the OS itself) | | | |
| E4 | Recovery procedures are accessible when the affected systems are offline | | | |
| E5 | Recovery procedures have been tested (tabletop exercise minimum; ideally a live drill) | | | |
| E6 | Recovery procedures identify the sequence for restoring systems: Tier 0 first | | | |

**Section E score:** _____ / 6 = _____%

---

## Section F — Communication and escalation

| # | Control | Pass ✅ | Fail ❌ | Notes |
|---|---|---|---|---|
| F1 | Incident escalation path is documented: who is notified first, second, third | | | |
| F2 | Executive and leadership contact information is available offline | | | |
| F3 | Customer communication template exists for major outage notification | | | |
| F4 | Communication channel functions when primary systems (email, Teams, Slack) are offline | | | |
| F5 | Cyber insurance policy number and claim process is documented and accessible offline | | | |

**Section F score:** _____ / 5 = _____%

---

## Overall checklist scorecard

| Section | Controls | Passing | Score |
|---|---|---|---|
| A — Staged rollout policy | 7 | | ____% |
| B — Test environment | 5 | | ____% |
| C — Vendor concentration | 5 | | ____% |
| D — Manual fallbacks | 6 | | ____% |
| E — Recovery capability | 6 | | ____% |
| F — Communication | 5 | | ____% |
| **Overall** | **34** | | ____% |

---

## Score interpretation

| Score | Assessment | Action |
|---|---|---|
| 90–100% | Strong vendor update governance | Annual review; maintain |
| 80–89% | Good baseline; gaps are specific | Address failing items within 60 days |
| 60–79% | Significant gaps present | Remediation programme required within 30 days |
| Below 60% | Critical gaps | Immediate remediation; do not wait for next review cycle |

**Current score: ____% — Status:** _______________________________________________

---

## Remediation register

| Control | Gap description | Owner | Target date | Status |
|---|---|---|---|---|
| | | | | |
| | | | | |

---

*Infrastructure Placement Framework · Module 4 CrowdStrike Lessons Checklist · 4th and Bailey · v1.0.0*
*github.com/4thandBailey/infrastructure-placement-framework*
