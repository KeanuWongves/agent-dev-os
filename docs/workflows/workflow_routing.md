# Workflow Routing

## Objective

Route each project into the smallest workflow profile that can safely produce the intended outcome.

Workflow routing prevents simple artifact-only projects from being forced through unnecessary research, architecture, QA, and release gates while still requiring stronger evidence for product, code, integration, or high-risk work.

## Responsible Gate

Gate 0: Idea Intake Review is always required. Gate 0 records the workflow mode, required artifacts, required gates, skipped gates, and escalation triggers before research, product discovery, architecture planning, or task execution begins.

Gate 0 output must be recorded in:

- `management/WORKFLOW_PROFILE.md`
- `management/APPROVALS.md`
- `management/HUMAN_REVIEW_GATES.md`

## Workflow Modes

| Mode | Use When | Primary Output | Default Risk |
| --- | --- | --- | --- |
| Light Artifact Workflow | The project produces planning, documentation, examples, templates, or other repository artifacts without product code or runtime behavior. | Approved artifact set and optionally one artifact-only task. | Low |
| Research-first Product Workflow | External references, open-source projects, closed-source products, creators, papers, screenshots, or reuse decisions may shape product scope. | Research artifacts feeding product discovery, PRD/MVP, and later planning. | Medium |
| Code Tool Workflow | The project will create or modify source code, tests, local tooling, or executable behavior under constrained scope. | Approved product/architecture/task chain plus executable task folders. | Medium |
| High-risk Integration Workflow | The project may involve credentials, external APIs, scraping/crawling, services, schedulers, databases, web UIs, agent runtimes, sensitive data, unclear licenses, or operational risk. | Research, architecture, task approval, exception gates, QA, and release acceptance evidence. | High |

## Routing Questions

Gate 0 must answer these questions before selecting a workflow mode:

| Question | Routing Impact |
| --- | --- |
| Is the requested output only documentation, templates, examples, or other artifacts? | Prefer Light Artifact Workflow. |
| Will product scope depend on reference products, repositories, creators, papers, screenshots, or reuse decisions? | Require or consider Research-first Product Workflow. |
| Will source code, tests, runtime behavior, commands, packaging, or local tooling be created or changed? | Require Code Tool Workflow or higher. |
| Will the work use external services, credentials, scraping, crawling, databases, schedulers, web UIs, agent runtimes, or background services? | Require High-risk Integration Workflow. |
| Is there license, privacy, security, compliance, or protected-content risk? | Require research, architecture review, and high-risk gates. |
| Can acceptance be verified by artifact inspection only? | QA and Gate 6 may be not applicable with rationale. |
| Could a downstream agent safely execute from a single task folder? | Gate 4 may be optional for low-risk tasks, required for non-trivial or high-risk tasks. |

## Required Artifacts by Mode

| Mode | Required Artifacts |
| --- | --- |
| Light Artifact Workflow | `management/WORKFLOW_PROFILE.md`, `management/HUMAN_REVIEW_GATES.md`, `management/APPROVALS.md`, minimal product brief or `product/PRD.md` with light scope, `management/TASK_BOARD.md` if tasks exist, task folder for executable artifact work. |
| Research-first Product Workflow | Light artifacts plus `research/RESEARCH_BRIEF.md`, `research/SOURCE_LOG.md`, relevant scans/analyses, `research/FEATURE_MATRIX.md`, `research/GAP_ANALYSIS.md`, `research/REUSE_DECISIONS.md`, `product/PRD.md`, `product/MVP.md`. |
| Code Tool Workflow | Product artifacts, architecture artifacts when implementation is constrained, `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `state/task_graph.yaml`, task folders, review and validation artifacts. |
| High-risk Integration Workflow | Research artifacts, full product artifacts, full architecture artifacts, approval records for required gates, explicit risk/exception handling, QA validation evidence, release/final acceptance artifacts when applicable. |

## Human Gates by Mode

| Gate | Light Artifact Workflow | Research-first Product Workflow | Code Tool Workflow | High-risk Integration Workflow |
| --- | --- | --- | --- | --- |
| Gate 0: Idea Intake Review | Required | Required | Required | Required |
| Gate 1: Research Review | Not required, optional, or waived | Required when research is required or performed | Optional unless references affect scope or dependencies | Required when external references, reuse, license, privacy, or integration risk exists |
| Gate 2: PRD / MVP Approval | Required for light product brief or scope approval | Required | Required | Required |
| Gate 3: Architecture Approval | Not required or light | Light or required when architecture constrains implementation | Required when architecture constrains implementation | Required |
| Gate 4: Task Plan Approval | Optional for low-risk artifact tasks; required for non-trivial artifact tasks | Required for non-trivial/high-risk tasks | Required for non-trivial/high-risk tasks | Required |
| Gate 5: Implementation Exception Review | Conditional | Conditional | Conditional | Conditional and likely |
| Gate 6: Release / Final Acceptance | Not applicable for internal drafts; optional for published artifact sets | Optional unless milestone/release acceptance is needed | Required for release/final acceptance | Required for release/final acceptance |

## Research Decision Rules

| Decision | Meaning | Required Evidence |
| --- | --- | --- |
| Required | References, competitors, repositories, creators, papers, screenshots, or reuse decisions may affect scope or risk. | Gate 0 decision plus research artifacts and Gate 1 review. |
| Optional | Research may improve quality but is not needed to safely define current scope. | Gate 0 rationale and allowed downstream assumptions. |
| Not Required | Work is artifact-only, internal, or based entirely on human-provided scope with no external dependency. | Gate 0 rationale in `management/WORKFLOW_PROFILE.md`. |
| Waived | Research would normally be useful or required, but the human owner chooses to proceed with limits. | Approval log entry naming waiver, limitations, and downstream scope unlocked. |
| Blocked | Research is required but sources, permissions, license evidence, or human notes are missing. | Blocker entry and stop condition. |

## Architecture Decision Rules

| Decision | Use When |
| --- | --- |
| Required | Source code, runtime behavior, interfaces, dependencies, data handling, services, schedulers, external APIs, scraping/crawling, credentials, databases, web UIs, or agent runtimes are in scope. |
| Light | Artifact-only or local-tool work needs file contracts, command contracts, boundaries, or no-runtime rules but not a full system design. |
| Not Required | The project only updates standalone documentation or templates and no implementation or runtime decisions are made. |

## Gate 4 Task Approval Rules

Gate 4 is required when a task is non-trivial or high-risk, including tasks that:

- touch source code, tests, runtime configuration, dependency manifests, credentials, external APIs, scraping/crawling, schedulers, services, databases, web UIs, or agent runtimes
- change product scope, architecture constraints, workflow gates, or validation requirements
- have broad edit surface or unclear rollback
- require non-obvious validation or unresolved assumptions

Gate 4 may be not required for low-risk artifact tasks only when the task records:

- `Required Human Gate` = `none`
- `Approval Status` = `not required`
- a filled not-required rationale
- clear allowed scope, forbidden scope, and validation method

## QA and Gate 6 Rules

QA is required when acceptance depends on executable behavior, user-visible behavior, release readiness, integration behavior, security/privacy risk, or validation evidence beyond manual artifact inspection.

QA may be light or not applicable when the work is an internal draft or artifact-only change that can be verified through:

- manual artifact inspection
- file existence checks
- changed-file scope checks
- no-code/dependency/runtime scans

Gate 6 is required before final release, milestone closure, or external acceptance. Gate 6 may be not applicable for internal drafts, template experiments, or pre-execution artifacts when `management/WORKFLOW_PROFILE.md` records the rationale.

## Escalation Triggers

Escalate to a stricter workflow mode when any of these appear:

- source code or tests become necessary after an artifact-only plan
- external references start shaping requirements without research artifacts
- architecture starts constraining implementation without Gate 3
- a low-risk task expands into broad or risky edit scope
- credentials, external APIs, scraping, crawling, services, schedulers, databases, web UIs, agent runtimes, or validation code enter scope
- license, privacy, compliance, or protected-content risk is unresolved
- QA evidence is needed to support a release or final acceptance claim

## Handoff

After Gate 0 routing:

- PM Agent uses the workflow profile to decide whether research is required before product discovery.
- Architect Agent uses the workflow profile to decide whether architecture is full, light, or not required.
- Task Manager Agent uses the workflow profile to decide whether Gate 4 is required before tasks become `Ready`.
- Review and QA Agents use the workflow profile to decide whether validation is artifact-only, light QA, full QA, or release acceptance.

If a downstream agent finds that the current work exceeds the workflow mode or risk level, the agent must stop and return to Gate 0 or the relevant human gate for rerouting.
