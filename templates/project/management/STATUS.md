# Status: <Project Name>

Template rule: status must be evidence-based. Do not report completion without linked artifacts.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Lead Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `management/WORKFLOW_PROFILE.md`, `management/TASK_BOARD.md`, `management/VALIDATION_STATUS.md`, `management/BLOCKERS.md` |
| Workflow Profile | `management/WORKFLOW_PROFILE.md` |
| Workflow Mode | <Light Artifact Workflow / Research-first Product Workflow / Code Tool Workflow / High-risk Integration Workflow> |
| Human Review Gates | `management/HUMAN_REVIEW_GATES.md` |
| Approval Log | `management/APPROVALS.md` |
| Required Human Gate | <Gate 0-6 / none> |
| Approval Status | <not required / pending / approved / approved with limitations / waived / blocked> |
| Approval Artifact | <APPROVALS row ID or path> |
| Next Human Decision Needed | <decision or N/A> |
| Skipped Gates | <none / list with rationale in `management/WORKFLOW_PROFILE.md`> |
| Escalation Triggers | <active trigger or N/A> |

## Current Summary

<Summarize current project state in factual terms. Name the active milestone, active tasks, blockers, and validation state.>

## Workflow Profile Status

| Field | Current Value | Evidence |
| --- | --- | --- |
| Workflow Mode | <mode> | `management/WORKFLOW_PROFILE.md` |
| Risk Level | <low / medium / high> | `management/WORKFLOW_PROFILE.md` |
| Research Decision | <required / optional / not required / waived / blocked> | <artifact or approval ID> |
| Architecture Decision | <required / light / not required / blocked> | <artifact or approval ID> |
| Review / QA Decision | <manual artifact inspection / light QA / full QA / not applicable> | <artifact or approval ID> |
| Skipped Gates | <gates and rationale> | `management/WORKFLOW_PROFILE.md` |
| Active Escalation Trigger | <trigger or N/A> | <artifact or task ID> |

## Milestone Status

| Milestone | Status | Required Human Gate | Approval Status | Evidence | Next Action |
| --- | --- | --- | --- | --- | --- |
| <milestone> | <Draft/Ready/In Progress/Blocked/Validated> | <Gate 0-6 / none> | <not required / pending / approved / approved with limitations / waived / blocked / N/A> | <artifact path or result> | <action> |

## Task Status

| Task ID | Status | Required Human Gate | Approval Artifact | Owner | Evidence | Risk |
| --- | --- | --- | --- | --- | --- | --- |
| TASK-001 | <status> | <Gate 4 / Gate 5 / none> | <APPROVALS row ID or N/A> | <owner> | <task folder, review, validation> | <risk or N/A> |

## Human Review Gate Status

| Gate | Approval Status | Approval Artifact | Next Human Decision Needed | Blocks |
| --- | --- | --- | --- | --- |
| Gate 0: Idea Intake Review | <pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |
| Gate 1: Research Review | <not required / pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |
| Gate 2: PRD / MVP Approval | <not required / pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |
| Gate 3: Architecture Approval | <not required / pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |
| Gate 4: Task Plan Approval | <not required / pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |
| Gate 5: Implementation Exception Review | <not required / pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |
| Gate 6: Release / Final Acceptance | <not applicable / pending / approved / approved with limitations / waived / blocked / N/A> | <APPROVALS row ID or N/A> | <decision or N/A> | <artifact/workflow> |

## Blockers and Decisions Needed

| Item | Owner | Required Artifact | Due or Sequence |
| --- | --- | --- | --- |
| <decision/blocker> | <role/person> | <path> | <date or order> |

## Recent Changes

| Date | Change | Source |
| --- | --- | --- |
| YYYY-MM-DD | <change> | <artifact or task> |
