# Implementation Log: TASK-001 create-commit-summary-template

This implementation log is adapted from `templates/task/implementation.md` for TASK-001. Code Agents update this artifact while executing the task.

Template rule: record evidence as work happens. Do not mark acceptance criteria complete without matching validation evidence in `test.md`.

## Metadata

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner Role | Code Agent |
| Task ID | TASK-001 |
| Task Folder | `tasks/TASK-001-create-commit-summary-template/` |
| Source Task | `tasks/TASK-001-create-commit-summary-template/task.md` |
| Source Plan | `tasks/TASK-001-create-commit-summary-template/plan.md` |
| Test Artifact | `tasks/TASK-001-create-commit-summary-template/test.md` |
| Last Updated | 2026-05-17 |
| Implemented By | Unassigned |

## Implementation Summary

Not started. This artifact is prepared for future Code Agent execution of TASK-001. Do not mark acceptance criteria as met until `product/COMMIT_SUMMARY_TEMPLATE.md` exists and validation evidence is recorded in `test.md`.

## Scope Confirmation

| Check | Result | Notes |
| --- | --- | --- |
| Read `task.md` before editing | Pending | Code Agent must confirm during execution. |
| Read `plan.md` before editing | Pending | Code Agent must confirm during execution. |
| Allowed scope is clear | Pending | Must be confirmed before editing. |
| Stop conditions checked | Pending | Must be confirmed before editing. |
| No out-of-scope files changed | Pending | Must be confirmed after diff review. |

## TDD or Alternative Validation Record

| Field | Value |
| --- | --- |
| Tests Written or Updated Before Implementation | Pending |
| Test Paths | N/A - no test code is allowed for this artifact-only task. |
| If No, Reason TDD Is Not Applicable | Pending Code Agent update in `test.md` before implementation starts. |
| Alternative Validation Recorded In `test.md` | Pending VAL-001 |

## Files Changed

| Path | Change Type | Acceptance Criteria | Notes |
| --- | --- | --- | --- |
| `product/COMMIT_SUMMARY_TEMPLATE.md` | Pending create | AC-001, AC-002, AC-003, AC-004 | Not created yet. |
| `tasks/TASK-001-create-commit-summary-template/test.md` | Pending update | AC-005, AC-006 | Must record alternative validation and results. |
| `tasks/TASK-001-create-commit-summary-template/implementation.md` | Pending update | AC-006 | This artifact will be updated during execution. |

## Design Decisions

| Decision | Source or Constraint | Why It Stayed In Scope | Artifact Updated |
| --- | --- | --- | --- |
| Pending | N/A - task not executed. | N/A - task not executed. | N/A |

## Deviations From Plan

| Planned Step or Surface | Deviation | Reason | Approval or Evidence |
| --- | --- | --- | --- |
| N/A | No deviations recorded because execution has not started. | N/A | N/A |

## Assumptions Made

| Assumption | Source or Rationale | Impact If Wrong | Follow-Up |
| --- | --- | --- | --- |
| N/A | No execution assumptions recorded yet. | N/A | N/A |

## Execution Log

| Timestamp | Agent | Action | Evidence or Output |
| --- | --- | --- | --- |
| N/A | N/A | Execution has not started. | N/A |

## Acceptance Criteria Status

| ID | Status | Evidence in `test.md` | Notes |
| --- | --- | --- | --- |
| AC-001 | Not Started | Pending VAL-002 | Template file does not exist yet. |
| AC-002 | Not Started | Pending VAL-003 | Template field inspection pending. |
| AC-003 | Not Started | Pending VAL-003 | Grouping rubric inspection pending. |
| AC-004 | Not Started | Pending VAL-004 | Missing-evidence guidance inspection pending. |
| AC-005 | Not Started | Pending VAL-005 | No-code/dependency scan pending after execution. |
| AC-006 | Not Started | Pending VAL-001 and VAL-006 | Task-local evidence pending. |

## Follow-up Items

| Item | Reason | Owner | Required Artifact |
| --- | --- | --- | --- |
| Execute TASK-001 | The task is Ready but not implemented. | Code Agent | `product/COMMIT_SUMMARY_TEMPLATE.md`, task-local `test.md`, task-local `implementation.md` |

## Risks and Gaps

| Risk or Gap | Impact | Mitigation or Follow-Up |
| --- | --- | --- |
| No implementation evidence yet. | Review and QA cannot proceed. | Execute TASK-001 and record validation evidence. |

## Handoff to Review Agent

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-001-create-commit-summary-template/implementation.md` |
| Target Artifact | `tasks/TASK-001-create-commit-summary-template/review.md` |
| Allowed Scope | Pending confirmation after execution; expected scope is `product/COMMIT_SUMMARY_TEMPLATE.md`, task-local `implementation.md`, and task-local `test.md` only. |
| Required Evidence | Pending validation IDs from `test.md` plus changed-file summary. |
| Next Owner Role | Review Agent |
| Stop Conditions | Failed validation, incomplete evidence, unresolved scope conflict, or known blocker. |
