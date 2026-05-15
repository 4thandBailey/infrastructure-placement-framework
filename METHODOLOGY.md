# Methodology

## Infrastructure Placement Framework · Scoring Rationale and Weighting Logic

**4TH AND BAILEY** · Version 1.0.0 · May 2026

---

## Purpose of this document

This document explains how the Infrastructure Placement Framework's assessments are structured, how scoring weights are assigned, how scores translate into recommendations, and how methodology decisions were made. It is intended for practitioners who want to understand the reasoning behind the framework before applying it, and for contributors who want to submit changes to scoring logic.

Any change to the scoring methodology requires an update to this document. Changes to METHODOLOGY.md are reviewed with higher scrutiny than changes to templates or documentation.

---

## Foundational design principles

**1. Vendor neutrality.** No module recommends a specific vendor. Scoring criteria are defined by business outcome (cost, risk, performance, compliance) — not by product capabilities. Where vendor examples are cited, they are illustrative, not prescriptive.

**2. Evidence over instinct.** Every placement recommendation must be traceable to scored criteria. The Architecture Decision Record template exists to document the reasoning, not just the conclusion.

**3. Sector sensitivity.** A workload placement decision for a healthcare organisation and the same decision for a logistics firm involve fundamentally different regulatory constraints. Scoring weights are adjusted by sector variant, not applied as universal constants.

**4. Honest scope.** This framework is a structured starting point, not a definitive answer. Assessments identify the right questions and score the available evidence — they do not replace domain expertise or legal counsel for regulated decisions.

**5. Living methodology.** Technology markets, regulatory requirements, and economic conditions change. Scoring weights are reviewed annually and updated with versioned releases. The date of the methodology version applies to all modules until superseded.

---

## Scoring model — Module 1 (Workload placement)

Each workload is scored across five dimensions. Each dimension is rated 1–5. The resulting score indicates the placement recommendation.

### Dimension definitions

**Cost gravity (weight: 25%)**

Measures whether the workload's cost profile favours cloud economics or private/on-premises infrastructure over a three-year TCO horizon.

| Score | Interpretation |
|---|---|
| 5 | Highly variable/bursty workload — cloud pay-per-use economics are clearly superior |
| 4 | Moderately variable — cloud economics slightly favourable |
| 3 | Mixed profile — cost roughly equivalent across tiers |
| 2 | Predominantly steady-state — private infrastructure becoming more cost-effective at scale |
| 1 | Steady-state, high-volume workload — private/on-premises clearly more cost-effective at 3-year TCO |

**Latency and performance tolerance (weight: 20%)**

Measures whether the workload can tolerate the latency inherent in cloud-based delivery.

| Score | Interpretation |
|---|---|
| 5 | Latency-tolerant — no performance requirement that cloud cannot meet |
| 4 | Low sensitivity — minor latency acceptable |
| 3 | Moderate sensitivity — some latency impact acceptable with optimisation |
| 2 | High sensitivity — latency is architecturally constraining; cloud requires significant engineering |
| 1 | Latency-critical — cloud is architecturally wrong for this workload regardless of cost |

**Compliance and data sovereignty (weight: 25%)**

Measures the extent to which regulatory, contractual, or sovereignty requirements constrain placement options.

| Score | Interpretation |
|---|---|
| 5 | No compliance constraints — workload can be placed in any tier |
| 4 | Minimal constraints — standard cloud compliance controls are sufficient |
| 3 | Moderate constraints — specific cloud regions or configurations required |
| 2 | Significant constraints — limited cloud options; requires extensive compliance validation |
| 1 | Data must remain on-premises or in a sovereign/private environment — cloud placement not viable |

**Private AI infrastructure fit (weight: 15%)**

Measures whether the workload involves AI processing of sensitive data that benefits from private infrastructure.

| Score | Interpretation |
|---|---|
| 5 | No AI component — dimension not applicable; score neutral |
| 4 | Uses AI features through approved SaaS vendors with acceptable data terms |
| 3 | Runs AI workloads in cloud but with managed data isolation |
| 2 | Processes sensitive data through AI; cloud AI vendor terms create IP or compliance risk |
| 1 | Processes proprietary or regulated data through AI at volume — private AI infrastructure indicated |

**Vendor lock-in and licensing risk (weight: 15%)**

Measures the extent to which the workload is subject to vendor lock-in risk that affects placement flexibility.

| Score | Interpretation |
|---|---|
| 5 | Open standards, portable data formats, no proprietary dependencies |
| 4 | Minor proprietary dependencies — manageable migration path exists |
| 3 | Moderate lock-in — migration feasible but non-trivial |
| 2 | Significant lock-in — proprietary formats, deep API integration, or high switching cost |
| 1 | Severe lock-in — VMware/Broadcom licensing shock, proprietary platform with no export path |

### Placement scoring thresholds

A weighted composite score is calculated across all five dimensions. The resulting score maps to a placement recommendation:

| Composite score | Placement recommendation |
|---|---|
| 4.0 – 5.0 | Public cloud — clear fit |
| 3.0 – 3.9 | Public cloud preferred — validate compliance and cost |
| 2.5 – 2.9 | Hybrid — workload may span tiers |
| 1.5 – 2.4 | Private cloud or colocation preferred |
| 1.0 – 1.4 | On-premises — cloud placement not indicated |

*Note: A score of 1 on the Compliance dimension is a hard override — regardless of composite score, workloads with an absolute compliance constraint cannot be placed in public cloud.*

---

## Scoring model — Module 2 (Repatriation readiness)

Repatriation readiness is assessed across five organisational dimensions. Each is rated as a readiness level (Not started / In progress / Established / Optimised).

| Dimension | What it measures |
|---|---|
| Financial readiness | Has a 3-year TCO model been completed? Is capital available for infrastructure investment? |
| Technical readiness | Does the team have the skills to operate on-premises infrastructure? Is the hardware pathway defined? |
| Operational readiness | Are runbooks, change management, and monitoring capabilities in place for on-premises operation? |
| VMware/Broadcom exposure | What is the licensing cost pressure and urgency driving the repatriation decision? |
| Dependency complexity | How deep are the hyperscaler service dependencies? What is the migration engineering effort? |

A readiness score below 60% in any dimension is a flagged risk that must be addressed before repatriation sequencing begins.

---

## Scoring model — Module 4 (Cyber resilience)

The third-party risk scorecard rates each critical vendor across five dimensions: data access level, single-point-of-failure risk, contractual portability, incident history, and update governance. Vendors with a combined risk score above the threshold are flagged for remediation or exit planning.

The CrowdStrike lessons checklist is binary — each control is either in place (pass) or not (fail). A score below 80% pass rate triggers an immediate remediation programme.

---

## Scoring model — Module 5 (AI governance)

The NIST AI RMF assessment scores each of the four RMF functions (Govern, Map, Measure, Manage) across the organisation. Each function is scored 0–25, for a maximum total of 100.

| Score range | Maturity level |
|---|---|
| 0 – 24 | Initial — no formal AI governance |
| 25 – 49 | Developing — some controls in place, not systematic |
| 50 – 74 | Defined — documented governance with gaps |
| 75 – 89 | Managed — systematic, measured governance |
| 90 – 100 | Optimising — continuous improvement programme |

The shadow AI audit is reported separately as a risk register — each identified tool is rated by data sensitivity accessed, regulatory risk, and remediation priority.

---

## Sector weighting adjustments

Sector variants adjust the weighting of scoring dimensions to reflect the dominant concerns of each sector. The base weights defined in Module 1 are modified as follows:

| Sector | Compliance weight | Cost gravity weight | Rationale |
|---|---|---|---|
| Healthcare | 35% | 15% | HIPAA, PHI sovereignty, and data residency requirements override cost optimisation |
| Legal | 30% | 20% | Client data sovereignty and matter management confidentiality constraints |
| Financial services | 35% | 15% | SOX, PCI-DSS, GLBA, and trading latency create hard placement constraints |
| Energy / Oil & Gas | 25% | 20% | NERC CIP and OT/IT convergence add compliance weight; remote site costs also significant |
| Logistics | 20% | 25% | Real-time tracking and fleet edge compute elevate cost and latency considerations |
| Non-profit / Faith-based | 20% | 30% | Cost sensitivity is the dominant placement driver; compliance constraints are lower |

---

## Architecture Decision Record requirements

Every placement recommendation output from Module 1 must be accompanied by an Architecture Decision Record (ADR) using the template in `/templates/workload-adr.md`. The ADR must include:

- The decision context (what triggered the assessment)
- The options considered (not just the recommendation)
- The scoring rationale (scores per dimension with brief justification)
- The risks and mitigations
- The review date (placement decisions expire — they must be reviewed on cadence)

ADRs without a defined review date are considered incomplete.

---

## Version control and review cadence

This methodology document is reviewed and updated on the following schedule:

- **Annual review:** Full methodology review aligned with framework major/minor release
- **Triggered review:** Any time a significant market event (regulatory change, major vendor pricing change, notable infrastructure incident) makes existing weights materially incorrect
- **Contribution-triggered review:** Any PR that proposes a change to scoring logic must update this document

All methodology changes are logged in CHANGELOG.md with the specific dimension or module affected.

---

## Cited sources

- Barclays CIO Survey Q4 2024 — cloud repatriation intent statistics
- Flexera 2025 State of the Cloud Report — repatriation rates and dual-stack prevalence
- NIST AI RMF 1.0 (2023) — AI governance scoring framework
- NIST AI 600-1 Generative AI Profile (July 2024) — generative AI risk categories
- NIST CSF 2.0 (2024) — cybersecurity framework
- NIST IR 8596 Cyber AI Profile (December 2025) — AI-specific cybersecurity considerations
- Verizon Data Breach Investigations Report 2025 — ransomware statistics
- IBM Cost of a Data Breach Report 2025 — recovery timeline statistics
- FEMA Small Business Disaster Statistics — survival rates post-disaster

---

*Infrastructure Placement Framework Methodology · Version 1.0.0 · May 2026*
*4th and Bailey · github.com/4thandBailey/infrastructure-placement-framework*
