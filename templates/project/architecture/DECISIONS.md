# Architecture Decisions: <Project Name>

Template rule: record decisions that constrain future tasks. Do not use this file as a brainstorming scratchpad.

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
| Downstream Consumers | `management/MASTER_PLAN.md`, `tasks/`, `tasks/*/review.md` |

Approval rule: architecture artifacts may be drafted before approval, but implementation planning must not treat these decisions as approved until Gate 3 approval or waiver is recorded in `management/APPROVALS.md` and linked above.

## Decision Index

| ID | Title | Status | Date | Owner |
| --- | --- | --- | --- | --- |
| ADR-001 | <decision title> | Draft | YYYY-MM-DD | <role/person> |

## ADR-001: <Decision Title>

| Field | Value |
| --- | --- |
| Status | Draft |
| Date | YYYY-MM-DD |
| Owner | <Architect Agent or human owner> |
| Source Artifacts | <paths and sections> |

### Context

<What forced this decision? Name product, technical, or operational constraints.>

### Decision

<The chosen direction in one or two precise paragraphs.>

### Alternatives Considered

| Alternative | Benefit | Cost or Risk | Reason Rejected |
| --- | --- | --- | --- |
| <alternative> | <benefit> | <cost/risk> | <reason> |

### Consequences

| Consequence | Impacted Artifacts | Required Follow-Up |
| --- | --- | --- |
| <consequence> | <paths> | <task, review, or validation action> |

### Review Trigger

<When this decision should be revisited.>
