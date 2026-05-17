# Reference Research Workflow

## Objective

Turn vague product inspiration, competitor references, repository links, creator workflows, papers, articles, screenshots, and manual notes into sourced research artifacts before product discovery approves PRD or MVP scope.

This workflow prevents agents from inventing competitor facts, blindly copying closed-source products, or recommending open-source reuse without license evidence.

## Responsible Role

PM Agent in Research Mode.

## Required Inputs

- Product idea, user problem, or project brief.
- Target users or target workflow.
- Human-provided reference links, screenshots, repositories, product names, creators, papers, articles, or manual notes when available.
- Known constraints, non-goals, privacy limits, license limits, time limits, and platform limits.
- Search permission or a human waiver when live source discovery is not available.

## Search Protocol

1. Read `research/RESEARCH_BRIEF.md` or create it from the product idea.
2. Define research questions before collecting sources.
3. Search only within the categories required by the brief: open-source repositories, closed-source products, creator workflows, papers, articles, screenshots, or manual notes.
4. Log every used source in `research/SOURCE_LOG.md`.
5. Do not invent competitor, product, repository, license, activity, popularity, or feature facts.
6. If a source cannot be fetched, record `human-provided required` in `research/SOURCE_LOG.md` and list the missing evidence.
7. Do not use an unfetched source to justify a PRD requirement unless the human owner provides notes and the artifact marks them as human-provided.

## GitHub and Open-source Scan Protocol

1. For each candidate repository, record repo name, URL, license, stars or activity when available, core functionality, reusable modules, risks, and reuse decision in `research/OPEN_SOURCE_SCAN.md`.
2. Record license before recommending reuse.
3. Treat missing or unclear license as a stop condition for reuse.
4. Separate `reuse` from `learn`: a repository can be useful as a pattern even when direct reuse is unsafe.
5. Do not recommend adding dependencies, CLIs, services, runtimes, databases, or validation code unless a later approved architecture and task artifact explicitly authorizes them.

## Closed-source and Reference-product Scan Protocol

1. Analyze only observable product behavior, public workflow, public docs, public videos, public screenshots, or human-provided notes.
2. Record product or account name, source links, observable features, user workflow, strengths, weaknesses, what can be learned, what must not be copied, and evidence notes in `research/REFERENCE_PRODUCT_ANALYSIS.md`.
3. Closed-source products may be studied for product patterns, not copied.
4. Do not copy proprietary wording, branding, layout, assets, prompts, hidden workflows, or implementation details.
5. If evidence is indirect, mark confidence accordingly in downstream artifacts.

## Source Logging Rules

- Every claimed feature must trace to a source row in `research/SOURCE_LOG.md`.
- Allowed source types are `GitHub repo`, `closed-source product`, `content creator`, `paper`, `article`, `user-provided screenshot`, and `manual note`.
- Allowed access statuses are `fetched`, `partially fetched`, `inaccessible`, and `human-provided required`.
- Allowed uses are `reuse`, `learn`, `compare`, `ignore`, and `restricted`.
- Sources marked `restricted` must not be used for direct reuse.

## Feature Matrix Procedure

1. Convert sourced observations into comparable feature rows in `research/FEATURE_MATRIX.md`.
2. For each feature, record reference source, user value, implementation complexity, MVP relevance, evidence, and decision.
3. Use only these decisions: `include`, `defer`, `reject`, `research more`.
4. Use `include` only when the feature has a clear user value, sourced evidence, and MVP relevance.
5. Use `research more` when evidence is missing, inaccessible, contradictory, or too weak.

## Gap Analysis Procedure

1. Compare sourced reference capabilities against the proposed product direction in `research/GAP_ANALYSIS.md`.
2. Record what references have that the project lacks.
3. Record what the project should learn.
4. Record what the project must not copy.
5. Identify differentiators without overstating unsupported claims.
6. Map implications separately for MVP and architecture.

## Reuse Decision Procedure

1. Record each build, reuse, learn, or ignore decision in `research/REUSE_DECISIONS.md`.
2. Link each decision to a source, rationale, license or restriction, risk, and downstream artifact impacted.
3. Treat license unknown, access restrictions, proprietary status, or unclear ownership as stop conditions for reuse.
4. A reuse decision may inform PRD, MVP, tech stack, or architecture, but does not authorize implementation by itself.

## Human Review Gate Handoff

Reference research must hand off to Gate 1: Research Review before PRD drafting or approval.

Required handoff artifacts:

- `research/RESEARCH_BRIEF.md`
- `research/SOURCE_LOG.md`
- `research/OPEN_SOURCE_SCAN.md` or explicit waiver
- `research/REFERENCE_PRODUCT_ANALYSIS.md` or explicit waiver
- `research/FEATURE_MATRIX.md`
- `research/GAP_ANALYSIS.md`
- `research/REUSE_DECISIONS.md`
- unresolved source gaps and human-provided-required items

AI agents may draft and revise research artifacts before Gate 1 approval. They must not draft or approve PRD/MVP from unreviewed research, turn low-confidence findings into MVP scope, or recommend open-source reuse without license evidence. Gate 1 approval, limitation, rejection, or waiver must be recorded in `management/APPROVALS.md`.

## Verification Rules

- No product requirement may cite an unlogged source.
- No claimed reference feature may appear without evidence.
- No open-source reuse recommendation may appear without license or restriction recorded.
- Inaccessible sources must be marked `human-provided required`.
- Closed-source references may influence observable workflow patterns but must not be copied.
- PRD approval requires completed research artifacts or an explicit research waiver recorded in PRD and research brief.
- Product discovery must not draft or approve PRD/MVP from reference findings until Gate 1 is recorded in `management/APPROVALS.md`.

## Common Failure Modes

- Inventing competitor or repository facts from names, memory, summaries, or assumptions.
- Treating stars, screenshots, or marketing claims as proof of implementation quality.
- Copying closed-source product text, workflow details, prompts, screenshots, or brand language.
- Recommending reuse without a license check.
- Turning every reference feature into MVP scope.
- Creating architecture or implementation work before PM research output is reviewed.

## Handoff to Product Discovery

After Gate 1 is recorded, hand off to `product_discovery.md` with:

- `research/RESEARCH_BRIEF.md`
- `research/SOURCE_LOG.md`
- `research/OPEN_SOURCE_SCAN.md` or explicit waiver
- `research/REFERENCE_PRODUCT_ANALYSIS.md` or explicit waiver
- `research/FEATURE_MATRIX.md`
- `research/GAP_ANALYSIS.md`
- `research/REUSE_DECISIONS.md`
- unresolved source gaps and human-provided-required items
- research waiver if applicable
- Gate 1 approval record from `management/APPROVALS.md`

Product discovery may approve PRD or MVP only when this handoff is complete or explicitly waived.
