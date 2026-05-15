# Module 4 — Cyber Resilience and Business Continuity

**Pillar:** Protect it fully · **Framework:** Infrastructure Placement Framework v1.0.0

---

## The question

Does your organization have documented, tested answers to the three questions every business leader needs answered before a crisis?

---

## Why this module exists

On July 19, 2024, a routine security update from CrowdStrike caused 8.5 million Windows systems to crash globally. The damage exceeded $10 billion. Delta Airlines took five days to recover, losing over $500 million. This was not a cyberattack. It was a trusted vendor making a routine change. No firewall, no antivirus, no password policy would have stopped it.

In February 2026, a ransomware attack on the University of Mississippi Medical Center forced the closure of all 35 clinic locations statewide, took the Epic electronic health records system offline, and canceled surgeries, chemotherapy appointments, and outpatient procedures across the state. Clinicians reverted to pen-and-paper documentation. The FBI surged resources on-site. The medical center remained in partial shutdown for nine days.

These two events share a common thread: the organizations affected were not unprepared because they lacked technology. They were unprepared because they had not defined and ranked which systems carried the highest risk — and had not documented, tested answers to three questions every business leader needs answered before a crisis begins.

The question is no longer whether an attack or outage will occur. It is whether your organization has answered those three questions in advance.

---

## The two questions every organization must be able to answer

Before any assessment begins, two diagnostic questions establish the baseline:

**How would you know whether or not your organization had been impacted by a cyber attack?**

Most organizations discover an incident through a user complaint, a ransom note on a screen, or an external notification — not through their own detection capability. The answer to this question reveals whether monitoring, alerting, and detection are in place, or whether the organization is flying blind.

**What is your organization's incident response plan in the event of a cyber attack?**

A plan that exists on paper but has never been tested is not a plan. The answer to this question reveals whether roles are assigned, playbooks exist, and the team has rehearsed — or whether the response will be improvised under pressure.

Organisations that cannot answer both questions clearly are, by definition, unprepared. This module builds the framework to change that.

---

## The three questions that define cyber resilience

### Q1 — How do we protect our data?

Most businesses believe their data is protected because they pay for a cloud service. The vendor's responsibility ends at the platform boundary. Your data — how it is backed up, encrypted, versioned, and recoverable — is almost always your responsibility, regardless of what the contract implies.

The UMMC attack illustrates this precisely: a healthcare system running Epic — one of the most widely deployed EHR platforms in the country — lost access to every patient record in the system when the network went down. The platform worked. The data protection architecture did not.

### Q2 — How do we keep operating if a vendor goes offline?

Every IaaS, PaaS, and SaaS provider your organization depends on will experience an outage. The question is whether your organization has mapped critical functions, defined manual fallbacks, established RTO and RPO targets per system, and tested those targets. UMMC hospitals kept emergency departments running using downtime procedures because those procedures existed. Outpatient clinics closed for nine days because theirs were insufficient for a multi-day outage.

Only 22% of healthcare organizations fully recovered from a ransomware attack in less than a week. Nearly 40% took more than a month (Sophos, 2024). Recovery speed correlates directly with the quality of preparation — not the size of the organization.

### Q3 — How do we move our data if a platform stops serving us?

Vendor lock-in accumulates quietly. Data formats that only one platform reads, integrations built on proprietary APIs, contracts with no portability clause — these combine to make exit prohibitively expensive at the moment it becomes necessary. This module produces an exit runbook for every mission-critical system before that moment arrives.

---

## The five components of organizational cyber resilience

Answering the three questions above requires five foundational capabilities to be in place:

**1. Risk definition and ranking.** Not every system carries the same risk. Cyber resilience begins with identifying which systems, if compromised or unavailable, would cause the greatest harm — to operations, to patients or customers, to regulatory standing, and to the organization's survival. Without this ranking, every system is treated as equally important, which means none are protected adequately.

**2. Data protection architecture.** Backup coverage, encryption at rest and in transit, recovery testing, and immutable backup copies that ransomware cannot encrypt or delete. The 3-2-1 rule — three copies, two media types, one offsite — is the minimum. Vault-locked, air-gapped backups are the standard for Tier 0 systems.

**3. Incident detection and response.** Monitoring and alerting that identifies an incident before a ransom note does. A tested incident response plan with assigned roles, pre-drafted communications, and a clear chain of authority — including who holds the authority to make a ransom payment decision.

**4. Operational continuity.** Manual fallback procedures for every critical function, tested regularly, printed and stored offline. The organizations that kept operating during the CrowdStrike outage had printed emergency procedures and practiced manual workflows. Those that did not took days longer to recover.

**5. Vendor governance and exit capability.** Staged update rollout policies that prevent a single vendor change from simultaneously affecting all systems. Concentration risk thresholds. Exit runbooks for every mission-critical platform. Data portability validation — not assumed, but tested.

---

## Files in this module

| File | Purpose |
|---|---|
| `README.md` | This file |
| `data-protection-assessment.md` | Assessment: backups, encryption, recovery across IaaS/PaaS/SaaS |
| `business-continuity-assessment.md` | Assessment: operations continuity, RTO/RPO, manual fallbacks |
| `vendor-exit-plan-template.md` | Template: exit runbook for each mission-critical vendor |
| `crowdstrike-lessons-checklist.md` | Checklist: CrowdStrike-informed vendor update governance controls |
| `third-party-risk-scorecard.md` | Scorecard: vendor dependency and concentration risk |

---

## Output

1. Data protection assessment with gaps identified
2. Business continuity plan framework
3. Vendor exit runbooks for each mission-critical system
4. Third-party risk scorecard surfacing concentration risks
5. CrowdStrike lessons checklist — binary pass/fail for update governance

---

## Sector context

Cyber resilience risk is not evenly distributed. Healthcare organizations are disproportionately targeted because medical records carry high value on criminal markets, operational disruption creates immediate patient safety pressure, and security has historically been underfunded relative to clinical priorities. The UMMC attack was the fourth ransomware attack to hit Mississippi hospital systems since 2023.

Financial services, legal, energy, and logistics organizations face sector-specific risk profiles that require adjusted assessment priorities. See the `/sectors` directory for sector-specific guidance.

---

## Connection to other modules

| If this module reveals... | Also review... |
|---|---|
| Data protection gaps in AI workloads | Module 5 — AI governance |
| Device management gaps in continuity | Module 6 — Device and BYOD strategy |
| Platform governance gaps (M365, Workspace) | Module 7 — Collaboration platform |
| Need for full recovery plan and playbooks | Module 8 — BCDR |

---

*Infrastructure Placement Framework · Module 4 · 4th and Bailey · github.com/4thandBailey/infrastructure-placement-framework*
