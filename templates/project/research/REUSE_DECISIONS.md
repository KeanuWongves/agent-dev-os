# Reuse Decisions

Template rule: reuse decisions influence product and architecture artifacts, but do not authorize implementation by themselves.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent in Research Mode> |
| Last Updated | YYYY-MM-DD |
| Upstream Sources | `research/SOURCE_LOG.md`, `research/OPEN_SOURCE_SCAN.md`, `research/GAP_ANALYSIS.md` |
| Downstream Consumers | `product/PRD.md`, `product/MVP.md`, `architecture/TECH_STACK.md`, `architecture/DECISIONS.md`, `management/MASTER_PLAN.md` |

## Decision Register

Allowed decisions: `build`, `reuse`, `learn`, `ignore`.

| Decision ID | Build / Reuse / Learn / Ignore Decision | Source | Rationale | License or Restriction | Risk | Downstream Artifact Impacted |
| --- | --- | --- | --- | --- | --- | --- |
| RD-001 | <allowed decision> | <SRC/OSS/REF/GAP ID> | <why this is the right treatment> | <license, terms, proprietary restriction, or none> | <legal, maintenance, quality, privacy, UX, scope, or unknown> | <PRD/MVP/TECH_STACK/DECISIONS/MASTER_PLAN/TASK> |

## Reuse Preconditions

| Decision ID | Required Before Reuse | Owner | Blocking? |
| --- | --- | --- | --- |
| RD-001 | <license review, security review, architecture approval, human confirmation, or none> | <role> | Yes/No |

## Product Discovery Impact

| Decision ID | Product Requirement or Non-goal Affected | Required PRD Action |
| --- | --- | --- |
| RD-001 | <PRD-XXX, MVP capability, non-goal, or open question> | <add, revise, defer, reject, or mark assumption> |

## Stop Conditions

- Stop reuse when license, terms, or ownership is unknown.
- Stop copying when the source is closed-source, proprietary, private, or content-protected.
- Stop downstream planning when a reuse decision would require an unapproved dependency, service, runtime, database, CLI, or product scope expansion.
