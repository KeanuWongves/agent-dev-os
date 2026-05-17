# Project Template Set

Copy this directory when starting a new software project under `agent-dev-os`.

Recommended order:

1. Copy `AGENTS.md` into the target project root.
2. Fill `research/` when reference research is required, or record an explicit waiver.
3. Fill `product/PRD.md`.
4. Fill `product/MVP.md`.
5. Fill `product/ROADMAP.md` and `product/USER_STORIES.md` as needed.
6. Fill `architecture/SYSTEM_DESIGN.md` for approved MVP scope.
7. Fill architecture support artifacts when they constrain execution: `TECH_STACK.md`, `API_SPEC.md`, `CODE_RULES.md`, and `DECISIONS.md`. For artifact-only projects, `API_SPEC.md` may describe file or artifact interface contracts; its existence does not authorize a network API, service, CLI, or runtime.
8. Fill `management/MASTER_PLAN.md`.
9. Create tasks in `management/TASK_BOARD.md`.
10. Generate one task folder under `tasks/TASK-XXX-short-title/`.
11. Record review and validation in task-local `review.md`, task-local `test.md`, and `management/VALIDATION_STATUS.md`.

## Nested Structure

| Directory | Purpose |
| --- | --- |
| `research/` | Research brief, source log, open-source scan, reference-product analysis, feature matrix, gap analysis, and reuse decisions. |
| `product/` | PRD, MVP, roadmap, and user stories. |
| `architecture/` | System design, stack, APIs, code rules, and decisions. |
| `management/` | Master plan, task board, blockers, status, changelog, and validation status. |
| `state/` | Lightweight project state, task graph, ownership, and workflow state. |

Each artifact should name upstream sources and downstream consumers so future agents know how to resume. `state/` helps with resumability but does not replace durable Markdown decisions.

Task templates are normalized so each task has `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md`.

Legacy flat files such as `PRD.md`, `SYSTEM_DESIGN.md`, `TASK_BOARD.md`, and `VALIDATION_STATUS.md` remain for backward compatibility. New generated projects should use the nested files.

Use `DOGFOOD_NOTES.md` when creating example projects or running template dogfood rounds. It captures template friction, repeated fields, missing patterns, and candidate improvements for the next round.
