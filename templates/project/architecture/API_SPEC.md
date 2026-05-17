# API Spec: <Project Name>

Template rule: interfaces must be explicit enough for implementation and review agents to detect contract drift.

Interface naming guidance: for runtime projects, this file may describe API contracts such as HTTP routes, functions, events, CLIs, or internal service boundaries. For artifact-only projects, this file may describe file or artifact interface contracts such as Markdown structures, YAML schemas, prompt inputs, or handoff artifacts. Do not infer a network API, service, CLI, MCP server, agent runtime, or other runtime surface from the existence of `API_SPEC.md`. A future template set may add `INTERFACE_SPEC.md`, but do not rename this file without an approved template migration.

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

Use `file/artifact` as the Type for artifact-only contracts. The interface ID may still use `API-###` in this template; the ID does not authorize runtime implementation.

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
- Artifact-only interface specs must stay within artifact scope unless `product/`, `architecture/`, and the task contract explicitly authorize runtime work.
