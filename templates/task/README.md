# Task Templates

Task templates convert approved product and architecture artifacts into bounded work for Code Agents.

Use `TASK_CONTRACT.md` before any implementation. Use `CODEX_EXECUTION_PLAN.md` when a task is ready to hand to Codex or another coding agent.

Task artifacts should be copied into a project-specific task directory instead of edited in place.

## Direction for Round 1

Future task instances should use this folder-per-task model:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

Current template mapping:

| Current Template | Round 1 Target |
| --- | --- |
| `TASK_CONTRACT.md` | `task.md` |
| `CODEX_EXECUTION_PLAN.md` | `plan.md` |

`implementation.md`, `test.md`, and `review.md` should become explicit task-local artifacts instead of being scattered across chat summaries.
