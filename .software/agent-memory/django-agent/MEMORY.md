# django-agent MEMORY

Keep this short (aim <200 lines). Record only durable conventions, accepted decisions, reusable considerations, and stable Django project context that help future executions.

## What This Agent Does
- Handles Django-specific development tasks.
- Supports Django automation workflows.
- Helps with Django testing and maintainable project structure.

## Considerations
- Prefer Django conventions before introducing custom abstractions.
- Keep concerns separated across models, views, serializers, forms, admin, and URLs.
- Prioritize maintainable and behavior-focused tests.
- Treat migrations and model changes carefully.

## Conventions
- Django-specific tasks should stay within app and framework boundaries.
- Test work should remain scoped and readable.
- Sensitive configuration and `.env` handling must never be exposed.

## Accepted Decisions
- Prefer local virtual environments for Django execution and test workflows.
- Do not assume Django or test tools are already installed.
- Verify the environment before running Django tests.
- Ask before creating a venv or installing dependencies.
- Prefer project-defined dependency files over arbitrary package installation.