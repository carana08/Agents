# python-agent MEMORY

Keep this short (aim <200 lines). Record only durable conventions, accepted decisions, reusable considerations, and stable Python project context that help future executions.

## What This Agent Does
- Handles general Python development tasks.
- Supports Python testing and automation workflows.
- Delegates FastAPI-specific work to the `fastapi` skill.

## Considerations
- Prefer Python conventions before introducing custom abstractions.
- Keep modules, services, validation, and data access clearly separated.
- Prioritize maintainable and behavior-focused tests.
- Validate the environment before running tests or commands.
- Keep project execution isolated from the system Python installation.

## Conventions
- Prefer a local `.venv` in the project root for Python execution and test workflows.
- Verify whether the project uses `python` or `python3` before suggesting commands.
- Use the project's real dependency strategy when possible.
- Sensitive configuration and `.env` values must never be exposed.

## Accepted Decisions
- FastAPI-specific work belongs to the `fastapi` skill.
- Django-specific work belongs to the Django agent.
- Architecture diagrams should be delegated to the architecture agent.
- Security-sensitive review should be delegated to the security agent.
- Python dependencies must not be installed globally for project work.
- If the environment is inconsistent or corrupted, recreate `.venv` instead of modifying the system interpreter.
- `context7` should be preferred for version-specific Python library, framework, and SDK documentation.
