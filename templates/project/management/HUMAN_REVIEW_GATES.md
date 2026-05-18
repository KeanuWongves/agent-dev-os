# Human Review Gates: <Project Name>

Template rule: AI agents may draft artifacts, but recorded human approval is required before downstream work treats gate-controlled artifacts as approved scope. Gate 0 is always required and must route the project before downstream workflows begin.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Workflow Profile | `management/WORKFLOW_PROFILE.md` |
| Approval Log | `management/APPROVALS.md` |
| Downstream Consumers | `product/`, `architecture/`, `management/TASK_BOARD.md`, `tasks/`, `management/VALIDATION_STATUS.md`, `management/CHANGELOG.md` |

## Gate Summary

Allowed decisions: `approved`, `approved with limitations`, `rejected`, `needs revision`, `waived`, `not required`.

Gate 0 decides which later gates are required, optional, waived, or not required. Use `not required` only when `management/WORKFLOW_PROFILE.md` records a rationale. Use `waived` only when a gate would normally apply but the human owner explicitly chooses to proceed with limitations.

| Gate | Name | Required Before | Primary Artifacts | Human Decision Required |
| --- | --- | --- | --- | --- |
| Gate 0 | Idea Intake Review | Any downstream workflow starts | project brief, discovery notes, `management/WORKFLOW_PROFILE.md` | Confirm problem, target user, constraints, workflow mode, risk level, required artifacts, required gates, and skipped-gate rationale. |
| Gate 1 | Research Review | PRD drafting or approval uses required/performed research | `research/SOURCE_LOG.md`, `FEATURE_MATRIX.md`, `GAP_ANALYSIS.md`, `REUSE_DECISIONS.md` | Approve research findings, limitations, confidence, and source gaps. Required only when research is required or performed. |
| Gate 2 | PRD / MVP Approval | Architecture or planning treats product scope as approved | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md`, `product/ROADMAP.md`, or light product brief | Approve problem, scope, non-goals, assumptions, success criteria, and MVP or light artifact boundaries. |
| Gate 3 | Architecture Approval | Architecture constrains implementation or runtime decisions | `architecture/SYSTEM_DESIGN.md`, `TECH_STACK.md`, `API_SPEC.md`, `CODE_RULES.md`, `DECISIONS.md` | Approve system boundaries, interfaces, dependency policy, runtime surfaces, and tradeoffs. Required when architecture constrains implementation. |
| Gate 4 | Task Plan Approval | Non-trivial or high-risk task becomes `Ready` | `tasks/TASK-XXX-short-title/`, `management/TASK_BOARD.md` | Approve allowed paths, forbidden scope, acceptance criteria, validation plan, and stop conditions. Required for non-trivial or high-risk tasks, not every low-risk task. |
| Gate 5 | Implementation Exception Review | Out-of-scope implementation continues | task folder, exception note, changed-file summary, validation gap | Approve, reject, limit, or defer scope expansion, dependencies, credentials, external APIs, scraping, runtime surfaces, or validation gaps. |
| Gate 6 | Release / Final Acceptance | Milestone, release, external delivery, or final acceptance is accepted | `management/VALIDATION_STATUS.md`, `CHANGELOG.md`, `STATUS.md`, review reports | Accept release scope, validation sufficiency, known gaps, deferred work, and final status. May be not applicable for internal drafts. |

## Gate Records

Record every gate decision in `management/APPROVALS.md`.

| Gate | Current Status | Latest Approval Record | Next Human Decision Needed | Blocks |
| --- | --- | --- | --- | --- |
| Gate 0 | <not started / pending / approved / approved with limitations / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 1 | <not started / pending / approved / approved with limitations / waived / not required / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 2 | <not started / pending / approved / approved with limitations / waived / not required / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 3 | <not started / pending / approved / approved with limitations / waived / not required / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 4 | <not started / pending / approved / approved with limitations / waived / not required / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 5 | <not started / pending / approved / approved with limitations / waived / not required / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |
| Gate 6 | <not started / pending / approved / approved with limitations / waived / not required / blocked> | <APPROVALS row ID> | <decision needed> | <artifact or workflow> |

## Skipped or Optional Gates

| Gate | Decision | Workflow Profile Rationale | Limitation |
| --- | --- | --- | --- |
| <Gate> | <optional / waived / not required> | <link or summary from `management/WORKFLOW_PROFILE.md`> | <what downstream agents must not assume> |

## AI Drafting Rules

- AI agents may draft gate-controlled artifacts before approval.
- Gate-controlled artifacts must remain `Draft`, `Reviewed`, or `Blocked` until approval is recorded.
- AI agents must not mark research, PRD/MVP, architecture, high-risk task plans, implementation exceptions, or release artifacts as `Approved`, `Ready`, `Validated`, or accepted unless `management/APPROVALS.md` records the required human decision.
- Waivers must name the gate, rationale, limitations, downstream scope unlocked, and owner.
- Gates marked `not required` must be justified in `management/WORKFLOW_PROFILE.md`.
- Agents must stop and reroute if the current work exceeds the workflow mode or risk level in `management/WORKFLOW_PROFILE.md`.

## Stop Conditions

- Required input artifacts are missing.
- Human owner is not named.
- Decision is only present in chat and not recorded in `management/APPROVALS.md`.
- Approval limitations conflict with downstream execution scope.
- A gate-controlled artifact attempts to unlock code, dependencies, runtime surfaces, credentials, external APIs, scraping, or release acceptance without the required gate decision.
