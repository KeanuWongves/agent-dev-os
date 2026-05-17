# Source Log

Template rule: every research claim used in product discovery must trace to a row in this log.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent in Research Mode> |
| Last Updated | YYYY-MM-DD |
| Upstream Context | `research/RESEARCH_BRIEF.md` |
| Downstream Consumers | `research/OPEN_SOURCE_SCAN.md`, `research/REFERENCE_PRODUCT_ANALYSIS.md`, `research/FEATURE_MATRIX.md`, `research/GAP_ANALYSIS.md`, `research/REUSE_DECISIONS.md`, `product/PRD.md` |

## Source Inventory

Allowed source types: `GitHub repo`, `closed-source product`, `content creator`, `paper`, `article`, `user-provided screenshot`, `manual note`.

Allowed access statuses: `fetched`, `partially fetched`, `inaccessible`, `human-provided required`.

Allowed uses: `reuse`, `learn`, `compare`, `ignore`, `restricted`.

| Source ID | Source Name | URL | Source Type | Access Status | Evidence Type | Last Checked Date | Reliability Notes | Allowed Use |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRC-001 | <name> | <URL or local artifact path> | <allowed source type> | <allowed access status> | <README, docs, screenshot, landing page, demo video, paper, human note> | YYYY-MM-DD | <bias, stale data, partial access, unverifiable claims> | <allowed use> |

## Human-provided Required Sources

Use this section when a source cannot be fetched by the agent.

| Source ID | Missing Evidence | Human Owner | Required Note or Artifact | Blocks Which Decision? |
| --- | --- | --- | --- | --- |
| SRC-XXX | <what could not be verified> | <owner> | <screenshot, link, summary, access grant, or manual note> | <PRD/MVP/reuse/feature decision> |

## Source Logging Rules

- Do not use a source in `product/PRD.md` unless it appears in this log.
- Mark inaccessible sources as `human-provided required`; do not infer facts from memory, snippets, names, or popularity.
- Record `restricted` when source terms, license, privacy, or proprietary status make reuse unsafe.
- Closed-source products may be used for comparison and learning from observable patterns, not copying.
