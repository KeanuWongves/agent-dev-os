# Success Criteria

## Product-Level Success

The project is successful when a developer can start with a rough idea and produce a coherent chain of artifacts that leads to validated implementation:

```text
vision -> product -> architecture -> plan -> task folder -> execution -> review -> validation
```

## MVP Success Criteria

| Criterion | Evidence |
| --- | --- |
| A project can be initialized manually. | `templates/project/` contains complete project-level artifact templates. |
| A task can be delegated to Codex. | A `tasks/TASK-XXX-short-title/` folder plus `templates/codex-prompts/EXECUTE_TASK.md` define bounded execution context. |
| Review can happen without chat history. | `templates/project/REVIEW_REPORT.md` asks reviewers to compare output against source artifacts. |
| Validation is evidence-based. | `templates/project/VALIDATION_STATUS.md` records exact checks, results, gaps, and risk. |
| Agent roles are clear. | `AGENTS.md` defines PM, architect, lead, task manager, code, review, and QA boundaries. |
| Repo stays inspectable. | No unnecessary dependencies, generated files, or hidden state. |

## Quality Bar

Artifacts are useful when they are:

- Specific enough to guide work.
- Short enough to be maintained.
- Explicit about assumptions and open questions.
- Linked to upstream and downstream artifacts.
- Written so a new agent can resume without private memory.

## Failure Signals

- A task requires rereading chat history to understand what to build.
- An implementation changes files not named or implied by a task folder.
- A review cannot identify the acceptance criteria.
- A validation artifact says "looks good" without commands or observations.
- Templates become broad checklists with no decision pressure.
