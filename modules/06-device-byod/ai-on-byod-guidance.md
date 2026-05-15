# Module 6 — AI on BYOD Devices: Guidance

**Infrastructure Placement Framework · 4th and Bailey · v1.0.0**

---

## The problem

Employees are using AI tools — ChatGPT, Gemini, Perplexity, and hundreds of AI-embedded mobile apps — on personal devices to process work data. This is the fastest-growing shadow AI vector in 2026 and the one most organisations have not addressed in their BYOD policies.

A BYOD policy that does not explicitly address AI tool usage is a gap. An AI acceptable use policy that does not address personal devices is a gap. These two gaps combine.

---

## Risk scenarios

| Scenario | Risk |
|---|---|
| Employee uses ChatGPT on personal iPhone to draft a contract based on a client document | Confidential client data enters a consumer AI tool with no enterprise data protections |
| Employee uses an AI note-taking app on personal laptop in a client meeting | Meeting audio (including client-privileged discussion) may be processed by the app's AI and stored on the vendor's servers |
| Employee uses an AI-embedded productivity app (e.g., Notion AI, Otter.ai) installed on personal device | The app's AI features may process all content the employee interacts with |
| Employee installs an AI coding assistant browser extension on personal laptop | Source code entered in browser is processed by the extension's AI backend |

---

## Required BYOD policy additions

The BYOD security policy must include all of the following AI-specific clauses:

| Clause | Policy language |
|---|---|
| Approved AI tool list applies to personal devices | "The organisation's AI acceptable use policy and approved AI tool list applies to the use of all AI tools on enrolled personal devices when used for work purposes." |
| Prohibited data on personal device AI tools | "Restricted and confidential data (as defined in the data classification policy) must not be entered into any AI tool on a personal device, regardless of whether the tool is on the approved list." |
| AI note-taking and transcription apps | "AI-based note-taking, transcription, or meeting recording apps may not be used on personal devices during client meetings, confidential business discussions, or any meeting where the content would be classified as internal or above." |
| AI browser extensions | "AI-enabled browser extensions on personal devices used for work must be approved under the same process as other AI tools." |

---

## MDM enforcement controls

| Control | How to implement |
|---|---|
| Block known unapproved AI apps | App blacklist in MDM App Protection Policy |
| Restrict data copy/paste from work apps to personal apps | App Protection Policy — restrict "Save to" and clipboard to managed apps only |
| Require approved AI tool list compliance | Include in annual BYOD policy acknowledgement |
| Monitor for new AI app installations | MDM app inventory reporting |

---

## Integration with Module 5

This guidance is an extension of the Module 5 AI governance programme. Ensure:

- The approved AI tool list (Module 5) explicitly states which tools are approved for use on personal devices
- The shadow AI audit (Module 5) includes personal device app inventory
- The NIST AI RMF assessment (Module 5) includes personal device risk scenarios in the MAP function

---

*Infrastructure Placement Framework · Module 6 AI on BYOD Guidance · 4th and Bailey · v1.0.0*
