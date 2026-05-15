# Module 4 — Cyber Resilience and Business Continuity

**Pillar:** Protect it fully · **Framework:** Infrastructure Placement Framework v1.0.0

---

## The question

Does your organisation have documented, tested answers to the three questions every business leader needs answered before a crisis?

---

## The CrowdStrike context

On July 19, 2024, a routine security update from CrowdStrike caused 8.5 million Windows systems to crash globally. The damage exceeded $10 billion. Delta Airlines took five days to recover, losing over $500 million. This was not a cyberattack. It was a trusted vendor making a routine change. No firewall, no antivirus, no password policy would have stopped it.

The organisations that recovered in hours had already answered three questions. Most had not.

---

## The three questions

### Q1 — How do we protect our data?

Most businesses believe their data is protected because they pay for a cloud service. The vendor's responsibility ends at the platform boundary. Your data — how it is backed up, encrypted, versioned, and recoverable — is almost always your responsibility.

### Q2 — How do we keep operating if a vendor goes offline?

Every IaaS, PaaS, and SaaS provider you depend on will experience an outage. The question is whether your organisation has mapped critical functions, defined manual fallbacks, established RTO/RPO targets, and tested them.

### Q3 — How do we move our data if a platform stops serving us?

Vendor lock-in accumulates quietly. Data formats, proprietary APIs, no portability clause — these combine to make exit prohibitively expensive at the moment it becomes necessary.

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

## Connection to other modules

| If this module reveals... | Also review... |
|---|---|
| Data protection gaps in AI workloads | Module 5 — AI governance |
| Device management gaps in continuity | Module 6 — Device and BYOD strategy |
| Platform governance gaps (M365, Workspace) | Module 7 — Collaboration platform |
| Need for full recovery plan and playbooks | Module 8 — BCDR |

---

*Infrastructure Placement Framework · Module 4 · 4th and Bailey · github.com/4thandBailey/infrastructure-placement-framework*
