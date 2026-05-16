# Execute Task Prompt

You are executing one task in an artifact-driven repository.

## Required Context

- Task folder: `<path/to/tasks/TASK-XXX-short-title/>`
- Task contract: `<path/to/TASK_CONTRACT.md>` if using transitional templates
- Execution plan: `<path/to/CODEX_EXECUTION_PLAN.md>` if using transitional templates
- Source artifacts: `<paths to PRD, MVP, system design, master plan>`

## Instructions

1. Read the task folder first, or the transitional task contract if Round 1 normalization has not happened yet.
2. Confirm the allowed scope before editing.
3. Inspect the files named in the execution plan.
4. Before implementation, write or update tests first.
5. If TDD is not applicable, explain why and record an alternative validation method before implementation starts.
6. Implement only the acceptance criteria in the task artifacts.
7. Run the required validation commands.
8. Update execution notes or validation artifacts if the task artifacts require it.
9. Final response must include changed files, TDD or alternative validation status, validation results, and unresolved risk.

## Stop Conditions

Stop and report instead of editing if:

- The task folder or transitional task contract is missing or still `Draft` when approval is required.
- Required artifacts contradict each other.
- The requested work exceeds allowed scope.
- A needed decision exists only in chat history.
- TDD is skipped without recording why and naming an alternative validation method.
