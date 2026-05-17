# agent-dev-os

`agent-dev-os` is an artifact-driven software development operating system for AI coding agents.

The repository is designed to turn vague product ideas into durable, reviewable artifacts that can be handed from one agent to another without relying on chat history. The primary source of truth is Markdown in this repo.

## What This Repo Manages

The operating system should help a developer produce and maintain:

- Research artifacts: source logs, open-source scans, reference-product analysis, feature matrices, gap analysis, reuse decisions.
- Product artifacts: PRD, MVP scope, roadmap, non-goals, success criteria.
- Architecture artifacts: system design, interface contracts, tradeoff records.
- Management artifacts: master plan, task board, validation status.
- Agent artifacts: task folders, Codex execution plans, review reports.

## Current Bootstrap Scope

This first version intentionally contains structure and templates only. There is no complex CLI, database, service, web app, or dependency graph yet.

Use the repository like this:

1. Start from `docs/vision/` to understand why the system exists.
2. Run reference research when external references, repositories, products, creators, papers, screenshots, or reuse decisions may affect scope.
3. Copy `templates/project/AGENTS.md` plus the nested `research/`, `product/`, `architecture/`, `management/`, and `state/` directories into a project workspace.
4. Fill product artifacts using research outputs or an explicit research waiver.
5. Continue to architecture, planning, task folders, execution, review, and QA.

## Directory Map

| Path | Purpose |
| --- | --- |
| `docs/vision/` | Foundational product direction for this repository itself. |
| `docs/product/` | Future product-management conventions and PRD guidance. |
| `docs/architecture/` | Future system-design conventions and architecture decisions. |
| `docs/management/` | Future planning, task-board, and validation-status conventions. |
| `docs/workflows/` | Artifact lifecycle and handoff workflows for humans and agents, including `reference_research.md`. |
| `docs/agents/` | Role boundaries and operating rules for AI agents. |
| `templates/project/` | Target-project AGENTS template, nested project artifact templates, state templates, and legacy flat compatibility templates. |
| `templates/project/research/` | Research templates for source logging, reference analysis, feature comparison, gap analysis, and reuse decisions. |
| `templates/task/` | Task-level contract and execution-plan templates. |
| `templates/codex-prompts/` | Prompt scaffolds for Codex execution and review. |
| `src/agent_dev_os/` | Reserved for small helper code after artifact conventions stabilize. |
| `tests/` | Reserved for tests once helper code exists. |
| `examples/` | Reserved for example projects and filled artifact sets. |

## Design Principles

- Artifacts over memory: if a decision matters, it belongs in the repo.
- Narrow handoffs: a Code Agent should receive one task folder, not a vague mandate.
- Reviewable state: every artifact should expose status, owner, assumptions, and evidence.
- Minimal machinery first: templates and workflows should prove value before tooling is added.
- Agent portability: artifacts should be understandable by Codex or any capable coding agent.

## Task Artifact Direction

Task instances should use a folder-per-task structure:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

Canonical templates live in `templates/task/task.md`, `templates/task/plan.md`, `templates/task/implementation.md`, `templates/task/test.md`, and `templates/task/review.md`. `templates/task/TASK_CONTRACT.md` and `templates/task/CODEX_EXECUTION_PLAN.md` remain as transitional compatibility templates.

## Project Template Direction

Generated projects should prefer the nested template structure:

```text
research/
product/
architecture/
management/
state/
tasks/
```

`templates/project/AGENTS.md` defines target-project role contracts. The `state/` layer is lightweight resumability metadata; durable decisions still belong in research, product, architecture, management, and task artifacts.

## Not Implemented Yet

- CLI commands for creating or validating artifacts.
- Template rendering engines.
- Task-board synchronization with external tools.
- Agent orchestration.
- Persistent database or web UI.

Those pieces should be added only after the artifact model has survived real project usage.
