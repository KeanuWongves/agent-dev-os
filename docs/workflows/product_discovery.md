# Product Discovery Workflow

## Objective

Convert a project idea or user problem into product artifacts that downstream agents can use without relying on chat history.

Product discovery starts after reference research when research is required. PRD and MVP approval must be based on completed research artifacts, user input, explicit assumptions, or a recorded research waiver.

## Responsible Role

PM Agent.

## Required Inputs

- User problem statement, project brief, or discovery notes.
- Research artifacts when available or required:
  - `research/RESEARCH_BRIEF.md`
  - `research/SOURCE_LOG.md`
  - `research/FEATURE_MATRIX.md`
  - `research/GAP_ANALYSIS.md`
  - `research/REUSE_DECISIONS.md`
  - `research/OPEN_SOURCE_SCAN.md` when open-source candidates are relevant
  - `research/REFERENCE_PRODUCT_ANALYSIS.md` when reference products, creators, or workflows are relevant
- Existing `product/PRD.md`, `product/MVP.md`, `product/ROADMAP.md`, and `product/USER_STORIES.md` when present.
- Known assumptions, constraints, non-goals, and success signals.
- Explicit research waiver when research is intentionally skipped.
- Gate 1 approval or waiver recorded in `management/APPROVALS.md` when reference research was required.

## Procedure

1. Read existing product and vision artifacts before editing.
2. Read research artifacts first when they exist or are required.
3. Confirm whether research is complete, incomplete, not applicable, or explicitly waived, and whether Gate 1 is recorded.
4. Separate problem, user segment, workflow, requirement, and solution proposal.
5. Write or update PRD sections for research inputs, target users, problem, goals, non-goals, requirements, constraints, assumptions, and open questions.
6. Trace each PRD requirement to a research artifact, user input, or explicit assumption.
7. Define MVP objective, included capabilities, excluded capabilities, journey, and acceptance criteria.
8. Add or update user stories with acceptance scenarios and edge cases.
9. Update roadmap milestones only after MVP scope is coherent.
10. Record unresolved decisions as open questions with owner and resolution artifact.
11. Hand off drafted PRD/MVP to Gate 2: PRD / MVP Approval before marking either artifact `Approved`.

## Required Outputs

- Updated PRD.
- Updated MVP scope.
- Updated roadmap when sequencing changes.
- Updated user stories when implementation-facing scenarios are needed.
- Handoff fields for architecture or planning.
- Gate 2 approval request or approval record in `management/APPROVALS.md`.

## Verification Rules

- Product discovery must read research artifacts before approving PRD or MVP when research exists or is required.
- PRD may be approved only if research is complete or explicitly waived.
- PRD and MVP may be marked `Approved` only when Gate 2 approval is recorded in `management/APPROVALS.md`.
- Every PRD requirement must trace to a research artifact, user input, or explicit assumption.
- Every reference-derived requirement must cite a source logged in `research/SOURCE_LOG.md`.
- MVP included capabilities must not include deferred roadmap items.
- Acceptance criteria must be observable.
- Open questions that block architecture must be marked blocking.

## Common Failure Modes

- Inventing requirements to fill template space.
- Approving PRD/MVP while required research is incomplete.
- Importing reference features without source traceability.
- Describing implementation before the user problem is stable.
- Treating non-goals as optional backlog rather than scope guards.
- Handing off to architecture with unresolved product contradictions.

## Handoff to Next Workflow

Hand off to Gate 2 with drafted PRD/MVP, research artifacts or waiver, requirement traceability, non-goals, assumptions, and open questions.

After Gate 2 is recorded, hand off to architecture planning with source product artifacts, Gate 2 approval record, approved MVP scope, non-goals, assumptions, open questions, required evidence, next owner role, and stop conditions.
