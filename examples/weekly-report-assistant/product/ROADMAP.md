# Roadmap: Weekly Report Assistant

Template rule: roadmap milestones describe product outcomes, not implementation task dumps.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Lead Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `product/PRD.md`, `product/MVP.md` |
| Downstream Consumers | `management/MASTER_PLAN.md`, `management/TASK_BOARD.md` |

## Release Strategy

The project should start with a fully local artifact workflow that proves evidence capture and grouping before any automation is considered. The first milestone produces the artifact chain and one executable task. The second milestone, outside this Round 2 example, may add more artifact templates such as weekly report outline and review checklist. Product code, CLI behavior, integrations, and scheduling remain deferred until the artifact workflow is validated by real weekly-report use.

## Milestones

| Milestone | Outcome | Scope | Exit Criteria | Target |
| --- | --- | --- | --- | --- |
| M0 | Artifact-ready MVP plan | PRD, MVP, roadmap, design, master plan, task board, state, and one task folder. | Artifacts exist and TASK-001 is Ready. | Round 2 example |
| M1 | Commit evidence capture workflow | Markdown commit summary template with grouping rubric and manual validation guidance. | TASK-001 is implemented, reviewed, and validated with artifact inspection evidence. | Next execution pass |
| M2 | Weekly report outline workflow | Artifact template that converts grouped commit summaries into draft report sections. | A second task folder is created after M1 validation. | Deferred |
| M3 | Automation feasibility decision | Decision on whether CLI or parser automation is worth building. | User feedback shows repeated manual pain and PM/Architect artifacts approve runtime scope. | Deferred |

## Dependency Map

| Dependency | Needed By | Owner | Status | Notes |
| --- | --- | --- | --- | --- |
| Approved artifact-only MVP scope | M0, TASK-001 | PM Agent | Approved | Captured in `product/MVP.md`. |
| Artifact-only architecture guardrails | TASK-001 | Architect Agent | Approved | Captured in `architecture/SYSTEM_DESIGN.md` and `architecture/CODE_RULES.md`. |
| Complete task folder | TASK-001 execution | Task Manager Agent | Ready | Folder exists with task, plan, implementation, test, and review artifacts. |
| Commit summary template validation evidence | M2 | QA Agent | Not Started | Must come from TASK-001 after execution. |

## Deferred Ideas

| Idea | Reason Deferred | Revisit Trigger | Parking Artifact |
| --- | --- | --- | --- |
| Git parser or CLI command. | Violates current artifact-only and no-CLI constraints. | Manual template use is validated but too repetitive. | Future PRD update |
| External service import from GitHub or GitLab. | Violates local-first MVP and external service non-goals. | Users approve integration scope and privacy model. | Future roadmap item |
| AI prose generation. | MVP must first prove evidence grouping. | Users confirm grouped evidence is sufficient and request final-draft assistance. | Future user story |
| Scheduler/reminder workflow. | Scheduler is explicitly disallowed for this example. | A future release permits runtime services. | Future architecture decision |

## Review Cadence

| Trigger | Required Review | Output |
| --- | --- | --- |
| MVP scope changes | PM Agent review | Updated `product/MVP.md` and roadmap row |
| Technical feasibility changes | Architect Agent review | Updated `architecture/DECISIONS.md` |
| TASK-001 validated | Lead Agent review | Updated `management/STATUS.md`, `management/TASK_BOARD.md`, and next milestone decision |

## Roadmap Review Checklist

- [x] Each milestone maps to product outcomes.
- [x] MVP scope is not expanded silently.
- [x] Dependencies are explicit.
- [x] Deferred work is captured without becoming active scope.
- [x] Downstream task planning can point to milestone exit criteria.
