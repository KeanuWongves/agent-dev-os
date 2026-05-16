# Plan: TASK-001 create-commit-summary-template

This plan artifact is adapted from `templates/task/plan.md` for TASK-001. It is ready for Code Agent execution.

Template rule: every implementation step must trace to an acceptance criterion in `task.md`. If TDD is not applicable, record the reason and alternative validation in `test.md` before implementation starts.

## Task Contract Reference

| Field | Value |
| --- | --- |
| Status | Ready |
| Owner Role | Task Manager Agent |
| Task ID | TASK-001 |
| Task Folder | `tasks/TASK-001-create-commit-summary-template/` |
| Source Task Contract | `tasks/TASK-001-create-commit-summary-template/task.md` |
| Last Updated | 2026-05-17 |
| Prepared By | Task Manager Agent |
| Execution Owner | Code Agent, unassigned |

## Files to Inspect

| Path | Required Section or Lines | Purpose |
| --- | --- | --- |
| `tasks/TASK-001-create-commit-summary-template/task.md` | All sections | Confirm objective, scope, acceptance criteria, required tests, and stop conditions. |
| `product/PRD.md` | PRD-001 through PRD-005, NFR-001 through NFR-004 | Confirm product requirements and non-goals. |
| `product/MVP.md` | Included Capabilities, Excluded Capabilities, Scope Guardrails | Confirm artifact-only MVP scope. |
| `product/USER_STORIES.md` | US-001 through US-003, Edge Cases | Confirm user-facing fields and ambiguity handling. |
| `architecture/API_SPEC.md` | API-001, API-002 | Confirm template field contract and validation evidence contract. |
| `architecture/CODE_RULES.md` | Required Rules, Forbidden Patterns | Confirm no-code and no-dependency constraints. |
| `management/MASTER_PLAN.md` | Validation Gates | Confirm required evidence. |

## Proposed Edit Surface

| Path | Change Type | Acceptance Criteria | Notes |
| --- | --- | --- | --- |
| `product/COMMIT_SUMMARY_TEMPLATE.md` | create | AC-001, AC-002, AC-003, AC-004 | The only new product-facing artifact for this task. |
| `tasks/TASK-001-create-commit-summary-template/test.md` | update | AC-005, AC-006 | Must record TDD alternative before creating the template and validation evidence after. |
| `tasks/TASK-001-create-commit-summary-template/implementation.md` | update | AC-006 | Must record changed files, decisions, deviations, and risks. |

## Execution Strategy

Use the API-001 field contract as the source of truth for the template structure. Build a concise Markdown artifact with three parts: instructions, commit evidence entry template, and grouping rubric. Keep all validation as manual inspection and existing shell/file commands, and stop immediately if the work appears to require source code, scripts, dependencies, or a runtime.

## Step-by-step Plan

| Step | Owner Role | Action | Traces To | Expected Output |
| --- | --- | --- | --- | --- |
| 1 | Code Agent | Read `task.md`, this plan, and source product/architecture artifacts. Stop if they conflict. | All ACs | Confirmed execution context. |
| 2 | Code Agent | Update `test.md` before implementation to record that TDD is not applicable and list alternative validation checks. | AC-006 | TDD alternative recorded before template creation. |
| 3 | Code Agent | Create `product/COMMIT_SUMMARY_TEMPLATE.md` with required evidence fields and plain Markdown instructions. | AC-001, AC-002 | Template artifact exists. |
| 4 | Code Agent | Add grouping rubric for project, feature, bugfix, experiment, blocker, optional tags, review-needed, and uncertainty reason. | AC-003, AC-004 | Rubric and missing-evidence guidance exist. |
| 5 | Code Agent | Run required commands and perform manual inspection against API-001. | AC-001, AC-002, AC-003, AC-004, AC-005 | Results recorded in `test.md`. |
| 6 | Code Agent | Update `implementation.md` with summary, files changed, decisions, deviations, assumptions, follow-ups, and risks. | AC-006 | Handoff-ready implementation notes. |
| 7 | Review Agent | Review diff, task artifacts, implementation notes, validation evidence, and scope compliance. | All ACs | `review.md` verdict and findings. |

## TDD Plan

| Field | Value |
| --- | --- |
| Tests To Write or Update First | N/A - no executable code or test code is allowed for this artifact-only task. |
| Expected First Failing Signal | N/A - TDD does not apply because the deliverable is a Markdown template and validation is by inspection. |
| Implementation May Start After | Code Agent records the TDD-not-applicable reason and alternative validation plan in `test.md`. |
| Alternative Validation If TDD Is Not Applicable | Manual artifact inspection against API-001, file existence command, no-code/dependency scan, and changed-file scope check. |
| Artifact Where Decision Is Recorded | `tasks/TASK-001-create-commit-summary-template/test.md` |

## Required Commands

```bash
test -f examples/weekly-report-assistant/product/COMMIT_SUMMARY_TEMPLATE.md
find examples/weekly-report-assistant -type f \( -name '*.py' -o -name '*.js' -o -name 'package.json' -o -name 'pyproject.toml' -o -name 'requirements.txt' \)
git diff --name-only -- examples/weekly-report-assistant
git diff --check
```

## Validation Plan

| Validation ID | Type | Command or Manual Check | Acceptance Criteria | Required Before |
| --- | --- | --- | --- | --- |
| VAL-001 | artifact/manual | Record TDD-not-applicable reason and alternative validation in `test.md` before creating the template. | AC-006 | Template creation |
| VAL-002 | static command | `test -f examples/weekly-report-assistant/product/COMMIT_SUMMARY_TEMPLATE.md` | AC-001 | Code Agent final response |
| VAL-003 | manual inspection | Inspect template for all API-001 fields and one primary group rule. | AC-002, AC-003 | Code Agent final response |
| VAL-004 | manual inspection | Inspect template for missing-evidence, unknown-metric, ambiguity, and review-needed guidance. | AC-004 | Code Agent final response |
| VAL-005 | static command | Run no-code/dependency scan and changed-file scope check. | AC-005 | Code Agent final response |
| VAL-006 | artifact/manual | Inspect `implementation.md` and `test.md` for complete evidence and risks. | AC-006 | Review Agent verdict |

## Risks

| Risk | Trigger | Mitigation |
| --- | --- | --- |
| Template overfits future automation. | Code Agent adds YAML schema, parser assumptions, or machine-only structure. | Keep human-readable Markdown as the primary interface. |
| Scope expands into source code. | Any executable file or dependency manifest appears. | Stop and return to Task Manager Agent. |
| Validation is too vague. | `test.md` says only "manual check passed". | Require exact check steps, expected result, observed result, and status. |

## Rollback Plan

| Changed Area | Rollback Action | Evidence Needed |
| --- | --- | --- |
| `product/COMMIT_SUMMARY_TEMPLATE.md` | Delete only this newly created file if task is abandoned before review. | `git diff --name-only -- examples/weekly-report-assistant` shows only task-allowed changes are affected. |
| Task-local execution artifacts | Revert only the task-local `implementation.md` and `test.md` edits from this execution attempt. | Diff shows no unrelated artifacts are touched. |

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
| Source Artifact | `tasks/TASK-001-create-commit-summary-template/implementation.md` and `tasks/TASK-001-create-commit-summary-template/test.md` |
| Target Artifact | `tasks/TASK-001-create-commit-summary-template/review.md` |
| Allowed Scope | Create `product/COMMIT_SUMMARY_TEMPLATE.md`; update task-local `implementation.md` and `test.md` only. |
| Required Evidence | Validation results for VAL-001 through VAL-006 and changed-file summary. |
| Next Owner Role | Review Agent |
| Stop Conditions | Missing evidence, out-of-scope diff, unresolved blocking question, failed validation, or unapproved runtime/code addition. |
