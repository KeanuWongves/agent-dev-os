# MVP Scope

## MVP Goal

Create a repository-native artifact system that helps a developer turn one vague product idea into a structured project plan and agent-executable task set.

## In Scope

### Repository Structure

- Standard directories for vision, product, architecture, management, workflows, agents, templates, examples, source, and tests.
- Clear ownership expectations for each directory.
- Minimal source package placeholder for future helper utilities.

### Vision Artifacts

- Project brief.
- Problem statement.
- MVP scope.
- Non-goals.
- Success criteria.

### Project Templates

Templates must exist for:

- PRD
- MVP definition
- roadmap
- system design
- master plan
- task board
- validation status
- review report

Each template should include status, owner, scope, assumptions, decisions, open questions, and evidence expectations where relevant.

### Task Templates

Templates must exist for:

- task contract
- Codex execution plan

Each task template must be narrow enough that a coding agent can execute from it without needing the entire chat history.

### Agent Prompts

Prompt scaffolds must exist for:

- executing a task contract
- reviewing completed work

These prompts should point agents back to artifacts instead of asking them to infer from conversation.

## Out of Scope for MVP

- Full CLI.
- Database.
- Web UI.
- External task manager sync.
- Agent scheduling.
- Template rendering engine.
- Automatic artifact validation.

## MVP Acceptance Criteria

- A new project can be bootstrapped by copying `templates/project/`.
- A task can be expressed by copying `templates/task/TASK_CONTRACT.md`.
- A Codex execution prompt can be created from `templates/codex-prompts/EXECUTE_TASK.md`.
- A reviewer can compare implementation output against the task contract.
- Validation evidence can be recorded without relying on chat history.
