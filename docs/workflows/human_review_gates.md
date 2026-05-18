# Human Review Gates Workflow

## Objective

Define when AI agents may draft artifacts, when they must stop for human review, and which approvals must be recorded before downstream execution.

Human review gates prevent agent-created artifacts from silently becoming approved scope, architecture, task authorization, implementation exceptions, or release acceptance. Gate 0 is also the workflow routing gate: it decides which later gates are required, optional, waived, or not required for the project.

## Approval Record

All human approvals, rejections, waivers, and limitations must be recorded in `management/APPROVALS.md` in generated projects. A chat message may explain intent, but it does not unlock downstream work until the decision is written into the approval artifact.

Allowed gate decisions: `approved`, `approved with limitations`, `rejected`, `needs revision`, `waived`, `not required`.

Use `not required` only when `management/WORKFLOW_PROFILE.md` records why a gate does not apply. Use `waived` when a gate would normally apply but the human owner explicitly chooses to proceed with limitations.

## Gate 0: Idea Intake Review

| Field | Rule |
| --- | --- |
| Trigger | A vague idea, project brief, user request, or problem statement is captured and may start research or product discovery. |
| Required Input Artifacts | `docs/vision/` for repository work, or project-local brief/discovery notes when available. |
| Human Decisions Required | Confirm the problem is worth exploring, name initial target users, identify known constraints, select a workflow mode, decide whether research/architecture/QA are required, and decide which later gates are required, optional, waived, or not required. |
| Allowed AI Actions Before Approval | Summarize the idea, list assumptions, propose research questions, draft intake notes, and identify missing inputs. |
| Forbidden AI Actions Before Approval | Draft approved PRD/MVP, create architecture, create execution tasks, write code, add dependencies, or claim scope is approved. |
| Exit Criteria | Human owner records an intake decision in `management/APPROVALS.md` and `management/WORKFLOW_PROFILE.md` records workflow mode, risk level, required artifacts, required gates, skipped gates with rationale, and escalation triggers. |
| Downstream Artifacts Unlocked | The artifact set named by `management/WORKFLOW_PROFILE.md`: research, light product brief, PRD/MVP, architecture, task folders, QA, or release artifacts as applicable. |
| Stop Conditions | Target user is unknown, problem statement is contradictory, constraints are missing, workflow mode is unresolved, or required/skipped gates are not recorded. |

## Gate 1: Research Review

| Field | Rule |
| --- | --- |
| Trigger | Research is required or performed, and research artifacts may influence PRD/MVP scope. |
| Required Input Artifacts | `research/RESEARCH_BRIEF.md`, `research/SOURCE_LOG.md`, `research/FEATURE_MATRIX.md`, `research/GAP_ANALYSIS.md`, `research/REUSE_DECISIONS.md`, plus `OPEN_SOURCE_SCAN.md` or `REFERENCE_PRODUCT_ANALYSIS.md` when relevant. |
| Human Decisions Required | Accept, reject, or limit the research findings; approve source confidence; resolve human-provided-required sources; decide whether product discovery may use the findings. |
| Allowed AI Actions Before Approval | Draft and revise research artifacts, mark source confidence, identify gaps, and propose build/reuse/learn/ignore decisions. |
| Forbidden AI Actions Before Approval | Draft or approve PRD/MVP from unreviewed research, recommend reuse with unknown license, copy closed-source content, or turn low-confidence findings into MVP scope. |
| Exit Criteria | `management/APPROVALS.md` records Gate 1 decision, approved research artifacts, limitations, unresolved gaps, and downstream product scope unlocked; or `management/WORKFLOW_PROFILE.md` records that research is not required. |
| Downstream Artifacts Unlocked | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md`, `product/ROADMAP.md`. |
| Stop Conditions | Unsourced claims, inaccessible sources without human notes, unknown license for reuse, low/unknown confidence used as scope without assumption or validation plan. |

## Gate 2: PRD / MVP Approval

| Field | Rule |
| --- | --- |
| Trigger | PRD and MVP artifacts are drafted or revised and may become downstream product scope. |
| Required Input Artifacts | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md` when needed, `product/ROADMAP.md` when sequencing changes, or a light product brief for Light Artifact Workflow; plus Gate 1 approval, research waiver, or research not-required rationale from `management/WORKFLOW_PROFILE.md`. |
| Human Decisions Required | Approve problem, target users, MVP inclusion/exclusion or light artifact scope, non-goals, success criteria, assumptions, and open questions that can remain unresolved. |
| Allowed AI Actions Before Approval | Draft product artifacts, trace requirements to research/user input/assumptions, propose scope cuts, and identify contradictions. |
| Forbidden AI Actions Before Approval | Mark PRD/MVP `Approved`, hand off approved scope to architecture, create implementation tasks, or treat assumptions as decisions. |
| Exit Criteria | `management/APPROVALS.md` records Gate 2 decision with approved product artifacts, downstream scope unlocked, and limitations or waivers. |
| Downstream Artifacts Unlocked | Architecture artifacts when required or light, master planning for artifact-only work, or task planning when `management/WORKFLOW_PROFILE.md` says full architecture is not required. |
| Stop Conditions | Requirements lack traceability, MVP includes deferred scope, non-goals conflict with included capabilities, or research waiver is missing when research was required. |

## Gate 3: Architecture Approval

| Field | Rule |
| --- | --- |
| Trigger | Architecture artifacts are required by the workflow profile, or drafted artifacts may constrain implementation planning, runtime behavior, interfaces, dependencies, or data handling. |
| Required Input Artifacts | Approved PRD/MVP or light product scope, `management/WORKFLOW_PROFILE.md`, and the architecture artifacts required by the selected workflow mode: full architecture for Code Tool or High-risk Integration work, light architecture for artifact/file-interface constraints, or a not-required rationale. |
| Human Decisions Required | Approve system boundaries, dependencies, interface contracts, data handling, runtime surfaces, implementation constraints, and architecture tradeoffs. |
| Allowed AI Actions Before Approval | Draft architecture artifacts, identify tradeoffs, propose alternatives, and flag required human decisions. |
| Forbidden AI Actions Before Approval | Create implementation task folders, mark tasks Ready, add dependencies, create runtime surfaces, or expand product scope through architecture. |
| Exit Criteria | `management/APPROVALS.md` records Gate 3 decision, approved architecture artifacts, rejected alternatives, and limitations; or `management/WORKFLOW_PROFILE.md` records light or not-required architecture rationale. |
| Downstream Artifacts Unlocked | `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `state/task_graph.yaml`, task planning within the approved or not-required architecture boundary. |
| Stop Conditions | Architecture exceeds MVP scope, dependency/license risk is unresolved, interface contract is ambiguous, or implementation constraints cannot be reviewed. |

## Gate 4: Task Plan Approval

| Field | Rule |
| --- | --- |
| Trigger | A non-trivial or high-risk task folder is drafted and may move to `Ready`; low-risk tasks may skip Gate 4 only when the task and workflow profile record a not-required rationale. |
| Required Input Artifacts | `management/WORKFLOW_PROFILE.md`, `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `tasks/TASK-XXX-short-title/task.md`, `plan.md`, `implementation.md`, `test.md`, `review.md`, and approved or explicitly not-required product/architecture artifacts. |
| Human Decisions Required | Approve task objective, allowed paths, forbidden scope, acceptance criteria, validation method, TDD or alternative validation plan, and stop conditions. |
| Allowed AI Actions Before Approval | Draft task folders, propose task slicing, prepare validation plans, and mark tasks as `Draft` or `Blocked`. |
| Forbidden AI Actions Before Approval | Mark high-risk tasks `Ready`, execute tasks, write code, add dependencies, access credentials, call external APIs, or create runtime/validation machinery. |
| Exit Criteria | `management/APPROVALS.md` records Gate 4 decision with task IDs, approved scope, limitations, and downstream execution authorization; or a low-risk task records `Required Human Gate` = `none`, `Approval Status` = `not required`, and a not-required rationale. |
| Downstream Artifacts Unlocked | TDD task execution for approved task folders only. |
| Stop Conditions | Allowed scope is vague, acceptance criteria are not observable, validation plan is missing, task requires unapproved architecture, or task risk is disputed. |

## Gate 5: Implementation Exception Review

| Field | Rule |
| --- | --- |
| Trigger | Code Agent discovers that implementation needs scope expansion, new dependencies, new runtime surfaces, credentials, external APIs, scraping, unresolved validation gaps, or other out-of-scope work. |
| Required Input Artifacts | Current task folder, `implementation.md`, `test.md`, changed-file summary, exception rationale, risk, and proposed artifact updates. |
| Human Decisions Required | Approve, reject, limit, or defer the exception; decide whether upstream product, architecture, or task artifacts must change first. |
| Allowed AI Actions Before Approval | Stop execution, document the exception, propose options, and preserve current work without expanding scope. |
| Forbidden AI Actions Before Approval | Continue out-of-scope implementation, add dependencies, create services/CLIs/runtimes/schedulers/validation scripts, use credentials, scrape sites, or mark acceptance criteria met. |
| Exit Criteria | `management/APPROVALS.md` records Gate 5 decision, authorized exception scope, required upstream updates, and validation requirements. |
| Downstream Artifacts Unlocked | Continued implementation only within the approved exception scope, or return to product/architecture/task planning. |
| Stop Conditions | Human owner is unavailable, exception touches protected data, legal/license risk is unclear, or validation gaps cannot be closed. |

## Gate 6: Release / Final Acceptance

| Field | Rule |
| --- | --- |
| Trigger | Reviewed and validated work is ready for milestone closure, release, external delivery, or final acceptance. Internal drafts may mark Gate 6 not applicable when the workflow profile records the rationale. |
| Required Input Artifacts | `management/TASK_BOARD.md`, `management/VALIDATION_STATUS.md`, `management/CHANGELOG.md`, `management/STATUS.md`, review reports, QA evidence, and known blockers. |
| Human Decisions Required | Accept release scope, known gaps, validation sufficiency, deferred work, and final status. |
| Allowed AI Actions Before Approval | Prepare release notes, summarize validation evidence, list known gaps, and propose follow-up tasks. |
| Forbidden AI Actions Before Approval | Mark release accepted, close milestone as done, hide partial validation, delete blockers, or claim final success without approval. |
| Exit Criteria | `management/APPROVALS.md` records Gate 6 decision, accepted artifacts, limitations, remaining risk, and next cycle trigger; or `management/WORKFLOW_PROFILE.md` records Gate 6 as not applicable for internal drafts. |
| Downstream Artifacts Unlocked | Final acceptance, milestone closure, changelog publication, or next product discovery cycle. |
| Stop Conditions | QA evidence is missing, known blockers remain unresolved, release scope differs from approved artifacts, or acceptance criteria are untested. |

## Global Gate Rules

- Agents may draft artifacts before human approval, but must keep status as `Draft`, `Reviewed`, or `Blocked`.
- Agents must not mark research, PRD/MVP, architecture, high-risk task plans, implementation exceptions, or release artifacts as `Approved`, `Ready`, `Validated`, or accepted unless the required human decision is recorded in `management/APPROVALS.md`.
- A waiver is a human decision. It must name the waived gate, rationale, limitations, and downstream scope unlocked.
- A not-required gate is a routing decision. It must be recorded in `management/WORKFLOW_PROFILE.md` with rationale and limitations.
- If a gate decision changes scope, update upstream artifacts before downstream execution continues.
- If work exceeds the workflow mode or risk level in `management/WORKFLOW_PROFILE.md`, stop and reroute through Gate 0 or the relevant human gate.
