# Task Board: <Project Name>

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Task Manager Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Plan | <MASTER_PLAN.md path> |

## Board Policy

Only tasks with a task folder may move to `Ready`. Code Agents should pick one `Ready` task at a time.

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
| TASK-001 | <title> | Backlog | `tasks/TASK-001-short-title/` | <dependencies> | <role/person> | <notes> |

## Blockers

| Task ID | Blocker | Owner | Next Action |
| --- | --- | --- | --- |
| <task> | <blocker> | <owner> | <action> |

## Board Review Checklist

- Every `Ready` task has a task folder with `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md`.
- Every `In Progress` task has exactly one current owner.
- Blocked tasks name a concrete next action.
- Done tasks link to validation evidence.
