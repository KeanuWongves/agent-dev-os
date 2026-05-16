# Problem Statement

## Problem

AI coding agents are increasingly capable at local implementation, but they are often driven by transient conversation state. This causes avoidable project failures:

- Product intent drifts as the conversation gets longer.
- Agents execute before requirements are explicit.
- Architecture decisions are made implicitly and cannot be reviewed later.
- Task boundaries are unclear, so agents overreach or leave hidden gaps.
- Validation is summarized conversationally instead of recorded as evidence.
- New agents cannot reliably resume work without rereading large chat history.

## Why Existing Repos Are Not Enough

A normal software repository usually contains source code, tests, and maybe a README. It rarely contains the full chain from product idea to agent-executable task:

```text
idea -> PRD -> MVP -> roadmap -> system design -> master plan -> task board
     -> task contract -> code-agent execution plan -> review -> validation
```

Without that chain, AI agents are forced to reconstruct intent from incomplete context.

## Desired Change

The repository should make each development step explicit, versioned, and inspectable. A future agent should be able to answer:

- What are we building?
- Why is this in scope?
- What is explicitly out of scope?
- Which design has been approved?
- Which task is authorized?
- What files may be changed?
- What evidence proves the work is complete?
- What risk remains?

## Anti-Problem

This project is not trying to replace human judgment. It is trying to reduce the amount of project state trapped in human memory or chat history.

## Initial Bet

Well-structured Markdown artifacts are enough to prove the workflow before adding automation. The first implementation should optimize for clarity, portability, and manual inspectability.
