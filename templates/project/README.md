# Project Template Set

Copy this directory when starting a new software project under `agent-dev-os`.

Recommended order:

1. Copy `AGENTS.md` into the target project root.
2. Fill `management/WORKFLOW_PROFILE.md` from Gate 0 to choose the workflow mode, risk level, required artifacts, required gates, skipped gates, and escalation triggers.
3. Fill `management/HUMAN_REVIEW_GATES.md` and use `management/APPROVALS.md` to record required human decisions.
4. Fill `research/` when the workflow profile says reference research is required or performed; otherwise record a not-required or waived rationale.
5. Fill `product/PRD.md`, `product/MVP.md`, or a light product brief according to the workflow profile.
6. Fill `product/ROADMAP.md` and `product/USER_STORIES.md` as needed.
7. Fill `architecture/SYSTEM_DESIGN.md` when architecture is required or light.
8. Fill architecture support artifacts when they constrain execution: `TECH_STACK.md`, `API_SPEC.md`, `CODE_RULES.md`, and `DECISIONS.md`. For artifact-only projects, `API_SPEC.md` may describe file or artifact interface contracts; its existence does not authorize a network API, service, CLI, or runtime.
9. Fill `management/MASTER_PLAN.md`.
10. Create tasks in `management/TASK_BOARD.md`.
11. Generate one task folder under `tasks/TASK-XXX-short-title/`.
12. Record review and validation in task-local `review.md`, task-local `test.md`, and `management/VALIDATION_STATUS.md` when the workflow profile requires them.

## Nested Structure

| Directory | Purpose |
| --- | --- |
| `research/` | Research brief, source log, open-source scan, reference-product analysis, feature matrix, gap analysis, and reuse decisions. |
| `product/` | PRD, MVP, roadmap, and user stories. |
| `architecture/` | System design, stack, APIs, code rules, and decisions. |
| `management/` | Workflow profile, human review gates, approvals, master plan, task board, blockers, status, changelog, and validation status. |
| `state/` | Lightweight project state, task graph, ownership, and workflow state. |

Each artifact should name upstream sources and downstream consumers so future agents know how to resume. `state/` helps with resumability but does not replace durable Markdown decisions.

Do not assume every project needs every artifact or gate. `management/WORKFLOW_PROFILE.md` decides whether research, architecture, QA, release acceptance, and later human gates are required, optional, waived, or not required. Skipped workflows and gates must record rationale and limitations.

Gate-controlled product, architecture, and task artifacts should expose approval metadata locally, not only in `management/APPROVALS.md`. Do not mark product or architecture artifacts `Approved`, and do not mark task artifacts `Ready`, unless the local approval metadata points to a valid approval, waiver, or explicit not-required rationale.

Task templates are normalized so each task has `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md`.

Legacy flat files such as `PRD.md`, `SYSTEM_DESIGN.md`, `TASK_BOARD.md`, and `VALIDATION_STATUS.md` remain for backward compatibility. New generated projects should use the nested files.

Use `DOGFOOD_NOTES.md` when creating example projects or running template dogfood rounds. It captures template friction, repeated fields, missing patterns, and candidate improvements for the next round.
