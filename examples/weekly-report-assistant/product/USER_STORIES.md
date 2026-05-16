# User Stories: Weekly Report Assistant

Template rule: every story must trace to a PRD requirement or be marked as an assumption.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | PM Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `product/PRD.md`, `product/MVP.md` |
| Downstream Consumers | `architecture/SYSTEM_DESIGN.md`, `management/TASK_BOARD.md`, `tasks/` |

## Story Map

| Story ID | User Segment | Story | Source Requirement | Priority |
| --- | --- | --- | --- | --- |
| US-001 | Individual engineer | As an engineer, I want to paste local commit history into a structured template, so that weekly-report evidence starts from source data instead of memory. | PRD-001 | Must |
| US-002 | Individual engineer | As an engineer, I want to classify each work item by project, feature, bugfix, experiment, or blocker, so that my weekly report has clear sections. | PRD-002 | Must |
| US-003 | Engineer maintaining multiple project threads | As an engineer, I want uncertain or cross-cutting commits to be marked for review, so that I do not overstate or misclassify work. | PRD-004 | Should |
| US-004 | Individual engineer | As an engineer, I want report bullets to keep commit evidence references, so that claims remain traceable during review. | PRD-003, PRD-005 | Should |

## Acceptance Scenarios

| Scenario ID | Story ID | Given | When | Then | Evidence Required |
| --- | --- | --- | --- | --- | --- |
| SC-001 | US-001 | The user has a local git commit list for a week. | The user fills the commit summary template. | Required evidence fields are present or explicitly marked unknown. | Artifact inspection of the template created by TASK-001. |
| SC-002 | US-002 | A commit summary item exists. | The user assigns a primary group. | The item has exactly one primary group from project, feature, bugfix, experiment, or blocker. | Manual check against the grouping rubric. |
| SC-003 | US-003 | A commit message could fit multiple groups. | The user marks optional tags and review-needed. | Ambiguity is visible and not silently resolved. | Manual check of uncertainty fields. |
| SC-004 | US-004 | A weekly-report bullet is drafted from grouped items. | The user reviews the bullet. | The bullet references commit evidence or states that evidence is missing. | Future weekly-report outline artifact inspection. |

## Edge Cases

| Edge Case ID | Story ID | Condition | Expected Behavior | Source |
| --- | --- | --- | --- | --- |
| EC-001 | US-001 | Commit hash is unavailable because the work item came from notes rather than git. | The item can be entered with `evidence missing` and a review-needed marker. | A-001 |
| EC-002 | US-002 | One commit includes both bugfix and feature work. | The user selects one primary group and records the other as an optional tag. | A-003 |
| EC-003 | US-004 | A commit implies performance improvement but has no metric. | The report draft must not claim quantified impact; it should mark metrics unknown. | PRD-003 |

## Story Readiness Checklist

- [x] Each story names a user segment.
- [x] Each story traces to PRD, MVP, or an explicit assumption.
- [x] Acceptance scenarios are observable.
- [x] Edge cases that affect MVP success are captured.
- [x] Stories do not introduce capabilities outside MVP scope.
