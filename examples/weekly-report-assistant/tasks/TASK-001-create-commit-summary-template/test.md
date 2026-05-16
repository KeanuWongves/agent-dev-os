# Test and Validation Evidence: TASK-001 create-commit-summary-template

This validation artifact is adapted from `templates/task/test.md` for TASK-001. Code Agents record implementation validation here; QA Agents extend it with independent validation when assigned.

Template rule: validation evidence must be exact enough for another agent to rerun or inspect. Do not write "tested manually" without observations and expected results.

## Metadata

| Field | Value |
| --- | --- |
| Status | Draft |
| Current Owner Role | Code Agent |
| Task ID | TASK-001 |
| Task Folder | `tasks/TASK-001-create-commit-summary-template/` |
| Source Task | `tasks/TASK-001-create-commit-summary-template/task.md` |
| Source Plan | `tasks/TASK-001-create-commit-summary-template/plan.md` |
| Implementation Artifact | `tasks/TASK-001-create-commit-summary-template/implementation.md` |
| Last Updated | 2026-05-17 |
| Validated By | Unassigned |

## TDD Status

| Field | Value |
| --- | --- |
| TDD Required By Task | No - task creates a Markdown artifact and no executable product code is allowed. |
| Tests Written or Updated Before Implementation | No - execution has not started; Code Agent must record alternative validation before creating the template. |
| First Test Change Timestamp | N/A - task not executed. |
| Implementation Started After Test Evidence | N/A - task not executed. |

## Tests Written Before Implementation

| Test ID | Path or Check | Acceptance Criteria | Expected Initial Result | Actual Initial Result |
| --- | --- | --- | --- | --- |
| T-001 | Alternative validation record in this file | AC-006 | Code Agent records TDD-not-applicable reason before template creation. | Not Run |

## Commands Run

| Timestamp | Command | Working Directory | Exit Code | Result Summary |
| --- | --- | --- | --- | --- |
| N/A | N/A | N/A | N/A | TASK-001 has not been executed. |

## Results

| Validation ID | Acceptance Criteria | Type | Command or Manual Check | Expected Result | Actual Result | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| VAL-001 | AC-006 | artifact/manual | Before creating `product/COMMIT_SUMMARY_TEMPLATE.md`, update this file with the TDD-not-applicable reason and validation plan. | Alternative validation is recorded before implementation. | Not executed yet. | Not Run | Pending Code Agent execution. |
| VAL-002 | AC-001 | static command | `test -f examples/weekly-report-assistant/product/COMMIT_SUMMARY_TEMPLATE.md` | Command exits 0 after implementation. | Not executed yet. | Not Run | Pending template creation. |
| VAL-003 | AC-002, AC-003 | manual inspection | Inspect template for API-001 required fields and five primary groups. | All required fields and groups are present. | Not executed yet. | Not Run | Pending template creation. |
| VAL-004 | AC-004 | manual inspection | Inspect template for missing-evidence, unknown-metric, ambiguity, and review-needed guidance. | All guidance exists and is user-visible. | Not executed yet. | Not Run | Pending template creation. |
| VAL-005 | AC-005 | static command | Run no-code/dependency scan and changed-file scope check from `task.md`. | No source/dependency files appear; changed files stay in allowed scope. | Not executed yet. | Not Run | Pending implementation diff. |
| VAL-006 | AC-006 | artifact/manual | Inspect `implementation.md` and this `test.md` after execution. | Evidence, gaps, risks, and AC statuses are recorded. | Not executed yet. | Not Run | Pending Code Agent update. |

## Not-run Tests

| Test or Area | Acceptance Criteria | Why Not Run | Risk | Follow-Up |
| --- | --- | --- | --- | --- |
| All TASK-001 validation | AC-001 through AC-006 | Task has not been executed. | Review and QA cannot proceed. | Execute TASK-001. |

## Alternative Validation Method If TDD Was Not Applicable

| Field | Value |
| --- | --- |
| Reason TDD Was Not Applicable | Planned: no executable code or test code is allowed; deliverable is a Markdown artifact. Code Agent must confirm this before implementation starts. |
| Alternative Method | Planned: manual artifact inspection against API-001, file existence check, no-code/dependency scan, changed-file scope check, and task-local evidence inspection. |
| Approved By Source Artifact | `task.md` T-001 and `plan.md` VAL-001 |
| Evidence Captured | Pending VAL-001 through VAL-006 |

## Manual Checks

| Check ID | Acceptance Criteria | Steps | Observation | Result |
| --- | --- | --- | --- | --- |
| MAN-001 | AC-002, AC-003 | Inspect `product/COMMIT_SUMMARY_TEMPLATE.md` for required fields and group definitions. | Not executed yet. | Not Run |
| MAN-002 | AC-004 | Inspect template guidance for missing evidence, unknown metrics, ambiguous groups, and review-needed entries. | Not executed yet. | Not Run |
| MAN-003 | AC-006 | Inspect task-local implementation and test artifacts for evidence completeness. | Not executed yet. | Not Run |

## Remaining Risk

| Risk | Source | Impact | Follow-Up |
| --- | --- | --- | --- |
| Template usability is unknown before execution. | TASK-001 not executed. | MVP workflow may still be too heavy. | Execute TASK-001 and document friction or gaps. |
| No validation evidence exists yet. | TASK-001 not executed. | Review and QA are blocked. | Run required checks after implementation. |

## QA Decision

| Field | Value |
| --- | --- |
| Decision | Not Run |
| Decision Rationale | QA cannot decide before TASK-001 is implemented and validation evidence is recorded. |
| Remaining Risk | All acceptance criteria are untested. |
| Follow-Up Tasks Required | Execute TASK-001; no new task required yet. |

## Handoff After Validation

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-001-create-commit-summary-template/test.md` |
| Target Artifact | `tasks/TASK-001-create-commit-summary-template/review.md` after Code Agent execution; `management/VALIDATION_STATUS.md` after QA. |
| Allowed Scope | Validation-only updates after implementation. |
| Required Evidence | VAL-001 through VAL-006 and QA decision. |
| Next Owner Role | Review Agent after Code Agent execution; QA Agent after review approval. |
| Stop Conditions | Failed validation, blocked check, untested acceptance criteria, or missing evidence. |
