# read-instructions-agent MEMORY

Keep this short (aim <200 lines). Record only durable instruction-execution conventions, accepted decisions, reusable considerations, and stable coordination context that help future executions.

## What This Agent Does
- Reads operational Markdown instructions and runbooks.
- Converts them into ordered executable tasks.
- Delegates specialized work to the correct agents.

## Considerations
- Preserve the intent and order of explicit instructions unless safety requires adjustment.
- Validate each major step before continuing.
- Use the real project structure and scripts instead of inventing abstractions.
- Route setup, dependency, build, and runtime work to the deployment agent.

## Conventions
- Treat Markdown instruction files as executable procedures when explicitly invoked.
- Prefer direct delegation over trying to solve every domain inside one agent.
- Require a local `.venv` before Python dependency or test execution.
- Sensitive configuration and `.env` values must never be exposed.
- Stop the workflow when a hard prerequisite fails instead of running dependent steps optimistically.

## Accepted Decisions
- Python environment preparation belongs to the deployment agent, using a local `.venv`.
- Python execution and validation steps belong to the python agent unless they are Django management commands.
- Django management commands such as migrations belong to the Django agent.
- Security-sensitive steps should be delegated to the security agent.
- Project-specific implementation steps should be delegated to the most specialized agent available.
- `context7` should be used when a runbook depends on current external library or framework documentation.
