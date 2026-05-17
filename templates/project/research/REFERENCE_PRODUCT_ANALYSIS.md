# Reference Product Analysis

Template rule: analyze observable product patterns only. Do not copy proprietary content, private workflows, branding, assets, or protected implementation details.

| Field | Value |
| --- | --- |
| Status | Draft |
| Owner | <PM Agent in Research Mode> |
| Last Updated | YYYY-MM-DD |
| Upstream Sources | `research/RESEARCH_BRIEF.md`, `research/SOURCE_LOG.md` |
| Downstream Consumers | `research/FEATURE_MATRIX.md`, `research/GAP_ANALYSIS.md`, `product/PRD.md`, `product/MVP.md` |

Evidence confidence values: `high`, `medium`, `low`, `unknown`.

## Reference Products or Accounts

| Reference ID | Product or Account Name | Source Links | Observable Features | User Workflow | Strengths | Weaknesses | What We Can Learn | What We Must Not Copy | Evidence Confidence | Evidence Notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| REF-001 | <name> | <URLs or source IDs> | <visible capabilities only> | <steps visible to a user> | <specific strengths> | <specific weaknesses or gaps> | <pattern, workflow, positioning, constraint> | <copy-protected content, branding, UI text, assets, private flow> | <high / medium / low / unknown> | <screenshots, docs, page sections, demo notes, date checked> |

## Workflow Observations

| Reference ID | Trigger | Inputs | Output | User Control | Failure or Edge Handling | Evidence Confidence | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| REF-001 | <what starts the workflow> | <visible inputs> | <visible output> | <settings, review, edit, export, none> | <observed or unknown> | <high / medium / low / unknown> | <source ID or note> |

## Copying Guardrails

- Use references to understand user expectations and workflow patterns.
- Do not copy proprietary wording, screenshots, branding, layout, hidden workflows, private prompts, or protected assets.
- If only a secondary article describes a closed-source feature, mark confidence accordingly and do not treat it as verified product behavior.
- Low or unknown confidence cannot directly authorize MVP scope. Product discovery must record it as an assumption or create a follow-up validation item before including the behavior in MVP.
