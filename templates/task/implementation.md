# Implementation Log: <TASK-ID> <short-title>

Copy this file to `tasks/TASK-XXX-short-title/implementation.md`. Code Agents update this artifact while executing the task.

Template rule: record evidence as work happens. Do not mark acceptance criteria complete without matching validation evidence in `test.md`.

Pre-execution rule: a `Ready` task may have a Draft `implementation.md` as long as this file is structurally prepared and does not claim implementation, validation, review, or completion.

## Metadata

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner Role | Code Agent |
| Task ID | <TASK-XXX> |
| Task Folder | `tasks/TASK-XXX-short-title/` |
| Source Task | `tasks/TASK-XXX-short-title/task.md` |
| Source Plan | `tasks/TASK-XXX-short-title/plan.md` |
| Test Artifact | `tasks/TASK-XXX-short-title/test.md` |
| Last Updated | YYYY-MM-DD |
| Implemented By | <agent or human> |

## Pre-execution Status Convention

Use these values consistently before execution:

- `Pending`: expected evidence or action has not happened yet.
- `Not Run`: a command, check, validation item, or review item has not been performed.
- `Not Started`: implementation work or acceptance-criteria progress has not begun.
- `Blocked`: progress cannot continue because a required artifact, decision, environment, or prior result is missing.

Before execution, keep implementation summary, scope confirmation, files changed, execution log, and acceptance-criteria status in `Pending`, `Not Run`, or `Not Started` states. Do not use `Met`, `Complete`, `Approved`, or `Validated` until evidence exists in `test.md`.

## Implementation Summary

<summarize the delivered change in 3-5 factual sentences. Include the acceptance criteria targeted and whether the task stayed inside scope.>

## Scope Confirmation

| Check | Result | Notes |
| --- | --- | --- |
| Read `task.md` before editing | <Yes/No> | <notes> |
| Read `plan.md` before editing | <Yes/No> | <notes> |
| Allowed scope is clear | <Yes/No> | <notes> |
| Stop conditions checked | <Yes/No> | <notes> |
| No out-of-scope files changed | <Yes/No> | <notes> |

## TDD or Alternative Validation Record

| Field | Value |
| --- | --- |
| Tests Written or Updated Before Implementation | <Yes/No> |
| Test Paths | <paths or N/A - reason> |
| If No, Reason TDD Is Not Applicable | <reason or N/A> |
| Alternative Validation Recorded In `test.md` | <validation ID or N/A> |

## Files Changed

| Path | Change Type | Acceptance Criteria | Notes |
| --- | --- | --- | --- |
| <path> | <created/updated/deleted> | <AC IDs> | <what changed and why> |

## Design Decisions

| Decision | Source or Constraint | Why It Stayed In Scope | Artifact Updated |
| --- | --- | --- | --- |
| <decision or N/A - none> | <task.md, plan.md, source artifact, or N/A> | <scope rationale> | <path or N/A> |

## Deviations From Plan

| Planned Step or Surface | Deviation | Reason | Approval or Evidence |
| --- | --- | --- | --- |
| <step/path or N/A - none> | <what changed> | <why> | <task update, user instruction, or N/A> |

## Assumptions Made

| Assumption | Source or Rationale | Impact If Wrong | Follow-Up |
| --- | --- | --- | --- |
| <assumption or N/A - none> | <artifact path, command output, or reasoning> | <impact> | <task ID, artifact path, or N/A> |

## Execution Log

| Timestamp | Agent | Action | Evidence or Output |
| --- | --- | --- | --- |
| YYYY-MM-DD HH:MM | <agent> | <specific action> | <command output summary, artifact path, or diff reference> |

## Acceptance Criteria Status

| ID | Status | Evidence in `test.md` | Notes |
| --- | --- | --- | --- |
| AC-001 | <Met/Not Met/Partial/Blocked> | <VAL ID, command, or manual check> | <notes> |
| AC-002 | <Met/Not Met/Partial/Blocked> | <VAL ID, command, or manual check> | <notes> |

## Follow-up Items

| Item | Reason | Owner | Required Artifact |
| --- | --- | --- | --- |
| <follow-up or N/A - none> | <why it remains> | <role/person> | <task, backlog, decision, or N/A> |

## Risks and Gaps

| Risk or Gap | Impact | Mitigation or Follow-Up |
| --- | --- | --- |
| <risk, gap, or N/A - none known> | <impact> | <mitigation, task ID, or N/A> |

## Handoff to Review Agent

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-XXX-short-title/implementation.md` |
| Target Artifact | `tasks/TASK-XXX-short-title/review.md` |
| Allowed Scope | <confirmed allowed paths and changes> |
| Required Evidence | <validation IDs from test.md plus changed-file summary> |
| Next Owner Role | Review Agent |
| Stop Conditions | <failed validation, incomplete evidence, unresolved scope conflict, or known blocker> |
