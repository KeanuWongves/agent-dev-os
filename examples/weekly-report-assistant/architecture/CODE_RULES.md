# Code Rules: Weekly Report Assistant

Template rule: code rules are implementation constraints, not style preferences. Keep them enforceable by review or validation.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Architect Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `architecture/SYSTEM_DESIGN.md`, `architecture/TECH_STACK.md` |
| Downstream Consumers | `tasks/`, `tasks/*/review.md` |

## Scope

These rules govern all files in `examples/weekly-report-assistant/`. The current MVP permits Markdown and YAML artifacts only. `src/`, `tests/`, executable scripts, dependency manifests, runtime configuration, generated assets, and validation code are outside approved scope.

## Required Rules

| Rule ID | Rule | Applies To | Evidence or Review Method |
| --- | --- | --- | --- |
| CR-001 | Changes must stay within the task's exact allowed paths. | `tasks/`, approved artifact deliverables | Review `git diff --name-only` against `task.md`. |
| CR-002 | Artifact templates must preserve source evidence fields instead of replacing them with generated prose. | `product/COMMIT_SUMMARY_TEMPLATE.md` and future report artifacts | Manual artifact inspection. |
| CR-003 | Every report claim field must allow `unknown` or `evidence missing` when evidence is unavailable. | Commit and report templates | Manual artifact inspection against API-001. |
| CR-004 | Validation evidence must be recorded in task-local `test.md` with command or manual-check details. | Task folders | Review `test.md` for exact checks, expected result, observed result, and status. |
| CR-005 | Scope friction found while using templates must be recorded in example-local `NOTES.md`. | Example artifacts | Inspect `NOTES.md`. |

## Forbidden Patterns

| Pattern ID | Pattern | Reason | Exception Process |
| --- | --- | --- | --- |
| FP-001 | Adding `.py`, `.js`, `.ts`, shell scripts, or other executable product files. | Violates artifact-only MVP. | Future approved product-code task and architecture decision required. |
| FP-002 | Adding `package.json`, `pyproject.toml`, `requirements.txt`, lockfiles, or dependency config. | Dependencies are explicitly forbidden. | Future approved dependency decision required. |
| FP-003 | Creating a CLI command, web UI, database schema, scheduler, service config, or agent runtime. | Expands product scope beyond MVP. | PM and Architect approval plus new task folder required. |
| FP-004 | Marking implementation, review, QA, or validation complete without evidence. | Breaks artifact-first status semantics. | Record evidence in `test.md`, then review. |
| FP-005 | Inferring metrics or impact not present in commit evidence. | Produces unsupported weekly-report claims. | Mark metric as unknown or evidence missing. |

## Testing Rules

- Code Agents must write or update tests before implementation when TDD applies.
- If TDD is not applicable, Code Agents must document the reason and alternative validation in the task-local `test.md` before implementation starts.
- Review Agents must reject implementation evidence that cannot be rerun or inspected.
- For artifact-only tasks, acceptable validation is manual artifact inspection plus existing shell/file checks listed in the task; do not create validation scripts.

## Documentation Rules

- Durable implementation decisions belong in task artifacts or architecture decisions, not chat history.
- Comments should explain non-obvious constraints, not restate obvious code.
- Public interfaces must trace to `architecture/API_SPEC.md` when applicable.
- Template friction discovered during dogfooding belongs in `NOTES.md`.
