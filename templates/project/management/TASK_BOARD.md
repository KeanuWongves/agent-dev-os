# Task Board: <Project Name>

Template rule: only tasks with a complete folder may move to `Ready`.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Task Manager Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Plan | `management/MASTER_PLAN.md` |
| Workflow Profile | `management/WORKFLOW_PROFILE.md` |
| Workflow Mode | <Light Artifact Workflow / Research-first Product Workflow / Code Tool Workflow / High-risk Integration Workflow> |
| Human Review Gates | `management/HUMAN_REVIEW_GATES.md` |
| Approval Log | `management/APPROVALS.md` |
| Required Human Gate | <Gate 4 / none> |
| Approval Status | <not required / pending / approved / approved with limitations / waived / blocked> |
| Approval Artifact | <APPROVALS row ID or path> |
| Next Human Decision Needed | <decision or N/A> |
| Skipped Gates | <none / list with rationale in `management/WORKFLOW_PROFILE.md`> |
| Escalation Triggers | <summary or `management/WORKFLOW_PROFILE.md#escalation-triggers`> |
| State Mirror | `state/task_graph.yaml` |

## Board Policy

Code Agents should pick one `Ready` task at a time. A task is not `Ready` until `task.md`, `plan.md`, `implementation.md`, `test.md`, and `review.md` exist and the task contract names allowed scope, acceptance criteria, required tests, and stop conditions.

Non-trivial or high-risk tasks are not `Ready` until Gate 4: Task Plan Approval is recorded in `management/APPROVALS.md`. Low-risk tasks that do not require Gate 4 must record the not-required rationale in this board.

The task board must follow `management/WORKFLOW_PROFILE.md`. If a task exceeds the selected workflow mode or risk level, keep it `Blocked` until the workflow profile is updated or the relevant human gate approves the escalation.

## Status Columns

- `Backlog`: identified but not yet contracted.
- `Ready`: task folder exists and dependencies are satisfied.
- `In Progress`: assigned to a Code Agent.
- `Review`: implementation complete, awaiting review.
- `Validation`: review accepted, awaiting validation evidence.
- `Done`: validation criteria met.
- `Blocked`: cannot progress without a decision or dependency.

## Tasks

| Task ID | Title | Status | Task Folder | Depends On | Workflow Mode | Required Human Gate | Approval Status | Approval Artifact | Escalation Trigger | Owner | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TASK-001 | <title> | Backlog | `tasks/TASK-001-short-title/` | <dependencies> | <mode> | <Gate 4 / none> | <not required / pending / approved / approved with limitations / waived / blocked> | <APPROVALS row ID or N/A> | <trigger or N/A> | <role/person> | <notes> |

## Human Decisions Needed

| Decision | Gate | Task or Artifact | Blocks | Owner | Next Action |
| --- | --- | --- | --- | --- | --- |
| <decision needed> | <Gate 0-6> | <task/artifact> | <status or workflow> | <human owner> | <specific action> |

## Blockers

| Task ID | Blocker | Owner | Next Action | Required Artifact |
| --- | --- | --- | --- | --- |
| <task> | <blocker> | <owner> | <action> | <path> |

## Board Review Checklist

- [ ] Every `Ready` task has a complete task folder.
- [ ] Every `Ready` task names allowed paths and validation evidence.
- [ ] Every non-trivial or high-risk `Ready` task has Gate 4 approval or a recorded waiver in `management/APPROVALS.md`.
- [ ] Every low-risk task that skips Gate 4 links to the not-required rationale in `management/WORKFLOW_PROFILE.md` or the task artifact.
- [ ] No task exceeds the workflow profile's mode or risk level without an escalation trigger and gate decision.
- [ ] Every `In Progress` task has exactly one current owner.
- [ ] Blocked tasks name a concrete next action.
- [ ] Done tasks link to review and validation evidence.
