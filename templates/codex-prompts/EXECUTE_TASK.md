# Execute Task Prompt

You are executing one task in an artifact-driven repository.

## Required Context

- Task contract: `<path/to/TASK_CONTRACT.md>`
- Execution plan: `<path/to/CODEX_EXECUTION_PLAN.md>`
- Source artifacts: `<paths to PRD, MVP, system design, master plan>`

## Instructions

1. Read the task contract first.
2. Confirm the allowed scope before editing.
3. Inspect the files named in the execution plan.
4. Implement only the acceptance criteria in the task contract.
5. Run the required validation commands.
6. Update execution notes or validation artifacts if the task contract requires it.
7. Final response must include changed files, validation results, and unresolved risk.

## Stop Conditions

Stop and report instead of editing if:

- The task contract is missing or still `Draft` when approval is required.
- Required artifacts contradict each other.
- The requested work exceeds allowed scope.
- A needed decision exists only in chat history.
