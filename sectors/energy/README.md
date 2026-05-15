# Sector Variant — Energy / Oil & Gas

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Sector overview

Energy and oil & gas organizations operate at the intersection of IT and Operational Technology (OT) — two environments with fundamentally different security models, latency requirements, and regulatory frameworks. SCADA systems, industrial control systems (ICS), and remote field operations cannot tolerate the latency of cloud delivery for control functions. NERC CIP (for organizations connected to the bulk electric system) creates mandatory security controls that constrain placement options.

The IT/OT convergence that has accelerated over the past decade has also expanded the attack surface dramatically. OT systems that were once air-gapped are now connected — and the frameworks that govern IT security were not designed for OT environments where a security failure can mean physical damage to equipment, environmental incidents, or loss of life.

---

## Scoring weight adjustments

| Dimension | Base weight | Energy weight | Rationale |
|---|---|---|---|
| Latency and performance tolerance | 20% | **30%** | OT/SCADA control systems have deterministic latency requirements that are architectural constraints, not preferences |
| Compliance and data sovereignty | 25% | **25%** | NERC CIP creates hard requirements for BES Cyber Systems; unchanged |
| Cost gravity | 25% | **20%** | Remote site connectivity costs and OT infrastructure economics differ significantly from standard IT |
| Vendor lock-in and licensing risk | 15% | **15%** | Unchanged — industrial control vendor lock-in is a real concern |
| Private AI infrastructure fit | 15% | **10%** | Lower weight in most OT contexts; higher for AI applied to operational data analytics |

---

## The IT/OT distinction

| Environment | Latency requirement | Primary concern | Cloud suitability |
|---|---|---|---|
| IT (office, ERP, email, HR) | Tolerant (seconds acceptable) | Confidentiality | Standard cloud assessment applies |
| OT (SCADA, DCS, PLCs, RTUs) | Deterministic (milliseconds or sub-millisecond) | Availability and integrity | Cloud is generally inappropriate for real-time control |
| IT/OT interface (historian, SIEM, analytics) | Near-real-time (seconds) | Both | Edge or private cloud preferred; public cloud for analytics |
| Field data (sensors, telemetry) | Varies | Availability | Edge compute at collection point; cloud for aggregation |

**OT systems must be assessed separately from IT systems under Module 1. A composite score that includes OT workloads alongside IT workloads will produce misleading results.**

---

## Module-specific questions

### Module 1 — Workload placement

- Is this workload a real-time control function (SCADA, DCS, PLC supervisory control)?
- Is this workload subject to NERC CIP as a BES Cyber System?
- Is this workload at a remote field location with limited or unreliable connectivity?
- Does this workload generate high-volume operational data (historian, telemetry) that would create excessive cloud egress costs?
- Is this workload a candidate for edge compute placement?

### Module 4 — Cyber resilience

- Does the cyber resilience assessment address OT systems separately from IT systems?
- Does the incident response plan address OT-specific scenarios (control system compromise, physical damage from cyber event)?
- Is the IT network segmented from the OT network (Purdue model or ISA/IEC 62443)?
- Does the third-party risk scorecard include OT vendor software and firmware updates?

### Module 5 — AI governance

- Is AI being applied to operational data (predictive maintenance, anomaly detection, production optimization)?
- Is operational data subject to export controls or data residency requirements?
- Does AI governance cover both IT and OT environments?

---

## Key regulations

| Regulation | Scope | Impact |
|---|---|---|
| NERC CIP | Bulk Electric System Cyber Systems | Mandatory security controls for applicable utilities; significant placement constraints |
| ISA/IEC 62443 | Industrial automation and control security | Widely adopted OT security standard |
| CISA advisories | ICS/SCADA vulnerabilities | Ongoing operational guidance for OT security |
| Texas Commission on Environmental Quality (TCEQ) | Operational compliance | Relevant for operations with environmental obligations |
| Pipeline and Hazardous Materials Safety Administration (PHMSA) | Pipeline safety and control systems | Relevant for pipeline operators |

---

*Infrastructure Placement Framework · Energy / Oil & Gas Sector Variant · 4th and Bailey · v1.0.0*
*4thandbailey.com · (888) 305-5977 · Houston, TX*
