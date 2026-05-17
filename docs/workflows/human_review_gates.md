# Human Review Gates Workflow

## Objective

Define when AI agents may draft artifacts, when they must stop for human review, and which approvals must be recorded before downstream execution.

Human review gates prevent agent-created artifacts from silently becoming approved scope, architecture, task authorization, implementation exceptions, or release acceptance.

## Approval Record

All human approvals, rejections, waivers, and limitations must be recorded in `management/APPROVALS.md` in generated projects. A chat message may explain intent, but it does not unlock downstream work until the decision is written into the approval artifact.

Allowed gate decisions: `approved`, `approved with limitations`, `rejected`, `needs revision`, `waived`.

## Gate 0: Idea Intake Review

| Field | Rule |
| --- | --- |
| Trigger | A vague idea, project brief, user request, or problem statement is captured and may start research or product discovery. |
| Required Input Artifacts | `docs/vision/` for repository work, or project-local brief/discovery notes when available. |
| Human Decisions Required | Confirm the problem is worth exploring, name initial target users, identify known constraints, and decide whether reference research is required. |
| Allowed AI Actions Before Approval | Summarize the idea, list assumptions, propose research questions, draft intake notes, and identify missing inputs. |
| Forbidden AI Actions Before Approval | Draft approved PRD/MVP, create architecture, create execution tasks, write code, add dependencies, or claim scope is approved. |
| Exit Criteria | Human owner records an intake decision, research requirement or waiver, and initial constraints in `management/APPROVALS.md`. |
| Downstream Artifacts Unlocked | `research/RESEARCH_BRIEF.md`, `research/SOURCE_LOG.md`, or product discovery only when research is explicitly waived. |
| Stop Conditions | Target user is unknown, problem statement is contradictory, constraints are missing, or research requirement is unresolved. |

## Gate 1: Research Review

| Field | Rule |
| --- | --- |
| Trigger | Research artifacts are drafted and may influence PRD/MVP scope. |
| Required Input Artifacts | `research/RESEARCH_BRIEF.md`, `research/SOURCE_LOG.md`, `research/FEATURE_MATRIX.md`, `research/GAP_ANALYSIS.md`, `research/REUSE_DECISIONS.md`, plus `OPEN_SOURCE_SCAN.md` or `REFERENCE_PRODUCT_ANALYSIS.md` when relevant. |
| Human Decisions Required | Accept, reject, or limit the research findings; approve source confidence; resolve human-provided-required sources; decide whether product discovery may use the findings. |
| Allowed AI Actions Before Approval | Draft and revise research artifacts, mark source confidence, identify gaps, and propose build/reuse/learn/ignore decisions. |
| Forbidden AI Actions Before Approval | Draft or approve PRD/MVP from unreviewed research, recommend reuse with unknown license, copy closed-source content, or turn low-confidence findings into MVP scope. |
| Exit Criteria | `management/APPROVALS.md` records Gate 1 decision, approved research artifacts, limitations, unresolved gaps, and downstream product scope unlocked. |
| Downstream Artifacts Unlocked | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md`, `product/ROADMAP.md`. |
| Stop Conditions | Unsourced claims, inaccessible sources without human notes, unknown license for reuse, low/unknown confidence used as scope without assumption or validation plan. |

## Gate 2: PRD / MVP Approval

| Field | Rule |
| --- | --- |
| Trigger | PRD and MVP artifacts are drafted or revised and may become downstream product scope. |
| Required Input Artifacts | `product/PRD.md`, `product/MVP.md`, `product/USER_STORIES.md` when needed, `product/ROADMAP.md` when sequencing changes, and Gate 1 approval or research waiver. |
| Human Decisions Required | Approve problem, target users, MVP inclusion/exclusion, non-goals, success criteria, assumptions, and open questions that can remain unresolved. |
| Allowed AI Actions Before Approval | Draft product artifacts, trace requirements to research/user input/assumptions, propose scope cuts, and identify contradictions. |
| Forbidden AI Actions Before Approval | Mark PRD/MVP `Approved`, hand off approved scope to architecture, create implementation tasks, or treat assumptions as decisions. |
| Exit Criteria | `management/APPROVALS.md` records Gate 2 decision with approved product artifacts, downstream scope unlocked, and limitations or waivers. |
| Downstream Artifacts Unlocked | `architecture/SYSTEM_DESIGN.md`, `architecture/TECH_STACK.md`, `architecture/API_SPEC.md`, `architecture/CODE_RULES.md`, `architecture/DECISIONS.md`. |
| Stop Conditions | Requirements lack traceability, MVP includes deferred scope, non-goals conflict with included capabilities, or research waiver is missing when research was required. |

## Gate 3: Architecture Approval

| Field | Rule |
| --- | --- |
| Trigger | Architecture artifacts are drafted and may constrain implementation planning. |
| Required Input Artifacts | Approved PRD/MVP, `architecture/SYSTEM_DESIGN.md`, `architecture/TECH_STACK.md`, `architecture/API_SPEC.md`, `architecture/CODE_RULES.md`, and `architecture/DECISIONS.md`. |
| Human Decisions Required | Approve system boundaries, dependencies, interface contracts, data handling, runtime surfaces, implementation constraints, and architecture tradeoffs. |
| Allowed AI Actions Before Approval | Draft architecture artifacts, identify tradeoffs, propose alternatives, and flag required human decisions. |
| Forbidden AI Actions Before Approval | Create implementation task folders, mark tasks Ready, add dependencies, create runtime surfaces, or expand product scope through architecture. |
| Exit Criteria | `management/APPROVALS.md` records Gate 3 decision, approved architecture artifacts, rejected alternatives, and limitations. |
| Downstream Artifacts Unlocked | `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `state/task_graph.yaml`, task planning. |
| Stop Conditions | Architecture exceeds MVP scope, dependency/license risk is unresolved, interface contract is ambiguous, or implementation constraints cannot be reviewed. |

## Gate 4: Task Plan Approval

| Field | Rule |
| --- | --- |
| Trigger | A non-trivial or high-risk task folder is drafted and may move to `Ready`. |
| Required Input Artifacts | `management/MASTER_PLAN.md`, `management/TASK_BOARD.md`, `tasks/TASK-XXX-short-title/task.md`, `plan.md`, `implementation.md`, `test.md`, `review.md`, and approved product/architecture artifacts. |
| Human Decisions Required | Approve task objective, allowed paths, forbidden scope, acceptance criteria, validation method, TDD or alternative validation plan, and stop conditions. |
| Allowed AI Actions Before Approval | Draft task folders, propose task slicing, prepare validation plans, and mark tasks as `Draft` or `Blocked`. |
| Forbidden AI Actions Before Approval | Mark high-risk tasks `Ready`, execute tasks, write code, add dependencies, access credentials, call external APIs, or create runtime/validation machinery. |
| Exit Criteria | `management/APPROVALS.md` records Gate 4 decision with task IDs, approved scope, limitations, and downstream execution authorization. |
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
| Trigger | Reviewed and validated work is ready for milestone closure, release, or final acceptance. |
| Required Input Artifacts | `management/TASK_BOARD.md`, `management/VALIDATION_STATUS.md`, `management/CHANGELOG.md`, `management/STATUS.md`, review reports, QA evidence, and known blockers. |
| Human Decisions Required | Accept release scope, known gaps, validation sufficiency, deferred work, and final status. |
| Allowed AI Actions Before Approval | Prepare release notes, summarize validation evidence, list known gaps, and propose follow-up tasks. |
| Forbidden AI Actions Before Approval | Mark release accepted, close milestone as done, hide partial validation, delete blockers, or claim final success without approval. |
| Exit Criteria | `management/APPROVALS.md` records Gate 6 decision, accepted artifacts, limitations, remaining risk, and next cycle trigger. |
| Downstream Artifacts Unlocked | Final acceptance, milestone closure, changelog publication, or next product discovery cycle. |
| Stop Conditions | QA evidence is missing, known blockers remain unresolved, release scope differs from approved artifacts, or acceptance criteria are untested. |

## Global Gate Rules

- Agents may draft artifacts before human approval, but must keep status as `Draft`, `Reviewed`, or `Blocked`.
- Agents must not mark research, PRD/MVP, architecture, high-risk task plans, implementation exceptions, or release artifacts as `Approved`, `Ready`, `Validated`, or accepted unless the required human decision is recorded in `management/APPROVALS.md`.
- A waiver is a human decision. It must name the waived gate, rationale, limitations, and downstream scope unlocked.
- If a gate decision changes scope, update upstream artifacts before downstream execution continues.
