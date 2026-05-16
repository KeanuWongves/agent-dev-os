# Roadmap: <Project Name>

Template rule: roadmap milestones describe product outcomes, not implementation task dumps.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent, PM Agent, or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `product/PRD.md`, `product/MVP.md` |
| Downstream Consumers | `management/MASTER_PLAN.md`, `management/TASK_BOARD.md` |

## Release Strategy

<Explain how the product should progress from MVP to later versions. Keep this outcome-oriented and state explicit non-goals for each phase.>

## Milestones

| Milestone | Outcome | Scope | Exit Criteria | Target |
| --- | --- | --- | --- | --- |
| M0 | Artifact-ready MVP plan | PRD, MVP, design, task board | Approved artifacts exist | <date or sequence> |
| M1 | <outcome> | <scope> | <evidence> | <date or sequence> |

## Dependency Map

| Dependency | Needed By | Owner | Status | Notes |
| --- | --- | --- | --- | --- |
| <dependency> | <milestone/task> | <owner> | Draft | <notes> |

## Deferred Ideas

| Idea | Reason Deferred | Revisit Trigger | Parking Artifact |
| --- | --- | --- | --- |
| <idea> | <reason> | <trigger> | <path or issue> |

## Review Cadence

| Trigger | Required Review | Output |
| --- | --- | --- |
| MVP scope changes | PM Agent review | Updated `product/MVP.md` and roadmap row |
| Technical feasibility changes | Architect Agent review | Updated architecture decision |
| Milestone validated | Lead Agent review | Updated status and next milestone decision |

## Roadmap Review Checklist

- Each milestone maps to product outcomes.
- MVP scope is not expanded silently.
- Dependencies are explicit.
- Deferred work is captured without becoming active scope.
- Downstream task planning can point to milestone exit criteria.
