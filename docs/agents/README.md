# Agent Operating Model

This directory holds detailed role contracts. The root `AGENTS.md` is the active rulebook for this repository.

## Agent Handoff Model

Agents should move work through explicit artifacts:

| From Role | Artifact Produced | Next Role |
| --- | --- | --- |
| PM Agent in Research Mode | research brief, source log, feature matrix, gap analysis, reuse decisions | PM Agent |
| PM Agent | PRD, MVP, roadmap | Architect Agent |
| Architect Agent | system design | Lead Agent |
| Lead Agent | master plan, task board | Task Manager Agent |
| Task Manager Agent | task folder, execution prompt | Code Agent |
| Code Agent | code changes, implementation notes, test notes | Review Agent |
| Review Agent | review report | QA Agent |
| QA Agent | validation status | Lead Agent or Task Manager Agent |

## Core Rule

An agent may use chat for discussion, but durable project state belongs in the repository.

## Detailed Role Contracts

- `PM_AGENT.md`
- `ARCHITECT_AGENT.md`
- `LEAD_AGENT.md`
- `TASK_MANAGER_AGENT.md`
- `CODE_AGENT.md`
- `REVIEW_AGENT.md`
- `QA_AGENT.md`

## Task Artifact Direction

Future task instances should live in:

```text
tasks/TASK-XXX-short-title/
  task.md
  plan.md
  implementation.md
  test.md
  review.md
```

The root `AGENTS.md` defines the active role contracts and handoff requirements.
