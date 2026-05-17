# Tech Stack: <Project Name>

Template rule: a technology is allowed only when it is listed here or explicitly authorized by a task artifact.

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
| Source Artifacts | `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |
| Downstream Consumers | `architecture/CODE_RULES.md`, `tasks/` |

Approval rule: architecture artifacts may be drafted before approval, but implementation planning must not treat this stack as approved until Gate 3 approval or waiver is recorded in `management/APPROVALS.md` and linked above.

## Approved Stack

| Area | Approved Choice | Version or Constraint | Rationale | Owner |
| --- | --- | --- | --- | --- |
| Language | <language> | <version> | <why> | <role/person> |
| Runtime | <runtime or N/A> | <version> | <why> | <role/person> |
| Framework | <framework or N/A> | <version> | <why> | <role/person> |
| Storage | <storage or N/A> | <version> | <why> | <role/person> |
| Testing | <test tool or manual method> | <version or N/A> | <why> | <role/person> |

## Disallowed or Deferred Technology

| Technology | Status | Reason | Revisit Trigger |
| --- | --- | --- | --- |
| <technology> | Disallowed/Deferred | <why> | <condition> |

## Dependency Policy

- New dependencies require an approved architecture decision and an explicit task contract allowance.
- Code Agents must stop if implementation requires an unapproved dependency.
- Version changes must update this artifact and any affected task validation commands.

## Environment Assumptions

| Assumption | Required By | Validation Method |
| --- | --- | --- |
| <assumption> | <component/task> | <command or manual check> |
