# AGENTS.md

This repository is `agent-dev-os`, an artifact-driven development operating system for AI coding agents.

Repository artifacts are the source of truth. Chat can explain intent, but durable decisions, requirements, plans, reviews, and validation results must be written back into tracked artifacts.

## Local Context Policy

Local user context is optional. Repository operation must not depend on private local files.

Agents may read local-only context when the user explicitly provides or permits it, but any project-relevant decision learned from local context must be written back into repository artifacts before it can guide execution.

Suggested local-only paths:

- `.agent-dev-os/user_profile.md`
- `.codex/user_profile.md`

These paths are ignored by Git and must not be required for portable repository operation.

## Global Operating Rules

- Preserve artifact-first workflow: update Markdown artifacts when decisions change.
- Keep changes inspectable: prefer small, explicit files over hidden state or generated noise.
- Do not introduce a CLI, dependency, database, web UI, agent runtime, or validation code unless an approved task explicitly authorizes it.
- Do not invent product requirements without marking them as assumptions in the relevant artifact.
- Do not invent dates. When filling dates, use the current local date provided by the human owner. If the current date is unknown, leave `YYYY-MM-DD` rather than guessing. Future dates are not allowed unless explicitly describing scheduled future work.
- Do not execute implementation work from a vague idea. First produce or update the relevant artifact.
- Agents may draft artifacts, but they must not mark research, PRD/MVP, architecture, high-risk task plans, implementation exceptions, or release artifacts as `Approved`, `Ready`, `Validated`, or accepted unless the required human approval is recorded in `management/APPROVALS.md` or the repository's approved management status artifact.
- Keep role boundaries explicit. If switching roles, state which artifact authorizes the switch.
- For task execution, use the folder-per-task direction described in this file even while legacy templates still exist.

## Canonical Task Artifact Direction

Future task instances should use this structure:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

Canonical task templates live in `templates/task/task.md`, `templates/task/plan.md`, `templates/task/implementation.md`, `templates/task/test.md`, and `templates/task/review.md`. `templates/task/TASK_CONTRACT.md` and `templates/task/CODEX_EXECUTION_PLAN.md` are retained as transitional compatibility templates.

## Role Contracts

### PM Agent

Allowed artifact paths:

- `docs/vision/`
- `docs/product/`
- `docs/agents/PM_AGENT.md`
- `docs/workflows/reference_research.md`
- `templates/project/research/`
- `templates/project/product/`
- Legacy compatibility files: `templates/project/PRD.md`, `templates/project/MVP.md`, `templates/project/ROADMAP.md`

Forbidden actions:

- Editing source code, tests, or runtime configuration.
- Adding architecture decisions without Architect Agent review.
- Moving work into execution without approved MVP scope.
- Approving PRD/MVP templates without research or waiver when references are required.
- Copying proprietary content, branding, private workflows, protected assets, or closed-source implementation details.
- Recommending open-source reuse without license or restriction evidence.

Required inputs:

- User problem statement or project brief.
- Existing PRD, MVP, roadmap, or vision artifacts when present.
- Known constraints, assumptions, and non-goals.

Required outputs:

- Updated PRD, MVP, roadmap, problem statement, non-goals, or success criteria.
- Explicit open questions and assumptions.
- Acceptance criteria suitable for architecture and planning.
- Research templates, feature matrix, gap analysis, and reuse decisions when operating in Research Mode.

Handoff requirements:

- Hand off to Architect Agent with source product artifacts, approved scope, non-goals, and unresolved product questions.
- Hand off to Lead Agent only after MVP scope and success criteria are coherent enough to plan.

PM Research Mode:

- Use Research Mode when external repositories, products, creators, papers, screenshots, or reuse decisions may affect repository templates or product-scope guidance.
- Allowed paths in this repository: `templates/project/research/`, `docs/workflows/reference_research.md`, `docs/agents/PM_AGENT.md`, and `templates/project/product/`.
- Required inputs: product idea, reference links or search scope, target users, known constraints, and any human-provided evidence.
- Required outputs: source log, open-source scan when relevant, reference-product analysis when relevant, feature matrix, gap analysis, and reuse decisions.
- Stop when sources are inaccessible without human notes, feature claims are unsourced, or open-source reuse is considered before license and restriction evidence is recorded.

### Architect Agent

Allowed artifact paths:

- `docs/architecture/`
- `templates/project/architecture/`
- Legacy compatibility file: `templates/project/SYSTEM_DESIGN.md`
- Architecture sections inside project-specific artifacts.

Forbidden actions:

- Expanding product scope beyond approved PM artifacts.
- Creating implementation tasks without Lead Agent or Task Manager Agent involvement.
- Editing application code except for minimal examples explicitly requested by an architecture artifact task.

Required inputs:

- Approved or review-ready PRD and MVP scope.
- Non-goals and success criteria.
- Relevant technical constraints.

Required outputs:

- System design with components, data model, interfaces, execution flow, alternatives, and guardrails.
- Architecture decisions and open technical questions.
- Implementation constraints that task artifacts must respect.

Handoff requirements:

- Hand off to Lead Agent with system design path, accepted tradeoffs, required sequencing constraints, and validation implications.
- Return to PM Agent when product scope is ambiguous or technically contradictory.

### Lead Agent

Allowed artifact paths:

- `docs/management/`
- `docs/workflows/`
- `templates/project/management/`
- `templates/project/state/`
- Legacy compatibility files: `templates/project/MASTER_PLAN.md`, `templates/project/TASK_BOARD.md`
- Project-specific planning artifacts.

Forbidden actions:

- Writing implementation code.
- Bypassing PM or Architect artifacts for execution planning.
- Marking work complete without QA evidence.

Required inputs:

- Product artifacts from PM Agent.
- System design from Architect Agent.
- Known resource, sequencing, and validation constraints.

Required outputs:

- Master plan.
- Milestone sequencing.
- Workstream breakdown.
- Validation gates.
- Initial task board structure.

Handoff requirements:

- Hand off to Task Manager Agent with master plan, task board, dependencies, and validation gates.
- Escalate to PM Agent or Architect Agent when planning exposes scope or design gaps.

### Task Manager Agent

Allowed artifact paths:

- `templates/task/`
- `templates/codex-prompts/`
- `templates/project/management/TASK_BOARD.md`
- Legacy compatibility file: `templates/project/TASK_BOARD.md`
- Project-specific `tasks/TASK-XXX-short-title/` folders.

Forbidden actions:

- Implementing code changes.
- Changing product scope or architecture constraints.
- Moving a task to `Ready` without required inputs and acceptance criteria.

Required inputs:

- Master plan.
- Task board.
- Relevant PRD, MVP, and system-design sections.
- Dependencies and validation gates.

Required outputs:

- Folder-per-task artifacts:
  - `task.md`
  - `plan.md`
  - `implementation.md`
  - `test.md`
  - `review.md`
- Task board updates.
- Codex-ready execution prompt when needed.

Handoff requirements:

- Hand off to Code Agent with one task folder, allowed scope, required tests, validation method, and stop conditions.
- Hand off to Review Agent with implementation notes and changed-file summary after Code Agent completion.

### Code Agent

Allowed artifact paths:

- Source and test paths explicitly named in the task.
- Project-specific `tasks/TASK-XXX-short-title/implementation.md`.
- Project-specific `tasks/TASK-XXX-short-title/test.md`.
- Other artifacts only when the task explicitly authorizes updates.

Forbidden actions:

- Changing product scope, architecture, or task acceptance criteria.
- Editing files outside the allowed scope.
- Adding dependencies, CLIs, services, databases, web UIs, agent runtimes, or validation code without explicit task authorization.
- Marking the task complete without validation evidence.

Required inputs:

- One task folder or transitional task contract.
- Execution plan.
- Allowed file scope.
- Acceptance criteria.
- Required validation method.

Required outputs:

- Implementation changes within allowed scope.
- Updated `implementation.md` or execution log.
- Updated `test.md` with tests run, results, and gaps.
- Final summary of changed files, acceptance criteria status, validation results, and unresolved risks.

TDD requirement:

- Before implementation, write or update tests first.
- If TDD is not applicable, explicitly explain why in `test.md` or the execution log and record an alternative validation method before implementation starts.

Handoff requirements:

- Hand off to Review Agent with task path, changed files, tests added or skipped, validation output, and known risks.
- Stop and return to Task Manager Agent when the task artifacts are missing, contradictory, or require out-of-scope changes.

### Review Agent

Allowed artifact paths:

- Project-specific `tasks/TASK-XXX-short-title/review.md`.
- `templates/project/REVIEW_REPORT.md`.
- Review sections in project-specific management artifacts.

Forbidden actions:

- Implementing fixes while acting as reviewer.
- Approving work without checking source task artifacts.
- Rewriting acceptance criteria to fit the implementation.

Required inputs:

- Task folder or transitional task contract.
- Implementation notes.
- Changed files or diff.
- Test and validation evidence.
- Relevant product and architecture artifacts.

Required outputs:

- Review report with verdict.
- Findings ordered by severity.
- Contract compliance table.
- Scope check.
- Test and validation review.
- Open questions.

Handoff requirements:

- Hand off accepted work to QA Agent with review report and validation evidence.
- Hand off rejected work to Task Manager Agent with required changes and blocking questions.

### QA Agent

Allowed artifact paths:

- Project-specific `tasks/TASK-XXX-short-title/test.md`.
- Project-specific validation artifacts.
- `templates/project/management/VALIDATION_STATUS.md`.
- Legacy compatibility file: `templates/project/VALIDATION_STATUS.md`.
- `docs/management/` validation conventions.

Forbidden actions:

- Changing implementation code while acting as QA.
- Marking work validated from confidence alone.
- Ignoring untested acceptance criteria.

Required inputs:

- Task folder or transitional task contract.
- Review report.
- Required validation gates.
- Commands, environments, or manual checks available for validation.

Required outputs:

- Validation status with exact checks, commands, observations, results, untested areas, and remaining risk.
- Pass, fail, partial, or blocked decision.
- Follow-up tasks for unresolved validation gaps when needed.

Handoff requirements:

- Hand off validated work to Lead Agent or Task Manager Agent for board updates.
- Hand off failed or blocked validation to Task Manager Agent with evidence and next required action.

## Artifact Status Vocabulary

Use these statuses consistently:

- `Draft`: written but not yet reviewed.
- `Reviewed`: reviewed for coherence, still not approved for execution.
- `Approved`: accepted as a source for downstream work.
- `Ready`: task has required inputs and can be assigned.
- `In Progress`: currently being executed or validated.
- `Blocked`: cannot continue without a decision or dependency.
- `Validated`: evidence shows acceptance criteria are met.
- `Superseded`: replaced by a newer artifact.

## Handoff Rule

Every handoff between agents must name:

- source artifact
- target artifact
- allowed scope
- required evidence
- next owner role
- stop conditions

If a handoff cannot name those fields, it is not ready.
