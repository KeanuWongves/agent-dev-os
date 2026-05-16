# MVP: <Project Name>

Template rule: implementation tasks may include only capabilities listed as included scope or explicitly authorized assumptions.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source PRD | `product/PRD.md` |
| Downstream Consumers | `product/ROADMAP.md`, `architecture/SYSTEM_DESIGN.md`, `management/MASTER_PLAN.md` |

## MVP Objective

<State the smallest coherent product outcome this release must prove.>

## Included Capabilities

| Capability ID | Capability | User Value | Acceptance Criteria | Source Requirement |
| --- | --- | --- | --- | --- |
| MVP-001 | <capability> | <why users need it> | <observable result> | PRD-### |

## Excluded Capabilities

| Exclusion ID | Exclusion | Reason | Revisit Trigger |
| --- | --- | --- | --- |
| EX-001 | <capability> | <why not MVP> | <condition that would reopen it> |

## User Journey Covered

| Step | User or System Action | Success Signal | Failure or Recovery Path |
| --- | --- | --- | --- |
| 1 | <entry point> | <observable result> | <recovery path> |

## MVP Acceptance Criteria

| ID | Criterion | Evidence Required |
| --- | --- | --- |
| MVP-AC-001 | <criterion> | <test, demo, screenshot, command, artifact diff, or user validation> |

## Launch Readiness

| Area | Minimum Evidence | Owner |
| --- | --- | --- |
| Product scope | <approved artifact or decision> | <role/person> |
| Technical feasibility | <system design section or spike evidence> | <role/person> |
| Validation | <QA or user validation evidence> | <role/person> |

## Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| <risk> | <impact> | <mitigation> |

## Scope Guardrails

- Implementation agents may build only the included capabilities.
- New capability requests must be added to `Excluded Capabilities`, the roadmap, or an approved PRD update before implementation.
- If MVP acceptance criteria cannot be validated, return to PM Agent before task execution continues.
