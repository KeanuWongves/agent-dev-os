# TDD Task Execution Workflow

## Objective

Execute one task within its allowed scope while recording implementation and validation evidence.

## Responsible Role

Code Agent.

## Required Inputs

- One task folder with `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md`.
- Source artifacts named by the task.
- Required tests, commands, acceptance criteria, and stop conditions.
- Gate 4 approval record when the task is non-trivial or high-risk.

## Procedure

1. Read `task.md`, `plan.md`, and source artifacts.
2. Stop if artifacts are missing, contradictory, or require out-of-scope work.
3. Write or update tests before implementation.
4. If TDD is not applicable, record the reason and alternative validation method in `test.md` before implementation starts.
5. Implement the smallest change that satisfies acceptance criteria.
6. Stop and hand off to Gate 5: Implementation Exception Review if execution requires scope expansion, new dependencies, new runtime surfaces, credentials, external APIs, scraping, or unresolved validation gaps.
7. Run required commands and manual checks.
8. Record commands, results, not-run tests, alternative validation, and remaining risk in `test.md`.
9. Record summary, files changed, design decisions, deviations, assumptions, follow-ups, and risks in `implementation.md`.
10. Prepare handoff to Review Agent.

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
- Gate 5 approval is required before continuing any out-of-scope implementation or unresolved validation exception.
- Code Agent must not add dependencies, runtime surfaces, credentials, external APIs, scraping, validation scripts, or broader file changes without a Gate 5 approval record in `management/APPROVALS.md`.

## Common Failure Modes

- Implementing before recording TDD decision.
- Expanding scope to adjacent cleanup.
- Adding dependencies or runtime systems not authorized by task.
- Reporting "manual test passed" without steps and observations.

## Handoff to Next Workflow

If no exception occurred, hand off to code review with task folder, changed files, implementation notes, test evidence, known risks, allowed scope, required evidence, next owner role, and stop conditions.

If an exception occurred, stop and hand off to Gate 5 with task folder, exception rationale, changed-file summary, validation gap, risk, proposed upstream artifact updates, and requested decision.
