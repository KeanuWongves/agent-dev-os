# Workflows

This directory describes repeatable artifact workflows.

## Initial Workflow

1. Capture the idea in a project brief or research brief.
2. Run reference research when external references, repositories, products, creators, papers, screenshots, or reuse decisions may influence scope.
3. Feed research findings into product discovery.
4. Define PRD, MVP scope, and non-goals.
5. Produce a system design only for approved MVP scope.
6. Convert the design into a master plan.
7. Break the plan into folder-per-task artifacts.
8. Give one task folder to a Code Agent.
9. Review output against the task artifacts.
10. Record validation evidence.
11. Update upstream artifacts if implementation reveals a product or architecture mismatch.

## Workflow Rule

Every workflow step should produce or update a repository artifact. A step that only changes chat history is incomplete.

## Task Instance Workflow

Task instances should use:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

Canonical templates now exist for this model. `TASK_CONTRACT.md` maps to `task.md`, and `CODEX_EXECUTION_PLAN.md` maps to `plan.md` for older task instances.

## Detailed Workflows

- `reference_research.md`
- `product_discovery.md`
- `architecture_planning.md`
- `task_planning.md`
- `tdd_task_execution.md`
- `code_review.md`
- `qa_validation.md`
- `release.md`
