# Workflows

This directory describes repeatable artifact workflows.

## Initial Workflow

1. Capture the idea in a project brief or research brief.
2. Run reference research when external references, repositories, products, creators, papers, screenshots, or reuse decisions may influence scope.
3. Record required human review gate approvals or waivers before downstream artifacts treat scope as approved.
4. Feed approved or waived research findings into product discovery.
5. Define PRD, MVP scope, and non-goals.
6. Produce a system design only for approved MVP scope.
7. Convert the design into a master plan.
8. Break the plan into folder-per-task artifacts.
9. Give one approved task folder to a Code Agent.
10. Review output against the task artifacts.
11. Record validation evidence.
12. Update upstream artifacts if implementation reveals a product or architecture mismatch.

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
- `human_review_gates.md`
- `product_discovery.md`
- `architecture_planning.md`
- `task_planning.md`
- `tdd_task_execution.md`
- `code_review.md`
- `qa_validation.md`
- `release.md`
