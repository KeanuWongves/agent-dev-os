# Architecture Planning Workflow

## Objective

Turn product scope into enforceable system design, interface contracts, code rules, and architecture decisions.

## Responsible Role

Architect Agent.

## Required Inputs

- PRD, MVP, roadmap, and user stories.
- Product constraints, non-goals, assumptions, and success criteria.
- Existing architecture artifacts and decisions when present.
- Gate 2 approval recorded in `management/APPROVALS.md`.

## Procedure

1. Read approved or review-ready product artifacts.
2. Identify system boundaries, non-goals, and external dependencies.
3. Define components with responsibilities, inputs, outputs, and owners.
4. Define data model, state, persistence, and failure behavior.
5. Specify interfaces in `API_SPEC.md` when component, file/artifact, or external contracts matter. Do not infer a network API, service, CLI, MCP server, agent runtime, or runtime implementation from the existence of `API_SPEC.md`.
6. Record approved technology choices and dependency policy in `TECH_STACK.md`.
7. Record enforceable implementation constraints in `CODE_RULES.md`.
8. Capture meaningful tradeoffs in `DECISIONS.md`.
9. Escalate to PM Agent when product scope is ambiguous or contradictory.
10. Hand off drafted architecture artifacts to Gate 3: Architecture Approval before implementation planning starts.

## Required Outputs

- Updated system design.
- Updated tech stack, API spec, code rules, and decisions as needed.
- Open technical questions with required resolution timing.
- Handoff to Lead Agent.
- Gate 3 approval request or approval record in `management/APPROVALS.md`.

## Verification Rules

- Every component must trace to MVP or PRD scope.
- Interfaces must be specific enough for review.
- New dependencies require an explicit decision and downstream task authorization.
- Implementation guardrails must be enforceable by review or validation.
- Artifact-only interface specs may describe file or artifact contracts and must not expand scope into runtime work.
- Implementation planning may start only after Gate 3 approval is recorded in `management/APPROVALS.md`.

## Common Failure Modes

- Expanding product scope through architecture.
- Leaving interface contracts implicit.
- Treating `API_SPEC.md` as permission to create a network API, service, CLI, MCP server, or runtime.
- Recording preferences instead of decisions.
- Approving technology without consequences and validation implications.

## Handoff to Next Workflow

Hand off to Gate 3 with architecture artifacts, product traceability, dependency policy, runtime-surface decisions, open technical questions, and stop conditions.

After Gate 3 is recorded, hand off to task planning through Lead Agent with source architecture artifacts, Gate 3 approval record, allowed technical scope, required evidence, sequencing constraints, next owner role, and stop conditions.
