# Module 2 — Vendor Risk Scorecard

**Hyperscaler Dependency and Vendor Concentration Risk**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Purpose

This scorecard identifies and scores the concentration risk created by hyperscaler dependencies across the organization's workload portfolio. High concentration in a single provider creates financial, operational, and strategic risk — particularly when repatriation is being considered.

This scorecard should be completed in conjunction with the repatriation readiness assessment and updated whenever the workload portfolio changes significantly.

---

## Section 1 — Hyperscaler concentration summary

| Provider | Number of workloads | % of total compute spend | Business-critical workloads | Assessment |
|---|---|---|---|---|
| AWS | | | | |
| Microsoft Azure | | | | |
| Google Cloud Platform | | | | |
| Other hyperscaler | | | | |
| On-premises / private | | | | |
| **Total** | | 100% | | |

**Single-provider concentration risk:**
- Above 70% spend in one provider = **High concentration risk**
- 40–70% in one provider = **Moderate concentration risk**
- Below 40% in any single provider = **Acceptable concentration**

**Assessment:** _______________________________________________

---

## Section 2 — Per-workload dependency scoring

Complete for each workload being evaluated for repatriation.

**Workload:** _______________________________________________

### 2.1 Service dependency depth

Rate the depth of dependency on cloud-native services:

| Cloud service category | Service in use | Portability rating |
|---|---|---|
| Compute (VMs, containers) | | High / Medium / Low portability |
| Managed databases | | High / Medium / Low portability |
| Serverless / functions | | High / Medium / Low portability |
| AI and ML services | | High / Medium / Low portability |
| Identity and access management | | High / Medium / Low portability |
| Networking (VPC, DNS, CDN) | | High / Medium / Low portability |
| Storage (object, block, file) | | High / Medium / Low portability |
| Messaging and event streaming | | High / Medium / Low portability |
| Monitoring and logging | | High / Medium / Low portability |

### 2.2 Migration complexity score

| Factor | Score (1=easy, 5=complex) | Notes |
|---|---|---|
| Data volume and format portability | | |
| Number of proprietary service dependencies | | |
| Integration complexity (internal and external) | | |
| Team familiarity with target platform | | |
| Estimated migration engineering effort (months) | | |
| **Average score** | | |

**Migration complexity rating:**
- Average 1.0–2.0 = Low complexity — straightforward migration
- Average 2.1–3.5 = Moderate complexity — planning and engineering required
- Average 3.6–5.0 = High complexity — multi-phase program required

---

## Section 3 — Vendor concentration risk register

| Risk | Likelihood | Impact | Risk score | Mitigation |
|---|---|---|---|---|
| Single hyperscaler outage affecting all workloads | Low / Med / High | Low / Med / High | | Workload distribution across providers |
| Hyperscaler pricing increase affecting total estate | Low / Med / High | Low / Med / High | | TCO modelling, repatriation option |
| Proprietary API deprecation forcing re-architecture | Low / Med / High | Low / Med / High | | Open standards preference in new builds |
| Data portability blocked by format lock-in | Low / Med / High | Low / Med / High | | Data format audit, export validation |
| Hyperscaler vendor insolvency or service termination | Low / Med / High | Low / Med / High | | Exit runbooks, data export procedures |
| Contract renewal leverage shift | Low / Med / High | Low / Med / High | | Multi-provider strategy, exit capability |

---

## Section 4 — Recommended actions

Based on the concentration and dependency assessment:

| Finding | Priority | Recommended action | Owner | Target date |
|---|---|---|---|---|
| | High / Med / Low | | | |
| | High / Med / Low | | | |
| | High / Med / Low | | | |

---

## Review cadence

This scorecard should be reviewed:
- **Annually** as part of the Module 3 hybrid estate optimization review
- **Triggered** when a new major workload is deployed to a hyperscaler
- **Triggered** when a hyperscaler announces significant pricing, API, or product changes

**Next review date:** _______________________________________________

---

*Infrastructure Placement Framework · Module 2 Vendor Risk Scorecard · 4th and Bailey · v1.0.0*
*github.com/4thandBailey/infrastructure-placement-framework*
