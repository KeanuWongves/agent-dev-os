# QA Validation Workflow

## Objective

Validate reviewed work with exact evidence and update validation artifacts.

## Responsible Role

QA Agent.

## Required Inputs

- Task folder.
- Review report that allows QA to proceed.
- Required validation gates.
- Commands, environment, data, or manual checks available for validation.

## Procedure

1. Confirm review verdict and blocking findings.
2. Read task acceptance criteria and validation gates.
3. Run required commands and manual checks where available.
4. Record command, working directory, exit code, result summary, expected result, and actual result.
5. Record manual check steps, observations, and result.
6. Mark untested or partially tested criteria with risk and follow-up.
7. Update task-local `test.md` and project `management/VALIDATION_STATUS.md` when assigned.
8. Decide pass, fail, partial, or blocked.

## Required Outputs

- Updated validation evidence.
- Updated validation status when assigned.
- Pass, fail, partial, or blocked decision.
- Follow-up tasks or blockers for unresolved validation gaps.

## Verification Rules

- QA must not mark work validated from confidence alone.
- Every validated criterion must have exact evidence.
- Untested acceptance criteria must be listed.
- Failed checks must remain visible.

## Common Failure Modes

- Treating review approval as validation.
- Omitting failed or blocked checks.
- Replacing exact commands with vague summaries.
- Ignoring acceptance criteria that are hard to test.

## Handoff to Next Workflow

Hand off validated work to release or management status update with validation status, evidence, remaining risk, next owner role, and stop conditions. Hand off failed or blocked validation to Task Manager Agent with evidence and required next action.
