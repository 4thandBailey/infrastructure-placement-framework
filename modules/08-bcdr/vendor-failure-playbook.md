# Module 8 — Vendor Failure Playbook

**Third-Party Outage and Vendor Failure Response**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

*CrowdStrike-informed. SolarWinds-informed. Built for the era when trusted vendors are the threat vector.*

---

> **Print and store offline.** This playbook must be accessible when vendor-managed systems — including communication and monitoring tools — are unavailable.

---

## Background

The CrowdStrike outage of July 19, 2024 demonstrated that a trusted, widely-deployed security vendor can take down 8.5 million systems globally with a single routine update — without a single malicious actor involved.

The organisations that recovered in hours had this in place before the incident:
- Printed emergency contact lists
- Tested manual operational fallbacks
- Staged update rollout policies preventing simultaneous impact
- A recovery procedure for mass system failure that did not assume working systems

This playbook addresses that scenario and extends it to cover all critical vendor failure modes.

---

## Part 1 — Vendor failure classification

| Failure type | Description | Examples | Response path |
|---|---|---|---|
| **Type A: Update-induced failure** | Vendor update causes system malfunction at scale | CrowdStrike July 2024, bad Windows update | Section 3 |
| **Type B: Vendor outage** | Vendor's service is unavailable (their infrastructure, not yours) | Microsoft 365 outage, AWS region failure | Section 4 |
| **Type C: Vendor security incident** | Vendor is compromised; your data or systems at risk | SolarWinds 2019, supply chain attack | Section 5 |
| **Type D: Vendor insolvency or discontinuation** | Vendor ceases operations or ends the product | Vendor acquired and product EOL'd | Section 6 |

---

## Part 2 — Pre-incident checklist

These items must be in place before a vendor failure occurs:

- [ ] Vendor concentration risk register complete (see Module 4 third-party risk scorecard)
- [ ] Manual fallback procedures documented for all Tier 0 and Tier 1 vendor dependencies
- [ ] Key vendor contacts printed and stored offline
- [ ] Staged update rollout policy in place (see Module 4 CrowdStrike checklist)
- [ ] RTO defined for recovery from each critical vendor failure
- [ ] Vendor exit runbooks completed for all Tier 0 and Tier 1 vendors (see Module 4 vendor exit plan template)

---

## Part 3 — Type A: Update-induced failure response

*(CrowdStrike scenario: trusted vendor update causes mass system failure)*

### Detection

| Indicator | Action |
|---|---|
| Multiple users reporting same system issue simultaneously | Open incident — likely update-induced |
| EDR/security tool alerts firing on all endpoints | Check vendor status page immediately |
| Systems entering boot loop or crashing with same error | Identify the most recent update deployed |
| Help desk tickets spiking with identical symptoms | Escalate to IT Lead immediately |

### Immediate response (first 30 minutes)

| Step | Action | Owner |
|---|---|---|
| 1 | Identify the most recently deployed update across all affected systems | IT Lead |
| 2 | Check vendor status page (use mobile phone if network is affected) | IT |
| 3 | Pause further staged rollout — prevent additional systems from receiving the update | IT |
| 4 | Activate manual fallbacks for any Tier 0 or Tier 1 functions now offline | Operations Lead |
| 5 | Retrieve printed emergency procedures (from offline storage) | IT |
| 6 | Contact vendor emergency support | IT Lead |

### Recovery (CrowdStrike-specific boot loop recovery procedure)

*Adapt this section for the specific vendor and failure mode encountered.*

For Windows systems in boot loop after a security tool update:

1. Boot the affected system in Safe Mode or Windows Recovery Environment (WRE)
2. Navigate to the vendor's agent directory
3. Remove or rename the faulty update file (per vendor's emergency guidance)
4. Reboot normally
5. Verify system functionality before restoring to production

**BitLocker consideration:** If full-disk encryption is enabled, the BitLocker recovery key is required to boot into recovery mode. Recovery keys must be stored outside the affected systems (in a separate system, printed, or in a cloud-based key management tool accessible from a different device).

**BitLocker recovery key location:** _______________________________________________

---

## Part 4 — Type B: Vendor outage response

*(Microsoft 365 outage, AWS region failure, SaaS platform unavailable)*

### Detection and classification

1. Check vendor status page (status.microsoft.com, status.aws.amazon.com, etc.) before escalating
2. Determine affected services and geographic scope
3. Estimate likely duration based on vendor communication

### Response by estimated duration

| Estimated outage duration | Response |
|---|---|
| < 1 hour | Monitor; communicate to affected users; wait for restoration |
| 1–4 hours | Activate manual fallbacks for affected Tier 0/1 functions; communicate timeline |
| > 4 hours | Activate BCP for affected functions; consider alternate platform/tool activation |
| Unknown / no vendor communication | Treat as extended; activate BCP; contact vendor emergency support |

### Manual fallback activation

| System | Fallback procedure | Owner | Activated? |
|---|---|---|---|
| Email (M365/Gmail outage) | SMS/phone for urgent comms; delay non-urgent correspondence | Comms Lead | |
| File access (SharePoint/Drive outage) | Local copies on COPE/managed devices; VPN to on-prem file share | IT | |
| Video conferencing | Alternate platform (Teams → Zoom, or Google Meet → Teams) | IT | |
| ERP / financial (SaaS outage) | Manual processes per Operations runbook | Operations Lead | |

---

## Part 5 — Type C: Vendor security incident response

*(SolarWinds scenario: the vendor's software is the attack vector)*

### The critical distinction

A vendor security incident is fundamentally different from a vendor outage. If the software used to manage your infrastructure has been compromised, **every system that communicated with that software must be treated as potentially compromised until forensically cleared.**

This is not a recovery exercise. This is an incident response exercise that may require rebuilding from scratch.

### Immediate response

| Step | Action | Owner |
|---|---|---|
| 1 | Isolate the affected vendor's software from the network immediately | IT Lead |
| 2 | Do not update, patch, or run the compromised software further | IT Lead |
| 3 | Notify legal counsel and cyber insurance carrier | IC |
| 4 | Engage forensics firm — do not attempt to assess blast radius without expertise | IT Lead + Forensics |
| 5 | Contact law enforcement (FBI IC3) — supply chain attacks often have broader significance | Legal |

### Blast radius assessment

Work with forensics to determine:
- Which systems communicated with the compromised software?
- What access did the compromised software have?
- Is there evidence of active exploitation (data exfiltration, lateral movement, persistence)?
- What is the earliest confirmed clean state (pre-compromise baseline)?

### Recovery approach

Recovery from a supply chain compromise often requires rebuilding affected systems from a trusted, pre-compromise baseline rather than restoring from backup (which may contain the compromised software).

**Trusted baseline location:** _______________________________________________

**Full credential rotation is required** for all accounts that could have been accessed by systems that communicated with the compromised software.

---

## Part 6 — Type D: Vendor insolvency or product discontinuation

*(Vendor acquired, ceases operations, or announces EOL for a critical product)*

### Response timeline

| Timeframe | Action |
|---|---|
| Immediately | Inventory all data stored with the vendor; initiate export |
| Within 30 days | Evaluate replacement options; begin procurement process |
| Before vendor EOL/closure | Complete data migration to replacement; terminate service |

### Data export priority

1. Export all data in open, portable formats immediately
2. Verify export completeness and integrity
3. Store exported data in a known-safe location before vendor closure
4. Do not rely on the vendor to maintain data access past their announced EOL date

---

## Part 7 — Post-incident review

After any vendor failure incident:

- [ ] Timeline of the incident documented
- [ ] Root cause (on vendor side) documented — obtain post-mortem from vendor
- [ ] Recovery time vs. RTO target — did we meet the target? If not, why?
- [ ] Gaps in manual fallback procedures identified and addressed
- [ ] Vendor concentration risk register updated
- [ ] Staged update policy reviewed — was it effective or does it need adjustment?
- [ ] This playbook updated with lessons learned

---

*Infrastructure Placement Framework · Module 8 Vendor Failure Playbook · 4th and Bailey · v1.0.0*
*PRINT AND STORE OFFLINE.*
