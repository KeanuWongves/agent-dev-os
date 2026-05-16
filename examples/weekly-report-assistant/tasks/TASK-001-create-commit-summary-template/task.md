# Task: TASK-001 create-commit-summary-template

This task artifact is adapted from `templates/task/task.md` for TASK-001. It is the active task contract for this example.

Template rule: every placeholder must be replaced before the task can move to `Ready`. If a field is not applicable, write a concrete `N/A - reason` value.

## Task ID and Title

| Field | Value |
| --- | --- |
| Task ID | TASK-001 |
| Title | create-commit-summary-template |
| Task Folder | `tasks/TASK-001-create-commit-summary-template/` |

## Status

| Field | Value |
| --- | --- |
| Status | Ready |
| Last Updated | 2026-05-17 |
| Readiness Decision | Ready |

## Owner

| Role | Owner |
| --- | --- |
| Task Manager Owner | Task Manager Agent |
| Execution Owner | Code Agent, unassigned |
| Review Owner | Review Agent, unassigned |
| QA Owner | QA Agent, unassigned |

## Source Artifacts

| Artifact | Status | Required Section or IDs | Why This Task Needs It |
| --- | --- | --- | --- |
| `product/PRD.md` | Approved | PRD-001, PRD-002, PRD-003, NFR-001, NFR-004 | Defines required evidence fields, grouping categories, traceability, and no-code constraints. |
| `product/MVP.md` | Approved | MVP-001, MVP-002, MVP-004, MVP-AC-002, MVP-AC-003 | Limits execution to artifact-only commit summary template creation. |
| `product/USER_STORIES.md` | Approved | US-001, US-002, US-003 | Provides user scenarios and edge cases for template fields. |
| `architecture/SYSTEM_DESIGN.md` | Approved | Component Map, Data Model, Implementation Guardrails | Defines artifact-only components and the deliverable path. |
| `architecture/API_SPEC.md` | Approved | API-001, API-002 | Defines the commit summary artifact contract and validation evidence contract. |
| `architecture/CODE_RULES.md` | Approved | CR-001 through CR-005, FP-001 through FP-005 | Provides enforceable scope, no-code, and evidence rules. |
| `management/MASTER_PLAN.md` | Approved | TASK-001 row, Validation Gates | Defines sequencing and validation gates. |
| `management/TASK_BOARD.md` | Approved | TASK-001 row | Confirms the task is Ready and has no blockers. |

## Objective

Produce exactly one observable outcome:

Create `product/COMMIT_SUMMARY_TEMPLATE.md`, a Markdown template for capturing local git commit evidence and grouping it by project, feature, bugfix, experiment, and blocker.

## Background

The MVP starts as a local artifact/workflow assistant. Before any automation can be considered, the project needs a commit summary template that captures raw git evidence, classification metadata, uncertainty, and missing-evidence handling. This task is intentionally artifact-only and must not create product source code, a parser, a CLI, dependencies, services, or validation scripts.

## Allowed Changes

| Scope Type | Allowed Paths or Behavior | Limit |
| --- | --- | --- |
| Source files | N/A - no product source files are allowed. | Do not create `src/`, executable files, or product implementation code. |
| Tests | N/A - no test code is allowed. | Do not create `tests/` or validation scripts. |
| Artifacts | `product/COMMIT_SUMMARY_TEMPLATE.md` | Create one Markdown product artifact only. |
| Artifacts | `tasks/TASK-001-create-commit-summary-template/implementation.md` | Update execution log, changed-file summary, decisions, deviations, and risks after implementation. |
| Artifacts | `tasks/TASK-001-create-commit-summary-template/test.md` | Record TDD-not-applicable decision before implementation starts, then record validation evidence. |
| Configuration | N/A - no configuration changes are allowed. | Do not add runtime, package, service, editor, or CI configuration. |
| External effects | Local filesystem writes to the three allowed artifact paths only. | No network access, external service calls, generated assets, commits, or scheduling. |

## Forbidden Changes

- Do not change files outside the allowed paths above.
- Do not change product scope, architecture constraints, or acceptance criteria.
- Do not add a dependency, CLI, database, web UI, service, scheduler, agent runtime, or validation code unless this task explicitly names it in Allowed Changes.
- Do not mark the task complete without validation evidence in `test.md`.
- Do not use chat-only decisions as source material unless they are written back into a repository artifact first.

## Files to Inspect

| Path | Required Section or Lines | Reason |
| --- | --- | --- |
| `tasks/TASK-001-create-commit-summary-template/task.md` | All sections | Confirm task contract before execution. |
| `tasks/TASK-001-create-commit-summary-template/plan.md` | All sections | Confirm execution steps, validation plan, and stop conditions. |
| `product/PRD.md` | PRD-001 through PRD-005, NFR-001 through NFR-004 | Source requirements for template fields and scope constraints. |
| `product/MVP.md` | Included Capabilities, MVP Acceptance Criteria, Scope Guardrails | Confirm included and excluded capabilities. |
| `product/USER_STORIES.md` | US-001 through US-003, EC-001 through EC-003 | Confirm user-facing scenarios and edge cases. |
| `architecture/API_SPEC.md` | API-001, API-002 | Required artifact fields and validation evidence contract. |
| `architecture/CODE_RULES.md` | Required Rules and Forbidden Patterns | Enforce no-code and no-dependency rules. |
| `management/MASTER_PLAN.md` | Validation Gates | Confirm evidence required for completion. |

## Expected Edit Surface

| Path | Change Type | Acceptance Criteria | Notes |
| --- | --- | --- | --- |
| `product/COMMIT_SUMMARY_TEMPLATE.md` | create | AC-001, AC-002, AC-003, AC-004 | Markdown artifact template for commit evidence capture. |
| `tasks/TASK-001-create-commit-summary-template/test.md` | update | AC-005, AC-006 | Record TDD alternative before implementation and validation evidence after implementation. |
| `tasks/TASK-001-create-commit-summary-template/implementation.md` | update | AC-006 | Record implementation summary, changed files, decisions, deviations, and risks. |

## Functional Requirements

| ID | Requirement | Source Artifact | Acceptance Criteria |
| --- | --- | --- | --- |
| FR-001 | Create a Markdown commit summary template with required evidence fields from API-001. | `architecture/API_SPEC.md` API-001 | AC-001, AC-002 |
| FR-002 | Include a grouping rubric for project, feature, bugfix, experiment, and blocker. | `product/PRD.md` PRD-002; `product/MVP.md` MVP-002 | AC-003 |
| FR-003 | Include uncertainty and missing-evidence handling. | `product/USER_STORIES.md` US-003; `architecture/API_SPEC.md` API-001 errors | AC-004 |
| FR-004 | Record implementation and validation evidence in task-local artifacts. | `architecture/API_SPEC.md` API-002 | AC-006 |

## Non-functional Requirements

| ID | Requirement | Source Artifact | Acceptance Criteria |
| --- | --- | --- | --- |
| NFR-001 | Keep the task artifact-only and local. | `product/PRD.md` NFR-001, NFR-004 | AC-005 |
| NFR-002 | Keep the template inspectable as plain Markdown. | `architecture/TECH_STACK.md` Approved Stack | AC-001, AC-005 |
| NFR-003 | Avoid unsupported impact claims. | `architecture/CODE_RULES.md` CR-003, FP-005 | AC-004 |

## Acceptance Criteria

| ID | Criterion | Evidence Required | Owner Role | Status |
| --- | --- | --- | --- | --- |
| AC-001 | `product/COMMIT_SUMMARY_TEMPLATE.md` exists and is a Markdown artifact, not executable code. | `test -f` command result and file inspection. | Code Agent | Draft |
| AC-002 | Template includes fields for repo, date range, commit hash, commit date, author, branch/context, raw message, source command, evidence notes, project name, optional tags, review-needed, and uncertainty reason. | Manual artifact inspection recorded in `test.md`. | Code Agent | Draft |
| AC-003 | Template defines the five primary groups: project, feature, bugfix, experiment, and blocker, and requires one primary group per item. | Manual artifact inspection recorded in `test.md`. | Code Agent | Draft |
| AC-004 | Template tells users how to mark missing evidence, unknown metrics, ambiguous groups, and review-needed items. | Manual artifact inspection recorded in `test.md`. | Code Agent | Draft |
| AC-005 | Execution adds no product source code, test code, dependency manifests, CLI, database, web UI, service, scheduler, agent runtime, generated assets, or validation code. | File scan and changed-file list recorded in `test.md`. | Code Agent | Draft |
| AC-006 | `implementation.md` and `test.md` are updated with changed files, TDD alternative decision, validation results, gaps, and remaining risks. | Task-local artifact inspection by Review Agent. | Review Agent | Draft |

## Required Tests

| Test ID | Type | Required Before Implementation? | Acceptance Criteria | Notes |
| --- | --- | --- | --- | --- |
| T-001 | artifact/manual | Yes | AC-006 | Before creating the template, record in `test.md` that TDD is not applicable because this task creates a Markdown artifact and define the alternative validation checks. |
| T-002 | static command | No | AC-001, AC-005 | After implementation, run file existence and no-code/dependency scans. |
| T-003 | manual inspection | No | AC-002, AC-003, AC-004 | After implementation, inspect template fields and rubric coverage against API-001. |
| T-004 | artifact review | No | AC-006 | Inspect `implementation.md` and `test.md` for evidence completeness. |

## Required Commands

```bash
test -f examples/weekly-report-assistant/product/COMMIT_SUMMARY_TEMPLATE.md
find examples/weekly-report-assistant -type f \( -name '*.py' -o -name '*.js' -o -name 'package.json' -o -name 'pyproject.toml' -o -name 'requirements.txt' \)
git diff --name-only -- examples/weekly-report-assistant
git diff --check
```

## Dependencies

| Dependency | Required State | Current State | Blocking? | Notes |
| --- | --- | --- | --- | --- |
| Product artifacts | Approved | Approved | No | Scope is sufficient for this artifact-only task. |
| Architecture artifacts | Approved | Approved | No | Guardrails and API-001 are defined. |
| Task folder | Ready | Ready | No | All five task artifacts exist. |
| Product source runtime | N/A | Not present | No | Runtime is intentionally disallowed. |

## Assumptions

| ID | Assumption | Source or Rationale | Validation Needed? |
| --- | --- | --- | --- |
| A-001 | A Markdown template can be validated by inspection for this first workflow step. | `product/MVP.md` and `architecture/DECISIONS.md` ADR-003 | Yes - record inspection evidence in `test.md`. |
| A-002 | Creating `product/COMMIT_SUMMARY_TEMPLATE.md` does not change product scope because ADR-002 already assigns this path as the MVP artifact deliverable. | `architecture/DECISIONS.md` ADR-002 | No - already approved by architecture. |

## Open Questions

| ID | Question | Owner | Blocks Ready? | Resolution Artifact |
| --- | --- | --- | --- | --- |
| N/A | No open question blocks this task. | Task Manager Agent | No | N/A |

## Stop Conditions

- Required source artifacts are missing or not at the status required above.
- Required task artifacts in `tasks/TASK-001-create-commit-summary-template/` are missing.
- Allowed Changes, acceptance criteria, required tests, or required commands conflict with each other.
- The task requires changing files outside Expected Edit Surface or Allowed Changes.
- The task requires a new dependency, CLI, database, web UI, service, scheduler, agent runtime, or validation code not explicitly authorized above.
- TDD is skipped without a recorded reason and alternative validation method in `test.md`.
- Validation cannot be run and no alternative evidence is approved in this task contract.

## Readiness Checklist

- [x] Source artifacts are named with paths and relevant sections or IDs.
- [x] Allowed Changes name exact paths or explicitly state a concrete `N/A - reason` value.
- [x] Forbidden Changes cover known out-of-scope changes.
- [x] Files to Inspect and Expected Edit Surface are specific enough for another agent to follow.
- [x] Functional and non-functional requirements trace to acceptance criteria.
- [x] Acceptance criteria are observable and have required evidence.
- [x] Required Tests and Required Commands are executable or have a documented alternative.
- [x] Dependencies are either ready or marked blocking.
- [x] Open questions that block execution are resolved.
- [x] `plan.md`, `implementation.md`, `test.md`, and `review.md` exist in the same task folder.

## Review Handoff

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-001-create-commit-summary-template/implementation.md` and `tasks/TASK-001-create-commit-summary-template/test.md` |
| Target Artifact | `tasks/TASK-001-create-commit-summary-template/review.md` |
| Allowed Scope | Create `product/COMMIT_SUMMARY_TEMPLATE.md`; update task-local `implementation.md` and `test.md` only. |
| Required Evidence | Changed-file summary, validation IDs for AC-001 through AC-006, no-code/dependency scan, and manual field/rubric inspection. |
| Next Owner Role | Review Agent |
| Stop Conditions | Missing evidence, out-of-scope diff, unresolved blocking question, failed validation, or unapproved runtime/code addition. |

## QA Handoff

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-001-create-commit-summary-template/review.md` and `tasks/TASK-001-create-commit-summary-template/test.md` |
| Target Artifact | `tasks/TASK-001-create-commit-summary-template/test.md`, `management/VALIDATION_STATUS.md`, and `management/TASK_BOARD.md` |
| Allowed Scope | Validation-only updates to task-local `test.md` and project validation/status artifacts. |
| Required Evidence | Accepted review verdict, validation commands, manual checks, untested areas, and remaining risk. |
| Next Owner Role | QA Agent |
| Stop Conditions | Open blocking findings, missing validation evidence, untested acceptance criteria, or environment blocker. |
