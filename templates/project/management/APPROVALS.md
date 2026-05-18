# Approvals: <Project Name>

Template rule: this file is the durable approval log. Chat approvals do not unlock downstream execution unless recorded here.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <human owner or Lead Agent maintaining the log> |
| Last Updated | YYYY-MM-DD |
| Workflow Profile | `management/WORKFLOW_PROFILE.md` |
| Gate Definitions | `management/HUMAN_REVIEW_GATES.md` |
| Downstream Consumers | `product/`, `architecture/`, `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `tasks/`, `management/VALIDATION_STATUS.md`, `management/CHANGELOG.md` |

## Approval Records

Allowed decisions: `approved`, `approved with limitations`, `rejected`, `needs revision`, `waived`, `not required`.

| Approval ID | Gate | Artifact | Decision | Human Owner | Date | Notes | Downstream Scope Unlocked | Limitations or Waiver |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| APP-001 | Gate <0-6>: <name> | <artifact path> | <allowed decision> | <human name or role> | YYYY-MM-DD | <decision evidence and context> | <specific downstream artifacts or workflows unlocked> | <limits, waiver rationale, unresolved risk, or N/A> |

## Pending Human Decisions

| Decision ID | Gate | Artifact | Question | Needed Before | Owner | Status |
| --- | --- | --- | --- | --- | --- | --- |
| DEC-001 | Gate <0-6>: <name> | <artifact path> | <decision needed> | <workflow or artifact blocked> | <human owner> | <pending / answered / blocked> |

## Approval Rules

- Record the specific artifact path and decision. Do not approve broad unnamed scope.
- Record limitations when approval is partial.
- Record waivers as human decisions, not as missing evidence.
- Record `not required` only when `management/WORKFLOW_PROFILE.md` explains why the gate does not apply.
- If approval unlocks execution, name the exact task folder, workflow, or artifact family unlocked.
- If a later decision supersedes an earlier approval, add a new row and reference the superseded approval ID.
