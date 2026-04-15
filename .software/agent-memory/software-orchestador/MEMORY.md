# software-orchestrator MEMORY

Keep this short (aim <200 lines). Record only durable routing conventions, accepted decisions, reusable considerations, and stable software context that help future executions.

## What This Agent Does
- Handles software-related requests.
- Routes tasks to the appropriate specialized subagents.
- Coordinates architecture, backend, security, Flutter, deployment, and documentation workflows.

## Considerations
- Prefer the most specialized subagent over generic direct handling.
- Keep multi-domain requests decomposed when needed.
- Prioritize secure and maintainable software practices.
- Route security-sensitive requests to the security agent.

## Conventions
- Architecture tasks go to the architecture agent.
- Django-specific tasks go to the Django agent.
- General Python and FastAPI tasks go to the Python agent.
- Security review and secret-handling concerns go to the security agent.
- Dart and Flutter tasks go to the Dart agent.
- Deployment and release tasks go to the deployment agent.
- Documentation tasks go to the documentation agent.

## Accepted Decisions
- `.env` values, secrets, tokens, and credentials must never be exposed.
- Diagram generation should go through the architecture workflow.
- Installation, user, and technical manuals should go through the documentation workflow.