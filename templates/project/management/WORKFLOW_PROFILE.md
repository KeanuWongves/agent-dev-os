# Workflow Profile: <Project Name>

Template rule: create this artifact immediately after Gate 0. It decides which workflows, artifacts, and human gates are required for this project. Do not assume the full workflow is required unless this profile says so.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent, PM Agent, or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Decision | `management/APPROVALS.md#<Gate-0-record>` |
| Human Review Gates | `management/HUMAN_REVIEW_GATES.md` |
| Approval Log | `management/APPROVALS.md` |
| Downstream Consumers | `research/`, `product/`, `architecture/`, `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `tasks/`, `state/workflow_state.yaml` |

## Project Classification

| Field | Value |
| --- | --- |
| Project Type | <artifact-only / product planning / code tool / integration / other> |
| Primary User | <user or role> |
| Primary Input | <idea, files, user action, external source, codebase, etc.> |
| Primary Output | <artifact, PRD, code tool, report, release, etc.> |
| Risk Level | <low / medium / high> |
| Workflow Mode | <Light Artifact Workflow / Research-first Product Workflow / Code Tool Workflow / High-risk Integration Workflow> |

## Routing Decision

| Decision Area | Decision | Rationale | Evidence or Approval |
| --- | --- | --- | --- |
| Research | <required / optional / not required / waived / blocked> | <why> | <artifact or approval ID> |
| Architecture | <required / light / not required / blocked> | <why> | <artifact or approval ID> |
| Implementation | <artifact-only / code allowed / blocked / not in scope> | <why> | <artifact or approval ID> |
| Review / QA | <manual artifact inspection / light QA / full QA / not applicable> | <why> | <artifact or approval ID> |

## Required Human Gates

| Gate | Required Status | Reason | Approval Artifact |
| --- | --- | --- | --- |
| Gate 0: Idea Intake Review | required | Workflow routing is always required. | `management/APPROVALS.md#<id>` |
| Gate 1: Research Review | <required / optional / waived / not required / blocked> | <reason> | <APPROVALS row ID or N/A> |
| Gate 2: PRD / MVP Approval | <required / light approval / waived / not required / blocked> | <reason> | <APPROVALS row ID or N/A> |
| Gate 3: Architecture Approval | <required / light approval / waived / not required / blocked> | <reason> | <APPROVALS row ID or N/A> |
| Gate 4: Task Plan Approval | <required for non-trivial/high-risk tasks / optional / waived / not required / blocked> | <reason> | <APPROVALS row ID or N/A> |
| Gate 5: Implementation Exception Review | conditional | Required only when execution exceeds approved scope. | <APPROVALS row ID or N/A> |
| Gate 6: Release / Final Acceptance | <required / optional / not applicable / blocked> | <reason> | <APPROVALS row ID or N/A> |

## Skipped Gates With Rationale

| Gate | Decision | Rationale | Limitation |
| --- | --- | --- | --- |
| <Gate> | <not required / waived> | <why skipping is acceptable> | <what downstream agents must not assume> |

## Minimum Artifact Set

| Artifact | Required? | Reason | Status |
| --- | --- | --- | --- |
| `management/WORKFLOW_PROFILE.md` | Yes | Records Gate 0 routing. | Draft |
| `management/HUMAN_REVIEW_GATES.md` | Yes | Defines gate semantics. | Draft |
| `management/APPROVALS.md` | Yes | Records human decisions. | Draft |
| `research/` | <Yes/No/Conditional> | <routing rationale> | <status> |
| `product/PRD.md` or light product brief | <Yes/No/Conditional> | <routing rationale> | <status> |
| `product/MVP.md` | <Yes/No/Conditional> | <routing rationale> | <status> |
| `architecture/` | <Full/Light/No/Conditional> | <routing rationale> | <status> |
| `management/MASTER_PLAN.md` | <Yes/No/Conditional> | <routing rationale> | <status> |
| `management/TASK_BOARD.md` | <Yes/No/Conditional> | <routing rationale> | <status> |
| `tasks/` | <Yes/No/Conditional> | <routing rationale> | <status> |
| `management/VALIDATION_STATUS.md` | <Yes/No/Conditional> | <routing rationale> | <status> |

## Escalation Triggers

If any trigger occurs, stop and update this workflow profile before continuing.

| Trigger | Escalate To | Required Action |
| --- | --- | --- |
| Source code, tests, runtime config, dependency manifests, or executable behavior become necessary. | Code Tool Workflow | Require architecture and task approval as applicable. |
| External references start shaping requirements. | Research-first Product Workflow | Create or complete research artifacts and Gate 1 review. |
| Credentials, external APIs, scraping, crawling, database, service, scheduler, web UI, agent runtime, or validation code enters scope. | High-risk Integration Workflow | Require full architecture review and high-risk gate handling. |
| Low-risk task scope becomes broad, ambiguous, or high-risk. | Gate 4 Task Plan Approval | Block execution until task approval or waiver is recorded. |
| Release or final acceptance is requested. | Gate 6 Release / Final Acceptance | Require validation evidence and human acceptance decision. |

## Routing Notes

<Record any project-specific constraints, assumptions, or human decisions that explain why this workflow profile is sufficient.>
