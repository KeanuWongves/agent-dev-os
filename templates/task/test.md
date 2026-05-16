# Test and Validation Evidence: <TASK-ID> <short-title>

Copy this file to `tasks/TASK-XXX-short-title/test.md`. Code Agents record implementation validation here; QA Agents extend it with independent validation when assigned.

Template rule: validation evidence must be exact enough for another agent to rerun or inspect. Do not write "tested manually" without observations and expected results.

## Metadata

| Field | Value |
| --- | --- |
| Status | Draft |
| Current Owner Role | Code Agent |
| Task ID | <TASK-XXX> |
| Task Folder | `tasks/TASK-XXX-short-title/` |
| Source Task | `tasks/TASK-XXX-short-title/task.md` |
| Source Plan | `tasks/TASK-XXX-short-title/plan.md` |
| Implementation Artifact | `tasks/TASK-XXX-short-title/implementation.md` |
| Last Updated | YYYY-MM-DD |
| Validated By | <agent, QA Agent, or human> |

## TDD Status

| Field | Value |
| --- | --- |
| TDD Required By Task | <Yes/No> |
| Tests Written or Updated Before Implementation | <Yes/No> |
| First Test Change Timestamp | <YYYY-MM-DD HH:MM or N/A - reason> |
| Implementation Started After Test Evidence | <Yes/No/N/A - reason> |

## Tests Written Before Implementation

| Test ID | Path or Check | Acceptance Criteria | Expected Initial Result | Actual Initial Result |
| --- | --- | --- | --- | --- |
| T-001 | <path, command, manual check, or N/A - reason> | <AC IDs> | <fail/pass/static diff expectation> | <actual result or N/A> |

## Commands Run

| Timestamp | Command | Working Directory | Exit Code | Result Summary |
| --- | --- | --- | --- | --- |
| YYYY-MM-DD HH:MM | `<command>` | `<path>` | <0/nonzero/N/A> | <key output and conclusion> |

## Results

| Validation ID | Acceptance Criteria | Type | Command or Manual Check | Expected Result | Actual Result | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| VAL-001 | <AC IDs> | <unit/integration/static/artifact/manual> | `<command>` or <manual check steps> | <expected result> | <actual result> | <Pass/Fail/Partial/Blocked> | <output summary, screenshot path, artifact diff, or log path> |
| VAL-002 | <AC IDs> | <unit/integration/static/artifact/manual> | `<command>` or <manual check steps> | <expected result> | <actual result> | <Pass/Fail/Partial/Blocked> | <output summary, screenshot path, artifact diff, or log path> |

## Not-run Tests

| Test or Area | Acceptance Criteria | Why Not Run | Risk | Follow-Up |
| --- | --- | --- | --- | --- |
| <test/area or N/A - none> | <AC IDs or N/A> | <reason> | <risk> | <task ID, owner, or N/A> |

## Alternative Validation Method If TDD Was Not Applicable

| Field | Value |
| --- | --- |
| Reason TDD Was Not Applicable | <reason or N/A> |
| Alternative Method | <manual/static/artifact validation method or N/A> |
| Approved By Source Artifact | <task.md AC ID, plan.md validation ID, or N/A> |
| Evidence Captured | <VAL ID, artifact diff, command output, or N/A> |

## Manual Checks

| Check ID | Acceptance Criteria | Steps | Observation | Result |
| --- | --- | --- | --- | --- |
| MAN-001 | <AC IDs> | <step-by-step check> | <specific observation> | <Pass/Fail/Partial/Blocked> |

## Remaining Risk

| Risk | Source | Impact | Follow-Up |
| --- | --- | --- | --- |
| <risk or N/A - none known> | <untested area, failed command, assumption, or N/A> | <impact> | <task ID, artifact path, or N/A> |

## QA Decision

| Field | Value |
| --- | --- |
| Decision | <Pass/Fail/Partial/Blocked> |
| Decision Rationale | <brief evidence-based rationale> |
| Remaining Risk | <risk or N/A - none known> |
| Follow-Up Tasks Required | <task IDs or N/A> |

## Handoff After Validation

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-XXX-short-title/test.md` |
| Target Artifact | <task board, validation status artifact, or `tasks/TASK-XXX-short-title/review.md`> |
| Allowed Scope | <validation-only scope> |
| Required Evidence | <validation IDs and decision> |
| Next Owner Role | <Review Agent, QA Agent, Task Manager Agent, or Lead Agent> |
| Stop Conditions | <failed validation, blocked check, untested acceptance criteria, or missing evidence> |
