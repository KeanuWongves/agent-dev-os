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
- Gate 3 approval recorded in `management/APPROVALS.md`.

## Procedure

1. Read the master plan, task board, source product artifacts, and source architecture artifacts.
2. Choose one narrow task outcome.
3. Create `tasks/TASK-XXX-short-title/`.
4. Fill `task.md` with objective, background, source artifacts, allowed changes, forbidden changes, files to inspect, expected edit surface, requirements, acceptance criteria, tests, commands, stop conditions, and handoffs.
5. Fill `plan.md` with task reference, files to inspect, proposed edit surface, step plan, TDD plan, risks, rollback plan, and stop conditions.
6. Add blank but structured `implementation.md`, `test.md`, and `review.md`.
7. Update task board and task graph.
8. Identify whether the task is non-trivial or high-risk.
9. Hand off non-trivial or high-risk tasks to Gate 4: Task Plan Approval before moving them to `Ready`.
10. Move low-risk tasks to `Ready` only when blockers are resolved and the task board records why Gate 4 is not required.

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
- Gate 4 approval request or approval record when a non-trivial or high-risk task may become `Ready`.

## Verification Rules

- Task objective has exactly one observable outcome.
- Allowed paths are exact.
- Acceptance criteria are observable and have evidence requirements.
- Required tests and commands are named or explicitly marked not applicable with reasons.
- Handoff fields include source artifact, target artifact, allowed scope, required evidence, next owner role, and stop conditions.
- Non-trivial or high-risk tasks may be marked `Ready` only after Gate 4 approval is recorded in `management/APPROVALS.md`.
- Low-risk tasks that skip Gate 4 must record the waiver or not-required rationale in `management/TASK_BOARD.md`.

High-risk signals include new dependencies, new runtime surfaces, credentials, external APIs, scraping, data privacy risk, license risk, broad refactors, unclear validation, or source/test paths that are not already authorized by approved architecture.

## Common Failure Modes

- Creating broad tasks that hide multiple outcomes.
- Leaving generic placeholders.
- Marking a task ready without validation method.
- Allowing implementation scope outside approved product or architecture artifacts.

## Handoff to Next Workflow

Hand off non-trivial or high-risk task folders to Gate 4 with task contract, plan, allowed scope, validation method, TDD or alternative validation plan, risks, and stop conditions.

After Gate 4 is recorded, hand off to TDD task execution with one task folder, approval record, allowed scope, required tests, required commands, stop conditions, next owner role, and expected final evidence.
