# Module 5 — Shadow AI Audit Checklist

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Purpose

Shadow AI — employees using unapproved AI tools without IT oversight — is present in virtually every organisation. This checklist identifies what AI tools are in use, what data has been exposed, and what regulatory liability exists.

**Assessment date:** _______________________________________________

**Assessed by:** _______________________________________________

---

## Section 1 — Discovery: what AI tools are in use?

### 1.1 Known / approved AI tools

| Tool | Approved? | Data terms reviewed? | Data classification allowed | Notes |
|---|---|---|---|---|
| Microsoft 365 Copilot | Yes / No | Yes / No | | |
| Google Gemini (Workspace) | Yes / No | Yes / No | | |
| GitHub Copilot | Yes / No | Yes / No | | |
| ChatGPT (OpenAI) | Yes / No | Yes / No | | |
| Claude (Anthropic) | Yes / No | Yes / No | | |
| AWS AI services | Yes / No | Yes / No | | |
| Salesforce Einstein | Yes / No | Yes / No | | |
| Other (list): | Yes / No | Yes / No | | |

### 1.2 Shadow AI discovery methods

Check all discovery methods used in this audit:

- [ ] DNS query log review — identify AI tool domains in use
- [ ] Web proxy / firewall log review — traffic to AI endpoints
- [ ] OAuth / app consent audit — third-party apps with AI functionality granted access
- [ ] Employee survey — anonymous survey about AI tool usage
- [ ] SaaS discovery tool (Nudge Security, BetterCloud, etc.)
- [ ] Browser extension inventory
- [ ] Mobile device management app inventory (Module 6 integration)

### 1.3 Shadow AI tools identified

| Tool identified | User group | Data accessed/submitted | Risk level | Action |
|---|---|---|---|---|
| | | | High / Med / Low | Block / Review / Permit with policy |
| | | | High / Med / Low | |

---

## Section 2 — Data exposure assessment

### 2.1 Data classification review for AI inputs

What categories of data have employees been submitting to AI tools?

| Data category | AI tools receiving this data | Classification | Regulatory risk | Action required |
|---|---|---|---|---|
| Customer PII | | Confidential | Yes / No | |
| Financial data | | Restricted | Yes / No | |
| Source code / IP | | Confidential | Yes / No | |
| Health / PHI | | Restricted — HIPAA | Yes / No | |
| Legal documents / matters | | Restricted | Yes / No | |
| HR / employee data | | Confidential | Yes / No | |
| Client contracts | | Confidential | Yes / No | |
| General internal communications | | Internal | Low | |

### 2.2 Training data exposure risk

For each AI tool in use, has the vendor confirmed:

| Vendor | Uses inputs for model training by default? | Opt-out available? | Enterprise terms obtained? |
|---|---|---|---|
| | Yes / No / Unknown | Yes / No | Yes / No |
| | Yes / No / Unknown | Yes / No | Yes / No |

---

## Section 3 — Policy and controls assessment

| Control | Status | Gap / action |
|---|---|---|
| AI acceptable use policy exists | ✅ / ⚠️ / ❌ | |
| Policy has been communicated to all employees | ✅ / ⚠️ / ❌ | |
| Approved AI tool list published and maintained | ✅ / ⚠️ / ❌ | |
| Data classification policy covers AI tool use | ✅ / ⚠️ / ❌ | |
| New AI tool approval process defined | ✅ / ⚠️ / ❌ | |
| Technical controls blocking unapproved AI tools | ✅ / ⚠️ / ❌ | |
| AI tool usage is audited/monitored | ✅ / ⚠️ / ❌ | |
| BYOD devices addressed in AI policy | ✅ / ⚠️ / ❌ | |
| AI governance ownership assigned (named individual) | ✅ / ⚠️ / ❌ | |

---

## Section 4 — Shadow AI risk register

| Tool / risk | Data exposed | Regulatory risk | Risk level | Remediation | Owner | Date |
|---|---|---|---|---|---|---|
| | | | High / Med / Low | | | |

---

## Section 5 — Recommended immediate actions

Based on findings, prioritise the following:

**Immediate (within 30 days):**
- [ ] Block confirmed high-risk shadow AI tools at the network/proxy level
- [ ] Communicate approved AI tool list to all staff
- [ ] Publish or update acceptable use policy (use template in `acceptable-use-policy-template.md`)
- [ ] Obtain enterprise data handling terms from approved AI vendors

**Short-term (30–90 days):**
- [ ] Complete NIST AI RMF assessment (`nist-ai-rmf-assessment.md`)
- [ ] Establish AI governance ownership
- [ ] Implement OAuth/app consent review process
- [ ] Complete vendor evaluation rubric for all approved AI tools

**Ongoing:**
- [ ] Quarterly shadow AI discovery sweep
- [ ] Policy review triggered by any new significant AI tool release

---

*Infrastructure Placement Framework · Module 5 Shadow AI Audit Checklist · 4th and Bailey · v1.0.0*
