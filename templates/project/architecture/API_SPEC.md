# API Spec: <Project Name>

Template rule: interfaces must be explicit enough for implementation and review agents to detect contract drift.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <Architect Agent or human owner> |
| Last Updated | YYYY-MM-DD |
| Source Artifacts | `architecture/SYSTEM_DESIGN.md`, `product/USER_STORIES.md` |
| Downstream Consumers | `tasks/`, `tasks/*/review.md`, `management/VALIDATION_STATUS.md` |

## Interface Inventory

| Interface ID | Name | Type | Producer | Consumer | Status |
| --- | --- | --- | --- | --- | --- |
| API-001 | <name> | <HTTP/function/event/file/CLI/internal> | <component> | <component> | Draft |

## Contract Details

### API-001: <Name>

| Field | Value |
| --- | --- |
| Purpose | <why this interface exists> |
| Source Requirement | <PRD/MVP/US ID> |
| Owner | <component or role> |
| Stability | <experimental/stable/deprecated> |

#### Request or Input

| Field | Type | Required? | Validation Rule | Notes |
| --- | --- | --- | --- | --- |
| <field> | <type> | <Yes/No> | <rule> | <notes> |

#### Response or Output

| Field | Type | Required? | Notes |
| --- | --- | --- | --- |
| <field> | <type> | <Yes/No> | <notes> |

#### Errors

| Error | Cause | Expected Handling | User-visible? |
| --- | --- | --- | --- |
| <error> | <cause> | <handling> | <Yes/No> |

## Compatibility Rules

- Breaking interface changes require an architecture decision before implementation.
- Review Agents must compare changed interfaces against this spec.
- QA Agents must validate at least one success path and one relevant failure path for MVP-critical interfaces.
