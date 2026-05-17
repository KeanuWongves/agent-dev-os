# Management Artifacts

This directory will hold planning and status conventions for projects using `agent-dev-os`.

Management artifacts should answer:

- What is the approved master plan?
- What tasks exist?
- Which task is ready for execution?
- What is blocked?
- What has been reviewed?
- What has been validated?
- What has been learned from repository dogfood rounds?
- What is the current repository-level status?

For new generated projects, use `templates/project/management/MASTER_PLAN.md`, `templates/project/management/TASK_BOARD.md`, `templates/project/management/BLOCKERS.md`, `templates/project/management/STATUS.md`, `templates/project/management/CHANGELOG.md`, and `templates/project/management/VALIDATION_STATUS.md`. Use `templates/project/state/` for lightweight resumability metadata. Legacy flat templates remain in `templates/project/` for backward compatibility.

Repository-level management artifacts:

- `ROUND_LOG.md` records dogfood rounds, results, findings, and proposed next-round focus.
- `PROJECT_STATUS.md` records current repository status, active constraints, watchpoints, and near-term focus.
