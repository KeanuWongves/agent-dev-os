# Architecture Decisions: Weekly Report Assistant

Template rule: record decisions that constrain future tasks. Do not use this file as a brainstorming scratchpad.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Architect Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |
| Downstream Consumers | `management/MASTER_PLAN.md`, `tasks/`, `tasks/*/review.md` |

## Decision Index

| ID | Title | Status | Date | Owner |
| --- | --- | --- | --- | --- |
| ADR-001 | Artifact-only MVP interface | Approved | 2026-05-17 | Architect Agent |
| ADR-002 | Commit summary template lives under product artifacts | Approved | 2026-05-17 | Architect Agent |
| ADR-003 | Validation uses inspection, not new validation code | Approved | 2026-05-17 | Architect Agent |

## ADR-001: Artifact-only MVP interface

| Field | Value |
| --- | --- |
| Status | Approved |
| Date | 2026-05-17 |
| Owner | Architect Agent |
| Source Artifacts | `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |

### Context

The Round 2 brief requires a complete example project that stress-tests artifact templates without implementing product source code. The product idea also states that the MVP starts from a local artifact/workflow assistant.

### Decision

The MVP interface is a set of Markdown/YAML artifacts. The system design treats templates and task evidence as the operating surface. No runtime component is approved in this example.

### Alternatives Considered

| Alternative | Benefit | Cost or Risk | Reason Rejected |
| --- | --- | --- | --- |
| Build a CLI prototype. | Demonstrates the eventual developer-tool direction. | Adds code and CLI surface. | Explicitly disallowed. |
| Build a validation script. | Makes checks repeatable. | Adds validation code. | Explicitly disallowed. |
| Use external service import. | Better metadata quality. | Requires network, credentials, and integration scope. | Outside MVP. |

### Consequences

| Consequence | Impacted Artifacts | Required Follow-Up |
| --- | --- | --- |
| API spec describes file contracts rather than network APIs. | `architecture/API_SPEC.md` | Review against artifact fields. |
| Task validation relies on manual inspection and existing shell commands. | `tasks/*/test.md`, `management/VALIDATION_STATUS.md` | Record exact observations. |
| Automation remains deferred. | `product/ROADMAP.md` | Revisit only after MVP validation. |

### Review Trigger

Revisit when a future task proposes product source code, automation, parser behavior, CLI, external integration, or generated validation.

## ADR-002: Commit summary template lives under product artifacts

| Field | Value |
| --- | --- |
| Status | Approved |
| Date | 2026-05-17 |
| Owner | Architect Agent |
| Source Artifacts | `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |

### Context

TASK-001 needs a concrete artifact-only deliverable. The deliverable is user-facing workflow content, not source code or runtime configuration.

### Decision

The first executable task will create `product/COMMIT_SUMMARY_TEMPLATE.md`. The task may update only that file plus its own `implementation.md` and `test.md` during execution.

### Alternatives Considered

| Alternative | Benefit | Cost or Risk | Reason Rejected |
| --- | --- | --- | --- |
| Store the template in `tasks/TASK-001-create-commit-summary-template/`. | Keeps task output local. | Makes the product-facing artifact harder to reuse. | The template is part of MVP product workflow. |
| Add a new top-level `templates/` directory inside the example. | Separates templates from requirements. | Expands the required example structure. | Not needed for one MVP artifact. |
| Store in `management/`. | Emphasizes process. | Confuses product-facing content with project management. | Product workflow content belongs in `product/`. |

### Consequences

| Consequence | Impacted Artifacts | Required Follow-Up |
| --- | --- | --- |
| Product directory will contain one operational template after TASK-001 execution. | `product/` | Task contract must make this allowed path explicit. |
| Future tasks should reference the template as a source artifact. | `tasks/`, `product/ROADMAP.md` | Update task board after validation. |

### Review Trigger

Revisit if multiple reusable templates appear and a dedicated template directory becomes clearer.

## ADR-003: Validation uses inspection, not new validation code

| Field | Value |
| --- | --- |
| Status | Approved |
| Date | 2026-05-17 |
| Owner | Architect Agent |
| Source Artifacts | `product/MVP.md`, `architecture/CODE_RULES.md` |

### Context

The example must prove validation evidence discipline without introducing validation code.

### Decision

Validation for artifact-only tasks uses manual artifact inspection and existing repository shell checks. Validation records must include exact command or manual check steps, expected result, observed result, and remaining risk.

### Alternatives Considered

| Alternative | Benefit | Cost or Risk | Reason Rejected |
| --- | --- | --- | --- |
| Add a Markdown validator script. | Repeatable and precise. | Creates validation code. | Explicitly disallowed. |
| Rely only on reviewer confidence. | Fast. | Violates validation evidence policy. | Review and QA need concrete evidence. |

### Consequences

| Consequence | Impacted Artifacts | Required Follow-Up |
| --- | --- | --- |
| `test.md` must document alternative validation when TDD does not apply. | `tasks/TASK-001-create-commit-summary-template/test.md` | Code Agent records this before creating the template. |
| QA cannot mark work validated until evidence exists. | `management/VALIDATION_STATUS.md` | Status remains Not Run before execution. |

### Review Trigger

Revisit only when validation code becomes explicitly allowed by product, architecture, and task artifacts.
