# Codex Execution Plan: <TASK-ID> <Title>

| Field | Value |
| --- | --- |
| Status | Draft |
| Prepared By | <Planning Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Task Contract | <TASK_CONTRACT.md path> |

## Execution Context

Codex must execute only the task contract named above. If the contract conflicts with repository state, Codex should stop and report the conflict instead of expanding scope.

## Files to Inspect First

| Path | Why It Matters |
| --- | --- |
| <path> | <reason> |

## Expected Edit Surface

| Path | Expected Change |
| --- | --- |
| <path> | <change> |

## Step Plan

1. Read the task contract and source artifacts.
2. Inspect the current implementation or artifact state.
3. Make the smallest change that satisfies the acceptance criteria.
4. Run the required validation commands.
5. Update execution notes, review inputs, or validation status as required.

## Required Commands

```bash
<command>
```

## Stop Conditions

- Required source artifacts are missing.
- Acceptance criteria contradict implementation constraints.
- The task requires changing files outside the allowed scope.
- Validation cannot be run and no alternative evidence is approved.

## Final Response Requirements

Codex should report:

- files changed
- acceptance criteria status
- validation commands and results
- unresolved risks or blocked items
