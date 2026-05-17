# Task: <TASK-ID> <short-title>

Copy this file to `tasks/TASK-XXX-short-title/task.md`. Do not edit this template in place for project work.

Template rule: every placeholder must be replaced before the task can move to `Ready`. If a field is not applicable, write `N/A - <reason>`.

## Task ID and Title

| Field | Value |
| --- | --- |
| Task ID | <TASK-XXX> |
| Title | <short-title> |
| Task Folder | `tasks/TASK-XXX-short-title/` |

## Status

| Field | Value |
| --- | --- |
| Status | Draft |
| Last Updated | YYYY-MM-DD |
| Readiness Decision | <Draft/Ready/Blocked> |
| Artifact-only task? | <Yes/No> |

## Owner

| Role | Owner |
| --- | --- |
| Task Manager Owner | <agent or human> |
| Execution Owner | <Code Agent, human owner, or unassigned> |
| Review Owner | <Review Agent, human reviewer, or unassigned> |
| QA Owner | <QA Agent, human validator, or unassigned> |

## Source Artifacts

| Artifact | Status | Required Section or IDs | Why This Task Needs It |
| --- | --- | --- | --- |
| <product/PRD.md> | <Draft/Reviewed/Approved/N/A> | <section, requirement ID, or N/A> | <specific dependency on product scope> |
| <product/MVP.md> | <Draft/Reviewed/Approved/N/A> | <section, MVP ID, or N/A> | <specific dependency on MVP scope> |
| <architecture/SYSTEM_DESIGN.md> | <Draft/Reviewed/Approved/N/A> | <section, decision ID, or N/A> | <specific dependency on technical design> |
| <management/MASTER_PLAN.md> | <Draft/Reviewed/Approved/N/A> | <milestone or workstream ID> | <specific dependency on sequencing> |
| <management/TASK_BOARD.md> | <Draft/Reviewed/Approved/N/A> | <row or task ID> | <specific dependency on board state> |

## Objective

Produce exactly one observable outcome:

<one-sentence outcome, written as a deliverable rather than an activity>

## Background

<state the user or project problem this task addresses, the current behavior or artifact state, and the decision path that made this task necessary. Do not add product requirements that are not present in source artifacts. Mark assumptions below.>

## Allowed Changes

| Scope Type | Allowed Paths or Behavior | Limit |
| --- | --- | --- |
| Source files | <exact files or directories, or N/A - reason> | <what may change> |
| Tests | <exact test files or directories, or N/A - reason> | <what may be added or updated> |
| Artifacts | <exact artifact paths, including this task folder> | <what may be updated> |
| Configuration | <exact config files, or N/A - reason> | <what may change> |
| External effects | <network, filesystem, generated assets, or N/A - reason> | <approved limits> |

## Artifact-only Task Rules

Use this section when `Artifact-only task?` is `Yes`. If the task is not artifact-only, write `N/A - task changes source or test code with explicit authorization`.

| Field | Value |
| --- | --- |
| Artifact-only deliverable | <exact artifact path or N/A - not artifact-only> |
| Source code allowed? | <No unless explicitly authorized, or Yes with exact paths and source artifact> |
| Test code allowed? | <No unless explicitly authorized, or Yes with exact paths and source artifact> |
| Runtime or service code allowed? | <No unless explicitly authorized, or Yes with exact paths and source artifact> |
| Validation scripts allowed? | <No unless explicitly authorized, or Yes with exact paths and source artifact> |
| Allowed validation modes | <manual artifact inspection, file existence check, changed-file scope check, no-code/dependency scan, or task-specific approved mode> |

Artifact-only tasks must not create source code, test code, runtime code, or validation scripts unless this task contract explicitly authorizes the exact paths and source artifact for that exception.

## Forbidden Changes

- Do not change files outside the allowed paths above.
- Do not change product scope, architecture constraints, or acceptance criteria.
- Do not add a dependency, CLI, database, web UI, service, scheduler, agent runtime, or validation code unless this task explicitly names it in Allowed Changes.
- For artifact-only tasks, do not create source code, test code, runtime code, or validation scripts unless this task explicitly authorizes the exact paths.
- Do not mark the task complete without validation evidence in `test.md`.
- Do not use chat-only decisions as source material unless they are written back into a repository artifact first.

## Files to Inspect

| Path | Required Section or Lines | Reason |
| --- | --- | --- |
| `tasks/TASK-XXX-short-title/task.md` | All sections | Confirm task contract before execution. |
| <source artifact path> | <section or IDs> | <specific decision or constraint to follow> |
| <source/test path> | <section or lines, or N/A - reason> | <existing behavior or pattern to inspect> |

## Expected Edit Surface

| Path | Change Type | Acceptance Criteria | Notes |
| --- | --- | --- | --- |
| <exact path> | <create/update/delete/N/A - reason> | <AC IDs> | <specific expected change> |

## Functional Requirements

| ID | Requirement | Source Artifact | Acceptance Criteria |
| --- | --- | --- | --- |
| FR-001 | <required behavior or artifact capability> | <path and section> | <AC IDs> |

## Non-functional Requirements

| ID | Requirement | Source Artifact | Acceptance Criteria |
| --- | --- | --- | --- |
| NFR-001 | <performance, security, accessibility, maintainability, portability, or artifact-quality requirement> | <path and section> | <AC IDs> |

## Acceptance Criteria

| ID | Criterion | Evidence Required | Owner Role | Status |
| --- | --- | --- | --- | --- |
| AC-001 | <specific observable criterion> | <command, test case, artifact diff, screenshot, or manual check> | <Code Agent/Review Agent/QA Agent> | Draft |
| AC-002 | <specific observable criterion> | <command, test case, artifact diff, screenshot, or manual check> | <Code Agent/Review Agent/QA Agent> | Draft |

## Required Tests

| Test ID | Type | Required Before Implementation? | Acceptance Criteria | Notes |
| --- | --- | --- | --- | --- |
| T-001 | <unit/integration/static/artifact/manual> | <Yes/No> | <AC IDs> | <exact test expectation or N/A - reason> |

For artifact-only tasks, acceptable alternative validation examples include:

- Manual artifact inspection against the task acceptance criteria.
- File existence check for required artifacts.
- Changed-file scope check against Allowed Changes and Expected Edit Surface.
- No-code/dependency scan confirming the task did not add source code, test code, runtime code, validation scripts, dependency manifests, CLIs, services, databases, schedulers, web UIs, or agent runtimes.

Artifact-only validation must still be exact enough for another agent to rerun or inspect. Do not use confidence-only wording.

## Required Commands

```bash
<command>
```

If no command is applicable, replace the block with `N/A - <reason>` and define manual evidence in `Required Tests`.

## Dependencies

| Dependency | Required State | Current State | Blocking? | Notes |
| --- | --- | --- | --- | --- |
| <artifact, decision, task, environment, or external input> | <Approved/Ready/available/N/A> | <current state> | <Yes/No> | <specific consequence> |

## Assumptions

| ID | Assumption | Source or Rationale | Validation Needed? |
| --- | --- | --- | --- |
| A-001 | <assumption required to make the task executable> | <artifact path, user instruction, or reasoning> | <Yes/No and method> |

## Open Questions

| ID | Question | Owner | Blocks Ready? | Resolution Artifact |
| --- | --- | --- | --- | --- |
| Q-001 | <question> | <role or person> | <Yes/No> | <where the answer must be recorded> |

## Stop Conditions

- Required source artifacts are missing or not at the status required above.
- Required task artifacts in `tasks/TASK-XXX-short-title/` are missing.
- Allowed Changes, acceptance criteria, required tests, or required commands conflict with each other.
- The task requires changing files outside Expected Edit Surface or Allowed Changes.
- The task requires a new dependency, CLI, database, web UI, service, scheduler, agent runtime, or validation code not explicitly authorized above.
- An artifact-only task creates source code, test code, runtime code, or validation scripts without explicit authorization above.
- TDD is skipped without a recorded reason and alternative validation method in `test.md`.
- Validation cannot be run and no alternative evidence is approved in this task contract.

## Readiness Checklist

- [ ] Source artifacts are named with paths and relevant sections or IDs.
- [ ] Allowed Changes name exact paths or explicitly state `N/A - <reason>`.
- [ ] Forbidden Changes cover known out-of-scope changes.
- [ ] Files to Inspect and Expected Edit Surface are specific enough for another agent to follow.
- [ ] Functional and non-functional requirements trace to acceptance criteria.
- [ ] Acceptance criteria are observable and have required evidence.
- [ ] Required Tests and Required Commands are executable or have a documented alternative.
- [ ] Dependencies are either ready or marked blocking.
- [ ] Open questions that block execution are resolved.
- [ ] `plan.md`, `implementation.md`, `test.md`, and `review.md` exist in the same task folder.

## Review Handoff

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-XXX-short-title/implementation.md` and `tasks/TASK-XXX-short-title/test.md` |
| Target Artifact | `tasks/TASK-XXX-short-title/review.md` |
| Allowed Scope | <summarize exact allowed paths and changes> |
| Required Evidence | <changed-file summary, validation IDs, and acceptance criteria evidence> |
| Next Owner Role | Review Agent |
| Stop Conditions | <missing evidence, out-of-scope diff, unresolved blocking question, or failed validation> |

## QA Handoff

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-XXX-short-title/review.md` and `tasks/TASK-XXX-short-title/test.md` |
| Target Artifact | `tasks/TASK-XXX-short-title/test.md`, project validation artifact, or task board |
| Allowed Scope | <validation-only scope and allowed artifacts> |
| Required Evidence | <accepted review verdict, validation commands, manual checks, untested areas, and remaining risk> |
| Next Owner Role | QA Agent |
| Stop Conditions | <open blocking findings, missing validation evidence, untested acceptance criteria, or environment blocker> |
