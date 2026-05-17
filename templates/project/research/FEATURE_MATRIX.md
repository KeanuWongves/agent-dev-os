# Feature Matrix

Template rule: every feature comparison must cite a logged source or be marked as a human assumption.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent in Research Mode> |
| Last Updated | YYYY-MM-DD |
| Upstream Sources | `research/SOURCE_LOG.md`, `research/OPEN_SOURCE_SCAN.md`, `research/REFERENCE_PRODUCT_ANALYSIS.md` |
| Downstream Consumers | `research/GAP_ANALYSIS.md`, `product/PRD.md`, `product/MVP.md`, `product/ROADMAP.md` |

## Feature Comparison

Allowed decisions: `include`, `defer`, `reject`, `research more`.

| Feature ID | Feature | Reference Source | User Value | Implementation Complexity | MVP Relevance | Evidence | Decision |
| --- | --- | --- | --- | --- | --- | --- | --- |
| FEAT-001 | <capability or workflow step> | <SRC/OSS/REF ID> | <why a user benefits> | <low / medium / high / unknown> | <must / should / could / no> | <source claim, screenshot, README section, note, or assumption ID> | <allowed decision> |

## Decision Rules

- Use `include` only when user value is clear, evidence exists, and MVP relevance is `must` or explicitly justified.
- Use `defer` when valuable but not needed for MVP.
- Use `reject` when it violates non-goals, constraints, ethics, privacy, license, or MVP focus.
- Use `research more` when source evidence is weak, inaccessible, or contradictory.

## Traceability to Product Requirements

| Feature ID | PRD Requirement ID | MVP Capability | Trace Status | Notes |
| --- | --- | --- | --- | --- |
| FEAT-001 | PRD-XXX | <capability or none> | <traced / deferred / rejected / unresolved> | <why> |
