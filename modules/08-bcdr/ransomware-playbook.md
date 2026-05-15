# Module 8 — Ransomware Response Playbook

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

*This playbook must be printed and stored physically. If ransomware is active, digital copies on the network may be encrypted or unavailable.*

**PRINT AND STORE OFFLINE.**

---

**Organization:** _______________________________________________

**Incident Commander:** _______________________________________________

**Backup Incident Commander:** _______________________________________________

**Last tested:** _______________________________________________

---

## Pre-incident — confirm these are in place before an incident

- [ ] Immutable/vault-locked backups exist for all Tier 0 and Tier 1 systems
- [ ] Backup restore has been tested in the last 30 days
- [ ] Ransom payment decision authority is defined (see Part 6)
- [ ] Cyber insurance policy number: _______________________
- [ ] Cyber insurance claim number (obtain pre-incident): _______________________
- [ ] Legal counsel contact (data breach): _______________________
- [ ] Forensics firm on retainer: _______________________
- [ ] FBI IC3 reporting URL: ic3.gov

---

## PHASE 1 — DETECT AND DECLARE

### Detection indicators

Ransomware may first be identified by:
- [ ] User reports files with unexpected extensions (e.g., .locked, .encrypted)
- [ ] Ransom note appearing on screens or as desktop wallpaper
- [ ] Endpoint detection and response (EDR) alert
- [ ] Backup system alerts showing encrypted files
- [ ] Sudden spike in disk I/O or file system activity
- [ ] Systems becoming unresponsive

### Declare the incident

**Who has authority to declare a ransomware incident:** _______________________________________________

**When to declare:** Ransomware confirmed on more than one system OR on any Tier 0 system.

**Declaration action:** Notify Incident Commander, activate this playbook, convene response team.

---

## PHASE 2 — CONTAIN

**CRITICAL: Do not reboot or shut down affected systems before forensic evidence is preserved.**

Rebooting a live ransomware infection may destroy forensic evidence needed to identify the entry point. Consult your forensics firm before rebooting any affected system.

### Immediate containment steps

| Step | Action | Owner | Time |
|---|---|---|---|
| 1 | Isolate affected systems from the network (physically disconnect ethernet / disable Wi-Fi) | IT | Immediate |
| 2 | Do NOT shut down unless instructed by forensics firm | IT | |
| 3 | Identify blast radius — which systems are confirmed encrypted vs. possibly affected | IT | Within 1 hour |
| 4 | Identify the entry point if possible (phishing email, RDP exposure, vulnerable application) | IT + Forensics | Within 4 hours |
| 5 | Preserve system memory and logs before any reboots | Forensics | Before any reboot |
| 6 | Identify the ransomware variant if possible (ransomware.live, ID Ransomware) | IT | Within 2 hours |
| 7 | Determine if data exfiltration occurred (ransomware groups often exfiltrate before encrypting) | Forensics | Within 24 hours |

### Blast radius assessment

| System | Affected? | Data sensitivity | Regulatory notification triggered? |
|---|---|---|---|
| | Confirmed / Possible / Not affected | | Yes / No / TBD |

---

## PHASE 3 — COMMUNICATE

**Communication sequence — do not skip steps or change the order without legal counsel approval.**

| Recipient | When | Channel | Owner | Template |
|---|---|---|---|---|
| Internal leadership / board | Within 2 hours of declaration | Phone (do not use potentially compromised email) | Incident Commander | |
| Cyber insurance carrier | Within 24 hours (check policy) | Phone then written | Legal/Finance | |
| Legal counsel | Within 2 hours | Phone | Incident Commander | |
| Forensics firm (if on retainer) | Within 2 hours | Phone | IT | |
| Law enforcement (FBI IC3, local) | Recommended within 24 hours | ic3.gov + local FBI field office | Legal | |
| Customers/clients | Per legal guidance — after breach assessment | Per legal counsel | Legal + Comms | See breach-notification-guide.md |
| Regulators | Per applicable regulations | Per breach-notification-guide.md | Legal | |

**Do not make public statements about the incident without legal counsel approval.**

**Do not communicate via systems that may be compromised. Use personal mobile phones for initial communications.**

---

## PHASE 4 — ASSESS RECOVERY OPTIONS

### Option 1 — Restore from backups (recommended)

Before restoring from backups:
- [ ] Confirm the entry point has been identified and closed
- [ ] Confirm the restoration environment is clean (not connected to the infected network)
- [ ] Confirm the backup predates the infection (ransomware may have been dormant)
- [ ] Confirm immutable backups are intact and not encrypted
- [ ] Confirm restoration has been tested (not just "backup completed successfully")

**Do not restore into a potentially infected environment. Rebuild the network segment first.**

### Option 2 — Ransom payment

This decision must be made by the designated authority (defined below), with input from:
- Legal counsel (legality, notification obligations)
- Cyber insurance carrier (coverage, approved payment process)
- Law enforcement (FBI guidance, sanctions risks)

**Paying ransom does not guarantee data recovery.** Approximately 20% of organizations that pay ransom do not receive a working decryption key.

**Ransom payment decision authority:**

| Threshold | Authority | Approval required from |
|---|---|---|
| Any amount | _____________________________ | _____________________________ |

---

## PHASE 5 — RECOVERY SEQUENCE

**Restore in tier order. Do not restore Tier 1 systems until all Tier 0 systems are clean and operational.**

| Step | System / action | Owner | Target completion | Completed |
|---|---|---|---|---|
| 1 | Rebuild clean network segment (isolated from infected environment) | IT | | |
| 2 | Restore Tier 0: Domain Controllers | IT | | |
| 3 | Restore Tier 0: DNS | IT | | |
| 4 | Restore Tier 0: Identity infrastructure | IT | | |
| 5 | Security validation of Tier 0 before proceeding | Forensics | | |
| 6 | Rotate ALL credentials (domain admin, service accounts, user passwords) | IT | | |
| 7 | Restore Tier 1: Email | IT | | |
| 8 | Restore Tier 1: ERP / financial systems | IT | | |
| 9 | User validation: confirm clean access for key users | IT + Users | | |
| 10 | Restore Tier 2 systems (see BIA for sequence) | IT | | |
| 11 | Restore Tier 3 systems | IT | | |
| 12 | Full security validation before declaring incident closed | Forensics + IT | | |

---

## PHASE 6 — REVIEW AND IMPROVE

- [ ] Post-incident review meeting scheduled within 14 days
- [ ] Root cause documented
- [ ] Entry point closed (technical remediation complete)
- [ ] Lessons learned documented and assigned to owners
- [ ] Playbook updated with findings
- [ ] Regulatory notifications completed (see breach-notification-guide.md)
- [ ] Insurance claim filed
- [ ] Legal notifications complete

---

*Infrastructure Placement Framework · Module 8 Ransomware Playbook · 4th and Bailey · v1.0.0*
*PRINT AND STORE OFFLINE. This document should be accessible when digital systems are unavailable.*
