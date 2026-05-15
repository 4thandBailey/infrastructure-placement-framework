# Business Continuity Plan

**[ORGANISATION NAME]**

*Template · Complete all sections · Requires annual review and leadership sign-off*

**Version:** _______  |  **Effective date:** _______  |  **Review date:** _______

**Plan owner:** _______________________  |  **Approved by:** _______________________

---

> **This document is CONFIDENTIAL.**
> It describes operational recovery priorities and dependencies. Distribute only to personnel with a role in plan execution. Store a printed copy offline — this document must be accessible if digital systems are unavailable.

---

## 1. Plan purpose and scope

### 1.1 Purpose

This Business Continuity Plan (BCP) defines how [ORGANISATION NAME] maintains or rapidly restores essential business functions during and after any significant disruption. It covers people, processes, communications, alternate work arrangements, and the manual workarounds required to keep the organization operating regardless of the nature of the disruption.

This BCP is distinct from the Disaster Recovery Plan (DRP), which addresses IT system and data restoration. The DRP is a component of this plan, not a replacement for it.

### 1.2 Scope

This plan covers all essential business functions of [ORGANISATION NAME] and applies to all employees, contractors, and key vendors involved in continuity operations.

**Locations in scope:**
- Primary location: _______________________________________________
- Secondary/alternate location: _______________________________________________

### 1.3 Plan activation criteria

This plan is activated when any of the following occur:

| Trigger | Authority to activate |
|---|---|
| Ransomware or cyberattack affecting critical systems | ___________________________ |
| Data breach involving regulated data | ___________________________ |
| Extended vendor outage (> ___ hours) affecting critical functions | ___________________________ |
| Natural disaster affecting primary location | ___________________________ |
| Loss of key personnel affecting critical functions | ___________________________ |
| Any event preventing normal operations for > ___ hours | ___________________________ |

---

## 2. Continuity team

### 2.1 Crisis management team

| Role | Name | Primary contact | Backup contact | Authority |
|---|---|---|---|---|
| Incident Commander | | | | Activate plan, make all continuity decisions |
| Deputy Incident Commander | | | | Act for IC when unavailable |
| IT Lead | | | | Systems, data, vendor coordination |
| Communications Lead | | | | Internal and external communications |
| Operations Lead | | | | Business function continuity |
| HR Lead | | | | People, safety, alternate staffing |
| Finance Lead | | | | Financial approvals, insurance, payments |
| Legal Counsel | | | | Regulatory, notification, liability |

### 2.2 External contacts (print and store offline)

| Contact | Organization | Phone | Notes |
|---|---|---|---|
| Cyber insurance carrier | | | Policy #: _______ |
| Legal counsel | | | Data breach specialization |
| IT forensics firm | | | On retainer: Yes / No |
| Primary IT vendor | | | |
| Backup/DR vendor | | | |
| Internet/connectivity provider | | | Account #: _______ |
| Facility management | | | |
| FBI Cyber Division (Houston) | FBI | (713) 693-5000 | Report to ic3.gov |

---

## 3. Critical business functions

*Derived from Business Impact Analysis. See `business-impact-analysis.md` for full detail.*

### 3.1 Tier 0 — Must be operational within 1 hour

| Function | Owner | System dependency | Manual fallback | Fallback owner |
|---|---|---|---|---|
| | | | | |
| | | | | |

### 3.2 Tier 1 — Must be operational within 4 hours

| Function | Owner | System dependency | Manual fallback | Fallback owner |
|---|---|---|---|---|
| | | | | |
| | | | | |

### 3.3 Tier 2 — Must be operational within 24 hours

| Function | Owner | System dependency | Manual fallback | Fallback owner |
|---|---|---|---|---|
| | | | | |
| | | | | |

---

## 4. The five phases

### Phase 1 — Detect and declare

**Detection:** Any employee who identifies a potential continuity-level event should immediately notify:

Primary: ___________________________ at ___________________________

Backup: ___________________________ at ___________________________

**Declaration criteria:** [Define the specific conditions that trigger plan activation — see Section 1.3]

**Declaration actions:**
1. Incident Commander declared — notifies all Crisis Management Team members
2. Situation assessment call convened within 30 minutes (use personal mobile phones if primary comms are affected)
3. This plan retrieved and activated
4. Incident log started — record all actions with timestamps

---

### Phase 2 — Contain and assess

**Immediate containment priorities (first 2 hours):**

| Priority | Action | Owner |
|---|---|---|
| 1 | Stop the spread — isolate affected systems, accounts, or locations | IT Lead |
| 2 | Preserve evidence — do not alter affected systems before forensic capture | IT Lead / Forensics |
| 3 | Determine blast radius — what is affected, what is not | IT Lead |
| 4 | Assess life safety — is anyone at physical risk? | Incident Commander |
| 5 | Activate manual fallbacks for any disrupted Tier 0 functions | Operations Lead |

**Blast radius assessment template:**

| Area | Affected? | Severity | Action taken |
|---|---|---|---|
| IT systems | Yes / No / Partial | Critical / High / Med / Low | |
| People / access | Yes / No / Partial | Critical / High / Med / Low | |
| Physical location | Yes / No / Partial | Critical / High / Med / Low | |
| Customer-facing services | Yes / No / Partial | Critical / High / Med / Low | |
| Vendor/partner dependencies | Yes / No / Partial | Critical / High / Med / Low | |

---

### Phase 3 — Communicate

**Communication sequence — do not deviate without Incident Commander approval:**

| Recipient | When | Channel | Owner | Template |
|---|---|---|---|---|
| Crisis Management Team | Immediately | Phone/SMS (if primary systems affected) | IC | |
| All staff | Within 2 hours | Email + SMS + phone tree | Comms Lead | See Appendix A |
| Board / executive leadership | Within 2 hours | Phone | IC | |
| Customers (if service affected) | Per legal guidance | Email / web / phone | Comms Lead | See Appendix B |
| Cyber insurance carrier | Within 24 hours | Phone + written | Finance Lead | |
| Legal counsel | Within 2 hours (any data incident) | Phone | IC | |
| Regulators | Per notification timelines in BIA | Written | Legal | See breach-notification-guide.md |
| Media | Only if required — per legal guidance only | Written statement | IC + Legal | |

**Critical rule:** All external communications about the incident must be approved by Legal before sending.

---

### Phase 4 — Recover and restore

**Recovery is executed in tier order. Tier 0 must be restored and validated before Tier 1 begins.**

Refer to the Disaster Recovery Plan (`drp-template.md`) for the technical restoration sequence.

**Business function restoration sequence:**

| Step | Function | Owner | RTO target | Completed |
|---|---|---|---|---|
| 1 | Confirm Tier 0 IT systems operational (from DRP) | IT Lead | < 1 hour | |
| 2 | Restore Tier 0 business functions | Operations Lead | < 1 hour | |
| 3 | Confirm Tier 1 IT systems operational (from DRP) | IT Lead | < 4 hours | |
| 4 | Restore Tier 1 business functions | Operations Lead | < 4 hours | |
| 5 | Confirm Tier 2 IT systems operational | IT Lead | < 24 hours | |
| 6 | Restore Tier 2 business functions | Operations Lead | < 24 hours | |
| 7 | Normal operations declared | IC | | |

---

### Phase 5 — Review and improve

Within 14 days of incident closure:

- [ ] Post-incident review meeting held — all Crisis Management Team members
- [ ] Root cause documented
- [ ] Timeline of events reconstructed
- [ ] What worked well documented
- [ ] What failed or was slower than expected documented
- [ ] Action items assigned to owners with target dates
- [ ] This BCP updated with lessons learned
- [ ] Regulatory notifications confirmed complete
- [ ] Insurance claim filed and confirmed
- [ ] Plan version incremented and re-approved

---

## 5. Alternate work arrangements

If the primary location is unavailable:

| Scenario | Alternate arrangement | Location | Who activates |
|---|---|---|---|
| Primary office inaccessible | Remote work — all staff | Home / VPN | HR Lead |
| Extended primary outage (> 3 days) | Alternate office location | ___________________________ | IC |
| IT systems inaccessible | Manual fallback procedures | See Section 3 | Operations Lead |

---

## 6. Plan maintenance

| Activity | Frequency | Owner |
|---|---|---|
| Annual full review and re-approval | Annually | Plan Owner |
| Post-incident update | After every activation | Plan Owner |
| Contact information verification | Quarterly | HR Lead |
| Tabletop exercise | Quarterly | IT Lead |
| Component recovery test | Semi-annually | IT Lead |
| Full simulation | Annually | IT Lead |

---

## Appendix A — Internal staff communication template

**Subject:** [ORGANISATION NAME] — Service disruption notice

Team,

We are experiencing [brief description of issue]. Our business continuity plan has been activated and our team is working to restore normal operations.

[What is affected and to what extent.]

[What staff should do / what manual processes are in effect.]

Estimated restoration time: [RTO target or "we will update you at HH:MM"]

Your manager will be in contact if your specific role is impacted. Questions: [contact].

[IC Name]

---

## Appendix B — Customer communication template

**Subject:** [SERVICE NAME] — Service update

Dear [Customer],

We want to inform you that [ORGANISATION NAME] is currently experiencing [brief, non-technical description of issue].

[What services are affected.]

[What you are doing about it.]

[When you expect to restore normal service, or next update time.]

We apologise for any inconvenience and are committed to keeping you informed.

[Contact for questions.]

---

*[ORGANISATION NAME] Business Continuity Plan · Template adapted from Infrastructure Placement Framework by 4th and Bailey (github.com/4thandBailey/infrastructure-placement-framework), CC BY 4.0*
*Version _______ · Approved by _______ · Date _______*
