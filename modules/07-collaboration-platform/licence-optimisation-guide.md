# Module 7 — License Optimization Guide

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Context

29% of SaaS licenses in the average organization are unused or underutilized (Flexera 2025). For a 200-person organization paying $22/user/month for M365 Business Premium, that is approximately $15,000 in annual waste. At enterprise scale, the number is significantly higher.

License optimization is not about cutting corners — it is about paying for what is used and assigning the right plan tier to each role.

---

## Section 1 — License utilisation audit

### Microsoft 365

Run the license assignment report from the M365 admin centre or using the PowerShell tool at [github.com/4thandBailey/tools](https://github.com/4thandBailey/tools).

| License type | Assigned | Active (last 30 days) | Inactive | Unassigned | Action |
|---|---|---|---|---|---|
| M365 Business Basic | | | | | |
| M365 Business Standard | | | | | |
| M365 Business Premium | | | | | |
| M365 E3 | | | | | |
| M365 E5 | | | | | |
| Microsoft 365 Copilot | | | | | |
| Other add-ons | | | | | |

**Reclamation opportunity:** _____ inactive licenses × $___/month = $___/month savings

### Google Workspace

| License type | Assigned | Active (last 30 days) | Inactive | Action |
|---|---|---|---|---|
| Workspace Business Starter | | | | |
| Workspace Business Standard | | | | |
| Workspace Business Plus | | | | |
| Workspace Enterprise | | | | |
| Gemini add-on | | | | |

**Reclamation opportunity:** _____ inactive licenses × $___/month = $___/month savings

---

## Section 2 — Right-sizing assessment

Not everyone needs the highest tier. Review whether users' actual usage justifies their current license tier.

| Role category | Current plan | Features actually used | Recommended plan | Saving per user |
|---|---|---|---|---|
| Executive | | | | |
| Power user (finance, legal, IT) | | | | |
| General knowledge worker | | | | |
| Frontline / field worker | | | | |
| Contractor (limited access) | | | | |

---

## Section 3 — Total optimization register

| Category | Users | Monthly saving per user | Annual saving |
|---|---|---|---|
| Inactive license reclamation | | | |
| Right-sizing to lower tier | | | |
| Duplicate platform elimination | | | |
| Unused add-on removal | | | |
| **Total estimated annual saving** | | | |

---

## Section 4 — Review cadence

| Review | Frequency | Method |
|---|---|---|
| Inactive user license audit | Monthly | PowerShell report or admin centre |
| License tier right-sizing review | Quarterly | Role-by-role review |
| Full license optimization | Annually | Complete this guide |

---

*Infrastructure Placement Framework · Module 7 License Optimization Guide · 4th and Bailey · v1.0.0*
*See also: github.com/4thandBailey/tools for PowerShell license reporting scripts*
