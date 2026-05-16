# User Stories: <Project Name>

Template rule: every story must trace to a PRD requirement or be marked as an assumption.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `product/PRD.md`, `product/MVP.md` |
| Downstream Consumers | `architecture/SYSTEM_DESIGN.md`, `management/TASK_BOARD.md`, `tasks/` |

## Story Map

| Story ID | User Segment | Story | Source Requirement | Priority |
| --- | --- | --- | --- | --- |
| US-001 | <segment> | As a <user>, I want <capability>, so that <outcome>. | PRD-### or A-### | Must |

## Acceptance Scenarios

| Scenario ID | Story ID | Given | When | Then | Evidence Required |
| --- | --- | --- | --- | --- | --- |
| SC-001 | US-001 | <starting state> | <user action> | <observable result> | <test, demo, artifact diff, or manual check> |

## Edge Cases

| Edge Case ID | Story ID | Condition | Expected Behavior | Source |
| --- | --- | --- | --- | --- |
| EC-001 | US-001 | <condition> | <behavior> | <artifact or assumption> |

## Story Readiness Checklist

- [ ] Each story names a user segment.
- [ ] Each story traces to PRD, MVP, or an explicit assumption.
- [ ] Acceptance scenarios are observable.
- [ ] Edge cases that affect MVP success are captured.
- [ ] Stories do not introduce capabilities outside MVP scope.
