# PRD: <Project Name>

Template rule: do not use this PRD to authorize implementation until status is `Approved` or the downstream artifact explicitly accepts `Reviewed` input.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Human Review Gates | `management/HUMAN_REVIEW_GATES.md` |
| Approval Log | `management/APPROVALS.md` |
| Required Human Gate | Gate 2: PRD / MVP Approval |
| Approval Status | <not required / pending / approved / approved with limitations / waived / rejected / needs revision / blocked> |
| Approval Artifact | <management/APPROVALS.md#APP-XXX or N/A> |
| Next Human Decision Needed | <decision or N/A> |
| Upstream Context | <idea, notes, user interview, issue, or brief> |
| Research Status | <complete / waived / not required / incomplete> |
| Downstream Consumers | `product/MVP.md`, `product/ROADMAP.md`, `architecture/SYSTEM_DESIGN.md`, `management/MASTER_PLAN.md` |

Approval rule: agents may draft this PRD, but must not mark it `Approved` unless Gate 2 approval or waiver is recorded in `management/APPROVALS.md` and linked above.

## Summary

<Describe the product in 3-5 precise sentences. Include who it serves, what workflow it changes, and what outcome it should create.>

## Research Inputs

Template rule: PRD approval requires completed research or an explicit waiver. Requirements must trace to research artifacts, user input, or assumptions.

| Research Artifact | Source | Key Learning | Used in Requirement | Confidence | Open Question |
| --- | --- | --- | --- | --- | --- |
| `research/FEATURE_MATRIX.md` | <SRC/OSS/REF/FEAT ID or user input> | <learning> | <PRD-XXX or none> | <high / medium / low> | <question or none> |

## Research Waiver

Use this section only when research is not required or is intentionally skipped.

| Field | Value |
| --- | --- |
| Research Waived? | No |
| Waiver Reason | <why research is not needed> |
| Approved By | <human owner or PM Agent> |
| Risk Accepted | <uncertainty accepted by product owner> |

## Target Users

| User Segment | Current Workflow | Pain | Desired Outcome |
| --- | --- | --- | --- |
| <segment> | <today> | <specific pain> | <measurable or observable outcome> |

## Problem

<State the concrete problem. Avoid describing the solution here.>

## Goals

| Goal ID | Goal | Why It Matters | Success Signal |
| --- | --- | --- | --- |
| G-001 | <goal> | <reason> | <metric, behavior, or evidence> |

## Non-goals

| Non-goal ID | Non-goal | Reason |
| --- | --- | --- |
| NG-001 | <out of scope item> | <why this is intentionally excluded> |

## User Workflows

### Workflow: <Name>

| Step | User Action | System Response | Evidence of Success |
| --- | --- | --- | --- |
| 1 | <action> | <response> | <observable result> |

## Functional Requirements

| ID | Requirement | Priority | Acceptance Criteria |
| --- | --- | --- | --- |
| PRD-001 | <requirement> | Must | <observable acceptance criteria> |

## Non-functional Requirements

| ID | Requirement | Priority | Acceptance Criteria |
| --- | --- | --- | --- |
| NFR-001 | <performance, security, reliability, maintainability, privacy, or usability requirement> | Must | <observable acceptance criteria> |

## Constraints

| Constraint | Source | Impact |
| --- | --- | --- |
| <business, technical, time, platform, data, privacy, or operational constraint> | <source> | <how downstream artifacts must respect it> |

## Assumptions

| ID | Assumption | Risk If False | Validation Plan |
| --- | --- | --- | --- |
| A-001 | <assumption> | <risk> | <how to check> |

## Open Questions

| ID | Question | Owner | Required Before | Resolution Artifact |
| --- | --- | --- | --- | --- |
| Q-001 | <question> | <owner> | <MVP/design/implementation/release> | <artifact path> |

## Decision Log

| Date | Decision | Rationale | Source |
| --- | --- | --- | --- |
| YYYY-MM-DD | <decision> | <why> | <link or note> |
