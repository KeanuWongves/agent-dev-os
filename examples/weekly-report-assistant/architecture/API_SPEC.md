# API Spec: Weekly Report Assistant

Template rule: interfaces must be explicit enough for implementation and review agents to detect contract drift.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | Architect Agent |
| Last Updated | 2026-05-17 |
| Source Artifacts | `architecture/SYSTEM_DESIGN.md`, `product/USER_STORIES.md` |
| Downstream Consumers | `tasks/`, `tasks/*/review.md`, `management/VALIDATION_STATUS.md` |

## Interface Inventory

| Interface ID | Name | Type | Producer | Consumer | Status |
| --- | --- | --- | --- | --- | --- |
| API-001 | Commit Summary Template Artifact | file/artifact | `product/COMMIT_SUMMARY_TEMPLATE.md` | User, Review Agent, future report-outline task | Approved |
| API-002 | Task Validation Evidence | file/artifact | task-local `test.md` | Review Agent, QA Agent | Approved |
| API-003 | Weekly Report Outline Artifact | file/artifact | future task | User | Deferred |

## Contract Details

### API-001: Commit Summary Template Artifact

| Field | Value |
| --- | --- |
| Purpose | Capture raw commit evidence and classification metadata for weekly-report drafting. |
| Source Requirement | PRD-001, PRD-002, MVP-001, MVP-002 |
| Owner | Code Agent for TASK-001 |
| Stability | experimental |

#### Request or Input

| Field | Type | Required? | Validation Rule | Notes |
| --- | --- | --- | --- | --- |
| repo | text | Yes | Non-empty or `unknown`. | Repository or project source. |
| date_range | text | Yes | Non-empty weekly range. | Example: `2026-05-11..2026-05-17`. |
| commit_hash | text | Yes | Commit hash or `evidence missing`. | Allows manual work items. |
| commit_date | text | Yes | Date or `unknown`. | No strict parser in MVP. |
| author | text | No | Text or blank. | Useful for multi-author logs, not required. |
| branch_or_context | text | No | Text or blank. | Can identify feature branch, experiment, or ticket. |
| raw_message | text | Yes | Non-empty. | Preserve original evidence. |
| source_command | text | Yes | Command text or source note. | Example: `git log --since=...`. |
| primary_group | enum | Yes | One of `project`, `feature`, `bugfix`, `experiment`, `blocker`. | Exactly one primary group. |
| project_name | text | Yes | Non-empty or `unknown`. | Needed for project grouping. |
| optional_tags | list/text | No | Text list or blank. | For cross-cutting work. |
| evidence_notes | text | No | Text or blank. | Source details, links, or review notes. |
| review_needed | boolean/text | Yes | `yes` or `no`. | Required for ambiguous entries. |
| uncertainty_reason | text | Required when `review_needed` is `yes` | Non-empty if review is needed. | Prevents hidden assumptions. |

#### Response or Output

| Field | Type | Required? | Notes |
| --- | --- | --- | --- |
| grouped_items | Markdown sections or table rows | Yes | Items are grouped by primary group and project name. |
| evidence_refs | text/list | Yes | Commit hashes or explicit missing-evidence markers. |
| open_review_items | Markdown list | Yes | Items with `review_needed: yes`. |

#### Errors

| Error | Cause | Expected Handling | User-visible? |
| --- | --- | --- | --- |
| Missing evidence | Commit hash, source command, or message unavailable. | Mark `evidence missing` and set `review_needed: yes` when needed. | Yes |
| Ambiguous group | Item fits multiple categories. | Choose one primary group, add optional tags, and record uncertainty reason. | Yes |
| Unsupported automation request | User expects CLI/parser/integration. | Stop and return to product or architecture artifacts. | Yes |

### API-002: Task Validation Evidence

| Field | Value |
| --- | --- |
| Purpose | Record enough evidence for review and QA without adding validation code. |
| Source Requirement | MVP-AC-002, NFR-004 |
| Owner | Code Agent, Review Agent, QA Agent |
| Stability | stable for this example |

#### Request or Input

| Field | Type | Required? | Validation Rule | Notes |
| --- | --- | --- | --- | --- |
| command_or_manual_check | text | Yes | Exact command or manual check steps. | No custom script creation. |
| working_directory | text | Yes for commands | Repository path. | Required for rerun. |
| expected_result | text | Yes | Observable expectation. | Must map to acceptance criteria. |
| actual_result | text | Yes after execution | Concrete observation. | No vague "manual test passed". |

#### Response or Output

| Field | Type | Required? | Notes |
| --- | --- | --- | --- |
| validation_result | enum | Yes | Pass, Fail, Partial, Blocked, or Not Run. |
| evidence | text | Yes | Command output summary or manual observation. |
| remaining_risk | text | Yes | Use `N/A - none known` only when justified. |

#### Errors

| Error | Cause | Expected Handling | User-visible? |
| --- | --- | --- | --- |
| Evidence missing | Validation not run or not recorded. | Block review or QA. | Yes |
| Scope drift | Changed files exceed allowed task scope. | Request changes; do not approve. | Yes |

## Compatibility Rules

- Breaking interface changes require an architecture decision before implementation.
- Review Agents must compare changed interfaces against this spec.
- QA Agents must validate at least one success path and one relevant failure path for MVP-critical interfaces.
- For this artifact-only MVP, "API" means file/artifact contract, not network or runtime API.
