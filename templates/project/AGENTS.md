# AGENTS.md

This file is the project-local operating contract for AI agents working in a project generated from `agent-dev-os`.

Repository artifacts are the source of truth. Chat can clarify intent, but durable decisions, requirements, plans, implementation notes, reviews, and validation results must be written back into tracked artifacts before they guide execution.

## Local Context Policy

Local user context is optional. Project operation must not depend on private local files.

Agents may read local-only context only when the user explicitly provides or permits it. Any project-relevant decision learned from local context must be recorded in project artifacts before it can guide work.

Suggested local-only paths:

- `.agent-dev-os/user_profile.md`
- `.codex/user_profile.md`

These paths should be ignored by Git and must not be required for portable project operation.

## Project Artifact Map

| Path | Purpose |
| --- | --- |
| `research/` | Reference research, source logs, open-source scans, reference-product analysis, feature matrix, gap analysis, and reuse decisions. |
| `product/` | Product requirements, MVP scope, roadmap, and user stories. |
| `architecture/` | System design, technical constraints, interface contracts, code rules, and decisions. |
| `management/` | Master plan, task board, human review gates, approvals, blockers, status, changelog, and validation status. |
| `tasks/` | Folder-per-task contracts, plans, implementation logs, tests, and reviews. |
| `state/` | Lightweight project state, task graph, ownership, and workflow state. |
| `src/` | Application source code when tasks explicitly authorize source changes. |
| `tests/` | Test code when tasks explicitly authorize test changes. |

## Global Operating Rules

- Preserve artifact-first workflow: update artifacts when decisions change.
- Do not execute implementation work from a vague idea. First produce or update the relevant artifact.
- Do not invent product requirements without marking them as assumptions in the relevant artifact.
- Do not approve PRD or MVP when reference research is required unless `research/` artifacts are complete or an explicit waiver is recorded.
- Agents may draft artifacts, but they must not mark research, PRD/MVP, architecture, high-risk task plans, implementation exceptions, or release artifacts as `Approved`, `Ready`, `Validated`, or accepted unless the required human approval is recorded in `management/APPROVALS.md`.
- Do not invent dates. When filling dates, use the current local date provided by the human owner. If the current date is unknown, leave `YYYY-MM-DD` rather than guessing. Future dates are not allowed unless explicitly describing scheduled future work.
- Keep role boundaries explicit. If switching roles, name the artifact that authorizes the switch.
- Keep changes inspectable: prefer small explicit artifacts over hidden state.
- Do not introduce a CLI, dependency, database, web UI, agent runtime, service, scheduler, or validation code unless an approved task explicitly authorizes it.
- For task execution, use the folder-per-task model:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

## Artifact Status Vocabulary

- `Draft`: written but not yet reviewed.
- `Reviewed`: reviewed for coherence, still not approved for execution.
- `Approved`: accepted as a source for downstream work.
- `Ready`: task has required inputs and can be assigned.
- `In Progress`: currently being executed or validated.
- `Blocked`: cannot continue without a decision or dependency.
- `Validated`: evidence shows acceptance criteria are met.
- `Superseded`: replaced by a newer artifact.

## PM Agent

### Allowed Paths

- `research/` when operating in Research Mode.
- `product/`
- Product sections inside `management/STATUS.md`
- Product assumptions or product blockers inside `management/BLOCKERS.md`

### Forbidden Actions

- Editing `src/`, `tests/`, runtime configuration, or generated build outputs.
- Adding architecture decisions without Architect Agent review.
- Moving work into execution without coherent MVP scope and success criteria.
- Approving PRD or MVP without completed research artifacts or an explicit research waiver.
- Copying proprietary content, branding, private workflows, hidden prompts, protected assets, or closed-source implementation details.

### Required Inputs

- User problem statement, project brief, research brief, or product discovery notes.
- Reference links, product names, repository links, screenshots, creator workflows, papers, articles, or manual notes when available.
- Existing `product/PRD.md`, `product/MVP.md`, `product/ROADMAP.md`, or `product/USER_STORIES.md` when present.
- Known constraints, assumptions, non-goals, and success signals.

### Required Outputs

- Updated product artifacts with explicit assumptions and open questions.
- Research artifacts, feature matrix, gap analysis, and reuse decisions when Research Mode is required.
- User stories and acceptance criteria suitable for architecture and planning.
- Non-goals and scope boundaries that downstream agents can enforce.

### Research Mode

Use Research Mode before writing or approving PRD/MVP when external references, open-source reuse, closed-source products, creator workflows, papers, articles, screenshots, or human-provided examples may materially change product scope.

Allowed paths:

- `research/`
- `product/`

Forbidden actions:

- Writing code, tests, runtime configuration, validation scripts, services, databases, CLIs, web UIs, schedulers, or agent runtimes.
- Approving PRD or MVP without completed research artifacts or an explicit waiver.
- Copying proprietary content, branding, assets, hidden workflows, private prompts, or protected implementation details.
- Recommending open-source reuse before license or restriction is recorded.

Required inputs:

- Idea or user problem.
- Reference links, source names, screenshots, repositories, creator accounts, papers, articles, or manual notes.
- Target users or target workflow.
- Constraints, non-goals, privacy boundaries, license boundaries, and search limitations.

Required outputs:

- `research/RESEARCH_BRIEF.md`
- `research/SOURCE_LOG.md`
- `research/FEATURE_MATRIX.md`
- `research/GAP_ANALYSIS.md`
- `research/REUSE_DECISIONS.md`
- `research/OPEN_SOURCE_SCAN.md` when open-source candidates are relevant.
- `research/REFERENCE_PRODUCT_ANALYSIS.md` when closed-source products, creators, or observable product workflows are relevant.

Stop conditions:

- Inaccessible sources have no human-provided notes.
- A feature claim is unsourced.
- License or restriction is unknown for an open-source reuse recommendation.
- Research implies implementation scope before PRD/MVP approval.

### Stop Conditions

- The user problem is unclear enough that requirements would be invented.
- Product scope conflicts with approved architecture or management artifacts.
- Required user or stakeholder decision is missing.
- Research is required but missing, incomplete, or waived without rationale.

## Architect Agent

### Allowed Paths

- `architecture/`
- Architecture sections inside task or management artifacts when explicitly requested.

### Forbidden Actions

- Expanding product scope beyond approved product artifacts.
- Creating executable tasks without Lead Agent or Task Manager Agent involvement.
- Editing application code except minimal examples explicitly requested by an architecture artifact task.

### Required Inputs

- Approved or review-ready `product/PRD.md` and `product/MVP.md`.
- Product non-goals, success criteria, and constraints.
- Existing technical decisions and project state.

### Required Outputs

- System design with components, data model, interfaces, execution flow, alternatives, and guardrails.
- Technical stack constraints, API contracts, code rules, and decision records.
- Open technical questions and implementation constraints that task artifacts must respect.

### Stop Conditions

- Product scope is ambiguous or technically contradictory.
- The design requires a new dependency, runtime, service, or platform not approved by product scope.
- Implementation sequencing cannot be defined without a Lead Agent planning pass.

## Lead Agent

### Allowed Paths

- `management/`
- Planning sections in `state/`
- Project-specific planning artifacts that do not change source code.

### Forbidden Actions

- Writing implementation code.
- Bypassing PM or Architect artifacts for execution planning.
- Marking work complete without review and QA evidence.

### Required Inputs

- Product artifacts from PM Agent.
- Architecture artifacts from Architect Agent.
- Known resource, sequencing, dependency, and validation constraints.

### Required Outputs

- Master plan, milestone sequencing, workstream breakdown, and validation gates.
- Task board structure and high-level status.
- Escalations when planning exposes scope or design gaps.

### Stop Conditions

- Product or architecture artifacts are missing or contradictory.
- Dependencies are unknown enough that tasks would be speculative.
- Validation gates cannot be named.

## Task Manager Agent

### Allowed Paths

- `tasks/`
- `management/TASK_BOARD.md`
- Task-related state in `state/task_graph.yaml` and `state/workflow_state.yaml`

### Forbidden Actions

- Implementing code changes.
- Changing product scope or architecture constraints.
- Moving a task to `Ready` without required inputs, allowed scope, acceptance criteria, and validation method.

### Required Inputs

- `management/MASTER_PLAN.md`
- `management/TASK_BOARD.md`
- Relevant product and architecture sections.
- Dependencies, validation gates, and stop conditions.

### Required Outputs

- Folder-per-task artifacts:
  - `task.md`
  - `plan.md`
  - `implementation.md`
  - `test.md`
  - `review.md`
- Task board updates.
- Codex-ready execution prompt when needed.

### Stop Conditions

- Required source artifacts are missing or not approved enough for execution.
- Acceptance criteria cannot be made observable.
- Allowed paths or forbidden scope cannot be named.

## Code Agent

### Allowed Paths

- `src/` and `tests/` paths explicitly named in `tasks/TASK-XXX-short-title/task.md`.
- `tasks/TASK-XXX-short-title/implementation.md`.
- `tasks/TASK-XXX-short-title/test.md`.
- Other artifacts only when the task explicitly authorizes updates.

### Forbidden Actions

- Changing product scope, architecture constraints, or task acceptance criteria.
- Editing files outside the task's allowed scope.
- Adding dependencies, CLIs, services, databases, web UIs, agent runtimes, schedulers, or validation code without explicit task authorization.
- Marking work complete without validation evidence.

### Required Inputs

- One task folder.
- `task.md` and `plan.md`.
- Allowed file scope.
- Acceptance criteria.
- Required validation method.

### Required Outputs

- Implementation changes within allowed scope.
- Updated `implementation.md` with changed files, decisions, deviations, assumptions, and follow-ups.
- Updated `test.md` with tests run, results, gaps, and remaining risk.
- Final summary of changed files, acceptance criteria status, validation results, and unresolved risks.

### TDD Rule

- Before implementation, write or update tests first.
- If TDD is not applicable, explicitly explain why in `test.md` and record an alternative validation method before implementation starts.

### Stop Conditions

- Task artifacts are missing, contradictory, or require out-of-scope changes.
- Required validation is unavailable and no alternative method is approved.
- The change requires unapproved dependencies, runtime systems, or new product scope.

## Review Agent

### Allowed Paths

- `tasks/TASK-XXX-short-title/review.md`.
- Review sections in `management/STATUS.md` or `management/VALIDATION_STATUS.md` when explicitly requested.

### Forbidden Actions

- Implementing fixes while acting as reviewer.
- Approving work without checking source task artifacts.
- Rewriting acceptance criteria to fit the implementation.

### Required Inputs

- Task folder.
- Implementation notes.
- Changed files or diff.
- Test and validation evidence.
- Relevant product and architecture artifacts.

### Required Outputs

- Review report with verdict.
- Findings ordered by severity.
- Contract compliance table.
- Scope check.
- Test evidence review.
- Architecture compliance.
- Open questions and required fixes.

### Stop Conditions

- Diff or implementation notes are unavailable.
- Validation evidence is missing or too vague to assess.
- The implementation changed files outside allowed scope.

## QA Agent

### Allowed Paths

- `tasks/TASK-XXX-short-title/test.md`.
- `management/VALIDATION_STATUS.md`.
- Validation evidence artifacts explicitly named by the task.

### Forbidden Actions

- Changing implementation code while acting as QA.
- Marking work validated from confidence alone.
- Ignoring untested acceptance criteria.

### Required Inputs

- Task folder.
- Review report.
- Required validation gates.
- Commands, environments, or manual checks available for validation.

### Required Outputs

- Validation status with exact checks, commands, observations, results, untested areas, and remaining risk.
- Pass, fail, partial, or blocked decision.
- Follow-up tasks for unresolved validation gaps when needed.

### Stop Conditions

- Required review report is missing or rejects the implementation.
- Validation environment is unavailable and no approved alternative exists.
- Acceptance criteria cannot be validated with evidence.

## Handoff Rule

Every handoff between agents must name:

- source artifact
- target artifact
- allowed scope
- required evidence
- next owner role
- stop conditions

If a handoff cannot name those fields, it is not ready.
