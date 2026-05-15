# Sector Variant — Financial Services

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Sector overview

Financial services organisations — banks, credit unions, investment firms, insurance companies, and financial technology businesses — operate under some of the most demanding regulatory environments for data governance and infrastructure security. SOX, PCI-DSS, GLBA, and (for larger institutions) OCC/Federal Reserve guidance create layered compliance obligations. Trading latency requirements for capital markets participants can make cloud architecturally incompatible with certain workloads regardless of cost.

The financial sector is also among the most targeted by ransomware and data breach actors. The combination of high regulatory penalty exposure and high data value makes the cyber resilience and BCDR modules particularly critical.

---

## Scoring weight adjustments

| Dimension | Base weight | Financial weight | Rationale |
|---|---|---|---|
| Compliance and data sovereignty | 25% | **35%** | SOX, PCI-DSS, GLBA, and state money transmitter laws create hard placement constraints |
| Latency and performance tolerance | 20% | **25%** | Trading and payment processing latency requirements can be architectural constraints |
| Cost gravity | 25% | **15%** | Cost matters but cannot override compliance or trading latency requirements |
| Vendor lock-in and licensing risk | 15% | **15%** | Unchanged |
| Private AI infrastructure fit | 15% | **10%** | Lower weight unless AI is being applied to trading or customer data at volume |

---

## Module-specific questions

### Module 1 — Workload placement

- Does this workload process cardholder data (PCI-DSS scope)?
- Is this workload subject to SOX financial reporting controls?
- Does this workload involve trading, market data, or payment processing with latency requirements?
- Is the data subject to customer financial data protection under GLBA?
- Does this workload involve customer PII subject to state financial privacy laws?

### Module 2 — Repatriation readiness

- Has the cloud provider demonstrated compliance with applicable financial regulations for the relevant jurisdiction?
- Does the cloud vendor have a FedRAMP or financial-services-specific compliance certification if required?
- Have regulatory notifications to examiners (OCC, Federal Reserve, FDIC, NCUA as applicable) been considered for significant infrastructure changes?

### Module 4 — Cyber resilience

- Does the third-party risk scorecard address third-party service providers under GLBA Safeguards Rule requirements?
- Does the breach notification guide address the GLBA 30-day notification requirement?
- Does the breach notification guide address PCI-DSS immediate card brand notification requirements?
- Has the cyber resilience assessment addressed payment system recovery priorities specifically?

### Module 8 — BCDR

- Does the BCP address regulatory reporting requirements during a continuity event?
- Are RTO/RPO targets aligned with examination guidance from applicable regulators?
- Has the ransomware playbook been reviewed against FS-ISAC guidance?

---

## Key regulations

| Regulation | Scope | Impact |
|---|---|---|
| SOX (Sarbanes-Oxley) | Public companies — financial reporting integrity | IT controls over financial reporting systems must be documented, tested, and audited |
| PCI-DSS | All organisations processing card payments | Cardholder data environment must meet PCI controls; cloud placement must be within PCI scope |
| GLBA Safeguards Rule | Financial institutions under FTC jurisdiction | Customer financial data protection; 30-day breach notification |
| Bank Secrecy Act / AML | Banks and money services businesses | Transaction data retention and monitoring requirements |
| FFIEC guidance | Federally regulated financial institutions | IT examination guidance; risk management expectations |
| Texas Finance Code | Texas-chartered financial institutions | State-level requirements in addition to federal |

---

*Infrastructure Placement Framework · Financial Services Sector Variant · 4th and Bailey · v1.0.0*
*4thandbailey.com · (888) 305-5977 · Houston, TX*
