# Review Task Prompt

You are reviewing completed work in an artifact-driven repository.

## Required Context

- Task folder: `<path/to/tasks/TASK-XXX-short-title/>`
- Task contract: `<path/to/TASK_CONTRACT.md>` if using transitional templates
- Review report destination: `<path/to/REVIEW_REPORT.md>`
- Source artifacts: `<paths to MVP, system design, master plan>`
- Changed files or commit range: `<paths or revision range>`

## Instructions

1. Read the task folder or transitional task contract and source artifacts.
2. Inspect the changed files or commit range.
3. Check whether the implementation satisfies each acceptance criterion.
4. Look for regressions, scope creep, missing tests, missing TDD justification, and unvalidated assumptions.
5. Write findings into the review report.
6. Lead with defects. If there are no findings, say that clearly and note remaining validation gaps.

## Output Requirements

The review report must include:

- verdict
- findings ordered by severity
- contract compliance table
- scope check
- test and validation review
- open questions
