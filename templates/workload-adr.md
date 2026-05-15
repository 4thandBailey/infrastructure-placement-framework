# Architecture Decision Record — Workload Placement

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

*Complete one ADR per workload placement decision. Store alongside the Module 1 assessment.*

---

## ADR metadata

| Field | Value |
|---|---|
| ADR ID | ADR-[YEAR]-[NUMBER] (e.g., ADR-2026-001) |
| Workload name | |
| Decision date | |
| Decision made by | |
| Approved by | |
| Review date | |
| Status | Proposed / Accepted / Superseded |
| Supersedes | (ADR ID of prior decision for this workload, if applicable) |

---

## 1. Context

*What triggered this placement decision? What is the business or technical situation that requires a documented choice?*

_______________________________________________

**Current placement:** _______________________________________________

**Trigger for this assessment:**
- [ ] New workload — first placement decision
- [ ] Existing workload — periodic review
- [ ] Existing workload — triggered by cost change
- [ ] Existing workload — triggered by compliance change
- [ ] Existing workload — triggered by vendor change (VMware/Broadcom, etc.)
- [ ] Existing workload — triggered by security incident or risk finding
- [ ] Other: _______________________________________________

---

## 2. Options considered

*List all placement options that were seriously considered, not just the one chosen. Record why each alternative was evaluated and why it was not selected.*

### Option A — [Placement tier]

**Description:** _______________________________________________

**Advantages:**
- 
- 

**Disadvantages:**
- 
- 

---

### Option B — [Placement tier]

**Description:** _______________________________________________

**Advantages:**
- 
- 

**Disadvantages:**
- 
- 

---

### Option C — [If applicable]

_______________________________________________

---

## 3. Decision

**Selected placement:** _______________________________________________

**Selected vendor / platform / environment:** _______________________________________________

---

## 4. Scoring rationale

*Record the Module 1 scores for this workload. This is the evidence base for the decision.*

| Dimension | Weight | Score (1–5) | Weighted score | Rationale for this score |
|---|---|---|---|---|
| Cost gravity | 25% | | | |
| Latency and performance tolerance | 20% | | | |
| Compliance and data sovereignty | 25% | | | |
| Private AI infrastructure fit | 15% | | | |
| Vendor lock-in and licensing risk | 15% | | | |
| **Composite score** | 100% | | | |

**Hard override applied?** Yes / No

If yes, which constraint: _______________________________________________

**Sector weighting applied?** Yes / No

If yes, which sector variant: _______________________________________________

---

## 5. TCO summary

*Summarise the 3-year TCO comparison. Full model in `tco-model.xlsx` (Module 2) or attached.*

| Option | 3-year TCO | Key cost drivers |
|---|---|---|
| Cloud (current or proposed) | $ | |
| On-premises / private cloud | $ | |
| **Selected option** | $ | |

---

## 6. Risks and mitigations

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| | Low / Med / High | Low / Med / High | |
| | Low / Med / High | Low / Med / High | |
| | Low / Med / High | Low / Med / High | |

---

## 7. Dependencies and constraints

*What else does this decision depend on? What constraints must be maintained for this decision to remain valid?*

| Dependency / constraint | Current status | Monitoring owner |
|---|---|---|
| | | |
| | | |

---

## 8. Consequences

*What is the effect of this decision? What becomes easier, and what becomes harder?*

**This decision makes the following easier:**
- 

**This decision makes the following harder or requires ongoing attention:**
- 

---

## 9. Review conditions

This ADR is reviewed on the scheduled review date above, OR when any of the following occur:

- [ ] Cloud provider announces significant pricing change (> 15% increase)
- [ ] New compliance requirement affects data placement for this workload
- [ ] Vendor announces End of Life or significant product change
- [ ] Organization's AI workload volume or sensitivity changes significantly
- [ ] Workload characteristics change materially (scale, latency requirement, data sensitivity)

**Review date:** _______________________________________________

**Reviewed by:** _______________________________________________

---

## 10. Sign-off

| Name | Role | Signature | Date |
|---|---|---|---|
| | Decision maker | | |
| | Technical reviewer | | |
| | Business sponsor | | |

---

*Architecture Decision Record Template · Infrastructure Placement Framework by 4th and Bailey*
*(github.com/4thandBailey/infrastructure-placement-framework), CC BY 4.0*
