# System Design: Weekly Report Assistant

Template rule: design only the approved or review-ready MVP scope. Product expansion belongs in `product/`.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Architect Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md` |
| Downstream Consumers | `management/MASTER_PLAN.md`, `tasks/`, `tasks/*/review.md` |

## Design Summary

The MVP is an artifact-only workflow made of Markdown templates and manual review steps. There is no product runtime, no parser, no CLI, no database, and no external integration. The first artifact interface is a commit summary template that captures raw git evidence and grouping metadata. A later artifact may turn grouped items into a weekly-report outline, but that is deferred until TASK-001 is validated. Validation is performed through artifact inspection, path checks, and no-code/dependency scans rather than executable product tests. This design fits the MVP because the product risk is workflow clarity, not runtime feasibility.

## Goals and Constraints

| Type | Item | Source |
| --- | --- | --- |
| Goal | Capture local commit evidence in a structured Markdown artifact. | PRD-001, MVP-001 |
| Goal | Classify work by project, feature, bugfix, experiment, and blocker. | PRD-002, MVP-002 |
| Goal | Preserve evidence references for later report drafting. | PRD-003, MVP-003 |
| Constraint | No product source code, CLI, dependency, database, web UI, agent runtime, scheduler, service, or validation code. | PRD constraints, Round 2 dogfood brief |
| Constraint | MVP must work without network access or external credentials. | NFR-001 |

## Component Map

| Component | Responsibility | Inputs | Outputs | Owner |
| --- | --- | --- | --- | --- |
| Commit Evidence Template | Capture raw commit entries and required evidence fields. | Local git log excerpt or manual work item. | Structured Markdown rows or sections. | Code Agent for TASK-001 |
| Grouping Rubric | Define project, feature, bugfix, experiment, blocker, optional tags, and uncertainty handling. | Product requirements and user stories. | Classification guidance embedded in the template. | Architect Agent and Task Manager Agent |
| Report Outline Contract | Define how grouped evidence can later become weekly-report sections. | Grouped commit summary items. | Future Markdown weekly-report outline. | PM Agent for deferred milestone |
| Manual Validation Checklist | Confirm artifact completeness without executable validation code. | Created template and task acceptance criteria. | Evidence in task-local `test.md`. | QA Agent |

## Data Model

| Entity | Fields | Owner | Persistence | Notes |
| --- | --- | --- | --- | --- |
| CommitEvidenceItem | repo, date_range, commit_hash, commit_date, author, branch_or_context, raw_message, source_command, evidence_notes | Commit Evidence Template | Markdown artifact | Commit hash may be `unknown` for manually entered work items. |
| WorkGrouping | primary_group, project_name, optional_tags, review_needed, uncertainty_reason | Grouping Rubric | Markdown artifact | `primary_group` must be one of project, feature, bugfix, experiment, blocker. |
| ReportBulletCandidate | report_section, summary, evidence_refs, metric_status, follow_up | Report Outline Contract | Future Markdown artifact | Deferred until after TASK-001 validation. |

## Interfaces

| Interface | Producer | Consumer | Contract | Failure Behavior |
| --- | --- | --- | --- | --- |
| Commit summary Markdown artifact | Commit Evidence Template | User and future report outline task | Required fields listed in `architecture/API_SPEC.md` API-001. | Missing fields are marked `unknown` or `evidence missing`; no silent inference. |
| Grouping rubric | Grouping Rubric | Commit Evidence Template and Review Agent | Category definitions and one primary group rule. | Ambiguous items use optional tags and `review_needed: yes`. |
| Task validation evidence | Manual Validation Checklist | Review Agent and QA Agent | `test.md` records checks, observations, and no-code/dependency scan results. | Missing evidence blocks review or QA. |

## Execution Flow

| Step | Actor or Component | Action | Input | Output |
| --- | --- | --- | --- | --- |
| 1 | Engineer | Collect local git history for the week. | `git log` excerpt or manual notes. | Raw commit evidence. |
| 2 | Commit Evidence Template | Provide fields for each raw item. | Raw commit evidence. | Structured evidence entries. |
| 3 | Grouping Rubric | Guide primary category selection and optional tags. | Structured evidence entries. | Grouped work items. |
| 4 | Manual Validation Checklist | Inspect template coverage and scope compliance. | TASK-001 output and task contract. | Validation evidence in `tasks/TASK-001-create-commit-summary-template/test.md`. |
| 5 | Future Report Outline Contract | Convert grouped items to report sections. | Validated grouped items. | Deferred weekly-report outline. |

## State and Persistence

| State Item | Location | Created By | Updated By | Retention or Cleanup |
| --- | --- | --- | --- | --- |
| Product and workflow decisions | `product/`, `architecture/`, `management/` | PM, Architect, Lead Agents | Responsible owner role | Retained as source of truth. |
| Task execution state | `tasks/TASK-001-create-commit-summary-template/` | Task Manager Agent | Code, Review, QA Agents | Retained with validation evidence. |
| Project state mirror | `state/*.yaml` | Lead and Task Manager Agents | Responsible owner role | Keep lightweight and consistent with task board. |
| Commit summary template deliverable | `product/COMMIT_SUMMARY_TEMPLATE.md` | Code Agent for TASK-001 | Future approved tasks only | Retained as MVP artifact after validation. |

## Alternatives Considered

| Alternative | Benefit | Reason Rejected |
| --- | --- | --- |
| CLI that parses git history. | Faster repeated use and less manual copying. | Explicitly disallowed for Round 2 and premature before workflow validation. |
| Web UI for editing weekly-report items. | More guided data entry. | Explicitly disallowed and adds runtime surface. |
| External GitHub/GitLab import. | Better commit metadata. | Violates local-first and no external service constraints. |
| Validation script for artifact checks. | Repeatable checks. | Validation code is explicitly disallowed; use shell/file inspection only. |

## Architecture Decisions

| ID | Decision | Rationale | Consequences |
| --- | --- | --- | --- |
| ADR-001 | Use Markdown artifacts as the MVP interface. | Satisfies local-first and no-runtime constraints. | Tasks validate structure by artifact inspection, not product tests. |
| ADR-002 | Store the first deliverable in `product/COMMIT_SUMMARY_TEMPLATE.md`. | The template is product-facing workflow content, not source code. | TASK-001 may create that artifact and update task-local execution evidence only. |
| ADR-003 | Treat API spec as artifact contract, not network API. | The MVP has no runtime API. | `architecture/API_SPEC.md` documents file/interface fields. |

## Implementation Guardrails

- Code Agents must not create product source files, executable scripts, dependency manifests, service configs, databases, web UI files, schedulers, or validation code.
- TASK-001 may create only `product/COMMIT_SUMMARY_TEMPLATE.md` and update its own `implementation.md` and `test.md`.
- Any future runtime implementation requires PM scope update, architecture decision, task board update, and a new task folder.
- Claims in report artifacts must keep evidence references or explicit missing-evidence markers.

## Open Technical Questions

| Question | Impact | Required Before | Resolution Artifact |
| --- | --- | --- | --- |
| Should the commit summary template use tables, repeated sections, or both? | Affects usability and review ergonomics. | TASK-001 execution | `tasks/TASK-001-create-commit-summary-template/implementation.md` |
| Should category values be encoded as plain text or YAML-like front matter in future templates? | Affects future automation compatibility. | Any parser or CLI planning | `architecture/DECISIONS.md` |
