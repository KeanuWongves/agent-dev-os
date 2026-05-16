# Agent Operating Model

This directory will hold detailed agent guidance. The root `AGENTS.md` is the active rulebook for this repository.

## Agent Handoff Model

Agents should move work through explicit artifacts:

| From Role | Artifact Produced | Next Role |
| --- | --- | --- |
| Product Agent | PRD, MVP, roadmap | Architecture Agent |
| Architecture Agent | system design | Planning Agent |
| Planning Agent | master plan, task board, task contract | Execution Agent |
| Execution Agent | code changes, execution notes | Review Agent |
| Review Agent | review report | Validation Agent |
| Validation Agent | validation status | Product or Planning Agent |

## Core Rule

An agent may use chat for discussion, but durable project state belongs in the repository.
