# agent-dev-os

`agent-dev-os` is an artifact-driven software development operating system for AI coding agents.

The repository is designed to turn vague product ideas into durable, reviewable artifacts that can be handed from one agent to another without relying on chat history. The primary source of truth is Markdown in this repo.

## What This Repo Manages

The operating system should help a developer produce and maintain:

- Product artifacts: PRD, MVP scope, roadmap, non-goals, success criteria.
- Architecture artifacts: system design, interface contracts, tradeoff records.
- Management artifacts: master plan, task board, validation status.
- Agent artifacts: task folders, Codex execution plans, review reports.

## Current Bootstrap Scope

This first version intentionally contains structure and templates only. There is no complex CLI, database, service, web app, or dependency graph yet.

Use the repository like this:

1. Start from `docs/vision/` to understand why the system exists.
2. Copy files from `templates/project/` into a project workspace when bootstrapping a new product idea.
3. Convert approved project artifacts into task folders under a project-specific task board.
4. Give Codex agents one task folder plus execution prompt templates from `templates/codex-prompts/`.
5. Record validation and review results back into repository artifacts.

## Directory Map

| Path | Purpose |
| --- | --- |
| `docs/vision/` | Foundational product direction for this repository itself. |
| `docs/product/` | Future product-management conventions and PRD guidance. |
| `docs/architecture/` | Future system-design conventions and architecture decisions. |
| `docs/management/` | Future planning, task-board, and validation-status conventions. |
| `docs/workflows/` | Artifact lifecycle and handoff workflows for humans and agents. |
| `docs/agents/` | Role boundaries and operating rules for AI agents. |
| `templates/project/` | Project-level artifact templates. |
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

Future task instances should use a folder-per-task structure:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

The current `templates/task/TASK_CONTRACT.md` and `templates/task/CODEX_EXECUTION_PLAN.md` files are transitional names. Round 1 should normalize the task templates into the folder-per-task model.

## Not Implemented Yet

- CLI commands for creating or validating artifacts.
- Template rendering engines.
- Task-board synchronization with external tools.
- Agent orchestration.
- Persistent database or web UI.

Those pieces should be added only after the artifact model has survived real project usage.
