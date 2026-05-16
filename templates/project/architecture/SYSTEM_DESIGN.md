# System Design: <Project Name>

Template rule: design only the approved or review-ready MVP scope. Product expansion belongs in `product/`.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Architect Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md` |
| Downstream Consumers | `management/MASTER_PLAN.md`, `tasks/`, `tasks/*/review.md` |

## Design Summary

<Describe the chosen system design in 5-8 precise sentences. Name the main components and why this design fits the MVP.>

## Goals and Constraints

| Type | Item | Source |
| --- | --- | --- |
| Goal | <technical goal> | PRD-### or MVP-### |
| Constraint | <constraint> | <source> |

## Component Map

| Component | Responsibility | Inputs | Outputs | Owner |
| --- | --- | --- | --- | --- |
| <component> | <responsibility> | <input> | <output> | <role/person> |

## Data Model

| Entity | Fields | Owner | Persistence | Notes |
| --- | --- | --- | --- | --- |
| <entity> | <fields> | <component> | <storage or none> | <notes> |

## Interfaces

| Interface | Producer | Consumer | Contract | Failure Behavior |
| --- | --- | --- | --- | --- |
| <interface> | <component> | <component> | <schema/API/path> | <expected handling> |

## Execution Flow

| Step | Actor or Component | Action | Input | Output |
| --- | --- | --- | --- | --- |
| 1 | <component> | <action> | <input> | <output> |

## State and Persistence

| State Item | Location | Created By | Updated By | Retention or Cleanup |
| --- | --- | --- | --- | --- |
| <state> | <path, database, memory, or none> | <component> | <component> | <rule> |

## Alternatives Considered

| Alternative | Benefit | Reason Rejected |
| --- | --- | --- |
| <alternative> | <benefit> | <reason> |

## Architecture Decisions

| ID | Decision | Rationale | Consequences |
| --- | --- | --- | --- |
| ADR-001 | <decision> | <why> | <tradeoff> |

## Implementation Guardrails

- <Rule that Code Agents must follow.>
- Do not add dependencies, runtimes, services, or storage systems unless this design and the task contract both authorize them.

## Open Technical Questions

| Question | Impact | Required Before | Resolution Artifact |
| --- | --- | --- | --- |
| <question> | <impact> | <task/milestone> | <path> |
