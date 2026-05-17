# Master Plan: <Project Name>

Template rule: do not break work into executable tasks until product and architecture inputs are coherent enough to constrain scope.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `product/PRD.md`, `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |
| Human Review Gates | `management/HUMAN_REVIEW_GATES.md` |
| Approval Log | `management/APPROVALS.md` |
| Required Human Gate | <Gate 3 / Gate 4 / none> |
| Approval Status | <not required / pending / approved / waived / blocked> |
| Approval Artifact | <APPROVALS row ID or path> |
| Next Human Decision Needed | <decision or N/A> |
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

## Human Approval Gates

| Gate | Applies To | Approval Status | Approval Artifact | Next Human Decision Needed |
| --- | --- | --- | --- | --- |
| Gate 3: Architecture Approval | <architecture/planning dependency> | <pending / approved / waived / blocked> | `management/APPROVALS.md#<id>` | <decision or N/A> |
| Gate 4: Task Plan Approval | <non-trivial or high-risk tasks> | <pending / approved / waived / blocked> | `management/APPROVALS.md#<id>` | <decision or N/A> |

## Task Breakdown

| Task ID | Title | Scope | Required Artifact | Required Human Gate | Approval Status | Status |
| --- | --- | --- | --- | --- | --- | --- |
| TASK-001 | <title> | <narrow scope> | `tasks/TASK-001-short-title/` | <Gate 4 / none> | <pending / approved / waived / blocked> | Draft |

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
