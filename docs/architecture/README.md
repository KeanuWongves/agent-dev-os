# Architecture Artifacts

This directory will hold architecture conventions for projects using `agent-dev-os`.

Architecture artifacts should answer:

- What are the system boundaries?
- What components exist?
- What data moves between components?
- Which interfaces are stable?
- Which tradeoffs were accepted?
- What operational assumptions must implementation agents respect?

For new generated projects, use `templates/project/architecture/SYSTEM_DESIGN.md`, `templates/project/architecture/TECH_STACK.md`, `templates/project/architecture/API_SPEC.md`, `templates/project/architecture/CODE_RULES.md`, and `templates/project/architecture/DECISIONS.md`. Legacy flat templates remain in `templates/project/` for backward compatibility.
