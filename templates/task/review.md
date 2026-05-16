# Review Report: <TASK-ID> <short-title>

Copy this file to `tasks/TASK-XXX-short-title/review.md`. Review Agents update this artifact after implementation evidence is available.

Template rule: review the implementation against the original task artifacts. Do not rewrite acceptance criteria to fit the implementation. Review Agents must not implement fixes while acting as reviewer.

## Metadata

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner Role | Review Agent |
| Task ID | <TASK-XXX> |
| Task Folder | `tasks/TASK-XXX-short-title/` |
| Source Task | `tasks/TASK-XXX-short-title/task.md` |
| Source Plan | `tasks/TASK-XXX-short-title/plan.md` |
| Implementation Artifact | `tasks/TASK-XXX-short-title/implementation.md` |
| Test Artifact | `tasks/TASK-XXX-short-title/test.md` |
| Last Updated | YYYY-MM-DD |
| Reviewed By | <agent or human> |
| Diff or Revision Reviewed | <git diff, commit, branch, or artifact snapshot> |

## Review Verdict

| Field | Value |
| --- | --- |
| Decision | <Approved/Changes Requested/Blocked> |
| Rationale | <evidence-based summary> |
| Can Proceed To QA | <Yes/No> |
| Blocking Findings | <finding IDs or N/A - none> |

## Scope Compliance

| Check | Result | Evidence |
| --- | --- | --- |
| Implementation stayed within Allowed Changes | <Pass/Fail/Partial> | <diff summary or path list> |
| Forbidden Changes were not touched | <Pass/Fail/Partial> | <diff summary or path list> |
| Expected Edit Surface matches actual changed files | <Pass/Fail/Partial> | <scope check or path list> |
| Acceptance criteria were not rewritten | <Pass/Fail/Partial> | <task.md and implementation.md comparison> |
| Required source artifacts were consulted | <Pass/Fail/Partial> | <implementation log or notes> |

## Acceptance Criteria Compliance

| ID | Implementation Status | Evidence Status | Review Result | Notes |
| --- | --- | --- | --- | --- |
| AC-001 | <Met/Not Met/Partial/Blocked> | <Complete/Missing/Weak> | <Pass/Fail/Partial> | <notes> |
| AC-002 | <Met/Not Met/Partial/Blocked> | <Complete/Missing/Weak> | <Pass/Fail/Partial> | <notes> |

## Findings By Severity

Order findings by severity. Use `P0` for correctness or data-loss blockers, `P1` for required task failures, `P2` for important but non-blocking issues, and `P3` for minor cleanup.

| ID | Severity | Status | Location | Finding | Required Change |
| --- | --- | --- | --- | --- | --- |
| F-001 | <P0/P1/P2/P3> | <Open/Resolved/N/A> | <file:line or artifact section> | <specific issue> | <required fix or N/A> |

## Test Evidence Review

| Validation ID | Acceptance Criteria | Review Result | Notes |
| --- | --- | --- | --- |
| VAL-001 | <AC IDs> | <Accepted/Rejected/Needs Rerun/Blocked> | <notes> |
| VAL-002 | <AC IDs> | <Accepted/Rejected/Needs Rerun/Blocked> | <notes> |

## Architecture Compliance

| Architecture Source | Constraint or Decision | Compliance Result | Evidence |
| --- | --- | --- | --- |
| <architecture/SYSTEM_DESIGN.md or N/A - reason> | <decision ID, guardrail, or N/A> | <Pass/Fail/Partial/N/A> | <implementation or diff evidence> |

## Required Fixes

| Fix ID | Finding ID | Required Change | Owner | Blocks QA? |
| --- | --- | --- | --- | --- |
| RF-001 | <F-001 or N/A - none> | <specific required change> | <Code Agent/Task Manager Agent> | <Yes/No> |

## Scope Check

| Changed Path | In Allowed Scope? | Notes |
| --- | --- | --- |
| <path> | <Yes/No> | <notes> |

## Open Questions

| ID | Question | Owner | Blocks Approval? | Required Resolution |
| --- | --- | --- | --- | --- |
| RQ-001 | <question or N/A - none> | <role or person> | <Yes/No> | <artifact path or action> |

## QA Handoff

| Required Handoff Field | Value |
| --- | --- |
| Source Artifact | `tasks/TASK-XXX-short-title/review.md` |
| Target Artifact | `tasks/TASK-XXX-short-title/test.md` or project validation artifact |
| Allowed Scope | <validation-only scope and approved implementation scope> |
| Required Evidence | <accepted validation IDs, required fixes, or blocker evidence> |
| Next Owner Role | <QA Agent if approved, Task Manager Agent if rejected or blocked> |
| Stop Conditions | <open blocking findings, missing validation evidence, out-of-scope implementation, or unresolved required question> |
