# Module 1 — Workload Placement Decision Tree

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

Use this decision tree for rapid initial triage before completing the full scored assessment. It does not replace the scored assessment — it identifies which path to prioritise and surfaces hard constraints early.

---

## Step 1 — Compliance hard gate

> Does this workload process, store, or transmit data subject to a regulatory or contractual requirement that mandates a specific placement?

Examples: HIPAA PHI, NERC CIP, classified data, client contract data residency clause, EU data transfer restriction.

- **YES** → The compliance requirement defines the placement. Document the constraint in the ADR. Proceed to Step 3 only for validation. *Do not apply cost or performance scoring to override a hard compliance constraint.*
- **NO** → Proceed to Step 2.

---

## Step 2 — Latency hard gate

> Does this workload have a latency or determinism requirement that cloud architecture cannot meet?

Examples: manufacturing OT systems, real-time diagnostics, SCADA/industrial control, financial trading systems, sub-millisecond response requirements.

- **YES** → On-premises, colocation, or edge placement is indicated. Proceed to Step 3 to validate cost and confirm tier.
- **NO** → Proceed to Step 3.

---

## Step 3 — Cost gravity check

> Is this workload characterised by steady-state, predictable compute demand at significant scale?

Indicators of steady-state: consistent CPU/memory utilisation, predictable traffic patterns, high monthly cloud bill for consistent workloads, running 24/7 at near-constant resource levels.

- **YES (steady-state, high scale)** → On-premises or private cloud likely more cost-effective. Run 3-year TCO comparison. Proceed to Step 4.
- **NO (bursty or unpredictable)** → Cloud economics likely favourable. Proceed to Step 4.

---

## Step 4 — VMware/Broadcom exposure

> Is this workload running on VMware infrastructure, and is the organisation affected by Broadcom's 2024 licensing changes?

- **YES** → Repatriation or virtualisation platform migration may be financially urgent. Initiate Module 2 (Cloud Repatriation Readiness). Flag this workload as priority for full scored assessment.
- **NO** → Proceed to Step 5.

---

## Step 5 — AI sensitivity check

> Does this workload process proprietary, confidential, or regulated data through AI services?

Examples: Pasting contracts, financial models, source code, or client data into LLMs. Running fine-tuned models on corporate data. Using AI-embedded SaaS tools that process sensitive inputs.

- **YES, at significant volume** → Private AI infrastructure may be indicated. Flag for Module 5 (AI Governance). Score Dimension 4 carefully in the full assessment.
- **NO or minimal** → Proceed to full scored assessment.

---

## Step 6 — Initial placement signal

Based on Steps 1–5, what is the initial placement signal?

| Signal | Initial recommendation |
|---|---|
| Compliance hard gate triggered | On-premises / sovereign private |
| Latency hard gate triggered | On-premises / colocation / edge |
| Steady-state + high scale + no compliance constraint | Private cloud or on-premises — run TCO |
| Bursty + no compliance or latency constraint | Public cloud likely |
| VMware exposure + repatriation consideration | Module 2 priority |
| AI sensitivity + sensitive data | Module 5 + private infrastructure review |
| No strong signals either way | Run full scored assessment — composite score will indicate |

---

## Proceed to full assessment

This decision tree provides an initial signal only. All workloads should be completed through the full [assessment.md](./assessment.md) before a placement recommendation is finalised and documented in an Architecture Decision Record.

---

*Infrastructure Placement Framework · Module 1 Decision Tree · 4th and Bailey · v1.0.0*
