# Module 7 — Dual-Stack Rationalisation Guide

**For organizations running both Microsoft 365 and Google Workspace**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Why dual-stack happens

64% of organizations run both M365 and Google Workspace (Flexera 2025). The most common causes:

- Acquisition or merger where the acquired company used the other platform
- Department-specific preference (Engineering prefers Google; Finance requires M365)
- Generational divide in IT teams
- Failed migration leaving a "shadow" deployment of the previous platform
- Specific capability gap met by one platform (e.g., Google Meet quality preferred for external calls; M365 required for Office document workflows)

Dual-stack is not automatically wrong. Ungoverned, unplanned dual-stack is expensive and creates data governance gaps.

---

## Section 1 — Current dual-stack assessment

| Platform | User count | Dept/function | Primary use case | Monthly cost | Justified? |
|---|---|---|---|---|---|
| M365 | | | | | Yes / No |
| Google Workspace | | | | | Yes / No |

**Total combined annual spend:** $ _______________

---

## Section 2 — Rationalisation options

| Option | Description | When appropriate |
|---|---|---|
| Consolidate to M365 | Migrate all Google users to M365; wind down Workspace | M365 is primary; Google deployment is small or legacy |
| Consolidate to Google Workspace | Migrate all M365 users to Workspace; wind down M365 | Google is primary; M365 use is limited to Office file compatibility |
| Maintain dual-stack with governance | Define clear use case allocation; govern both platforms | Genuine departmental or use-case differences justify both |
| Reduce scope of secondary platform | Keep secondary platform for specific use cases only (e.g., Google Meet for external calls only) | Primary platform covers most needs; secondary fills a specific gap |

**Recommended option for this organization:** _______________________________________________

**Rationale:** _______________________________________________

---

## Section 3 — Consolidation planning (if consolidating)

| Phase | Activity | Owner | Timeline |
|---|---|---|---|
| 1 — Inventory | Identify all data, groups, and integrations on the platform being retired | | |
| 2 — Migration planning | Map source to target; identify data requiring special handling | | |
| 3 — Communication | Notify affected users; training and change management | | |
| 4 — Migration execution | Wave-based migration; verify each wave before proceeding | | |
| 5 — Cutover | DNS/routing changes; decommission source platform | | |
| 6 — Validation | Confirm all data migrated; old platform access terminated | | |

---

*Infrastructure Placement Framework · Module 7 Dual-Stack Rationalisation · 4th and Bailey · v1.0.0*
