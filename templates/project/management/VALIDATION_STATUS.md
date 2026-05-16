# Validation Status: <Project Name>

Template rule: QA must not mark work validated from confidence alone. Every validation decision needs exact evidence.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <QA Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `tasks/`, `management/TASK_BOARD.md`, `architecture/SYSTEM_DESIGN.md` |

## Validation Summary

<Summarize what has been validated and what remains unvalidated. Do not use confidence-only language.>

## Validation Matrix

| Item | Source Requirement | Check Performed | Result | Evidence | Remaining Risk |
| --- | --- | --- | --- | --- | --- |
| <feature/task> | <PRD/MVP/TASK ID> | <command, test, inspection, demo> | Pass/Fail/Partial/Not Run/Blocked | <output path or notes> | <risk> |

## Commands Run

| Timestamp | Command | Working Directory | Exit Code | Result Summary |
| --- | --- | --- | --- | --- |
| YYYY-MM-DD HH:MM | `<exact command>` | `<path>` | <0/nonzero/N/A> | <key output> |

## Manual Observations

| Check ID | Steps | Expected | Observed | Result |
| --- | --- | --- | --- | --- |
| MAN-001 | <steps> | <expected> | <observed> | <Pass/Fail/Partial/Blocked> |

## Not Validated

| Item | Reason | Risk | Required Follow-Up |
| --- | --- | --- | --- |
| <item> | <why not checked> | <risk> | <next check> |

## Validation Decision

| Field | Value |
| --- | --- |
| Decision | <Validated/Partially Validated/Failed/Blocked> |
| Rationale | <evidence-based rationale> |
| Follow-Up Required | <task IDs, artifacts, or N/A> |
