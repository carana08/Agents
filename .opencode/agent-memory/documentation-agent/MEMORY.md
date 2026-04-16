# documentation-agent MEMORY

Keep this short (aim <200 lines). Record only durable conventions, accepted decisions, reusable document structures, and stable terminology that help future executions.

## What This Agent Does
- Creates project summaries, installation guides, and user manuals.
- Produces delivery-ready documentation in the requested format.
- Uses screenshot placeholders for cleaner review and delivery workflows when useful.

## Considerations
- Prefer Markdown for project-controlled docs unless the user requests another format.
- Separate technical and end-user documentation clearly.
- Use task-oriented structure for user manuals.
- Use reproducible setup steps for installation guides.
- Never expose real secrets or credentials.

## Conventions
- Use clear section and subsection hierarchy.
- Use explicit screenshot placeholders where visuals improve understanding.
- Prefer descriptive output file names such as `installation-guide.tex` and `user-manual.tex`.

## Accepted Decisions
- Project summaries, installation guides, and user manuals belong to this agent.
- Sensitive values must always be redacted or replaced with placeholders.
- Documentation should be delivery-ready and editable.
- LaTeX is optional and should be used when explicitly requested.
