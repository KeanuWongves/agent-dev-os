# Codex Execution Plan: <TASK-ID> <Title>

| Field | Value |
| --- | --- |
| Status | Draft |
| Prepared By | <Task Manager Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Task Folder | <tasks/TASK-XXX-short-title/ path> |
| Transitional Task Contract | <TASK_CONTRACT.md path if still used> |

## Execution Context

Codex must execute only the task folder or transitional task contract named above. If the task artifacts conflict with repository state, Codex should stop and report the conflict instead of expanding scope.

For new task instances, use `tasks/TASK-XXX-short-title/plan.md`. This file remains available for transitional task instances.

## Files to Inspect First

| Path | Why It Matters |
| --- | --- |
| <path> | <reason> |

## Expected Edit Surface

| Path | Expected Change |
| --- | --- |
| <path> | <change> |

## Step Plan

1. Read the task folder or transitional task contract and source artifacts.
2. Inspect the current implementation or artifact state.
3. Before implementation, write or update tests first.
4. If TDD is not applicable, record why and define an alternative validation method before implementation starts.
5. Make the smallest change that satisfies the acceptance criteria.
6. Run the required validation commands.
7. Update execution notes, review inputs, or validation status as required.

## TDD or Alternative Validation

Before implementation, the Code Agent must either:

- write or update tests first, or
- explicitly explain why TDD is not applicable and record an alternative validation method.

Record the decision in the task-local `test.md` artifact when using the folder-per-task model.

## Required Commands

```bash
<command>
```

## Stop Conditions

- Required source artifacts are missing.
- Acceptance criteria contradict implementation constraints.
- The task requires changing files outside the allowed scope.
- Validation cannot be run and no alternative evidence is approved.
- TDD is skipped without a recorded alternative validation method.

## Final Response Requirements

Codex should report:

- files changed
- acceptance criteria status
- tests written first, or reason TDD was not applicable
- validation commands and results
- unresolved risks or blocked items
