# Code Rules: <Project Name>

Template rule: code rules are implementation constraints, not style preferences. Keep them enforceable by review or validation.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Architect Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Human Review Gates | `management/HUMAN_REVIEW_GATES.md` |
| Approval Log | `management/APPROVALS.md` |
| Required Human Gate | Gate 3: Architecture Approval |
| Approval Status | <not required / pending / approved / approved with limitations / waived / rejected / needs revision / blocked> |
| Approval Artifact | <management/APPROVALS.md#APP-XXX or N/A> |
| Next Human Decision Needed | <decision or N/A> |
| Source Artifacts | `architecture/SYSTEM_DESIGN.md`, `architecture/TECH_STACK.md` |
| Downstream Consumers | `tasks/`, `tasks/*/review.md` |

Approval rule: architecture artifacts may be drafted before approval, but implementation planning must not treat these code rules as approved until Gate 3 approval or waiver is recorded in `management/APPROVALS.md` and linked above.

## Scope

<Name the source paths, test paths, and artifact paths these rules govern.>

## Required Rules

| Rule ID | Rule | Applies To | Evidence or Review Method |
| --- | --- | --- | --- |
| CR-001 | <rule> | <paths/components> | <lint/test/review/static check/manual check> |

## Forbidden Patterns

| Pattern ID | Pattern | Reason | Exception Process |
| --- | --- | --- | --- |
| FP-001 | <pattern> | <why forbidden> | <architecture decision or task approval required> |

## Testing Rules

- Code Agents must write or update tests before implementation when TDD applies.
- If TDD is not applicable, Code Agents must document the reason and alternative validation in the task-local `test.md` before implementation starts.
- Review Agents must reject implementation evidence that cannot be rerun or inspected.

## Documentation Rules

- Durable implementation decisions belong in task artifacts or architecture decisions, not chat history.
- Comments should explain non-obvious constraints, not restate obvious code.
- Public interfaces must trace to `architecture/API_SPEC.md` when applicable.
