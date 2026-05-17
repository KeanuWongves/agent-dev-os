# Gap Analysis

Template rule: gaps must compare sourced reference evidence against the proposed product direction. Do not turn every reference feature into scope.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent in Research Mode> |
| Last Updated | YYYY-MM-DD |
| Upstream Sources | `research/FEATURE_MATRIX.md`, `research/OPEN_SOURCE_SCAN.md`, `research/REFERENCE_PRODUCT_ANALYSIS.md` |
| Downstream Consumers | `research/REUSE_DECISIONS.md`, `product/PRD.md`, `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |

## Reference Gaps

| Gap ID | What References Have That We Lack | Source Evidence | User Impact | MVP Implication | Decision |
| --- | --- | --- | --- | --- | --- |
| GAP-001 | <capability, workflow, constraint, or quality bar> | <FEAT/SRC/OSS/REF ID> | <impact if ignored> | <include / defer / reject / research more> | <what to do> |

## What We Should Learn

| Learning ID | Source | Lesson | How It Should Influence Product Discovery |
| --- | --- | --- | --- |
| LEARN-001 | <source ID> | <specific lesson> | <PRD/MVP/user story impact> |

## What We Should Not Copy

| Item | Source | Reason | Guardrail |
| --- | --- | --- | --- |
| <feature, wording, workflow, branding, or implementation> | <source ID> | <license, proprietary content, poor fit, or non-goal> | <how downstream artifacts avoid copying> |

## Differentiators

| Differentiator ID | Differentiator | Evidence or Assumption | Why It Matters |
| --- | --- | --- | --- |
| DIFF-001 | <what this product should do differently> | <source ID or assumption ID> | <user value or strategic reason> |

## MVP Implications

| Implication | Include in MVP? | Rationale | Affected Artifact |
| --- | --- | --- | --- |
| <capability or constraint> | Yes/No/Research more | <why> | `product/MVP.md` |

## Architecture Implications

| Implication | Required Now? | Rationale | Affected Artifact |
| --- | --- | --- | --- |
| <interface, data, integration, privacy, or extensibility implication> | Yes/No/Research more | <why> | `architecture/SYSTEM_DESIGN.md` |
