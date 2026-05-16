# Task Planning Workflow

## Objective

Convert approved product, architecture, and master-plan artifacts into strict folder-per-task work.

## Responsible Role

Task Manager Agent, using Lead Agent planning outputs.

## Required Inputs

- `management/MASTER_PLAN.md`
- `management/TASK_BOARD.md`
- Relevant product artifacts.
- Relevant architecture artifacts.
- Dependencies, validation gates, and current workflow state.

## Procedure

1. Read the master plan, task board, source product artifacts, and source architecture artifacts.
2. Choose one narrow task outcome.
3. Create `tasks/TASK-XXX-short-title/`.
4. Fill `task.md` with objective, background, source artifacts, allowed changes, forbidden changes, files to inspect, expected edit surface, requirements, acceptance criteria, tests, commands, stop conditions, and handoffs.
5. Fill `plan.md` with task reference, files to inspect, proposed edit surface, step plan, TDD plan, risks, rollback plan, and stop conditions.
6. Add blank but structured `implementation.md`, `test.md`, and `review.md`.
7. Update task board and task graph.
8. Move task to `Ready` only when blockers are resolved.

## Required Outputs

- Complete task folder:
  - `task.md`
  - `plan.md`
  - `implementation.md`
  - `test.md`
  - `review.md`
- Updated task board.
- Updated task graph when used.
- Codex-ready execution prompt when needed.

## Verification Rules

- Task objective has exactly one observable outcome.
- Allowed paths are exact.
- Acceptance criteria are observable and have evidence requirements.
- Required tests and commands are named or explicitly marked not applicable with reasons.
- Handoff fields include source artifact, target artifact, allowed scope, required evidence, next owner role, and stop conditions.

## Common Failure Modes

- Creating broad tasks that hide multiple outcomes.
- Leaving generic placeholders.
- Marking a task ready without validation method.
- Allowing implementation scope outside approved product or architecture artifacts.

## Handoff to Next Workflow

Hand off to TDD task execution with one task folder, allowed scope, required tests, required commands, stop conditions, next owner role, and expected final evidence.
