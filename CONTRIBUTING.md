# Contributing

This framework is maintained by 4th and Bailey. Contributions are welcome in three forms.

---

## 1. Issue filing

Use the feedback template to report:
- Outdated statistics or cited sources that require updating
- Missing sector scenarios not covered by existing variants
- Gaps in the framework (assessment questions that should exist but don't)
- Errors in scoring logic or weighting rationale
- Broken links or formatting issues

Open an Issue using the [framework-feedback template](.github/ISSUE_TEMPLATE/framework-feedback.md).

---

## 2. Sector additions

IT practitioners with domain expertise in a sector not yet covered — non-profit, property management, education, manufacturing, veterinary, or others — are encouraged to submit a sector variant.

A sector variant consists of:
- A `sectors/{sector-name}/README.md` explaining the sector's key IT governance context
- Scoring weight adjustments with rationale for each modified dimension
- Sector-specific assessment questions for each module
- Relevant regulatory and compliance callouts (regulations, standards, obligations)

Submit a sector addition request using the [sector-addition-request template](.github/ISSUE_TEMPLATE/sector-addition-request.md) before beginning work. This allows the maintainer to confirm scope and avoid duplicate effort.

---

## 3. Pull requests

1. Fork the repository
2. Create a feature branch from `develop` (not from `main`)
   - Branch naming: `modules/{module-number}-{description}` or `sectors/{sector-name}`
3. Make your changes
4. Include a clear rationale in the PR description — explain *why* the change improves the framework, not just *what* changed
5. Submit the PR targeting `develop`

**Requirements for all PRs:**
- Markdown formatting consistent with existing files (headings, table style, bold emphasis)
- No vendor promotional content of any kind
- All factual claims supported by a cited source with a date (e.g., "IBM Cost of a Data Breach Report 2025")
- Assessment questions must be answerable by an organisation working independently, without requiring external expertise to understand the question

**Additional requirements for methodology changes:**
- Any PR that proposes changes to scoring weights, thresholds, or dimension definitions must include a corresponding update to `METHODOLOGY.md`
- Rationale for the weighting change must be documented in METHODOLOGY.md, not just in the PR description

---

## Attribution

All contributions are acknowledged in `CHANGELOG.md` and, where substantive, in the affected module's README.

Contributors who submit accepted sector variants are acknowledged by name or organisation (at their preference) in the sector README.

---

## Standards for contributions

| Standard | Requirement |
|---|---|
| Formatting | Match existing Markdown style — H2 and H3 headings, pipe tables, bold for key terms |
| Citations | Every statistical claim must include source name and year |
| Vendor neutrality | No product recommendations, pricing claims, or affiliate content |
| Question accessibility | Assessment questions must be independently answerable |
| Scope | Changes should address a gap in the framework, not expand scope beyond the framework's purpose |

---

*Infrastructure Placement Framework · github.com/4thandBailey/infrastructure-placement-framework*
