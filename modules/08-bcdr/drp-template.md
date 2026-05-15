# Disaster Recovery Plan

**[ORGANISATION NAME]**

*Template · Complete all sections · Requires annual review and testing*

**Version:** _______  |  **Effective date:** _______  |  **Review date:** _______

**IT Lead / Plan owner:** _______________________

---

> **This document is CONFIDENTIAL.**
> Store a printed copy in a location accessible when IT systems are unavailable. This document must be readable when your network is offline.

---

## 1. Purpose and scope

This Disaster Recovery Plan (DRP) defines the step-by-step process for restoring [ORGANISATION NAME]'s IT systems, data, and infrastructure after a technical failure, cyberattack, or disaster. It is a component of the Business Continuity Plan (BCP), not a replacement for it.

The BCP addresses how the organization keeps operating. This DRP addresses how IT systems are restored.

**Scope:** All IT systems, data stores, and infrastructure operated by or on behalf of [ORGANISATION NAME].

**This plan is activated when:** The BCP is activated AND IT system restoration is required, OR when an IT-specific incident (hardware failure, data corruption, ransomware) requires structured recovery even without a broader continuity event.

---

## 2. Recovery team

| Role | Name | Contact | Responsibilities |
|---|---|---|---|
| IT Recovery Lead | | | Overall DRP execution, escalation |
| Systems Administrator | | | Server and infrastructure restoration |
| Network Administrator | | | Network, firewall, connectivity |
| Security Lead | | | Security validation before systems return to production |
| Backup/Storage Lead | | | Backup retrieval, integrity validation, restore execution |
| Application Owner(s) | | | Validate application function post-restore |
| Vendor Contacts | See Section 8 | | External support for vendor-managed systems |

---

## 3. Recovery tier definitions and targets

*RTO and RPO targets are set in the Business Impact Analysis. Copy approved targets here.*

| Tier | Examples | RTO target | RPO target | Recovery approach |
|---|---|---|---|---|
| Tier 0 — Critical | Domain Controllers, DNS, identity, payment | < 1 hour | < 15 min | Hot standby / automated failover |
| Tier 1 — Mission-critical | Email, ERP, financial, core LoB | 1–4 hours | < 1 hour | Warm standby / near-real-time backup |
| Tier 2 — Business-important | CRM, collaboration, HR, file servers | 4–24 hours | 4 hours | Regular backup / restore from clean image |
| Tier 3 — Non-critical | Archives, dev environments, internal portals | 24–72 hours | 24 hours | Standard backup / restore on availability |

---

## 4. Backup inventory

*Verify this inventory quarterly. An outdated backup inventory is as dangerous as no backup.*

| System | Backup type | Backup frequency | Backup location | Retention | Last restore test | Immutable? |
|---|---|---|---|---|---|---|
| Domain Controllers | | Daily | | 90 days | | Yes / No |
| DNS / DHCP | | Daily | | 90 days | | Yes / No |
| Email (Exchange / M365) | | Continuous / Daily | | 1 year | | Yes / No |
| File servers / SharePoint | | Daily | | 1 year | | Yes / No |
| ERP / financial system | | Daily + transaction log | | 7 years | | Yes / No |
| CRM | | Daily | | 3 years | | Yes / No |
| Databases (list each) | | | | | | |

**Backup storage locations:**
- Primary backup: _______________________________________________
- Secondary backup (offsite): _______________________________________________
- Immutable/air-gapped copy: _______________________________________________

**Backup access credentials are stored at:** _______________________________________________ (offline)

---

## 5. Restoration sequence

**Critical rule: Restore in tier order. Do not begin Tier 1 restoration until all Tier 0 systems are restored, validated, and security-approved for production.**

### Tier 0 restoration

| Step | System | Action | Owner | Estimated time | Completed |
|---|---|---|---|---|---|
| T0-1 | Network infrastructure | Confirm network layer is operational; firewall rules verified | Network Admin | | |
| T0-2 | Domain Controllers | Restore primary DC from clean backup; validate AD replication | Sys Admin | | |
| T0-3 | DNS | Restore DNS; validate resolution for all critical names | Sys Admin | | |
| T0-4 | Identity / IdP | Restore/validate identity infrastructure; confirm auth is functional | Sys Admin | | |
| T0-5 | Security validation | Security Lead confirms Tier 0 is clean before Tier 1 begins | Security Lead | | |

**STOP. Security Lead must sign off on Tier 0 before proceeding.**

Security Lead sign-off: _____________________________ Date/Time: _____________________________

---

### Tier 1 restoration

| Step | System | Action | Owner | Estimated time | Completed |
|---|---|---|---|---|---|
| T1-1 | Email platform | Restore / validate email service | Sys Admin | | |
| T1-2 | ERP / financial system | Restore from clean backup; validate data integrity | App Owner | | |
| T1-3 | Core LoB applications | Restore per application runbook | App Owner | | |
| T1-4 | VPN / remote access | Validate remote access functional | Network Admin | | |
| T1-5 | Credential rotation | Reset all privileged account passwords | Security Lead | | |
| T1-6 | User validation | Key users validate access and data integrity | IT Lead + Users | | |

**STOP. IT Lead and Application Owners must validate Tier 1 data integrity before declaring Tier 1 restored.**

---

### Tier 2 and Tier 3 restoration

Follow the same pattern. All credentials rotated before users are re-enabled on each system.

| System | Owner | Action | Completed |
|---|---|---|---|
| CRM | | | |
| Collaboration platform | | | |
| HR system | | | |
| File servers | | | |
| Archives | | | |
| Dev environments | | | |

---

## 6. Security validation checklist

**Before any system returns to production, confirm ALL items below:**

| Check | Status | Verified by |
|---|---|---|
| System restored from a backup that predates the incident | ✅ / ❌ | |
| System is not connected to potentially compromised network segments | ✅ / ❌ | |
| All credentials (admin, service accounts, user passwords) rotated | ✅ / ❌ | |
| EDR/AV scan completed on restored system — clean | ✅ / ❌ | |
| Entry point of incident is confirmed closed | ✅ / ❌ | |
| Forensic investigation has cleared this system | ✅ / ❌ | |
| Patch level is current | ✅ / ❌ | |
| Audit logging is enabled and functional | ✅ / ❌ | |

---

## 7. Ransomware-specific restoration notes

If the incident is ransomware, additional steps apply before any restoration begins. Refer to `ransomware-playbook.md` for the full ransomware-specific sequence, including:

- Forensic capture before reboot
- Entry point identification and closure
- Immutable backup validation
- Clean environment build before restore

**Do not restore any system into a potentially infected environment.**

---

## 8. Vendor contacts and emergency support

| Vendor | System | Support type | Emergency phone | Account / contract # | SLA |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

---

## 9. DRP testing schedule

| Test type | Frequency | Last completed | Next scheduled | Lead |
|---|---|---|---|---|
| Backup restore validation | Monthly (Tier 0), Quarterly (Tier 1–2) | | | |
| Tabletop exercise | Quarterly | | | |
| Component failover test | Semi-annually | | | |
| Full DR simulation | Annually | | | |

**Test findings are documented and fed back into this plan at each review cycle.**

---

## 10. Plan maintenance

This DRP is reviewed and updated:
- Annually as a scheduled review
- After every plan activation
- When the infrastructure changes significantly (new systems, new vendors, new backup architecture)
- When test exercises identify gaps

**Version history:**

| Version | Date | Changed by | Summary of changes |
|---|---|---|---|
| 1.0 | | | Initial version |

---

*[ORGANISATION NAME] Disaster Recovery Plan · Template adapted from Infrastructure Placement Framework by 4th and Bailey (github.com/4thandBailey/infrastructure-placement-framework), CC BY 4.0*
*Version _______ · IT Lead _______ · Date _______*
