# Round Log

This log records repository-level dogfood and template evolution rounds. It is a management artifact, not an execution task board.

## Round Index

| Round | Result | Summary | Evidence |
| --- | --- | --- | --- |
| Round 0 | Completed | Bootstrapped the artifact-driven development OS with root operating rules, vision docs, initial workflow docs, flat project templates, transitional task templates, Codex prompts, and minimal package/test placeholders. | Git commit `e0dcb50`; root `AGENTS.md`; `docs/vision/`; `templates/project/`; `templates/task/` |
| Round 0.1 | Completed | Tightened the root operating model, expanded role boundaries, corrected package naming, and refined README, workflow, template, and prompt wording from the initial baseline. | Git commit `48c6292`; root `AGENTS.md`; `README.md`; template diffs |
| Round 1 | Completed | Normalized the project template set with project-local `AGENTS.md`, nested product/architecture/management/state artifacts, dedicated role docs, workflow docs, and canonical folder-per-task templates. | Git commit `82fd736`; `templates/project/`; `templates/task/task.md`; `docs/agents/`; `docs/workflows/` |
| Round 2 | PASS WITH MINOR FIXES | Created the Weekly Report Assistant example project to stress-test the artifact chain from vague product idea to structured product, architecture, management, state, and one Ready task folder. | Git commit `b6c3d47`; `examples/weekly-report-assistant/`; `examples/weekly-report-assistant/NOTES.md` |

## Round 2 Findings

### Easy to Use

| Area | Finding |
| --- | --- |
| Product templates | PRD and MVP templates made it easy to separate goals, non-goals, assumptions, included scope, and excluded scope. |
| Architecture code rules | `CODE_RULES.md` mapped cleanly to no-code, no-CLI, no-dependency, and no-runtime constraints. |
| Task board | Ready policy made task folder completeness observable. |
| Task contract and plan | Allowed/forbidden scope, expected edit surface, acceptance criteria, stop conditions, and TDD alternative planning worked well for constraining TASK-001. |

### Too Heavy

| Area | Finding |
| --- | --- |
| API spec naming | `API_SPEC.md` can imply runtime or network API scope even when an artifact-only file contract is intended. |
| Pre-execution task artifacts | `implementation.md`, `test.md`, and `review.md` are heavy before task execution and need standard `Pending`, `Not Run`, `Not Started`, and `Blocked` conventions. |
| Project validation status | Validation status is useful but awkward before any task has run; it needs a clear "not run because task is Ready but unexecuted" pattern. |
| State YAML | Lightweight state is useful, but status vocabulary can drift from artifact approval and task-board status. |

### Repeated Fields

| Field Family | Impact |
| --- | --- |
| Status, owner, and last updated | Traceable, but repetitive across almost every artifact. |
| Source artifacts and downstream consumers | Useful for resumability, but path drift is easy. |
| Allowed scope and stop conditions | Important safety guardrails, but repeated in many task and workflow artifacts. |
| Validation commands and validation IDs | Necessary for QA, but repeated across task, plan, test, and project validation artifacts. |
| Handoff fields | Enforces discipline, but could be centralized or referenced to reduce duplication. |

### Missing Fields or Patterns

| Gap | Impact |
| --- | --- |
| Explicit artifact-only task support | Templates assumed code/test execution unless manually adapted. |
| Pre-execution status pattern | Ready tasks can validly have Draft implementation/test/review artifacts, but the convention was not documented. |
| Runtime-surface checklist | No single checklist covered source code, test code, runtime code, CLIs, dependencies, services, schedulers, agent runtimes, and validation scripts. |
| Standard dogfood notes template | Round findings had to be captured in an example-local file without a standard template. |
| File/artifact interface guidance | Artifact-only projects need interface contracts without implying network APIs or services. |

## Round 2.1 Scope

Round 2.1 converts Round 2 findings into repository templates and management docs. Date replacement in the Weekly Report Assistant example is intentionally skipped per human instruction.

## Proposed Round 3 Focus

| Focus | Rationale | Candidate Artifacts |
| --- | --- | --- |
| Reduce task-template duplication | Handoff, validation, and stop-condition blocks repeat across task artifacts. | `templates/task/` |
| Split or supplement API naming | Artifact-only workflows need interface contracts without runtime/API implication. | `templates/project/architecture/API_SPEC.md`, future `INTERFACE_SPEC.md` |
| Add a no-runtime checklist template | Runtime-surface prohibitions are common and should be reusable. | `templates/task/task.md`, `templates/project/architecture/CODE_RULES.md` |
| Dogfood another project type | Weekly-report assistant tested artifact-only work; another example should test a small code-authorized task. | `examples/` |
| Normalize status vocabulary | Artifact approval, task board state, validation state, and pre-execution placeholders should be easier to distinguish. | `AGENTS.md`, `templates/task/`, `templates/project/state/` |
