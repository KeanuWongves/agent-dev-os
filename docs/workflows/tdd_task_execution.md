# TDD Task Execution Workflow

## Objective

Execute one task within its allowed scope while recording implementation and validation evidence.

## Responsible Role

Code Agent.

## Required Inputs

- One task folder with `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md`.
- Source artifacts named by the task.
- Required tests, commands, acceptance criteria, and stop conditions.

## Procedure

1. Read `task.md`, `plan.md`, and source artifacts.
2. Stop if artifacts are missing, contradictory, or require out-of-scope work.
3. Write or update tests before implementation.
4. If TDD is not applicable, record the reason and alternative validation method in `test.md` before implementation starts.
5. Implement the smallest change that satisfies acceptance criteria.
6. Run required commands and manual checks.
7. Record commands, results, not-run tests, alternative validation, and remaining risk in `test.md`.
8. Record summary, files changed, design decisions, deviations, assumptions, follow-ups, and risks in `implementation.md`.
9. Prepare handoff to Review Agent.

## Required Outputs

- Implementation changes within allowed scope.
- Updated `implementation.md`.
- Updated `test.md`.
- Final execution summary.

## Verification Rules

- Tests must be written or updated before implementation unless explicitly not applicable.
- If TDD is not applicable, the alternative validation method must be recorded before implementation starts.
- Validation evidence must include command, working directory, exit code, result summary, and relevant observations.
- No acceptance criterion may be marked met without evidence.

## Common Failure Modes

- Implementing before recording TDD decision.
- Expanding scope to adjacent cleanup.
- Adding dependencies or runtime systems not authorized by task.
- Reporting "manual test passed" without steps and observations.

## Handoff to Next Workflow

Hand off to code review with task folder, changed files, implementation notes, test evidence, known risks, allowed scope, required evidence, next owner role, and stop conditions.
