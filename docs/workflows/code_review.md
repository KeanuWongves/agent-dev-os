# Code Review Workflow

## Objective

Evaluate completed task work against task artifacts, validation evidence, and architecture constraints.

## Responsible Role

Review Agent.

## Required Inputs

- Task folder.
- Changed files or diff.
- Implementation log.
- Test and validation evidence.
- Relevant product and architecture artifacts.

## Procedure

1. Read `task.md`, `plan.md`, `implementation.md`, and `test.md`.
2. Inspect changed files or diff.
3. Compare actual changes with allowed changes and expected edit surface.
4. Confirm acceptance criteria were not modified to fit the implementation.
5. Review validation evidence for completeness.
6. Check architecture and code-rule compliance.
7. Record findings by severity with location, evidence, and required change.
8. Decide `Approved`, `Changes Requested`, or `Blocked`.
9. Complete QA handoff only if review can proceed to validation.

## Required Outputs

- Updated `review.md`.
- Findings ordered by severity.
- Scope compliance table.
- Acceptance criteria compliance table.
- Test evidence review.
- Architecture compliance and required fixes.

## Verification Rules

- Review Agents must not implement fixes while acting as reviewer.
- A review verdict must cite artifacts or diff evidence.
- Missing validation evidence blocks approval or must be explicitly accepted as a risk by the task contract.
- Out-of-scope changes must be findings.

## Common Failure Modes

- Reviewing only the diff and ignoring task artifacts.
- Fixing issues instead of recording findings.
- Accepting weak validation because the code appears correct.
- Rewriting acceptance criteria after implementation.

## Handoff to Next Workflow

Hand off accepted work to QA validation with review report, validation evidence, required checks, allowed validation scope, next owner role, and stop conditions. Return rejected work to Task Manager Agent or Code Agent with required fixes.
