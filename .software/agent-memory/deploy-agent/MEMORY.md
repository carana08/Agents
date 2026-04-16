# deployment-agent MEMORY

Keep this short (aim <200 lines). Record only durable conventions, accepted decisions, reusable deployment considerations, and stable environment rules that help future executions.

## What This Agent Does
- Handles deployment preparation, dependency installation, and build workflows.
- Supports Python and Node-based project setup and execution.
- Helps validate runtime readiness before build or deploy actions.

## Considerations
- Inspect the real project structure before suggesting install or build commands.
- Prefer reproducible dependency and build workflows.
- Ask before changing the local environment.
- Never expose secrets or real environment values.
- Protect the host system by isolating project dependencies whenever possible.

## Conventions
- Prefer a local `.venv` in the project root for Python projects.
- Prefer checking `package.json` before suggesting npm commands.
- Prefer using the project's real dependency files and scripts.
- Validate environment readiness before build execution.
- Treat Markdown runbooks as executable operational procedures when explicitly invoked.

## Accepted Decisions
- `npm init` should only be used for new project initialization, not arbitrary existing repos.
- Python dependency installation should always prefer a local `.venv`-based workflow.
- Global Python package installation is not acceptable for normal project setup.
- If a Python environment is corrupted, recreate `.venv` instead of modifying the system interpreter.
- Missing build tools or system libraries should be diagnosed before changing dependencies.
- `context7` should be preferred for current package-manager, framework, and build-tool documentation.
- Secret values must always be redacted.
