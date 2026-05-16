# Project Brief

## Working Name

agentic-dev-os

## One-Sentence Description

An artifact-driven operating system that lets developers guide AI coding agents from vague product ideas to validated implementation through durable repository documents.

## Core Thesis

AI agents can execute software work more reliably when the source of truth is a structured repository of artifacts instead of an expanding chat transcript. The system should make product intent, technical design, task scope, execution plans, reviews, and validation evidence explicit enough that different agents can resume, audit, and continue work.

## Primary Users

| User | Need | Failure Mode Today |
| --- | --- | --- |
| Solo developer | Turn rough ideas into buildable plans. | Requirements stay vague and drift across chat sessions. |
| AI-assisted developer | Give Codex a bounded task with context and acceptance criteria. | Agents overreach, miss constraints, or rely on stale context. |
| Technical reviewer | Check whether work matched the original intent. | Review happens against memory instead of written requirements. |
| Project maintainer | Resume a project after time away. | The plan exists only in prior messages or mental context. |

## Product Shape

This repository should start as a documented artifact system:

- Canonical folders for vision, product, architecture, management, workflows, agents, templates, examples, source, and tests.
- Markdown templates that can be copied into real projects.
- Role rules in `AGENTS.md` so agents know whether they are acting as product planner, architect, executor, reviewer, or validator.
- Future helper code only after template usage reveals repeated mechanical work.

## Source of Truth

Repository artifacts are authoritative. Chat is allowed for discussion, but final decisions must be written back to the relevant artifact.

## First-Version Deliverable

The first useful version is not a CLI. It is a clean repository with enough structure that a future Codex agent can:

1. Read the vision.
2. Bootstrap a project artifact set from templates.
3. Convert a project plan into task contracts.
4. Execute one task from a contract.
5. Produce a review report.
6. Record validation status.
