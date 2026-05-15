# Module 8 — Tabletop Exercise Guide

**Six scenario scripts for quarterly exercises**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## About tabletop exercises

A tabletop exercise is a facilitated discussion in which the response team walks through a scenario without touching live systems. The goal is not to simulate the technical recovery — it is to test whether the plan works as a human process: who decides, who communicates, who does what, in what order.

**Frequency:** Quarterly minimum. Annual full simulation (live systems) in addition.

**Duration:** 60–90 minutes per scenario. Do not rush.

**Participants:** Crisis Management Team + IT Recovery Team + any role with a responsibility in the plan being tested.

**Facilitator:** An individual not currently responsible for executing the plan (an independent IT leader, advisor, or the plan owner in a facilitation role).

**Rules:**
1. Refer to the actual plan — not to memory or intuition
2. If the plan is missing an answer, that is a finding
3. No one is blamed for gaps; the gaps are in the plan, not the person
4. All findings are documented and fed back into the plan

---

## How to use this guide

Select the scenario most relevant to your current risk profile or rotate through all six annually. Read the scenario injects to the group sequentially. After each inject, allow the group to discuss and document their responses before moving to the next. Record all discussions, decisions, and gaps.

---

## Scenario 1 — Ransomware attack

**Scenario background:** It is 7:45 AM on a Tuesday. Several employees arriving at the office report that their computers show a ransom note. The IT helpdesk is receiving multiple calls about screens showing the same message. The network file server appears to be encrypted.

---

**Inject 1.1 — First 15 minutes**

*"The ransom note has appeared on approximately 30 workstations and the file server. Email appears to be working. You don't yet know if domain controllers are affected."*

Discussion questions:
- Who is notified first, and how?
- Who has authority to declare this a ransomware incident?
- What is the first technical action IT takes?
- What do you tell employees to do right now?

---

**Inject 1.2 — 45 minutes in**

*"IT has confirmed domain controllers are not encrypted but have been communicating with infected workstations. The entry point appears to be a phishing email opened yesterday. Your forensics firm estimates the ransomware has been dormant for 3 days before encrypting."*

Discussion questions:
- Does the 3-day dormancy period affect which backups you can use? (Check your most recent backup date)
- Do you have a backup that predates the dormancy window?
- Who from your team contacts the forensics firm?
- What communication goes to staff and when?

---

**Inject 1.3 — 3 hours in**

*"The ransomware group has posted that they exfiltrated data before encrypting. They are threatening to publish customer data in 72 hours if ransom is not paid. Your cyber insurance carrier is on the phone."*

Discussion questions:
- Who holds authority to make the ransom payment decision?
- What is your legal counsel's role at this point?
- Which regulatory notifications may be triggered?
- What is your customer communication plan?
- Does your cyber insurance policy cover ransom payment?

**Findings from Scenario 1:** _______________________________________________

---

## Scenario 2 — Data breach and exfiltration

**Scenario background:** Your IT security monitoring alert (or a third-party notification) indicates that a large volume of data was transferred out of your environment to an external IP address over the past 48 hours. The data includes customer records from your CRM.

---

**Inject 2.1 — Discovery**

*"Initial analysis shows approximately 15,000 customer records including names, email addresses, and phone numbers were exfiltrated. It appears to have come through a compromised admin credential."*

Discussion questions:
- Who is the first person notified, and through what channel?
- Which regulations require notification based on this data type?
- What is the regulatory notification deadline?
- Is legal counsel engaged before any notifications are sent?

---

**Inject 2.2 — Scope expansion**

*"Further analysis reveals the compromised account also had access to a file share containing contracts. Some contracts include Social Security numbers for background check records."*

Discussion questions:
- Does the inclusion of SSNs change the notification requirements?
- How does Texas HB 3834 apply here?
- Do any other state notification laws apply to your customers?
- Who drafts the notification and who approves it before it is sent?
- Is your notification template ready? (Locate it now — do not describe where it is; retrieve it.)

**Findings from Scenario 2:** _______________________________________________

---

## Scenario 3 — Third-party vendor failure

**Scenario background:** It is 6:30 AM. Your monitoring shows that 80% of your Windows endpoints are in a boot loop. The issue began approximately 20 minutes ago. Social media reports indicate it is a global issue affecting a major security vendor.

*(This is the CrowdStrike scenario.)*

---

**Inject 3.1 — Mass failure**

*"Confirmed: a security vendor update is causing boot loops. Approximately 120 of your 150 Windows endpoints and 4 servers are affected. Domain controllers are functional. Your staged rollout policy did or did not prevent some systems from being affected — how many systems are you working with?"*

Discussion questions:
- Does your staged rollout policy exist? How many systems are in each ring?
- What is the recovery procedure for a Windows boot loop? (Retrieve the printed procedure now.)
- Where are your BitLocker recovery keys stored?
- What manual fallbacks are in place for staff who cannot work?
- Who communicates to staff and customers?

---

**Inject 3.2 — Extended outage**

*"The vendor has released a fix, but applying it requires manual intervention on each affected system — there is no automated recovery path. You have 2 IT staff available. With 120 affected systems, full recovery will take 14–18 hours."*

Discussion questions:
- What is your prioritisation order for recovery? (Identify the Tier 0 and Tier 1 servers first)
- How do you communicate expected recovery times to leadership and staff?
- Do you have external IT support available to accelerate recovery?
- What customer-facing services can you maintain manually during the outage?

**Findings from Scenario 3:** _______________________________________________

---

## Scenario 4 — Natural disaster / physical infrastructure loss

**Scenario background:** A major hurricane has made landfall in the Houston area. Your primary office is inaccessible and has no power. The building may have sustained water damage. All on-premises infrastructure is offline.

*(This is not a theoretical scenario for Houston-area organisations.)*

---

**Inject 4.1 — Day 1**

*"The office will be inaccessible for at least 5 days. Power restoration is estimated at 3–7 days. Staff are physically safe and working from home or alternate locations. Your cloud-based services (M365/Google Workspace) are operational."*

Discussion questions:
- Which systems are cloud-based and operational right now?
- Which systems are on-premises and offline?
- Do staff have the devices and VPN access to work remotely?
- Is your backup data stored offsite and accessible?
- Who is the decision-maker for all recovery actions during the outage?

---

**Inject 4.2 — Day 3**

*"Your on-premises server room has sustained water damage. The hardware is likely a total loss. Your most recent offsite backup is 48 hours old."*

Discussion questions:
- What is the process for procuring replacement hardware? Do you have emergency vendor agreements?
- What is the estimated recovery time given the hardware lead time?
- What is the data loss represented by a 48-hour RPO? Is this acceptable to the business?
- Does your business continuity plan address alternate physical locations?
- How do you maintain customer-facing services during an extended outage?

**Findings from Scenario 4:** _______________________________________________

---

## Scenario 5 — Insider threat / accidental data loss

**Scenario background:** A departing employee submitted their resignation last week. This morning, you discover that their M365 account was used last night to download 2,000 files from SharePoint to a personal OneDrive account before the account was disabled.

---

**Inject 5.1 — Discovery**

*"The files include client contracts and financial reports. The employee has already left the building. Their account is now disabled. You do not know if the files have been shared externally."*

Discussion questions:
- Can you determine what files were downloaded? (Does your audit logging capture this?)
- Can you remotely wipe corporate data from the personal device if it was a managed device?
- Is there a legal obligation to notify clients whose contracts were taken?
- What is the process for escalating to legal and HR?

---

**Inject 5.2 — Accidental deletion**

*Alternative inject — replace 5.1 if preferred:*
*"A system administrator ran an infrastructure-as-code script in the wrong environment. The production SharePoint site for the Finance team has been deleted. 3 months of financial documents are gone."*

Discussion questions:
- What is the restore process for a deleted SharePoint site?
- What is the retention period for SharePoint Recycle Bin and second-stage Recycle Bin?
- Is there a third-party backup for M365 data? Can it restore a full site?
- What is the RPO for this data? How much, if any, is unrecoverable?
- Who notifies the Finance team and what do you tell them?

**Findings from Scenario 5:** _______________________________________________

---

## Scenario 6 — Supply chain compromise

**Scenario background:** A cybersecurity firm has published a report that RMMTool (a widely-used remote monitoring and management tool similar to SolarWinds), which is used by your IT managed service provider to manage your infrastructure, has been compromised. The compromise has been ongoing for 4 months.

---

**Inject 6.1 — Initial notification**

*"Your MSP has notified you that their management tool has been compromised. All clients of the MSP, including your organisation, should assume their infrastructure has been exposed to the attacker."*

Discussion questions:
- What is your first action when you receive this notification?
- Who is involved in the decision about the scope of the response?
- Do you engage your own forensics firm independent of the MSP?

---

**Inject 6.2 — Blast radius assessment**

*"Forensics has confirmed the compromised tool had admin-level access to your domain controllers, file servers, and email platform for the past 4 months. You must assume all credentials are compromised."*

Discussion questions:
- What is the full scope of credential rotation required?
- Which systems must be rebuilt from a trusted baseline vs. which can be restored from backup?
- What is the earliest clean backup that predates the 4-month compromise window?
- What customer notifications are required?
- How do you communicate this to your board?

**Findings from Scenario 6:** _______________________________________________

---

## Post-exercise documentation

After each exercise, document the following:

**Exercise date:** _______________________

**Scenario(s) covered:** _______________________

**Participants:** _______________________

**Facilitator:** _______________________

### Findings summary

| Finding | Severity | Plan section affected | Remediation action | Owner | Target date |
|---|---|---|---|---|---|
| | Critical / High / Med / Low | | | | |
| | | | | | |

### What worked well

_______________________________________________

### Plan updates required

| Section | Current text | Updated text | Updated by | Date |
|---|---|---|---|---|
| | | | | |

**Plan version after this exercise:** _______________________

---

*Infrastructure Placement Framework · Module 8 Tabletop Exercise Guide · 4th and Bailey · v1.0.0*
*github.com/4thandBailey/infrastructure-placement-framework*
