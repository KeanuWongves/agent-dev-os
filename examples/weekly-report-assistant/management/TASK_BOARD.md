# Task Board: Weekly Report Assistant

Template rule: only tasks with a complete folder may move to `Ready`.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Task Manager Agent |
| Last Updated | 2026-05-17 |
| Source Plan | `management/MASTER_PLAN.md` |
| State Mirror | `state/task_graph.yaml` |

## Board Policy

Code Agents should pick one `Ready` task at a time. A task is not `Ready` until `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md` exist and the task contract names allowed scope, acceptance criteria, required tests, and stop conditions.

## Status Columns

- `Backlog`: identified but not yet contracted.
- `Ready`: task folder exists and dependencies are satisfied.
- `In Progress`: assigned to a Code Agent.
- `Review`: implementation complete, awaiting review.
- `Validation`: review accepted, awaiting validation evidence.
- `Done`: validation criteria met.
- `Blocked`: cannot progress without a decision or dependency.

## Tasks

| Task ID | Title | Status | Task Folder | Depends On | Owner | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| TASK-001 | Create commit summary template | Ready | `tasks/TASK-001-create-commit-summary-template/` | None | Code Agent, unassigned | Artifact-only task; creates `product/COMMIT_SUMMARY_TEMPLATE.md` and updates task-local evidence only. |

## Blockers

| Task ID | Blocker | Owner | Next Action | Required Artifact |
| --- | --- | --- | --- | --- |
| N/A | No active blockers for TASK-001 readiness. | Task Manager Agent | Assign Code Agent when ready to execute. | `tasks/TASK-001-create-commit-summary-template/task.md` |

## Board Review Checklist

- [x] Every `Ready` task has a complete task folder.
- [x] Every `Ready` task names allowed paths and validation evidence.
- [x] Every `In Progress` task has exactly one current owner. N/A - no task is in progress.
- [x] Blocked tasks name a concrete next action. N/A - no blocked task.
- [ ] Done tasks link to review and validation evidence. N/A until TASK-001 is executed and validated.
