# Task Board: <Project Name>

Template rule: only tasks with a complete folder may move to `Ready`.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Task Manager Agent or human owner> |
| Last Updated | YYYY-MM-DD |
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
| TASK-001 | <title> | Backlog | `tasks/TASK-001-short-title/` | <dependencies> | <role/person> | <notes> |

## Blockers

| Task ID | Blocker | Owner | Next Action | Required Artifact |
| --- | --- | --- | --- | --- |
| <task> | <blocker> | <owner> | <action> | <path> |

## Board Review Checklist

- [ ] Every `Ready` task has a complete task folder.
- [ ] Every `Ready` task names allowed paths and validation evidence.
- [ ] Every `In Progress` task has exactly one current owner.
- [ ] Blocked tasks name a concrete next action.
- [ ] Done tasks link to review and validation evidence.
