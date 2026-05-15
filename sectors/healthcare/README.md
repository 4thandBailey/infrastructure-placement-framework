# Sector Variant — Healthcare

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Sector overview

Healthcare organizations face the most constrained infrastructure placement environment of any sector in this framework. HIPAA creates hard placement rules for Protected Health Information (PHI) that override cost and performance optimization in almost every case. Real-time clinical workloads add latency requirements that cloud cannot always meet. And the consequences of a breach — regulatory, financial, and reputational — are among the highest of any industry.

This sector variant adjusts scoring weights and adds domain-specific questions for each module.

---

## Scoring weight adjustments

| Dimension | Base weight | Healthcare weight | Rationale |
|---|---|---|---|
| Compliance and data sovereignty | 25% | **35%** | HIPAA PHI requirements create hard placement constraints that override cost optimization |
| Cost gravity | 25% | **15%** | Cost is still relevant but cannot override compliance |
| Latency and performance tolerance | 20% | **25%** | Real-time diagnostics, EHR performance, and clinical workflow latency are patient safety issues |
| Private AI infrastructure fit | 15% | **15%** | Unchanged — but AI on PHI is a HIPAA concern; see Module 5 |
| Vendor lock-in and licensing risk | 15% | **10%** | Lower weight — cloud vendor changes are harder when HIPAA BAAs are in place |

---

## Module-specific questions

### Module 1 — Workload placement

Additional questions for healthcare workloads:

- Does this workload process, store, or transmit PHI?
- Does the workload involve real-time clinical data (diagnostics, monitoring, EHR access at point of care)?
- Does a signed Business Associate Agreement (BAA) exist with the current cloud vendor for this workload?
- Is the data subject to state-level health data residency requirements beyond HIPAA?
- Does the workload involve medical imaging (PACS/DICOM) with high storage or bandwidth requirements?

### Module 2 — Repatriation readiness

- Is the repatriation motivated in part by a vendor's inability to maintain HIPAA BAA compliance?
- Has a BAA been obtained from the target on-premises infrastructure provider (colocation, managed hosting)?
- Is the EHR system cloud-hosted by the vendor? (EHR vendor-hosted deployments have different repatriation dynamics than self-hosted)

### Module 4 — Cyber resilience

- Does the backup architecture cover the EHR system specifically?
- Has the HIPAA Breach Risk Assessment been completed for all data in scope?
- Are clinical operations manual fallback procedures documented for IT system outages?
- Does the breach notification guide address the 60-day HIPAA notification timeline?
- Is the ransomware playbook adapted for scenarios involving PHI exfiltration?

### Module 5 — AI governance

- Has the AI tool vendor signed a HIPAA BAA?
- Are any clinical AI tools (diagnostic AI, imaging AI) subject to FDA Software as a Medical Device (SaMD) classification?
- Does the AI acceptable use policy explicitly prohibit PHI entry into non-approved AI tools?

### Module 7 — Collaboration platform

- Does the M365 or Workspace configuration have a HIPAA BAA in place?
- Is Microsoft 365 Copilot or Google Gemini enabled on accounts that have access to PHI?
- Does the collaboration platform meet HIPAA requirements for audit logging, access control, and data retention?

---

## Key regulations

| Regulation | Scope | Impact |
|---|---|---|
| HIPAA Privacy Rule | PHI use and disclosure | Defines what PHI can be shared and with whom |
| HIPAA Security Rule | Electronic PHI (ePHI) safeguards | Technical, administrative, and physical safeguards required |
| HIPAA Breach Notification Rule | PHI breach notification | 60-day notification deadline to HHS and affected individuals |
| HITECH Act | Extends HIPAA to business associates | All vendors with PHI access need BAA |
| Texas Health & Safety Code § 181 | Texas medical records | Additional Texas-specific health data protections |
| 21st Century Cures Act | EHR interoperability | Information blocking provisions affect data portability |

---

## Healthcare-specific contacts

For organizations served by 4th and Bailey in the healthcare sector:

**4th and Bailey** · 4thandbailey.com · (888) 305-5977
2500 CityWest Blvd., Suite #150-165 · Houston, TX 77042

---

*Infrastructure Placement Framework · Healthcare Sector Variant · 4th and Bailey · v1.0.0*
