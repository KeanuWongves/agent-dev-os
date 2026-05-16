# MVP: Weekly Report Assistant

Template rule: implementation tasks may include only capabilities listed as included scope or explicitly authorized assumptions.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | PM Agent |
| Last Updated | 2026-05-17 |
| Source PRD | `product/PRD.md` |
| Downstream Consumers | `product/ROADMAP.md`, `architecture/SYSTEM_DESIGN.md`, `management/MASTER_PLAN.md` |

## MVP Objective

Prove that an engineer can convert local commit history into structured weekly-report input using only repository artifacts and manual review.

## Included Capabilities

| Capability ID | Capability | User Value | Acceptance Criteria | Source Requirement |
| --- | --- | --- | --- | --- |
| MVP-001 | Commit summary template. | Gives the user a consistent place to capture raw commit evidence. | Template captures repo, date range, commit hash, message, context, source command, and evidence notes. | PRD-001 |
| MVP-002 | Grouping rubric. | Helps classify work without relying on memory. | Rubric defines project, feature, bugfix, experiment, and blocker, and requires one primary group. | PRD-002 |
| MVP-003 | Evidence-preserving weekly-report outline. | Lets the user draft a report while keeping source references visible. | Outline links each report bullet to commit evidence or marks evidence missing. | PRD-003, PRD-005 |
| MVP-004 | Manual uncertainty review. | Prevents overconfident classification. | Template includes review-needed and uncertainty fields for ambiguous commits. | PRD-004 |

## Excluded Capabilities

| Exclusion ID | Exclusion | Reason | Revisit Trigger |
| --- | --- | --- | --- |
| EX-001 | Product source implementation. | Round 2 dogfood is artifact-only. | A future approved project-code task after artifact workflow validation. |
| EX-002 | CLI or git parser. | The first MVP step is a local Markdown workflow. | Commit template proves insufficient for repeated use. |
| EX-003 | External integrations. | Local-first privacy and no external services are hard constraints. | A future product decision explicitly changes non-goals. |
| EX-004 | Automated prose generation. | The MVP focuses on evidence grouping, not final copywriting. | Users validate that grouped evidence is useful and ask for generated prose. |

## User Journey Covered

| Step | User or System Action | Success Signal | Failure or Recovery Path |
| --- | --- | --- | --- |
| 1 | User collects commit history from local git. | Raw commit entries exist for the week. | If commit history is unavailable, user records manual work items and marks evidence missing. |
| 2 | User copies entries into the commit summary template. | Required evidence fields are filled or explicitly marked unknown. | Missing fields are kept visible for review. |
| 3 | User assigns a primary group and optional tags. | Each item is grouped under project, feature, bugfix, experiment, or blocker. | Ambiguous items are marked review-needed. |
| 4 | User drafts the weekly report from grouped evidence. | Draft outline contains evidence-backed bullets and blocker/follow-up sections. | Unsupported claims remain as review notes, not final claims. |

## MVP Acceptance Criteria

| ID | Criterion | Evidence Required |
| --- | --- | --- |
| MVP-AC-001 | The project has an approved artifact chain from PRD to Ready task. | `product/`, `architecture/`, `management/`, `state/`, and `tasks/TASK-001-create-commit-summary-template/` artifacts exist and are internally consistent. |
| MVP-AC-002 | The first task can be executed without product code. | `task.md` and `plan.md` authorize only Markdown artifact creation and forbid code, dependencies, CLIs, services, and validation code. |
| MVP-AC-003 | The future commit summary template can support grouping by project, feature, bugfix, experiment, and blocker. | TASK-001 acceptance criteria require fields and rubric coverage for all five groups. |

## Launch Readiness

| Area | Minimum Evidence | Owner |
| --- | --- | --- |
| Product scope | This MVP artifact and `product/PRD.md` are approved for example execution. | PM Agent |
| Technical feasibility | `architecture/SYSTEM_DESIGN.md` confirms artifact-only design and no runtime dependency. | Architect Agent |
| Validation | TASK-001 must record artifact inspection and no-code/dependency checks in task-local `test.md` before completion. | QA Agent |

## Risks

| Risk | Impact | Mitigation |
| --- | --- | --- |
| Template feels heavier than the problem. | Users may skip fields or abandon the workflow. | Use TASK-001 to keep required fields minimal and document template friction in `NOTES.md`. |
| Commit messages lack enough context. | Grouping may be inaccurate. | Include context, evidence notes, and review-needed fields. |
| Manual workflow does not scale. | Future users may need automation. | Capture automation as deferred roadmap work, not MVP scope. |

## Scope Guardrails

- Implementation agents may build only the included capabilities.
- New capability requests must be added to `Excluded Capabilities`, the roadmap, or an approved PRD update before implementation.
- If MVP acceptance criteria cannot be validated, return to PM Agent before task execution continues.
