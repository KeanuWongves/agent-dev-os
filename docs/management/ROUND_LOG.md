# Round Log

This log records repository-level dogfood and template evolution rounds. It is a management artifact, not an execution task board.

## Round Index

| Round | Result | Summary | Evidence |
| --- | --- | --- | --- |
| Round 0 | Completed | Bootstrapped the artifact-driven development OS with root operating rules, vision docs, initial workflow docs, flat project templates, transitional task templates, Codex prompts, and minimal package/test placeholders. | Git commit `eaee267`; root `AGENTS.md`; `docs/vision/`; `templates/project/`; `templates/task/` |
| Round 0.1 | Completed | Tightened the root operating model, expanded role boundaries, corrected package naming, and refined README, workflow, template, and prompt wording from the initial baseline. | Git commit `391b3a6`; root `AGENTS.md`; `README.md`; template diffs |
| Round 1 | Completed | Normalized the project template set with project-local `AGENTS.md`, nested product/architecture/management/state artifacts, dedicated role docs, workflow docs, and canonical folder-per-task templates. | Git commit `00fb5dd`; `templates/project/`; `templates/task/task.md`; `docs/agents/`; `docs/workflows/` |
| Round 2 | PASS WITH MINOR FIXES | Created the Weekly Report Assistant example project to stress-test the artifact chain from vague product idea to structured product, architecture, management, state, and one Ready task folder. | Git commit `b3faa8b`; `examples/weekly-report-assistant/`; `examples/weekly-report-assistant/NOTES.md` |
| Round 2.1 | Completed | Converted Round 2 review findings into artifact-only task support, pre-execution status conventions, interface naming guidance, dogfood notes template, and management status artifacts. | Git commit `568c6c4`; `templates/task/`; `templates/project/DOGFOOD_NOTES.md`; `docs/management/` |
| Round 2.2 | Completed with required synchronization fixes | Added a research-first layer before product discovery, including reference research templates, PM Research Mode, source traceability rules, product discovery gates, PRD research inputs, and management status updates. Follow-up synchronization was required across README, root agent rules, state templates, evidence confidence fields, and management status. | Git commit `11e9675`; `templates/project/research/`; `docs/workflows/reference_research.md`; `docs/agents/PM_AGENT.md`; `templates/project/product/PRD.md` |
| Round 2.3 | Completed | Synchronized the Research Layer across repository README, root role contracts, generated-project state templates, evidence confidence fields, and management docs. | `README.md`; root `AGENTS.md`; `templates/project/state/`; `templates/project/research/`; `docs/management/` |
| Round 2.4 | Completed | Added explicit human review gates that define when AI agents may draft artifacts, when they must stop, and which human approvals unlock downstream work. | `docs/workflows/human_review_gates.md`; `templates/project/management/HUMAN_REVIEW_GATES.md`; `templates/project/management/APPROVALS.md`; workflow docs; AGENTS templates |

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

## Round 2.2 Scope

Round 2.2 adds explicit reference research before product discovery. PM Agent in Research Mode now owns research artifacts that log sources, scan open-source repositories, analyze closed-source or creator workflows, compare features, identify gaps, and record build/reuse/learn/ignore decisions before PRD or MVP approval.

## Round 2.2 Findings

| Finding | Response |
| --- | --- |
| The previous workflow moved too quickly from idea to PRD/MVP. | Added `docs/workflows/reference_research.md` and research templates under `templates/project/research/`. |
| PRD requirements needed clearer traceability to evidence. | Added `Research Inputs` and waiver sections to `templates/project/product/PRD.md`. |
| PM Agent needed a mode for research without implementation authority. | Added PM Research Mode to `docs/agents/PM_AGENT.md` and `templates/project/AGENTS.md`. |
| Open-source reuse needed license gating. | Added source log, open-source scan, and reuse decision templates with license and restriction stop conditions. |
| Closed-source product analysis needed copy boundaries. | Added reference-product analysis rules that allow learning from observable patterns but forbid copying proprietary content. |

## Round 2.3 Scope

Round 2.3 synchronizes the Research Layer across repository-level guidance and generated-project state templates. This pass does not create a new example, execute existing example tasks, or add runtime machinery.

## Round 2.3 Synchronization Results

| Area | Result |
| --- | --- |
| Root README | Use flow and directory map now include the Research Layer before product discovery. |
| Root AGENTS | PM Agent now has repository-scoped Research Mode rules, allowed paths, forbidden actions, required outputs, and stop conditions. |
| State templates | `project_state.yaml`, `ownership.yaml`, and `workflow_state.yaml` now represent `research/` and the PRD research gate. |
| Evidence confidence | Source log, reference-product analysis, feature matrix, and gap analysis now use `high`, `medium`, `low`, and `unknown` confidence values. |
| Management status | Project status now points to the next planned dogfood round: a Bilibili video analysis channel research-first example. |

## Round 2.4 Scope

Round 2.4 adds human review gates across the artifact workflow. Agents may draft artifacts before review, but must not mark gate-controlled artifacts as approved, ready, validated, or accepted unless the required human decision is recorded in `management/APPROVALS.md`.

## Round 2.4 Gate Additions

| Gate | Unlocks |
| --- | --- |
| Gate 0: Idea Intake Review | Research brief or product discovery when research is waived. |
| Gate 1: Research Review | PRD/MVP drafting and use of research findings. |
| Gate 2: PRD / MVP Approval | Architecture planning from approved product scope. |
| Gate 3: Architecture Approval | Master planning and implementation task planning. |
| Gate 4: Task Plan Approval | Execution of non-trivial or high-risk task folders. |
| Gate 5: Implementation Exception Review | Continued implementation after scope, dependency, runtime, credential, external API, scraping, or validation exceptions. |
| Gate 6: Release / Final Acceptance | Final acceptance, milestone closure, and release completion. |

## Proposed Round 3 Focus

| Focus | Rationale | Candidate Artifacts |
| --- | --- | --- |
| Reduce task-template duplication | Handoff, validation, and stop-condition blocks repeat across task artifacts. | `templates/task/` |
| Split or supplement API naming | Artifact-only workflows need interface contracts without runtime/API implication. | `templates/project/architecture/API_SPEC.md`, future `INTERFACE_SPEC.md` |
| Add a no-runtime checklist template | Runtime-surface prohibitions are common and should be reusable. | `templates/task/task.md`, `templates/project/architecture/CODE_RULES.md` |
| Dogfood research-first workflow | Weekly-report assistant tested artifact-only work; the next active dogfood example should be a new Bilibili video analysis channel example that starts with reference research. | `examples/bilibili-video-analysis-channel/` |
| Normalize status vocabulary | Artifact approval, task board state, validation state, and pre-execution placeholders should be easier to distinguish. | `AGENTS.md`, `templates/task/`, `templates/project/state/` |
