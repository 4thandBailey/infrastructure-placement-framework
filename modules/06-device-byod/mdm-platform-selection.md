# Module 6 — MDM/UEM Platform Selection Guide

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## The principle: MDM follows collaboration platform

The MDM/UEM selection decision should follow the collaboration platform decision, not precede it. The platforms integrate natively with their respective management solutions:

| Collaboration platform | Natural MDM/UEM choice | Why |
|---|---|---|
| Microsoft 365 | Microsoft Intune | Native Entra ID integration, Conditional Access, co-management with SCCM |
| Google Workspace | Google Endpoint Management | Native Workspace admin integration, single console |
| Apple-centric (Mac/iOS dominant) | Jamf | Purpose-built for Apple; deepest Apple MDM API usage |
| Mixed / platform-agnostic | Intune (broadest cross-platform) | Windows, macOS, iOS, Android, Linux from one console |
| VDI / contractor-heavy | AWS WorkSpaces + Intune or Workspace ONE | Deliver desktop to any device; manage the session, not the device |

---

## Platform comparison

| Capability | Microsoft Intune | Google Endpoint Mgmt | Jamf |
|---|---|---|---|
| Windows management | Excellent | Basic | Limited |
| macOS management | Good | Limited | Excellent |
| iOS management | Good | Good | Excellent |
| Android management | Good | Excellent | Limited |
| ChromeOS management | Limited | Excellent | None |
| Conditional Access integration | Native (Entra ID) | Native (Workspace) | Via third-party |
| Application management (MAM) | Yes | Yes | Yes |
| Zero-touch enrollment | Yes (Autopilot) | Yes (Zero Touch) | Yes (PreStage) |
| Compliance reporting | Excellent | Good | Good |
| Estimated annual cost per device | $$ (included in M365 E3+) | $ (included in Workspace) | $$$ |

---

## Selection checklist

Answer these questions to validate the MDM recommendation:

| Question | Answer | Implication |
|---|---|---|
| What is the primary collaboration platform? | M365 / Google / Mixed | See principle above |
| What OS mix does the device fleet use? | % Windows / Mac / iOS / Android | Cross-platform = Intune advantage |
| Are Apple devices > 50% of the fleet? | Yes / No | Yes → evaluate Jamf |
| Is Conditional Access in use or planned? | Yes / No | Yes → Intune strongly preferred |
| Are contractors/vendors included in scope? | Yes / No | Yes → MAM-only tier needed |
| Is co-management (SCCM + Intune) relevant? | Yes / No | Yes → Intune only |
| Is VDI in scope? | Yes / No | Yes → evaluate WorkSpaces or AVD |

---

## Recommended configuration checklist

Once MDM platform is selected, configure these baseline controls:

| Control | Intune | Google | Jamf |
|---|---|---|---|
| Require device encryption | Compliance policy | Endpoint policy | Configuration profile |
| Require passcode/PIN on mobile | Compliance policy | Device policy | Configuration profile |
| Block jailbroken/rooted devices | Compliance policy | Device policy | Restrictions profile |
| Enforce approved AI apps only | App protection policy | App management | Configuration profile |
| Enable remote wipe | Enrollment | Enrollment | Enrollment |
| Certificate-based Wi-Fi access | SCEP profile | Network settings | Configuration profile |

---

*Infrastructure Placement Framework · Module 6 MDM Platform Selection · 4th and Bailey · v1.0.0*
