# Product Discovery Workflow

## Objective

Convert a project idea or user problem into product artifacts that downstream agents can use without relying on chat history.

## Responsible Role

PM Agent.

## Required Inputs

- User problem statement, project brief, or discovery notes.
- Existing `product/PRD.md`, `product/MVP.md`, `product/ROADMAP.md`, and `product/USER_STORIES.md` when present.
- Known assumptions, constraints, non-goals, and success signals.

## Procedure

1. Read existing product and vision artifacts before editing.
2. Separate problem, user segment, workflow, requirement, and solution proposal.
3. Write or update PRD sections for target users, problem, goals, non-goals, requirements, constraints, assumptions, and open questions.
4. Define MVP objective, included capabilities, excluded capabilities, journey, and acceptance criteria.
5. Add or update user stories with acceptance scenarios and edge cases.
6. Update roadmap milestones only after MVP scope is coherent.
7. Record unresolved decisions as open questions with owner and resolution artifact.

## Required Outputs

- Updated PRD.
- Updated MVP scope.
- Updated roadmap when sequencing changes.
- Updated user stories when implementation-facing scenarios are needed.
- Handoff fields for architecture or planning.

## Verification Rules

- Every requirement must trace to a source or explicit assumption.
- MVP included capabilities must not include deferred roadmap items.
- Acceptance criteria must be observable.
- Open questions that block architecture must be marked blocking.

## Common Failure Modes

- Inventing requirements to fill template space.
- Describing implementation before the user problem is stable.
- Treating non-goals as optional backlog rather than scope guards.
- Handing off to architecture with unresolved product contradictions.

## Handoff to Next Workflow

Hand off to architecture planning with source product artifacts, approved or review-ready MVP scope, non-goals, assumptions, open questions, required evidence, next owner role, and stop conditions.
