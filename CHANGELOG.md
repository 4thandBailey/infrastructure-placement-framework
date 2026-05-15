# Changelog

All notable changes to the Infrastructure Placement Framework are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/).

---

## [Unreleased]

---

## [1.0.0] — 2026-05-15

### Added

- **Module 1:** Workload placement assessment — five-dimension scoring model (cost gravity, latency tolerance, compliance/data sovereignty, private AI infrastructure fit, vendor lock-in/licensing risk). Output: per-workload placement recommendation with Architecture Decision Record.
- **Module 2:** Cloud repatriation readiness — 3-year TCO comparison model, VMware/Broadcom licensing exposure assessment, team skills gap evaluation, hyperscaler dependency mapping, repatriation sequencing guidance. Output: readiness score, prioritised migration sequence, risk register.
- **Module 3:** Hybrid estate optimisation — workload placement audit, cloud cost anomaly detection, FinOps governance establishment, governance gap assessment, quarterly review cadence. Output: optimisation report, cost reduction register, governance roadmap.
- **Module 4:** Cyber resilience and business continuity — CrowdStrike-informed three-question framework (protect data / keep operating / exit platform), data protection assessment across IaaS/PaaS/SaaS, vendor exit runbooks, third-party risk scorecard. Output: data protection assessment, BCP, vendor exit runbooks, third-party risk scorecard.
- **Module 5:** AI governance and NIST alignment — shadow AI audit, 90-day SMB AI readiness programme, large enterprise IP protection framework. NIST standards: AI RMF 1.0, AI 600-1 Generative AI Profile (Jul 2024), CSF 2.0, IR 8596 Cyber AI Profile (Dec 2025). Output: shadow AI audit, data classification policy, vendor evaluation rubric, acceptable use policy, NIST RMF scored assessment, standards crosswalk.
- **Module 6:** End-user device and BYOD strategy — four ownership models (BYOD/CYOD/COPE/COBO), MDM/UEM platform selection framework, AI-on-personal-device guidance. Output: device model matrix by role, MDM recommendation, BYOD security policy, containerisation architecture, acceptable use policy, remote wipe scope.
- **Module 7:** Collaboration platform and productivity strategy — platform-agnostic assessment across M365, Google Workspace, and AWS WorkSpaces; governance baseline; licence optimisation framework; AI feature data handling review. Output: platform selection assessment, dual-stack rationalisation plan, governance baseline, licence optimisation report.
- **Module 8:** Business continuity and disaster recovery — five-phase BCDR framework (detect/declare, contain/assess, communicate, recover/restore, review/improve); RTO/RPO tier model; six scenario playbooks (ransomware, data breach, vendor failure, natural disaster, insider threat, supply chain compromise); tabletop exercise guides. Output: BIA, BCP, DRP, ransomware playbook, breach notification guide, vendor failure playbook, backup validation checklist, tabletop exercise guide, BCDR readiness assessment.
- **Sector variants:** Healthcare, Legal, Energy/Oil & Gas, Financial Services, Logistics & Distribution — sector-specific scoring weight adjustments and domain questions.
- **GitHub Issue templates:** Assessment request (warm lead pipeline), framework feedback, sector addition request.
- **Templates:** Architecture Decision Record, quarterly review, assessment request.
- **Supporting documentation:** METHODOLOGY.md (scoring rationale and weighting logic), CONTRIBUTING.md, LICENSE.md (CC BY 4.0), SECURITY.md.

---

## Planned releases

| Version | Planned content |
|---|---|
| v1.1.0 | Module 8 full document set: backup validation checklist, tabletop exercise scripts for all six scenarios, BCDR readiness assessment scoring |
| v1.2.0 | Non-profit/faith-based and education sector variants |
| v1.3.0 | Property management and logistics sector variants |
| v1.4.0 | Google Workspace and AWS tools equivalents in tools repo; framework cross-links updated |
| v2.0.0 | Major revision incorporating updated NIST standards, new market data, expanded sector coverage |

---

*Infrastructure Placement Framework · Maintained at github.com/4thandBailey/infrastructure-placement-framework*
