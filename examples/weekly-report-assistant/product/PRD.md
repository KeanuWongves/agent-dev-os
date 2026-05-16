# PRD: Weekly Report Assistant

Template rule: do not use this PRD to authorize implementation until status is `Approved` or the downstream artifact explicitly accepts `Reviewed` input.

| Field | Value |
| --- | --- |
| Status | Approved |
| Owner | PM Agent |
| Last Updated | 2026-05-17 |
| Upstream Context | Round 2 dogfood brief: local developer tool that turns git commit history into weekly-report material grouped by project, feature, bugfix, experiment, and blocker. |
| Downstream Consumers | `product/MVP.md`, `product/ROADMAP.md`, `architecture/SYSTEM_DESIGN.md`, `management/MASTER_PLAN.md` |

## Summary

Weekly Report Assistant helps engineers turn local git commit history into structured weekly-report input. The MVP starts as a local artifact/workflow assistant, not an implemented application. It should preserve commit evidence, group work by project and work type, and produce a report-ready outline without connecting to external services.

## Target Users

| User Segment | Current Workflow | Pain | Desired Outcome |
| --- | --- | --- | --- |
| Individual engineer | Manually scans `git log`, notes, and memory before writing a weekly report. | Commit evidence is scattered and gets rewritten from memory, causing missed work and vague status claims. | A structured local template that turns commit history into grouped weekly-report material. |
| Engineer maintaining multiple project threads | Manually separates project work, feature work, bugfixes, experiments, and blockers. | Categories blur together and context is lost when work spans several repos or branches. | Clear grouping fields and prompts that keep work evidence traceable. |

## Problem

Engineers often need to report weekly progress from local development activity, but raw commit history is too granular and unstructured for management-facing reporting. The core problem is not generating prose; it is preserving evidence while reducing commit history into project, feature, bugfix, experiment, and blocker groups that can be reviewed quickly.

## Goals

| Goal ID | Goal | Why It Matters | Success Signal |
| --- | --- | --- | --- |
| G-001 | Capture commit history in a structured local artifact. | The workflow must be usable before any product code exists. | A user can paste commit entries into a consistent template with fields for repo, date range, commit hash, summary, and evidence. |
| G-002 | Group work by project, feature, bugfix, experiment, and blocker. | The report categories match the requested weekly-report structure. | Each commit or work item can be assigned to exactly one primary group and optional supporting tags. |
| G-003 | Keep the MVP private and local. | The brief explicitly excludes external services and infrastructure. | No external service, database, scheduler, web UI, CLI, agent runtime, or dependency is required for the MVP workflow. |
| G-004 | Produce report-ready material without unsupported claims. | Weekly reports should not invent impact or overstate progress. | The draft output keeps evidence references and marks unknown metrics as unknown instead of implying quantified impact. |

## Non-goals

| Non-goal ID | Non-goal | Reason |
| --- | --- | --- |
| NG-001 | Connecting to GitHub, GitLab, Slack, email, Notion, or calendar services. | MVP starts from local artifacts and local git history only. |
| NG-002 | Implementing a CLI, daemon, web UI, scheduler, database, or agent runtime. | The Round 2 example is artifact-only and must not add runtime surface. |
| NG-003 | Automatically rewriting final polished management prose. | The MVP focuses on evidence grouping and draft structure; final wording remains user-reviewed. |
| NG-004 | Inferring business impact without evidence. | The workflow must avoid vague success claims when commits do not contain metrics. |

## User Workflows

### Workflow: Local Commit Evidence to Weekly Report Draft

| Step | User Action | System Response | Evidence of Success |
| --- | --- | --- | --- |
| 1 | Export or copy a date-bounded git commit list from one or more repos. | The local artifact workflow provides fields for commit hash, repo, date, author, and raw message. | Commit entries are captured without requiring external services. |
| 2 | Fill or review grouping fields for each work item. | The workflow separates project, feature, bugfix, experiment, and blocker categories. | Every item has a primary group and optional notes for uncertainty. |
| 3 | Review a weekly-report outline assembled from grouped items. | The workflow preserves source evidence and highlights gaps such as missing metric data. | The user can write the final weekly report from grouped evidence instead of memory. |

## Functional Requirements

| ID | Requirement | Priority | Acceptance Criteria |
| --- | --- | --- | --- |
| PRD-001 | Provide a local commit summary template for raw commit evidence. | Must | Template includes repo, date range, commit hash, commit message, branch/context, source command, and evidence notes. |
| PRD-002 | Provide a grouping rubric for project, feature, bugfix, experiment, and blocker. | Must | Template explains category definitions and requires one primary group per item. |
| PRD-003 | Preserve traceability from report statements back to commit evidence. | Must | Draft sections include source commit references or explicit `evidence missing` markers. |
| PRD-004 | Support manual review of uncertain classifications. | Should | Template includes an uncertainty field and a review-needed marker. |
| PRD-005 | Produce a weekly-report outline from grouped inputs. | Should | Outline sections map to grouped work and separate metrics, blockers, and follow-up needs. |

## Non-functional Requirements

| ID | Requirement | Priority | Acceptance Criteria |
| --- | --- | --- | --- |
| NFR-001 | Local-first privacy. | Must | MVP workflow can run as Markdown artifact editing without network access. |
| NFR-002 | Portability. | Must | Artifacts are plain Markdown/YAML and do not require installed product dependencies. |
| NFR-003 | Evidence quality. | Must | Claims that lack commit evidence or metric evidence are explicitly marked for user review. |
| NFR-004 | Scope control. | Must | Downstream tasks must not add product code, CLIs, dependencies, services, or validation code unless a later approved task changes scope. |

## Constraints

| Constraint | Source | Impact |
| --- | --- | --- |
| Artifact example only. | Round 2 dogfood brief. | This repository example may create project artifacts and task artifacts only. |
| MVP starts from local artifact/workflow assistant. | Product idea. | Architecture must model artifact interfaces instead of runtime services. |
| No external service integrations. | Product idea and non-goals. | API spec must avoid network APIs and external credentials. |
| No CLI, dependency, database, web UI, agent runtime, scheduler, or validation code. | Round 2 dogfood brief. | Task contracts must explicitly forbid those additions. |

## Assumptions

| ID | Assumption | Risk If False | Validation Plan |
| --- | --- | --- | --- |
| A-001 | Engineers can provide a local `git log` excerpt or equivalent commit list. | The workflow cannot start without raw evidence. | Validate with manual sample commit entries in a future task or user-provided fixture. |
| A-002 | A Markdown template is sufficient to prove the first workflow step. | Users may need automation sooner than expected. | Use TASK-001 to create and inspect the commit summary template before planning automation. |
| A-003 | One primary category per work item is acceptable for the first grouping model. | Some commits may span feature and bugfix work. | Allow optional tags and review-needed notes in the template. |

## Open Questions

| ID | Question | Owner | Required Before | Resolution Artifact |
| --- | --- | --- | --- | --- |
| Q-001 | Should the eventual assistant accept multi-repo commit lists in one weekly report? | PM Agent | Product-code planning | `product/MVP.md` or future task |
| Q-002 | What exact final weekly-report style should be generated after evidence grouping is validated? | PM Agent | Roadmap M2 | `product/ROADMAP.md` |
| Q-003 | Should experiments require metric fields before appearing in the final report? | PM Agent | Report outline task | `product/USER_STORIES.md` |

## Decision Log

| Date | Decision | Rationale | Source |
| --- | --- | --- | --- |
| 2026-05-17 | Approve artifact-only MVP scope for Round 2 dogfood. | The example must stress-test artifact templates without implementing product code. | User brief |
| 2026-05-17 | Start with a commit summary template task. | It is the smallest executable task that supports local evidence capture. | `management/MASTER_PLAN.md` |
