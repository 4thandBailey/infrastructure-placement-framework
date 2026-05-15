# Sector Variant — Legal

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Sector overview

Legal organizations — law firms, corporate legal departments, and legal service providers — operate under a unique combination of professional obligation and regulatory constraint. Attorney-client privilege, client data confidentiality, and bar association ethics rules create placement constraints that go beyond typical regulatory compliance. The consequences of a breach extend beyond financial liability to include bar discipline, loss of client trust, and potential disqualification from matters.

Matter management systems (document management, billing, practice management) are typically mission-critical, latency-sensitive, and often involve proprietary vendor platforms that create their own lock-in dynamics.

---

## Scoring weight adjustments

| Dimension | Base weight | Legal weight | Rationale |
|---|---|---|---|
| Compliance and data sovereignty | 25% | **30%** | Client data sovereignty, privilege protection, and bar ethics obligations |
| Cost gravity | 25% | **20%** | Cost matters but cannot compromise client data obligations |
| Latency and performance tolerance | 20% | **20%** | Unchanged — matter management system performance is important |
| Vendor lock-in and licensing risk | 15% | **20%** | Proprietary matter management and document management lock-in is a significant risk |
| Private AI infrastructure fit | 15% | **10%** | AI governance matters but typically lower AI workload volume |

---

## Module-specific questions

### Module 1 — Workload placement

- Does this workload process, store, or transmit client data or attorney-client privileged communications?
- Is the workload subject to a client contract specifying data residency or confidentiality requirements?
- Does the workload involve matter management or document management with proprietary data formats?
- Are there bar association ethics opinions in the relevant jurisdiction governing cloud storage of client data?

### Module 2 — Repatriation readiness

- Is the matter management system cloud-hosted by the vendor? (Most legal DMS platforms — iManage, NetDocuments — are cloud-first; repatriation may not be applicable)
- Are client data residency requirements creating pressure to maintain on-premises document storage?

### Module 4 — Cyber resilience

- Does the breach notification guide address client notification obligations beyond regulatory requirements?
- Does the incident response plan address bar notification obligations (some state bars require notification of a security incident affecting client data)?
- Is the ransomware playbook adapted to address privilege waiver risks in the communication of a breach?

### Module 5 — AI governance

- Does the AI acceptable use policy address attorney-client privilege protection?
- Are lawyers using AI tools to draft documents involving privileged client information?
- Does the AI vendor evaluation rubric assess whether the vendor's data use terms are compatible with privilege protection?
- Have bar association ethics opinions on AI use been reviewed for the relevant jurisdictions?

### Module 7 — Collaboration platform

- Is client data shared in collaboration platform channels or shared drives accessible to non-authorised parties?
- Does the governance baseline address matter-level access controls (not just organization-level)?

---

## Key regulations and obligations

| Obligation | Source | Impact |
|---|---|---|
| Attorney-client privilege | Common law / evidence rules | Cloud placement must maintain confidentiality sufficient to preserve privilege |
| ABA Model Rule 1.6 | ABA Model Rules of Professional Conduct | Competence obligation includes understanding technology used for client data |
| State bar ethics opinions on cloud | Varies by state bar | Many state bars have published guidance on cloud storage of client data |
| Client data residency (contractual) | Client contracts | Some enterprise clients specify data location requirements |
| Document retention obligations | Varies by jurisdiction and matter type | Affects backup retention and destruction policies |

---

*Infrastructure Placement Framework · Legal Sector Variant · 4th and Bailey · v1.0.0*
*4thandbailey.com · (888) 305-5977 · Houston, TX*
