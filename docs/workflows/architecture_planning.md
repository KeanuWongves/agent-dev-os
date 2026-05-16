# Architecture Planning Workflow

## Objective

Turn product scope into enforceable system design, interface contracts, code rules, and architecture decisions.

## Responsible Role

Architect Agent.

## Required Inputs

- PRD, MVP, roadmap, and user stories.
- Product constraints, non-goals, assumptions, and success criteria.
- Existing architecture artifacts and decisions when present.

## Procedure

1. Read approved or review-ready product artifacts.
2. Identify system boundaries, non-goals, and external dependencies.
3. Define components with responsibilities, inputs, outputs, and owners.
4. Define data model, state, persistence, and failure behavior.
5. Specify interfaces in `API_SPEC.md` when component or external contracts matter.
6. Record approved technology choices and dependency policy in `TECH_STACK.md`.
7. Record enforceable implementation constraints in `CODE_RULES.md`.
8. Capture meaningful tradeoffs in `DECISIONS.md`.
9. Escalate to PM Agent when product scope is ambiguous or contradictory.

## Required Outputs

- Updated system design.
- Updated tech stack, API spec, code rules, and decisions as needed.
- Open technical questions with required resolution timing.
- Handoff to Lead Agent.

## Verification Rules

- Every component must trace to MVP or PRD scope.
- Interfaces must be specific enough for review.
- New dependencies require an explicit decision and downstream task authorization.
- Implementation guardrails must be enforceable by review or validation.

## Common Failure Modes

- Expanding product scope through architecture.
- Leaving interface contracts implicit.
- Recording preferences instead of decisions.
- Approving technology without consequences and validation implications.

## Handoff to Next Workflow

Hand off to task planning through Lead Agent with source architecture artifacts, allowed technical scope, required evidence, sequencing constraints, next owner role, and stop conditions.
