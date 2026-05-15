# Module 1 — Workload Placement Assessment

**Pillar:** Place it right · **Framework:** Infrastructure Placement Framework v1.0.0

---

## The question

For every workload in your environment — application, database, service, or dataset — which infrastructure tier actually earns it?

The default answer for the past decade was "cloud." That default is now being actively tested by rising costs, compliance requirements, and the emergence of private AI infrastructure as a genuine workload driver. The correct answer in 2026 is different for each workload and requires a structured, scored methodology to get right.

---

## What this module covers

This module provides a five-dimension scoring model for evaluating each workload against the full range of placement options:

- **Public cloud** — hyperscaler IaaS/PaaS (AWS, Azure, GCP)
- **Private cloud** — on-premises virtualised infrastructure
- **Colocation** — organisation-owned hardware in a third-party data centre
- **On-premises** — organisation-owned hardware in organisation-owned facilities
- **Edge** — compute at or near the point of data generation (OT, IoT, field operations)

---

## The five scoring dimensions

| Dimension | Weight | What it measures |
|---|---|---|
| Cost gravity | 25% | 3-year TCO across placement options |
| Latency and performance tolerance | 20% | Whether the workload can tolerate cloud delivery latency |
| Compliance and data sovereignty | 25% | Regulatory, contractual, and sovereignty constraints |
| Private AI infrastructure fit | 15% | Whether AI processing of sensitive data requires private infrastructure |
| Vendor lock-in and licensing risk | 15% | VMware/Broadcom exposure and proprietary dependency risk |

Full scoring definitions and thresholds are documented in [METHODOLOGY.md](../../METHODOLOGY.md).

---

## Files in this module

| File | Purpose |
|---|---|
| `README.md` | This file — module overview and navigation |
| `assessment.md` | Scored workload assessment guide — work through this for each workload |
| `assessment.json` | Machine-readable assessment schema for structured data capture |
| `decision-tree.md` | Visual decision tree for rapid initial placement triage |

---

## Output

Completing this module for each workload produces:

1. A scored placement recommendation (public cloud / private cloud / colocation / on-premises / edge)
2. A completed Architecture Decision Record (using the template at `/templates/workload-adr.md`)
3. A workload inventory with placement rationale suitable for board or leadership review

---

## Sector variants

Scoring weights are adjusted for the following sectors. See `/sectors/` for sector-specific guidance:

- Healthcare — compliance weight increased to 35%; HIPAA and PHI sovereignty are hard constraints
- Legal — compliance weight increased to 30%; client data sovereignty and matter confidentiality
- Financial services — compliance weight increased to 35%; SOX, PCI-DSS, GLBA, trading latency
- Energy / Oil & Gas — OT/IT convergence; NERC CIP; SCADA system placement considerations
- Logistics — latency and cost gravity elevated; real-time tracking and fleet edge compute

---

## Connection to other modules

| If this module reveals... | Proceed to... |
|---|---|
| Significant workloads currently in cloud that score for on-premises | Module 2 — Cloud repatriation readiness |
| Existing hybrid estate with placement gaps | Module 3 — Hybrid estate optimisation |
| VMware/Broadcom licensing exposure driving urgent decisions | Module 2 — Repatriation readiness |
| AI workloads processing sensitive data in public cloud | Module 5 — AI governance and NIST alignment |

---

*Infrastructure Placement Framework · Module 1 · 4th and Bailey · github.com/4thandBailey/infrastructure-placement-framework*
