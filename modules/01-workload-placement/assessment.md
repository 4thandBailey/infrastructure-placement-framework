# Module 1 — Workload Placement Assessment

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## How to use this assessment

Complete one copy of this assessment for each workload being evaluated. A "workload" is any discrete application, database, service, or dataset that could be placed in a different infrastructure tier independently.

**Recommended approach:**
1. Identify all workloads in scope before beginning scoring (use the workload inventory table below)
2. Score each workload independently across all five dimensions
3. Calculate the weighted composite score
4. Document the recommendation in an Architecture Decision Record (`/templates/workload-adr.md`)
5. Review the full portfolio — placement decisions interact with each other

**Time estimate:** 30–60 minutes per workload for an experienced IT practitioner. Initial portfolio inventory may take 2–4 hours for a typical mid-market organisation.

---

## Workload inventory

Before scoring, list all workloads in scope:

| # | Workload name | Type | Owner | Current placement | Last reviewed |
|---|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

*Add rows as needed. Types: Application / Database / Service / Dataset / AI workload / OT/IoT*

---

## Assessment — per workload

**Workload name:** _______________________________________________

**Workload type:** Application / Database / Service / Dataset / AI workload / OT/IoT *(circle one)*

**Current placement:** Public cloud / Private cloud / On-premises / Colocation / Edge *(circle one)*

**Assessment date:** _______________________

**Assessed by:** _______________________

---

### Dimension 1 — Cost gravity (weight: 25%)

The 3-year Total Cost of Ownership comparison across placement options. This should be based on actual cost modelling, not estimates. Include compute, storage, egress, licensing, staffing, and capital expenditure.

**Scoring guide:**

| Score | Description |
|---|---|
| 5 | Highly variable or bursty workload — cloud pay-per-use economics clearly superior; 3-year TCO favours cloud |
| 4 | Moderately variable workload — cloud economics slightly favourable; private infrastructure approaching parity |
| 3 | Mixed cost profile — TCO roughly equivalent across tiers within 10–15% margin |
| 2 | Predominantly steady-state workload — private infrastructure more cost-effective at scale; 3-year TCO favours private |
| 1 | High-volume, steady-state workload — on-premises clearly most cost-effective at 3-year TCO; cloud premium not justified |

**Supporting data (required for scores of 1 or 5):**
- Current monthly/annual cloud cost or estimated on-premises cost: $ _______________
- 3-year TCO estimate (cloud): $ _______________
- 3-year TCO estimate (on-premises/private): $ _______________
- Key cost drivers identified: _______________________________________________

**Score (1–5):** _______ | **Weighted contribution (score × 0.25):** _______

---

### Dimension 2 — Latency and performance tolerance (weight: 20%)

Whether the workload can tolerate the latency inherent in cloud-based delivery, and whether performance requirements make cloud architecturally appropriate.

**Scoring guide:**

| Score | Description |
|---|---|
| 5 | No latency sensitivity — workload functions normally with 50–100ms+ round-trip latency |
| 4 | Low latency sensitivity — minor latency acceptable; cloud with CDN or regional deployment sufficient |
| 3 | Moderate sensitivity — some latency impact acceptable with architectural optimisation (caching, edge nodes) |
| 2 | High sensitivity — latency is constraining; cloud requires significant additional engineering to meet requirements |
| 1 | Latency-critical — sub-millisecond or deterministic latency required; cloud is architecturally wrong regardless of cost |

**Supporting data:**
- Current latency requirement (if defined): _______________________________________________
- Latency-sensitive functions or users: _______________________________________________
- Any existing latency complaints or incidents: _______________________________________________

**Score (1–5):** _______ | **Weighted contribution (score × 0.20):** _______

---

### Dimension 3 — Compliance and data sovereignty (weight: 25%)

The extent to which regulatory, contractual, or data sovereignty requirements constrain where this workload can be placed.

**Check all that apply:**

- [ ] HIPAA — Protected Health Information (PHI) processed or stored
- [ ] PCI-DSS — Cardholder data or payment processing
- [ ] SOX — Financial reporting data or systems
- [ ] GLBA — Financial institution customer data
- [ ] NERC CIP — Bulk electric system or OT/SCADA
- [ ] FERPA — Student educational records
- [ ] State data residency law (specify): _______________________________________________
- [ ] Contractual data residency obligation (e.g., client contract, government contract)
- [ ] EU/international data transfer restrictions (GDPR or equivalent)
- [ ] Classified or export-controlled data
- [ ] No compliance constraints applicable

**Scoring guide:**

| Score | Description |
|---|---|
| 5 | No compliance constraints — workload data can be placed in any tier or geography |
| 4 | Minimal constraints — standard cloud compliance controls (SOC 2, ISO 27001, FedRAMP) are sufficient |
| 3 | Moderate constraints — specific cloud regions required; compliance validation effort is significant but achievable |
| 2 | Significant constraints — limited cloud options; requires extensive compliance validation and architectural controls |
| 1 | Hard constraint — data must remain on-premises or in sovereign/private environment; cloud placement not viable |

*Note: A score of 1 on this dimension is a hard override — regardless of composite score, the workload cannot be placed in public cloud.*

**Score (1–5):** _______ | **Weighted contribution (score × 0.25):** _______

---

### Dimension 4 — Private AI infrastructure fit (weight: 15%)

Whether this workload involves AI processing of sensitive or proprietary data at a volume or sensitivity level that makes private AI infrastructure preferable to cloud AI services.

**Scoring guide:**

| Score | Description |
|---|---|
| 5 | No AI component — workload does not use or generate AI inference; dimension not applicable (score 3 if neutral) |
| 4 | Uses AI features through approved SaaS vendors with reviewed and acceptable data handling terms |
| 3 | Runs AI workloads in cloud with managed data isolation; terms reviewed; IP risk is managed |
| 2 | Processes sensitive or proprietary data through AI at moderate volume; cloud AI vendor terms create IP or compliance exposure |
| 1 | Processes proprietary, confidential, or regulated data through AI at significant volume; private AI infrastructure clearly indicated |

**Supporting data:**
- Does this workload use AI features? Yes / No
- If yes, which AI tools or services: _______________________________________________
- Data classification of inputs to AI processing: _______________________________________________
- AI vendor data handling terms reviewed? Yes / No / Not applicable

**Score (1–5):** _______ | **Weighted contribution (score × 0.15):** _______

---

### Dimension 5 — Vendor lock-in and licensing risk (weight: 15%)

The extent to which the workload is subject to vendor lock-in that limits placement flexibility or creates financial exposure through proprietary licensing.

**VMware/Broadcom exposure checklist:**
- [ ] Workload runs on VMware vSphere / ESXi
- [ ] Organisation is on VMware perpetual licences affected by Broadcom's 2024 pricing changes
- [ ] No VMware dependency

**Additional lock-in indicators:**
- [ ] Proprietary data formats with no export capability
- [ ] Deep integration with hyperscaler-proprietary services (e.g., AWS Lambda, Azure AD B2C beyond standard protocols)
- [ ] No contractual portability clause with current vendor
- [ ] Team lacks knowledge to export or migrate the workload

**Scoring guide:**

| Score | Description |
|---|---|
| 5 | Open standards, portable data formats, documented migration path — no meaningful lock-in |
| 4 | Minor proprietary dependencies — manageable migration path exists with reasonable effort |
| 3 | Moderate lock-in — migration feasible but non-trivial; 2–6 months engineering effort estimated |
| 2 | Significant lock-in — proprietary formats, deep API integration, or high switching cost; 6–18 months effort |
| 1 | Severe lock-in — VMware/Broadcom licensing shock, platform with no export path, or contractual trap |

**Score (1–5):** _______ | **Weighted contribution (score × 0.15):** _______

---

## Score summary

| Dimension | Weight | Raw score | Weighted score |
|---|---|---|---|
| Cost gravity | 25% | | |
| Latency and performance tolerance | 20% | | |
| Compliance and data sovereignty | 25% | | |
| Private AI infrastructure fit | 15% | | |
| Vendor lock-in and licensing risk | 15% | | |
| **Composite score** | **100%** | | **_____ / 5.0** |

---

## Placement recommendation

| Composite score | Recommendation |
|---|---|
| 4.0 – 5.0 | Public cloud — clear fit |
| 3.0 – 3.9 | Public cloud preferred — validate compliance and cost |
| 2.5 – 2.9 | Hybrid — workload may span tiers |
| 1.5 – 2.4 | Private cloud or colocation preferred |
| 1.0 – 1.4 | On-premises — cloud placement not indicated |

**Hard override:** If Dimension 3 (Compliance) scored 1, placement is **On-premises or sovereign private environment** regardless of composite score.

**Recommended placement:** _______________________________________________

**Rationale summary (2–3 sentences):** _______________________________________________

---

## Next steps

- [ ] Complete Architecture Decision Record at `/templates/workload-adr.md`
- [ ] If recommendation differs from current placement: initiate Module 2 (repatriation) or Module 3 (optimisation)
- [ ] If AI dimension scored 1 or 2: initiate Module 5 (AI governance)
- [ ] Schedule review date: _______________________ (placement decisions should be reviewed annually)

---

*Infrastructure Placement Framework · Module 1 Assessment · 4th and Bailey · v1.0.0*
*github.com/4thandBailey/infrastructure-placement-framework*
