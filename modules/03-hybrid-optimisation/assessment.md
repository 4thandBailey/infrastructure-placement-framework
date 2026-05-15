# Module 3 — Hybrid Estate Optimization Assessment

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

**Assessment date:** _______________________________________________

**Assessed by:** _______________________________________________

**Organization:** _______________________________________________

---

## Section 1 — Workload placement audit

Compare each workload's current placement against its Module 1 score. Flag any workload where the current placement does not match the scored recommendation.

| Workload | Current placement | Module 1 score | Recommended placement | Match? | Action |
|---|---|---|---|---|---|
| | | | | ✅ / ⚠️ | |
| | | | | ✅ / ⚠️ | |
| | | | | ✅ / ⚠️ | |

**Workloads flagged for placement review:** _____ of _____ total

---

## Section 2 — Cloud cost anomaly detection

### 2.1 Idle and underutilized resources

Review each cloud account for the following categories of waste:

| Category | Tool used to identify | Estimated annual waste ($) | Action |
|---|---|---|---|
| Idle virtual machines (< 5% CPU utilisation) | | | |
| Oversized instances (consistent < 40% utilisation) | | | |
| Orphaned storage volumes (not attached to any instance) | | | |
| Unused load balancers or IP addresses | | | |
| Unused or stale database instances | | | |
| Egress costs from unnecessary data movement | | | |
| Unattended development/test environments running 24/7 | | | |
| **Total estimated annual waste** | | | |

### 2.2 License utilisation

| SaaS product | Licenses purchased | Licenses actively used | Utilisation % | Action |
|---|---|---|---|---|
| Microsoft 365 | | | | |
| Google Workspace | | | | |
| Other SaaS (list) | | | | |

**Licenses flagged for reclamation:** _____

**Estimated annual savings from license optimization:** $ _______________

### 2.3 Reserved instance and savings plan utilisation

| Provider | Reserved capacity purchased | Utilisation % | Action |
|---|---|---|---|
| AWS Reserved Instances | | | |
| Azure Reserved VMs | | | |
| GCP Committed Use | | | |

---

## Section 3 — FinOps governance assessment

### 3.1 Tagging and cost allocation

| Control | Status | Gap / action |
|---|---|---|
| Resource tagging policy defined and documented | ✅ / ⚠️ / ❌ | |
| Tags applied to 90%+ of cloud resources | ✅ / ⚠️ / ❌ | |
| Cost allocated to business units or cost centres | ✅ / ⚠️ / ❌ | |
| Cloud spend is visible to business owners (not just IT) | ✅ / ⚠️ / ❌ | |
| Monthly cloud cost review meeting in place | ✅ / ⚠️ / ❌ | |
| Anomaly alerts configured for spend spikes | ✅ / ⚠️ / ❌ | |
| Budget alerts configured per account/project | ✅ / ⚠️ / ❌ | |

### 3.2 FinOps maturity level

| Level | Description | Current? |
|---|---|---|
| Crawl | Some visibility, ad hoc cost reviews, no structured ownership | |
| Walk | Regular cost reviews, tagging in place, basic cost allocation | |
| Run | Continuous optimization, chargeback/showback, FinOps ownership defined | |

**Current FinOps maturity:** _______________________________________________

**Target FinOps maturity:** _______________________________________________

---

## Section 4 — Governance gap assessment

### 4.1 Access and identity governance

| Control | Status | Gap / action |
|---|---|---|
| Cloud IAM policy documented and enforced | ✅ / ⚠️ / ❌ | |
| Privileged access review completed in last 90 days | ✅ / ⚠️ / ❌ | |
| Service accounts and API keys inventoried and rotated | ✅ / ⚠️ / ❌ | |
| Guest and external access reviewed in last 90 days | ✅ / ⚠️ / ❌ | |
| MFA enforced for all cloud console access | ✅ / ⚠️ / ❌ | |

### 4.2 Change management

| Control | Status | Gap / action |
|---|---|---|
| Change management process covers cloud infrastructure | ✅ / ⚠️ / ❌ | |
| Infrastructure changes are reviewed before deployment | ✅ / ⚠️ / ❌ | |
| Emergency change process documented | ✅ / ⚠️ / ❌ | |

### 4.3 Documentation and architecture

| Control | Status | Gap / action |
|---|---|---|
| Network architecture diagram current (< 6 months old) | ✅ / ⚠️ / ❌ | |
| Workload inventory current and maintained | ✅ / ⚠️ / ❌ | |
| Data flow diagrams available for sensitive data | ✅ / ⚠️ / ❌ | |

---

## Section 5 — Cost reduction opportunity register

Summarise all identified savings opportunities from this assessment:

| Category | Description | Estimated annual saving ($) | Effort to implement | Priority |
|---|---|---|---|---|
| Idle/orphaned resource cleanup | | | Low / Med / High | High / Med / Low |
| Rightsizing opportunities | | | Low / Med / High | High / Med / Low |
| License reclamation | | | Low / Med / High | High / Med / Low |
| Reserved instance optimization | | | Low / Med / High | High / Med / Low |
| FinOps program establishment | | | Low / Med / High | High / Med / Low |
| **Total estimated annual savings** | | | | |

---

## Section 6 — Governance improvement roadmap

| Control gap identified | Priority | Recommended action | Owner | Target date |
|---|---|---|---|---|
| | High | | | |
| | Medium | | | |
| | Low | | | |

---

## Quarterly review cadence

Hybrid estate optimization is not a one-time exercise. The following reviews should be scheduled:

| Review | Frequency | Scope |
|---|---|---|
| Cloud cost anomaly review | Monthly | Spend anomalies, idle resources, new waste identified |
| Workload placement review | Quarterly | New workloads assessed; existing workloads reviewed against criteria |
| FinOps governance review | Quarterly | Tagging compliance, cost allocation accuracy, budget vs. actuals |
| Access and IAM review | Quarterly | Privileged access, service accounts, external access |
| Full estate optimization assessment | Annually | Complete re-run of this assessment |

**Next quarterly review scheduled:** _______________________________________________

---

*Infrastructure Placement Framework · Module 3 Assessment · 4th and Bailey · v1.0.0*
