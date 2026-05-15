# Module 6 — Device Model Matrix

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## Ownership model selection guide

Use this matrix to determine the correct ownership model for each role category in your organization.

| Role category | Data sensitivity | Regulatory requirement | Recommended model | MDM requirement |
|---|---|---|---|---|
| Executive / C-Suite | High | Varies | COPE | Required |
| Finance / Accounting | High | SOX, PCI-DSS, GLBA | COPE or COBO | Required |
| Healthcare clinical staff | Restricted — PHI | HIPAA | COBO | Required |
| Legal / compliance | High | Client confidentiality | COPE | Required |
| Sales / business development | Medium | Varies | CYOD or COPE | Required |
| IT administration | High — system access | Varies | COPE or COBO | Required |
| General knowledge worker | Low–Medium | Varies | BYOD or CYOD | Conditional enrollment |
| Field operations / OT | Medium | Varies | COPE or COBO | Required |
| Contractors and vendors | Low (limited access) | Varies | BYOD with containerisation | Conditional/MAM only |
| Part-time / seasonal | Low | Varies | BYOD with containerisation | MAM only |

---

## Organization-specific role matrix

Complete this matrix for your organization's specific roles:

| Role | Department | Data sensitivity | Current model | Recommended model | MDM enrolled? | Gap |
|---|---|---|---|---|---|---|
| | | High / Med / Low | BYOD / CYOD / COPE / COBO | | Yes / No | |
| | | | | | | |

---

## Containerisation architecture

For BYOD and CYOD deployments where the organization cannot manage the full device, a containerisation approach separates corporate data from personal data:

| Approach | How it works | Best for |
|---|---|---|
| MDM with work profile (Android) | Separate work profile managed by MDM; personal data untouched | Android BYOD |
| MDM with managed apps (iOS) | Corporate apps managed; personal apps unaffected | iOS BYOD |
| MAM-only (no device enrollment) | Application-level management only; no device wipe capability | Contractors, high-BYOD environments |
| Virtual desktop (VDI) | Corporate work delivered through a virtual session; no data on device | High-security remote access |

**Remote wipe scope (critical to define before deployment):**

| Model | What can IT wipe remotely? |
|---|---|
| Full MDM enrollment | Full device wipe OR selective (corporate data only) |
| Work profile (Android) | Work profile only — personal data untouched |
| MAM-only | Corporate app data only — no device-level wipe |
| COBO/COPE full MDM | Full device wipe |

*Remote wipe scope must be communicated to employees and included in the acceptable use agreement before enrollment.*

---

*Infrastructure Placement Framework · Module 6 Device Model Matrix · 4th and Bailey · v1.0.0*
