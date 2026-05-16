# Workflows

This directory will describe repeatable artifact workflows.

## Initial Workflow

1. Capture the idea in a project brief or PRD.
2. Define MVP scope and non-goals.
3. Produce a system design only for approved MVP scope.
4. Convert the design into a master plan.
5. Break the plan into folder-per-task artifacts.
6. Give one task folder to a Code Agent.
7. Review output against the task artifacts.
8. Record validation evidence.
9. Update upstream artifacts if implementation reveals a product or architecture mismatch.

## Workflow Rule

Every workflow step should produce or update a repository artifact. A step that only changes chat history is incomplete.

## Task Instance Workflow

Future task instances should use:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

Round 1 should migrate the transitional task templates into this model. Until then, `TASK_CONTRACT.md` maps to `task.md`, and `CODEX_EXECUTION_PLAN.md` maps to `plan.md`.
