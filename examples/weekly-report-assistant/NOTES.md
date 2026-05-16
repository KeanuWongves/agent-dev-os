# Round 2 Dogfood Notes: Weekly Report Assistant

## Templates That Were Easy to Use

| Template Area | What Worked |
| --- | --- |
| `templates/project/product/PRD.md` | The split between goals, non-goals, requirements, constraints, assumptions, and open questions made it easy to keep the vague idea from turning into hidden implementation scope. |
| `templates/project/product/MVP.md` | Included and excluded capabilities were useful for making the no-code, no-CLI, no-integration boundary explicit. |
| `templates/project/architecture/CODE_RULES.md` | Required rules and forbidden patterns mapped cleanly to the Round 2 constraints. |
| `templates/project/management/TASK_BOARD.md` | The Ready policy helped make the task folder completeness requirement concrete. |
| `templates/task/task.md` | Allowed Changes, Forbidden Changes, Expected Edit Surface, Acceptance Criteria, and Stop Conditions were the strongest parts of the task contract. |
| `templates/task/plan.md` | The TDD Plan made it possible to explicitly record an alternative validation method for an artifact-only task. |

## Templates That Felt Too Heavy

| Template Area | Friction |
| --- | --- |
| `templates/project/architecture/API_SPEC.md` | For an artifact-only MVP, "API" was easy to misread as runtime scope. It had to be adapted into a file/artifact contract. |
| `templates/task/review.md` | A full review report is useful after implementation, but heavy for a Ready task that has not been executed. Most sections need blocked or not-run rows. |
| `templates/task/implementation.md` | Before execution, many fields are necessarily pending. The template could use a clearer pre-execution variant. |
| `templates/project/management/VALIDATION_STATUS.md` | Project-level validation status is useful, but awkward before any task has been executed. It needs an explicit "Not Run because task is Ready but not executed" pattern. |
| State YAML templates | They are lightweight, but status vocabulary differs from artifact statuses and task-board statuses, which creates small consistency decisions. |

## Repeated Fields

| Repeated Field | Appears In | Impact |
| --- | --- | --- |
| Status, owner, last updated | Nearly every artifact | Good for traceability, but repetitive to fill for example projects. |
| Source artifacts and downstream consumers | Product, architecture, management, task artifacts | Helpful, but easy for paths to drift across files. |
| Allowed scope and stop conditions | `AGENTS.md`, `task.md`, `plan.md`, `review.md`, `workflow_state.yaml` | Necessary for safety, but repeated enough that a task-summary block could reduce drift. |
| Validation commands and validation IDs | `task.md`, `plan.md`, `test.md`, `management/VALIDATION_STATUS.md` | Useful for QA, but the same command list appears several times. |
| Handoff fields | `AGENTS.md`, `task.md`, `plan.md`, `implementation.md`, `test.md`, `review.md`, `workflow_state.yaml` | Enforces discipline, but a compact common handoff schema could be referenced instead of rewritten. |

## Missing Fields or Patterns

| Gap | Why It Matters |
| --- | --- |
| No explicit template field for "artifact-only task." | Several templates assume code/test execution unless the user manually writes N/A and alternative validation. |
| No explicit "pre-execution placeholder" status. | `implementation.md`, `test.md`, and `review.md` need to be Draft but structurally ready without pretending work happened. |
| No separate status vocabulary for task board state vs artifact approval state. | A task can be `Ready` while its implementation/test/review artifacts are `Draft`, which is valid but easy to misread. |
| No friction log field in core templates. | Dogfood friction had to be captured in example-local `NOTES.md`; that is useful enough to make standard. |
| No "no runtime surface" checklist. | The Round 2 constraints map to many separate forbidden items and would benefit from one reusable checklist. |
| No simple path for "API spec is a file contract, not a service API." | Artifact-only products need a clearer interface-contract naming option. |

## Recommended Template Improvements

| Recommendation | Target Template |
| --- | --- |
| Add an `Artifact-only task?` field with allowed validation modes and examples. | `templates/task/task.md`, `templates/task/plan.md`, `templates/task/test.md` |
| Add a pre-execution skeleton for `implementation.md`, `test.md`, and `review.md` that uses `Pending`, `Not Run`, and `Blocked` consistently. | `templates/task/implementation.md`, `templates/task/test.md`, `templates/task/review.md` |
| Rename or supplement `API_SPEC.md` with `INTERFACE_SPEC.md` for non-runtime projects. | `templates/project/architecture/API_SPEC.md` |
| Provide a common no-runtime checklist for tasks that must forbid code, dependencies, CLIs, databases, services, schedulers, UIs, and validation code. | `templates/task/task.md`, `templates/project/architecture/CODE_RULES.md` |
| Reduce repeated handoff blocks by allowing a canonical task-level handoff summary that later artifacts can reference. | All task templates |
| Add a standard dogfood notes template for template friction, repeated fields, missing fields, and recommended improvements. | `templates/project/` or `templates/task/` |
| Clarify when source artifacts may be marked `Approved` inside examples without implying real product launch readiness. | `templates/project/README.md`, workflow docs |
