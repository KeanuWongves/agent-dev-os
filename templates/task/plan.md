# Plan: <TASK-ID> <short-title>

Copy this file to `tasks/TASK-XXX-short-title/plan.md`. Do not edit this template in place for project work.

Template rule: every implementation step must trace to an acceptance criterion in `task.md`. If TDD is not applicable, record the reason and alternative validation in `test.md` before implementation starts.

## Task Contract Reference

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner Role | Task Manager Agent |
| Task ID | <TASK-XXX> |
| Task Folder | `tasks/TASK-XXX-short-title/` |
| Source Task Contract | `tasks/TASK-XXX-short-title/task.md` |
| Last Updated | YYYY-MM-DD |
| Prepared By | <Task Manager Agent or human owner> |
| Execution Owner | <Code Agent, human owner, or unassigned> |

## Files to Inspect

| Path | Required Section or Lines | Purpose |
| --- | --- | --- |
| `tasks/TASK-XXX-short-title/task.md` | All sections | Confirm objective, scope, acceptance criteria, required tests, and stop conditions. |
| <source artifact path> | <section or IDs> | <specific decision or constraint to follow> |
| <source/test path> | <section or lines, or N/A - reason> | <existing behavior or pattern to inspect> |

## Proposed Edit Surface

| Path | Change Type | Acceptance Criteria | Notes |
| --- | --- | --- | --- |
| <exact path> | <create/update/delete/N/A - reason> | <AC IDs> | <specific expected change> |

## Execution Strategy

<describe the smallest coherent approach that satisfies the acceptance criteria without expanding scope.>

## Step-by-step Plan

| Step | Owner Role | Action | Traces To | Expected Output |
| --- | --- | --- | --- | --- |
| 1 | Code Agent | Read `task.md`, this plan, and source artifacts. Stop if they conflict. | All ACs | Confirmed execution context. |
| 2 | Code Agent | Write or update tests first. If not applicable, record the reason and alternative validation in `test.md`. | <AC IDs> | Test change or documented alternative validation. |
| 3 | Code Agent | Make the minimum implementation or artifact change within allowed scope. | <AC IDs> | Changed files listed in `implementation.md`. |
| 4 | Code Agent | Run required validation commands and manual checks. | <AC IDs> | Results recorded in `test.md`. |
| 5 | Code Agent | Update `implementation.md` with summary, files changed, design decisions, deviations, assumptions, follow-ups, and known risks. | All ACs | Handoff-ready implementation notes. |
| 6 | Review Agent | Review diff, task artifacts, implementation notes, and validation evidence. | All ACs | `review.md` verdict and findings. |

## TDD Plan

| Field | Value |
| --- | --- |
| Tests To Write or Update First | <exact test paths, checks, or N/A - reason> |
| Expected First Failing Signal | <test failure, static check, artifact diff expectation, or N/A - reason> |
| Implementation May Start After | <test exists, failing signal captured, or alternative validation recorded> |
| Alternative Validation If TDD Is Not Applicable | <manual/static/artifact validation method or N/A> |
| Artifact Where Decision Is Recorded | `tasks/TASK-XXX-short-title/test.md` |

## Required Commands

```bash
<command>
```

If no command is applicable, replace the block with `N/A - <reason>` and define manual evidence in the TDD Plan and validation table below.

## Validation Plan

| Validation ID | Type | Command or Manual Check | Acceptance Criteria | Required Before |
| --- | --- | --- | --- | --- |
| VAL-001 | <unit/integration/artifact/manual/static> | `<command>` or <manual check> | <AC IDs> | Code Agent final response |
| VAL-002 | <unit/integration/artifact/manual/static> | `<command>` or <manual check> | <AC IDs> | Review Agent verdict |

## Risks

| Risk | Trigger | Mitigation |
| --- | --- | --- |
| <risk or N/A - none known> | <signal> | <action, stop condition, or follow-up artifact> |

## Rollback Plan

| Changed Area | Rollback Action | Evidence Needed |
| --- | --- | --- |
| <path or area> | <how to revert only this task's changes without touching unrelated work> | <git diff, artifact snapshot, or validation result> |

## Stop Conditions

- Required task or source artifacts are missing.
- `task.md` and `plan.md` disagree on allowed scope, acceptance criteria, required tests, or validation.
- The required change needs files outside the allowed scope.
- The work requires a new dependency, CLI, database, web UI, service, scheduler, agent runtime, or validation code not explicitly authorized by `task.md`.
- TDD is skipped without a recorded reason and alternative validation in `test.md`.
- Validation cannot be run and no alternative evidence is approved in `task.md`.

## Final Response Requirements for Code Agent

- Changed file paths.
- Acceptance criteria status.
- Tests written first, or reason TDD was not applicable.
- Validation commands and results.
- Unresolved risks, gaps, or blocked items.

## Handoff to Review Agent

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-XXX-short-title/implementation.md` and `tasks/TASK-XXX-short-title/test.md` |
| Target Artifact | `tasks/TASK-XXX-short-title/review.md` |
| Allowed Scope | <same allowed paths from task.md> |
| Required Evidence | <validation results and changed-file summary> |
| Next Owner Role | Review Agent |
| Stop Conditions | <missing evidence, out-of-scope diff, unresolved blocking question, or failed validation> |
