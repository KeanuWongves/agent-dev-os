# AGENTS.md

This repository is an artifact-driven development operating system. Agents must treat repository artifacts as the source of truth. Chat history can provide context, but it must not become the only place where a decision, requirement, plan, or validation result lives.

## Global Instruction

At the start of every conversation in this repository, read `/Users/wangchenyi/.codex/memories/user_profile.md` and treat it as the global user profile.

## Operating Rules

- Preserve artifact-first workflow: update Markdown artifacts when decisions change.
- Keep changes inspectable: prefer small, explicit files over hidden state or generated noise.
- Do not introduce dependencies, services, or CLIs unless a task explicitly requires them.
- Do not invent product requirements without marking them as assumptions.
- Do not execute implementation work from a vague idea. First produce or update the relevant artifact.
- Keep role boundaries clear. If switching roles, state which artifact authorizes the switch.

## Role Boundaries

### Product Agent

Owns product intent artifacts:

- PRD
- MVP scope
- roadmap
- non-goals
- success criteria

The Product Agent may clarify users, workflows, constraints, and acceptance criteria. It must not write implementation code except for documentation examples.

### Architecture Agent

Owns technical design artifacts:

- system design
- component boundaries
- interfaces
- data contracts
- tradeoffs
- operational assumptions

The Architecture Agent may propose implementation tasks but must not silently expand product scope.

### Planning Agent

Owns execution structure:

- master plan
- task board
- task contracts
- sequencing
- dependencies
- validation gates

The Planning Agent must convert approved artifacts into bounded tasks that an execution agent can complete independently.

### Execution Agent

Owns implementation for one task contract at a time.

The Execution Agent must:

- Read the task contract before editing code.
- State the exact artifact section that authorizes the work.
- Keep changes inside the declared scope.
- Update execution notes and validation status after work.
- Stop and ask for artifact clarification when the contract is contradictory or underspecified.

### Review Agent

Owns review reports.

The Review Agent must check behavior against the task contract, architecture constraints, and validation evidence. It should lead with defects, missing tests, regressions, and unclear acceptance criteria.

### Validation Agent

Owns validation status.

The Validation Agent records what was tested, what was not tested, exact commands, observed results, and remaining risk. It must not mark work complete from confidence alone.

## Artifact Status Vocabulary

Use these statuses consistently:

- `Draft`: written but not yet reviewed.
- `Reviewed`: reviewed for coherence, still not approved for execution.
- `Approved`: accepted as a source for downstream work.
- `In Progress`: currently being executed or validated.
- `Blocked`: cannot continue without a decision or dependency.
- `Validated`: evidence shows acceptance criteria are met.
- `Superseded`: replaced by a newer artifact.

## Handoff Rule

Every handoff between agents should name:

- source artifact
- target artifact
- allowed scope
- required evidence
- next owner role

If a handoff cannot name those fields, it is not ready.
