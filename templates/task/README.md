# Task Templates

Task templates convert approved product and architecture artifacts into bounded folder-per-task work for AI coding agents.

Copy these files into a project-specific task directory instead of editing the templates in place:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

## Canonical Templates

| Template | Primary Owner Role | Purpose |
| --- | --- | --- |
| `task.md` | Task Manager Agent | Defines source artifacts, allowed scope, forbidden scope, acceptance criteria, dependencies, and handoff conditions. |
| `plan.md` | Task Manager Agent | Defines the execution sequence, planned edit surface, TDD or validation approach, required commands, and stop conditions. |
| `implementation.md` | Code Agent | Records scope confirmation, changed files, execution log, acceptance status, decisions, and risks. |
| `test.md` | Code Agent or QA Agent | Records TDD decision, validation matrix, commands, manual checks, untested areas, and QA decision. |
| `review.md` | Review Agent | Records verdict, findings, contract compliance, scope check, acceptance review, and handoff. |

## Compatibility Templates

`TASK_CONTRACT.md` and `CODEX_EXECUTION_PLAN.md` are transitional compatibility templates. Keep them for older task instances, but new task instances should use the canonical files above.

| Compatibility Template | Canonical Replacement |
| --- | --- |
| `TASK_CONTRACT.md` | `task.md` |
| `CODEX_EXECUTION_PLAN.md` | `plan.md` |

Implementation notes, validation evidence, and review findings belong in task-local `implementation.md`, `test.md`, and `review.md` files, not in chat-only summaries.
