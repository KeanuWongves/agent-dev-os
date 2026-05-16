# Tech Stack: Weekly Report Assistant

Template rule: a technology is allowed only when it is listed here or explicitly authorized by a task artifact.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Architect Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `product/MVP.md`, `architecture/SYSTEM_DESIGN.md` |
| Downstream Consumers | `architecture/CODE_RULES.md`, `tasks/` |

## Approved Stack

| Area | Approved Choice | Version or Constraint | Rationale | Owner |
| --- | --- | --- | --- | --- |
| Language | Markdown and YAML artifacts only | Plain text files tracked in the repository | Matches artifact-only MVP and is inspectable without runtime dependencies. | Architect Agent |
| Runtime | N/A | No product runtime approved | MVP is a manual local workflow. | Architect Agent |
| Framework | N/A | No framework approved | A framework would imply implementation scope. | Architect Agent |
| Storage | Repository files | Markdown/YAML only | Durable decisions and task evidence live in artifacts. | Architect Agent |
| Testing | Manual artifact inspection plus existing shell/file checks | No validation code | Round 2 allows inspection commands but not new validation scripts. | QA Agent |

## Disallowed or Deferred Technology

| Technology | Status | Reason | Revisit Trigger |
| --- | --- | --- | --- |
| Python, JavaScript, TypeScript, shell scripts, or generated validators | Disallowed | Would create source or validation code, which is out of scope. | Future approved implementation task. |
| Package managers and dependency manifests | Disallowed | Dependencies are explicitly forbidden for this example. | Future architecture decision. |
| CLI | Disallowed | MVP starts as local artifact/workflow assistant. | Manual workflow is validated but too repetitive. |
| Database or persistent service | Disallowed | Repository artifacts are the only approved persistence. | Future product scope requires multi-user or history storage. |
| Web UI | Disallowed | Adds runtime surface beyond MVP. | Future user research proves Markdown workflow is insufficient. |
| External APIs or integrations | Disallowed | Violates local-first MVP and no external services constraint. | Future product decision changes non-goals. |
| Scheduler or agent runtime | Disallowed | Explicitly out of scope for Round 2. | Future roadmap and architecture approval. |

## Dependency Policy

- New dependencies require an approved architecture decision and an explicit task contract allowance.
- Code Agents must stop if implementation requires an unapproved dependency.
- Version changes must update this artifact and any affected task validation commands.

## Environment Assumptions

| Assumption | Required By | Validation Method |
| --- | --- | --- |
| Repository supports Markdown and YAML artifact review. | All MVP artifacts | Inspect files with `find` and review Markdown content. |
| Shell commands are available for repository checks. | Task validation | Run the exact commands listed in task-local `test.md`; do not add scripts. |
| Git diff is available for scope review. | Review and QA | Use `git diff --check` and path inspection. |
