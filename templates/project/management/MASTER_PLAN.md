# Master Plan: <Project Name>

Template rule: do not break work into executable tasks until product and architecture inputs are coherent enough to constrain scope.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `product/PRD.md`, `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |
| Downstream Consumers | `management/TASK_BOARD.md`, `tasks/`, `state/task_graph.yaml` |

## Objective

<State the implementation objective for the current planning cycle.>

## Workstreams

| Workstream | Outcome | Source Artifact | Owner Role |
| --- | --- | --- | --- |
| <workstream> | <outcome> | <artifact section> | <role> |

## Sequencing

| Sequence | Task or Milestone | Depends On | Exit Criteria |
| --- | --- | --- | --- |
| 1 | <task/milestone> | <dependency> | <evidence> |

## Task Breakdown

| Task ID | Title | Scope | Required Artifact | Status |
| --- | --- | --- | --- | --- |
| TASK-001 | <title> | <narrow scope> | `tasks/TASK-001-short-title/` | Draft |

## Validation Gates

| Gate | Applies To | Evidence Required | Owner |
| --- | --- | --- | --- |
| <gate> | <task/milestone> | <commands, tests, review, demo> | <role> |

## Risks and Watchpoints

| Risk | Trigger | Response |
| --- | --- | --- |
| <risk> | <signal> | <action> |

## Plan Update Rules

- If product scope changes, update `product/PRD.md` or `product/MVP.md` first.
- If design constraints change, update `architecture/SYSTEM_DESIGN.md` or `architecture/DECISIONS.md` before task folders.
- If task ordering changes, update this plan, `management/TASK_BOARD.md`, and `state/task_graph.yaml`.
