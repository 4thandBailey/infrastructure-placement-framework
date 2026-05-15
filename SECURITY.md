# Security policy

## Scope

This repository contains framework documentation, assessment templates, and decision guides. It does not contain production code, credentials, or executable deployment scripts.

For security issues in the 4th and Bailey tools repository ([github.com/4thandBailey/tools](https://github.com/4thandBailey/tools)), which contains PowerShell scripts that interact with Microsoft Graph API, please follow the disclosure process below.

---

## Supported versions

| Repository | Supported |
|---|---|
| `infrastructure-placement-framework` — current release | Yes |
| `tools` — current release | Yes |
| Previous versions of either repository | No |

---

## Reporting a vulnerability

**Email:** security@4thandbailey.com
**Expected response time:** Within 5 business days

Please do not open a public GitHub Issue to report a security vulnerability. Public disclosure before a fix is available may put others at risk.

### What to include in your report

- A description of the vulnerability and its potential impact
- Steps to reproduce (where applicable)
- Any relevant environment details (OS, PowerShell version, API version)
- Your preferred contact method for follow-up

---

## What qualifies as a security issue in this repository

Given that this repository contains documentation only, security issues are limited to:

- A template or checklist that contains factually incorrect security guidance that could lead an organisation to make a harmful decision
- A cited tool or resource in the framework that has itself been identified as malicious or compromised
- A script example (if any are added in future) that contains a vulnerability

General disagreements with framework recommendations or scoring methodology are not security issues — submit those using the [framework-feedback issue template](.github/ISSUE_TEMPLATE/framework-feedback.md).

---

*4th and Bailey · security@4thandbailey.com · 4thandbailey.com*
