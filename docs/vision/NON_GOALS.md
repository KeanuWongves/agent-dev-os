# Non-Goals

This file prevents scope creep. Any agent proposing work that conflicts with these non-goals must first update this artifact and get approval.

## Not a Full Project Management Platform

The system should not start by rebuilding Linear, Jira, Notion, or GitHub Projects. It can define task-board artifacts and later integrate with tools, but the MVP source of truth remains Markdown in the repository.

## Not an Agent Runtime

The system should not initially schedule agents, run background workers, manage credentials, or orchestrate multi-agent execution. It should prepare artifacts that agents can consume.

## Not a Complex CLI

The first version should not include a feature-rich CLI. Helper scripts may be added later only after repeated manual workflows are clear.

## Not a Template Marketplace

The first version should focus on one strong project workflow rather than many generic templates for every domain.

## Not a Replacement for Review

The system should make review easier, not skip it. Validation status must be based on evidence.

## Not Chat-Only Workflow

Agents must not leave important decisions only in conversation. If a decision affects product scope, architecture, execution, or validation, it belongs in a tracked artifact.

## Not Dependency-Heavy

Do not add frameworks, package managers, or runtime dependencies until there is executable code that clearly needs them.
