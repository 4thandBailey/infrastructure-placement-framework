# Module 2 — Cloud Repatriation Readiness Assessment

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Instructions

This assessment evaluates organisational readiness to execute cloud repatriation successfully across five dimensions. Complete this assessment before beginning any repatriation sequencing or vendor selection.

**Readiness threshold:** A score below 60% in any dimension is a flagged risk requiring a remediation plan before repatriation begins. Attempting repatriation with unresolved readiness gaps is the leading cause of failed or cost-overrun repatriation projects.

**Assessment date:** _______________________________________________

**Assessed by:** _______________________________________________

**Organisation:** _______________________________________________

**Candidate workloads for repatriation** *(list from Module 1 assessment)*:

| # | Workload | Current cloud provider | Module 1 placement score | Rationale for repatriation |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

---

## Dimension 1 — Financial readiness

### 1.1 TCO analysis completion

Has a 3-year Total Cost of Ownership analysis been completed for each candidate workload?

- [ ] Yes — full TCO model completed for all candidate workloads (see `tco-model.xlsx`)
- [ ] Partially — TCO completed for some workloads; gaps remain
- [ ] No — TCO analysis not yet completed

*Note: Proceeding without a completed TCO model is the single most common source of repatriation regret. Cloud bills feel visible; on-premises costs (hardware refresh, power, cooling, staffing) are frequently underestimated.*

### 1.2 Capital availability

Is capital budget available for on-premises hardware investment?

- [ ] Yes — capex budget identified and approved
- [ ] In progress — budget request submitted; approval pending
- [ ] No — capital budget not yet identified

### 1.3 Ongoing operational cost model

Has the ongoing operational cost model (staffing, maintenance, power, facilities) been included in the TCO?

- [ ] Yes — full operational cost model included
- [ ] Partially — some operational costs included
- [ ] No — operational costs not included

### 1.4 Cloud exit costs

Have cloud exit costs been estimated? (Egress fees, contract termination penalties, data transfer costs)

- [ ] Yes — exit costs quantified per workload
- [ ] Partially — estimated but not fully quantified
- [ ] No — exit costs not assessed

**Financial readiness score:** _____ / 4 items complete = _____%

**Flag if below 60%:** [ ] Flagged for remediation

**Notes / gaps:** _______________________________________________

---

## Dimension 2 — Technical readiness

### 2.1 Infrastructure platform decision

Has a decision been made on the target on-premises infrastructure platform?

- [ ] Yes — platform selected and procurement underway or complete
- [ ] In evaluation — shortlist identified, evaluation in progress
- [ ] No — platform not yet evaluated

*If VMware exposure is the driver, alternatives to evaluate include: Nutanix, Proxmox, OpenStack, VMware (post-Broadcom with new licensing), bare-metal, or hyperconverged from other vendors.*

### 2.2 Data centre or colocation capacity

Is physical hosting capacity available for repatriated workloads?

- [ ] Yes — existing data centre or colocation space is available and sufficient
- [ ] Partially — some capacity available; expansion required
- [ ] No — hosting capacity not identified; colocation evaluation required

### 2.3 Network connectivity

Is network connectivity (bandwidth, redundancy, latency) sufficient to support repatriated workloads and users?

- [ ] Yes — current connectivity is adequate for repatriated workloads
- [ ] Upgrade required — connectivity upgrade identified and in progress
- [ ] Not assessed — connectivity requirements not yet evaluated

### 2.4 Monitoring and observability

Will the organisation have equivalent monitoring and observability for on-premises workloads as currently exists in cloud?

- [ ] Yes — on-premises monitoring tooling is available or identified
- [ ] Partial — some monitoring capability; gaps identified
- [ ] No — monitoring capability gap; cloud native monitoring will be lost

### 2.5 Backup and DR for repatriated workloads

Has the backup and disaster recovery architecture been defined for repatriated workloads?

- [ ] Yes — backup and DR architecture defined and costed
- [ ] In progress — architecture in design
- [ ] No — backup and DR not yet addressed for repatriated workloads

**Technical readiness score:** _____ / 5 items complete = _____%

**Flag if below 60%:** [ ] Flagged for remediation

**Notes / gaps:** _______________________________________________

---

## Dimension 3 — Operational and skills readiness

The leading cause of repatriation failure is not technology — it is the absence of operational capability to run on-premises infrastructure. Cloud-native IT teams frequently lack the skills that were considered table-stakes a decade ago.

### 3.1 On-premises infrastructure operations skills

Does the team have current, practised skills in:

| Skill area | In-house capability | Gap / remediation needed |
|---|---|---|
| Physical server provisioning and management | Yes / No / Partial | |
| Storage area network (SAN) or NAS management | Yes / No / Partial | |
| Virtualisation platform administration (VMware or alternative) | Yes / No / Partial | |
| Network infrastructure (switching, routing, firewall) | Yes / No / Partial | |
| On-premises backup and recovery operations | Yes / No / Partial | |
| Patch management and change control (on-premises) | Yes / No / Partial | |
| Hardware break/fix and vendor management | Yes / No / Partial | |

### 3.2 Runbook and documentation status

Do operational runbooks exist for the repatriated workloads?

- [ ] Yes — runbooks are current and have been tested
- [ ] Partially — some runbooks exist; gaps remain
- [ ] No — runbooks do not exist or are significantly out of date

### 3.3 24/7 operational coverage

Is 24/7 or after-hours operational coverage available for critical on-premises systems?

- [ ] Yes — on-call coverage is in place or contracted
- [ ] Partial — coverage during business hours only
- [ ] No — no after-hours coverage plan exists

**Operational readiness score:** _____ / skills complete + 2 process items = _____%

**Flag if below 60%:** [ ] Flagged for remediation

**Skills gap remediation plan required:** _______________________________________________

---

## Dimension 4 — VMware / Broadcom licensing exposure

### 4.1 VMware licence status

What is the organisation's current VMware licensing position?

- [ ] Perpetual licences — affected by Broadcom's 2024 elimination of perpetual licensing
- [ ] Subscription licences — current; evaluate renewal cost
- [ ] No VMware licences — not applicable

### 4.2 Broadcom pricing impact

Has the financial impact of Broadcom's VMware licensing changes been quantified?

- [ ] Yes — impact quantified: estimated additional annual cost: $ _______________
- [ ] In progress — analysis underway
- [ ] No — impact not yet assessed

### 4.3 Migration timeline pressure

Does the VMware licensing situation create a time pressure on the repatriation decision?

- [ ] Yes — licence renewal deadline creates urgency: date _______________
- [ ] No — no immediate time pressure from licensing

### 4.4 Alternative platform evaluation

Have alternative virtualisation platforms been evaluated?

- [ ] Yes — alternatives evaluated; decision made or in progress
- [ ] No — alternatives not yet evaluated

**VMware/Broadcom exposure score:** _____ / 4 items assessed = _____%

**Flag if below 60%:** [ ] Flagged for remediation

---

## Dimension 5 — Hyperscaler dependency mapping

For each candidate workload, identify the cloud-native services it depends on that may complicate migration.

### 5.1 Dependency inventory

| Workload | Cloud-native services used | Portability assessment | Migration complexity |
|---|---|---|---|
| | | | Low / Medium / High |
| | | | Low / Medium / High |
| | | | Low / Medium / High |

*Cloud-native service examples: AWS Lambda, AWS RDS, Azure AD B2C, Azure Kubernetes Service, GCP BigQuery, Cloud Pub/Sub, managed AI services*

### 5.2 Data format portability

Is data stored in open, portable formats — or in proprietary formats that complicate extraction?

- [ ] Open formats — data is portable with standard tools
- [ ] Mixed — some proprietary formats; extraction effort required
- [ ] Proprietary formats — significant extraction and transformation effort required

### 5.3 API and integration dependencies

Are any business-critical integrations dependent on hyperscaler-proprietary APIs?

- [ ] No — integrations use open standards (REST, OAuth, standard protocols)
- [ ] Some — a small number of proprietary API dependencies; replaceable with effort
- [ ] Significant — deep proprietary API dependencies; re-architecture required

### 5.4 Repatriation sequencing recommendation

Based on the dependency assessment, sequence candidate workloads:

**Repatriate first (low dependency, high savings or compliance driver):**

| Workload | Rationale |
|---|---|
| | |

**Repatriate second (moderate dependency, clear business case):**

| Workload | Rationale |
|---|---|
| | |

**Remain in cloud (high dependency or cloud-native by design):**

| Workload | Rationale |
|---|---|
| | |

**Dependency mapping score:** _____ / 4 items complete = _____%

**Flag if below 60%:** [ ] Flagged for remediation

---

## Overall readiness summary

| Dimension | Score | Status |
|---|---|---|
| Financial readiness | ____% | ✅ Ready / ⚠️ Flagged |
| Technical readiness | ____% | ✅ Ready / ⚠️ Flagged |
| Operational and skills readiness | ____% | ✅ Ready / ⚠️ Flagged |
| VMware/Broadcom exposure | ____% | ✅ Ready / ⚠️ Flagged |
| Hyperscaler dependency mapping | ____% | ✅ Ready / ⚠️ Flagged |
| **Overall readiness** | ____%  | |

---

## Recommended next steps

Based on the assessment above:

- [ ] Complete TCO model for all candidate workloads (`tco-model.xlsx`)
- [ ] Address flagged dimensions before beginning migration
- [ ] Develop skills remediation plan for identified gaps
- [ ] Initiate platform selection for virtualisation alternative (if VMware-exposed)
- [ ] Begin Module 3 (Hybrid estate optimisation) to govern the resulting hybrid estate
- [ ] Document repatriation sequencing in project plan with milestones
- [ ] Review assessment: _______________________ (recommend within 90 days if flagged items exist)

---

*Infrastructure Placement Framework · Module 2 Assessment · 4th and Bailey · v1.0.0*
*github.com/4thandBailey/infrastructure-placement-framework*
