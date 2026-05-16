# Master Plan: Weekly Report Assistant

Template rule: do not break work into executable tasks until product and architecture inputs are coherent enough to constrain scope.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Lead Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `product/PRD.md`, `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |
| Downstream Consumers | `management/TASK_BOARD.md`, `tasks/`, `state/task_graph.yaml` |

## Objective

Create an artifact-only MVP workflow foundation and prepare exactly one Ready task that can create the commit summary template without product code.

## Workstreams

| Workstream | Outcome | Source Artifact | Owner Role |
| --- | --- | --- | --- |
| Product scope | Approved local-first weekly-report assistant MVP scope. | `product/PRD.md`, `product/MVP.md` | PM Agent |
| Architecture guardrails | Artifact-only design with no runtime or dependencies. | `architecture/SYSTEM_DESIGN.md`, `architecture/CODE_RULES.md` | Architect Agent |
| Task planning | One executable task folder for commit summary template creation. | `management/TASK_BOARD.md` | Task Manager Agent |
| Validation readiness | Evidence expectations for artifact-only execution. | `architecture/API_SPEC.md`, `management/VALIDATION_STATUS.md` | QA Agent |

## Sequencing

| Sequence | Task or Milestone | Depends On | Exit Criteria |
| --- | --- | --- | --- |
| 1 | M0 artifact chain | User brief | Product, architecture, management, state, and TASK-001 artifacts exist. |
| 2 | TASK-001 create commit summary template | M0 artifact chain | `product/COMMIT_SUMMARY_TEMPLATE.md` exists and task-local evidence is recorded. |
| 3 | M1 validation decision | TASK-001 execution and review | QA validates or blocks the commit summary template with evidence. |
| 4 | M2 weekly report outline planning | M1 validation | New task folder is planned only after TASK-001 validation. |

## Task Breakdown

| Task ID | Title | Scope | Required Artifact | Status |
| --- | --- | --- | --- | --- |
| TASK-001 | Create commit summary template | Create one Markdown product artifact for commit evidence capture; update task-local execution and test logs only. | `tasks/TASK-001-create-commit-summary-template/` | Ready |

## Validation Gates

| Gate | Applies To | Evidence Required | Owner |
| --- | --- | --- | --- |
| VG-001 | TASK-001 scope | `git diff --name-only` or equivalent path list showing only allowed files changed during execution. | Review Agent |
| VG-002 | TASK-001 artifact quality | Manual inspection that template covers required evidence fields, five primary groups, uncertainty handling, and missing-evidence handling. | QA Agent |
| VG-003 | No-code/dependency constraint | File scan showing no `.py`, `.js`, dependency manifests, CLI files, services, or validation scripts added. | QA Agent |
| VG-004 | TDD alternative evidence | `test.md` records why TDD is not applicable and what manual/static validation was used before implementation starts. | Code Agent |

## Risks and Watchpoints

| Risk | Trigger | Response |
| --- | --- | --- |
| Task expands into a parser or CLI. | Code Agent proposes executable files or dependency manifests. | Stop and return to Task Manager Agent; update product/architecture only if scope is approved. |
| Template becomes too heavy for weekly-report use. | Required fields exceed the evidence needed for MVP. | Keep only required fields from API-001 and record friction in `NOTES.md`. |
| Validation is reported from confidence alone. | `test.md` lacks exact checks or observations. | Review Agent blocks QA handoff. |

## Plan Update Rules

- If product scope changes, update `product/PRD.md` or `product/MVP.md` first.
- If design constraints change, update `architecture/SYSTEM_DESIGN.md` or `architecture/DECISIONS.md` before task folders.
- If task ordering changes, update this plan, `management/TASK_BOARD.md`, and `state/task_graph.yaml`.
