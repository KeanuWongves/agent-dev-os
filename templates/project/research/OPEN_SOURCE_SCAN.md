# Open Source Scan

Template rule: open-source reuse recommendations require a logged source and recorded license or restriction.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent in Research Mode> |
| Last Updated | YYYY-MM-DD |
| Upstream Sources | `research/RESEARCH_BRIEF.md`, `research/SOURCE_LOG.md` |
| Downstream Consumers | `research/FEATURE_MATRIX.md`, `research/GAP_ANALYSIS.md`, `research/REUSE_DECISIONS.md`, `product/PRD.md`, `architecture/TECH_STACK.md` |

## Repository Scan

| Repo ID | Repo Name | URL | License | Stars / Activity if Available | Core Functionality | Reusable Modules | Risks | Reuse Decision |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| OSS-001 | <owner/name> | <URL> | <license or unknown> | <stars, last commit, release cadence, issue activity, or unavailable> | <what it does> | <module, pattern, prompt, schema, workflow, or none> | <license, quality, maintenance, security, scope mismatch> | <build / reuse / learn / ignore / research more> |

## License and Restriction Check

| Repo ID | License Recorded? | Compatible with Project? | Restriction Notes | Blocks Reuse? |
| --- | --- | --- | --- | --- |
| OSS-001 | Yes/No | Yes/No/Unknown | <obligations or uncertainty> | Yes/No |

## Reuse Candidate Summary

| Candidate | Decision | Rationale | Downstream Artifact Impacted |
| --- | --- | --- | --- |
| <repo/module/pattern> | <build / reuse / learn / ignore> | <why> | <PRD/MVP/TECH_STACK/SYSTEM_DESIGN/TASK> |

## Stop Conditions

- Stop reuse recommendation when license is missing or incompatible.
- Stop product claims when repository functionality cannot be verified from fetched evidence.
- Stop architecture influence when the scanned repository would require unapproved dependencies, runtime services, or scope expansion.
