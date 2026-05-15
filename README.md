# Infrastructure Placement Framework

> **The right technology, in the right environment, governed the right way.**

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-CC--BY--4.0-green)
![Maintained](https://img.shields.io/badge/maintained-yes-brightgreen)
![Issues](https://img.shields.io/github/issues/4thandBailey/infrastructure-placement-framework)
![Stars](https://img.shields.io/github/stars/4thandBailey/infrastructure-placement-framework)

A vendor-neutral, open-source enterprise IT framework for cloud migration, cloud repatriation, workload placement, cybersecurity resilience, AI governance, BYOD strategy, and collaboration platform decisions. Built and maintained by [4th and Bailey](https://4thandbailey.com) — Houston, TX.

---

## What this framework solves

**Infrastructure pressure.** Cloud costs are rising. 86% of CIOs planned to repatriate at least some workloads back on-premises in 2025 (Barclays CIO Survey). The question is no longer "should we go to cloud?" — it is "which workload belongs in which environment, and how do we prove that decision was the right one?" Most organisations are navigating this without a structured methodology, making placement decisions workload by workload without a unifying scoring model.

**Security pressure.** The CrowdStrike outage of July 2024 demonstrated that a single routine vendor update can take down 8.5 million systems globally and cause over $10 billion in damage — without a single malicious actor involved. The organisations that recovered fastest had answers to three questions before the crisis: how do we protect our data, how do we keep operating if a vendor goes offline, and how do we exit a platform that stops serving us? Most did not.

**Governance pressure.** AI is now embedded in virtually every productivity tool, every cloud platform, and every personal device employees carry. Most organisations have no policy, no inventory, and no idea what data has already entered public AI systems through employee usage. The regulatory environment — driven by NIST AI RMF 1.0, NIST AI 600-1, and NIST IR 8596 — is catching up faster than most organisations are moving.

This framework addresses all three pressures through eight interconnected modules. It is built for organisations that have outgrown commodity IT and need structured, vendor-neutral guidance to make infrastructure decisions that hold up under financial, regulatory, and operational scrutiny.

---

## The eight modules

| Module | Name | Core question | Key outputs |
|---|---|---|---|
| 01 | Workload placement assessment | Which environment earns each workload? | Placement recommendation, Architecture Decision Record |
| 02 | Cloud repatriation readiness | Are you ready to repatriate? | Readiness score, migration sequence, risk register |
| 03 | Hybrid estate optimisation | Is your hybrid estate optimised? | Optimisation report, cost reduction register, governance roadmap |
| 04 | Cyber resilience and business continuity | Can you protect, operate, and exit? | Data protection assessment, BCP, vendor exit runbooks |
| 05 | AI governance and NIST alignment | Is your AI use defensible and governed? | Shadow AI audit, NIST RMF assessment, acceptable use policy |
| 06 | End-user device and BYOD strategy | Are your devices and policies aligned? | Device model matrix, MDM recommendation, BYOD policy |
| 07 | Collaboration platform strategy | Are you on the right platform, governed correctly? | Platform assessment, governance baseline, licence optimisation |
| 08 | Business continuity and disaster recovery | When something goes wrong, how exactly do you recover? | BCP, DRP, ransomware playbook, tabletop exercise guide |

---

## The three pillars

| Pillar | Modules | Core question |
|---|---|---|
| **Place it right** | 1 – 3 | Which environment earns each workload, and is it optimised? |
| **Protect it fully** | 4 – 5 | Is the data safe, the business resilient, and AI governed? |
| **Run it well** | 6 – 7 | Are people equipped with the right tools on the right devices? |
| **Survive and recover** | 8 | When something goes wrong, exactly how does the business recover? |

---

## Why it matters now

Three statistics define the landscape in 2026:

- **86%** of CIOs planned to repatriate at least some public cloud workloads (Barclays CIO Survey Q4 2024) — most without a structured readiness framework
- **$10 billion+** in damage from the CrowdStrike outage of July 2024 — caused by a trusted vendor's routine update, not a malicious actor
- **64%** of organisations currently run both Microsoft 365 and Google Workspace simultaneously (Flexera 2025) — most without a coherent governance baseline for either

Each of these represents a decision that most organisations are making — or failing to make — without a structured framework. This is that framework.

---

## Who this is for

This framework is designed for:

- **IT Directors and CTOs** making infrastructure placement and platform decisions
- **CIOs and CFOs** evaluating cloud repatriation, FinOps, and total cost of ownership
- **Compliance officers and legal counsel** navigating HIPAA, NIST, SOX, PCI-DSS, and state data residency requirements
- **Security leaders** building cyber resilience programmes after CrowdStrike
- **SMB owners and operators** who need structured AI governance from a standing start
- **IT consultants and advisors** who want a vendor-neutral framework to structure client assessments

---

## Sector variants

Every module ships with scoring weight adjustments and domain-specific questions for the sectors 4th and Bailey serves:

| Sector | Key regulatory and operational considerations |
|---|---|
| Healthcare | HIPAA, EHR migration, clinical data residency, PHI sovereignty, real-time diagnostic latency |
| Legal | Matter management systems, client data sovereignty, bar association compliance, document retention |
| Energy / Oil & Gas | OT/IT convergence, NERC CIP, remote site latency, SCADA systems, field device management |
| Financial services | SOX, PCI-DSS, GLBA, trading latency, data residency, financial data classification |
| Logistics & distribution | Fleet edge compute, warehouse OT, real-time tracking, carrier data, multi-location governance |
| Non-profit & faith-based | Donor data protection, limited IT staff, cost-sensitive platform selection, volunteer device management |
| Property management | Tenant data, multi-location infrastructure, integrated property management systems |
| Education | FERPA, student data protection, mixed device fleets, collaboration platform for staff and students |

See the [`/sectors`](./sectors/) directory for sector-specific variants.

---

## How to use this framework

### Self-assessment
Fork this repository at `github.com/4thandBailey/infrastructure-placement-framework`. Work through the modules relevant to your situation using the assessment guides, decision trees, and scoring templates. No cost, no commitment, no sales call required.

### Guided assessment
Open a GitHub Issue using the [assessment-request template](.github/ISSUE_TEMPLATE/assessment-request.md), or contact 4th and Bailey directly at [4thandbailey.com/contact](https://4thandbailey.com/contact). A no-obligation conversation walks through your specific situation using the framework as a structured starting point. Most guided assessments identify three to five immediately actionable findings.

### Deployment and implementation
4th and Bailey designs, builds, and deploys the infrastructure changes, governance structures, security controls, and policy frameworks the assessment identifies — from cloud migration to MDM deployment to NIST-aligned AI governance programmes.

### Ongoing advisory
Infrastructure decisions are not one-time events. 4th and Bailey provides fractional CIO services, quarterly framework reviews, and continuous advisory as technology landscapes, regulatory requirements, and business needs evolve.

---

## Connection to 4th and Bailey tools

Every PowerShell tool in [`4thandBailey/tools`](https://github.com/4thandBailey/tools) maps to one or more framework modules:

| Tool | Framework module |
|---|---|
| MFA status report | Module 4 (cyber resilience) + Module 7 (collaboration governance) |
| Inactive users report | Module 5 (shadow AI) + Module 7 (licence optimisation) |
| Licence assignment report | Module 3 (FinOps) + Module 7 (SaaS governance) |
| Mailbox statistics | Module 4 (data protection) + Module 7 (platform governance) |
| Group membership report | IAM governance + Module 4 (access control) |

**Six tools in development:**
1. Conditional Access gap audit → Module 4 + Module 7
2. Shadow app / OAuth consent audit → Module 5 (shadow AI)
3. Licence cost optimisation report → Module 3 + Module 7
4. Teams and SharePoint external sharing audit → Module 4 + Module 7
5. Device compliance / Intune MDM enrollment status → Module 6
6. Google Workspace and AWS equivalents → Module 7 (platform-agnostic)

---

## Repository structure

```
infrastructure-placement-framework/
├── README.md
├── METHODOLOGY.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE.md
├── SECURITY.md
├── assets/
│   └── banner.jpg
├── modules/
│   ├── 01-workload-placement/
│   ├── 02-repatriation-readiness/
│   ├── 03-hybrid-optimisation/
│   ├── 04-cyber-resilience/
│   ├── 05-ai-governance/
│   ├── 06-device-byod/
│   ├── 07-collaboration-platform/
│   └── 08-bcdr/
├── sectors/
│   ├── healthcare/
│   ├── legal/
│   ├── energy/
│   ├── financial/
│   └── logistics/
└── templates/
    ├── workload-adr.md
    ├── assessment-request.md
    └── quarterly-review.md
```

---

## About 4th and Bailey

4th and Bailey is an enterprise IT consulting firm headquartered in Houston, TX, serving organisations nationwide. We specialise in Cloud Services, Cybersecurity, Infrastructure Governance, and Technology Strategy for organisations that have outgrown commodity IT.

We serve: Distribution & Wholesale · Education · Energy, Oil & Gas · Financial Institutions · Global Logistics & Carriers · Healthcare · Legal · Manufacturing · Non-Profit & Faith-Based · Professional Services · Property Management · Title Companies · Veterinary & Animal Hospitals

This framework was built because the conversation about where technology belongs, how it is governed, and how organisations stay resilient takes place everywhere — in boardrooms, IT departments, leadership teams, and budget reviews across every industry we serve. That conversation deserves a structured starting point, a documented methodology, and a contact who can help turn the assessment into action.

**[Start a conversation](https://4thandbailey.com/contact)** · **[GitHub](https://github.com/4thandBailey)** · **(888) 305-5977**

2500 CityWest Blvd., Suite #150-165 · Houston, TX 77042

---

## License

Published under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

Free to use and adapt with attribution to 4th and Bailey.
When attributing, use: *"Infrastructure Placement Framework by 4th and Bailey (github.com/4thandBailey/infrastructure-placement-framework), CC BY 4.0"*

---

*Version 1.0.0 · May 2026 · Maintained at github.com/4thandBailey/infrastructure-placement-framework*
