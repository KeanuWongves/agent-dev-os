# Task Board: <Project Name>

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Planning Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Plan | <MASTER_PLAN.md path> |

## Board Policy

Only tasks with a task contract may move to `Ready`. Execution agents should pick one `Ready` task at a time.

## Status Columns

- `Backlog`: identified but not yet contracted.
- `Ready`: task contract exists and dependencies are satisfied.
- `In Progress`: assigned to an execution agent.
- `Review`: implementation complete, awaiting review.
- `Validation`: review accepted, awaiting validation evidence.
- `Done`: validation criteria met.
- `Blocked`: cannot progress without a decision or dependency.

## Tasks

| Task ID | Title | Status | Contract | Depends On | Owner | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| TASK-001 | <title> | Backlog | <path> | <dependencies> | <role/person> | <notes> |

## Blockers

| Task ID | Blocker | Owner | Next Action |
| --- | --- | --- | --- |
| <task> | <blocker> | <owner> | <action> |

## Board Review Checklist

- Every `Ready` task has a contract.
- Every `In Progress` task has exactly one current owner.
- Blocked tasks name a concrete next action.
- Done tasks link to validation evidence.
