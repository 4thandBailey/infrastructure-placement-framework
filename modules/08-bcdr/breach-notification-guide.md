# Module 8 — Data Breach Notification Guide

**Sector-specific regulatory timelines and notification requirements**

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

> **This guide is for planning purposes only. It does not constitute legal advice.**
> Notification obligations vary by the specific facts of each incident. Have legal counsel review all notifications before sending. Retain this guide alongside the BCP — notification decisions are time-sensitive and must not wait for legal counsel to research the basics.

---

## The core principle

A confirmed data breach triggers simultaneous obligations on different timelines. Drafting notifications under pressure during an active incident produces errors that become liability. Every notification template must exist before an incident occurs, reviewed by legal counsel, and stored offline alongside this guide.

---

## Notification decision tree

### Step 1 — Was personal data accessed, exfiltrated, or exposed?

- **No confirmed personal data involved** → Standard incident response; no breach notification required. Document the finding and retain for audit.
- **Yes or uncertain** → Continue to Step 2.

### Step 2 — Who does the data belong to?

Identify all categories of personal data that may have been involved:

| Data category | Regulation | Notification required? |
|---|---|---|
| Protected Health Information (PHI) | HIPAA | Yes — specific timelines apply |
| Texas resident personally identifiable information | Texas HB 3834 / Texas Identity Theft Enforcement and Protection Act | Yes — 60-day deadline |
| Payment card data (credit/debit card numbers) | PCI-DSS | Yes — immediate |
| Financial institution customer data | GLBA Safeguards Rule | Yes — 30 days |
| Student educational records | FERPA | Yes — without unreasonable delay |
| EU resident personal data | GDPR | Yes — 72 hours to supervisory authority |
| Federal government data | FISMA / agency-specific | Yes — 1 hour (US-CERT) |
| Other state residents | State breach notification laws (all 50 states have laws) | Varies by state — see below |

---

## Notification requirements by regulation

### HIPAA (Protected Health Information)

**Who it applies to:** Healthcare providers, health plans, healthcare clearinghouses, and their business associates.

**What triggers notification:** Unauthorized access, use, or disclosure of PHI unless the organisation can demonstrate a low probability that PHI has been compromised (4-factor risk assessment required).

| Recipient | Deadline | Method | Notes |
|---|---|---|---|
| Affected individuals | Within 60 days of discovery | Written (first-class mail or email if preferred) | Must include specific elements — see below |
| HHS Office for Civil Rights | Within 60 days (< 500 individuals) or simultaneously with individual notice (≥ 500) | HHS web portal | Breaches of 500+ in a state also require media notice |
| Media (prominent outlets in affected state) | If ≥ 500 individuals in a state | Press release | Same 60-day deadline |

**Individual notification must include:**
- Description of what happened
- Types of information involved
- Steps individuals should take to protect themselves
- What the covered entity is doing to investigate, mitigate, and prevent recurrence
- Contact information for questions

**HIPAA notification template — obtain legal review of organisation-specific version before incident.**

---

### Texas HB 3834 / Texas Identity Theft Enforcement and Protection Act

**Who it applies to:** Any person or business conducting business in Texas that owns or licenses computerised data containing sensitive personal information of Texas residents.

**What triggers notification:** Unauthorized acquisition of computerised data that compromises the security, confidentiality, or integrity of sensitive personal information.

**Sensitive personal information includes:** Name + SSN, driver's licence/state ID, account number + access code/password, debit/credit card number + code, or certain medical information.

| Recipient | Deadline | Method | Notes |
|---|---|---|---|
| Affected Texas residents | As quickly as possible, no later than 60 days | Written, electronic, telephone, or substitute | Substitute notice available for large breaches (> 250,000) |
| Texas Attorney General | Within 60 days if breach affects more than 500 Texas residents | Written | AG may investigate |

---

### PCI-DSS (Payment Card Data)

**Who it applies to:** Any organisation that processes, stores, or transmits cardholder data.

**What triggers notification:** Confirmed or suspected compromise of cardholder data.

| Recipient | Deadline | Method | Notes |
|---|---|---|---|
| Acquiring bank | Immediately upon suspicion | Phone + written | Do not wait for confirmation |
| Card brands (Visa, Mastercard, Amex, Discover) | Per acquiring bank direction | Via acquiring bank | Acquiring bank coordinates |
| Cardholders | Per card brand direction | | Varies by incident |

**PCI-DSS breach penalties can include fines, increased transaction fees, and loss of card processing rights.**

---

### GLBA Safeguards Rule (Financial Customer Data)

**Who it applies to:** Financial institutions subject to FTC jurisdiction (banks, credit unions, securities firms, insurance companies, and broadly, any entity providing financial products or services).

**What triggers notification:** Notification event — unauthorized acquisition of unencrypted customer information, or encrypted information and the encryption key.

| Recipient | Deadline | Method | Notes |
|---|---|---|---|
| FTC (or applicable federal regulator) | As soon as possible, no later than 30 days after discovery | FTC Safeguards Rule notification portal | |
| Affected customers | As soon as reasonably practicable | Written or electronic | Only required if customer information was acquired |

---

### FERPA (Student Educational Records)

**Who it applies to:** Educational institutions receiving federal funding.

**What triggers notification:** Unauthorized disclosure of education records.

| Recipient | Deadline | Method |
|---|---|---|
| Affected students/parents | Without unreasonable delay | Written |
| U.S. Department of Education | Per ED guidance | Written |

---

### GDPR (EU Resident Personal Data)

**Who it applies to:** Any organisation processing EU/EEA resident personal data, regardless of where the organisation is located.

| Recipient | Deadline | Method | Notes |
|---|---|---|---|
| Lead supervisory authority (EU data protection authority) | 72 hours after becoming aware | Written | Required if risk to individuals; not required if risk is unlikely |
| Affected EU individuals | Without undue delay | Written | Required if high risk to individuals |

**72-hour deadline from *awareness*, not from *confirmation*. Begin the notification process immediately upon becoming aware.**

---

## Multi-state notification obligations

If the breach affects residents of multiple states, each state's breach notification law applies to its residents. All 50 US states have breach notification laws with varying requirements. Key variations:

| State | Notable requirements |
|---|---|
| California (CCPA/CPRA) | Specific content requirements; AG notification if > 500 Californians |
| New York (SHIELD Act) | Broad definition of private information; AG notification |
| Florida | 30-day deadline (shorter than most) |
| Colorado | 30-day deadline; specific content requirements |
| All others | Generally 30–90 days; consult legal counsel for each affected state |

---

## Notification readiness checklist

Complete before any incident occurs:

- [ ] Legal counsel identified with data breach notification experience
- [ ] Notification templates drafted and reviewed by legal counsel for each applicable regulation
- [ ] Templates stored offline alongside this guide
- [ ] Cyber insurance carrier confirmed — notification obligations reviewed with carrier
- [ ] Regulatory contact information current (HHS portal, FTC portal, state AG contacts)
- [ ] Incident classification process defined — who determines if notification is required
- [ ] Notification decision authority assigned — who approves notifications before they are sent

---

## Notification log

Maintain a log of all notifications for audit and regulatory purposes:

| Recipient | Regulation | Date sent | Method | Sent by | Content reference | Confirmation received |
|---|---|---|---|---|---|---|
| | | | | | | |

---

*Infrastructure Placement Framework · Module 8 Breach Notification Guide · 4th and Bailey · v1.0.0*
*This guide is for planning reference only and does not constitute legal advice. Consult qualified legal counsel for all breach notification decisions.*
*4th and Bailey · 4thandbailey.com · (888) 305-5977 · Houston, TX*
