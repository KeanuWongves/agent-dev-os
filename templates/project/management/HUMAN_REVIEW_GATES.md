# Human Review Gates: <Project Name>

Template rule: AI agents may draft artifacts, but recorded human approval is required before downstream work treats gate-controlled artifacts as approved scope.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Approval Log | `management/APPROVALS.md` |
| Downstream Consumers | `product/`, `architecture/`, `management/TASK_BOARD.md`, `tasks/`, `management/VALIDATION_STATUS.md`, `management/CHANGELOG.md` |

## Gate Summary

Allowed decisions: `approved`, `approved with limitations`, `rejected`, `needs revision`, `waived`.

| Gate | Name | Required Before | Primary Artifacts | Human Decision Required |
| --- | --- | --- | --- | --- |
| Gate 0 | Idea Intake Review | Research or product discovery starts | project brief, discovery notes, `research/RESEARCH_BRIEF.md` when created | Confirm problem, target user, constraints, and whether research is required. |
| Gate 1 | Research Review | PRD drafting or approval uses reference findings | `research/SOURCE_LOG.md`, `FEATURE_MATRIX.md`, `GAP_ANALYSIS.md`, `REUSE_DECISIONS.md` | Approve research findings, limitations, confidence, and source gaps. |
| Gate 2 | PRD / MVP Approval | Architecture planning treats product scope as approved | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md`, `product/ROADMAP.md` | Approve problem, scope, non-goals, assumptions, success criteria, and MVP boundaries. |
| Gate 3 | Architecture Approval | Implementation planning starts | `architecture/SYSTEM_DESIGN.md`, `TECH_STACK.md`, `API_SPEC.md`, `CODE_RULES.md`, `DECISIONS.md` | Approve system boundaries, interfaces, dependency policy, runtime surfaces, and tradeoffs. |
| Gate 4 | Task Plan Approval | Non-trivial or high-risk task becomes `Ready` | `tasks/TASK-XXX-short-title/`, `management/TASK_BOARD.md` | Approve allowed paths, forbidden scope, acceptance criteria, validation plan, and stop conditions. |
| Gate 5 | Implementation Exception Review | Out-of-scope implementation continues | task folder, exception note, changed-file summary, validation gap | Approve, reject, limit, or defer scope expansion, dependencies, credentials, external APIs, scraping, runtime surfaces, or validation gaps. |
| Gate 6 | Release / Final Acceptance | Milestone or release is accepted | `management/VALIDATION_STATUS.md`, `CHANGELOG.md`, `STATUS.md`, review reports | Accept release scope, validation sufficiency, known gaps, deferred work, and final status. |

## Gate Records

Record every gate decision in `management/APPROVALS.md`.

| Gate | Current Status | Latest Approval Record | Next Human Decision Needed | Blocks |
| --- | --- | --- | --- | --- |
| Gate 0 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 1 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 2 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 3 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 4 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 5 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 6 | <not started / pending / approved / waived / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |

## AI Drafting Rules

- AI agents may draft gate-controlled artifacts before approval.
- Gate-controlled artifacts must remain `Draft`, `Reviewed`, or `Blocked` until approval is recorded.
- AI agents must not mark research, PRD/MVP, architecture, high-risk task plans, implementation exceptions, or release artifacts as `Approved`, `Ready`, `Validated`, or accepted unless `management/APPROVALS.md` records the required human decision.
- Waivers must name the gate, rationale, limitations, downstream scope unlocked, and owner.

## Stop Conditions

- Required input artifacts are missing.
- Human owner is not named.
- Decision is only present in chat and not recorded in `management/APPROVALS.md`.
- Approval limitations conflict with downstream execution scope.
- A gate-controlled artifact attempts to unlock code, dependencies, runtime surfaces, credentials, external APIs, scraping, or release acceptance without the required gate decision.
