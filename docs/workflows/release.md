# Release Workflow

## Objective

Prepare a reviewed and validated set of changes for release, delivery, or milestone closure using repository artifacts.

## Responsible Role

Lead Agent, with QA Agent validation input and PM/Architect review when release scope or technical constraints change.

## Required Inputs

- Task board.
- Validation status.
- Review reports.
- Changelog.
- Product and architecture artifacts for the release scope.
- Open blockers and known gaps.
- Gate 6 approval request or existing approval record in `management/APPROVALS.md`.

## Procedure

1. Read task board, validation status, blockers, and changelog.
2. Confirm release scope maps to approved product and architecture artifacts.
3. Confirm all included tasks have review and validation evidence.
4. Record known gaps, partial validations, and deferred work.
5. Update changelog with evidence-linked changes.
6. Update status and roadmap milestone state.
7. Hand off release package to Gate 6: Release / Final Acceptance before marking release or milestone accepted.
8. Stop if release requires unapproved product scope, architecture changes, or unvalidated acceptance criteria.

## Required Outputs

- Updated changelog.
- Updated validation status.
- Updated project status.
- Updated roadmap or task board when milestone state changes.
- Follow-up tasks for unresolved gaps.
- Gate 6 approval request or approval record in `management/APPROVALS.md`.

## Verification Rules

- Release readiness must be evidence-based.
- No task may be treated as done without review and validation artifacts.
- Partial validation must be called out with remaining risk.
- Product or architecture changes discovered during release prep must return to the responsible role before release.
- Final acceptance, milestone closure, or release completion requires Gate 6 approval recorded in `management/APPROVALS.md`.

## Common Failure Modes

- Publishing a release summary that is only a commit list.
- Hiding known gaps.
- Treating QA confidence as validation.
- Closing a milestone while blockers remain unresolved.

## Handoff to Next Workflow

Hand off to Gate 6 with task board, validation status, changelog, status, review reports, QA evidence, known blockers, deferred work, and unresolved risks.

After Gate 6 is recorded, hand off to the next product discovery or task planning cycle with approval record, updated status, changelog, validation evidence, unresolved risks, source artifact, target artifact, allowed scope, next owner role, and stop conditions.
