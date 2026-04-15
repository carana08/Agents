# AGENTS.md

## Project Scope
This repository is focused on software and web development workflows.

Main working areas:
- Django development
- Python backend services, including FastAPI
- software architecture and UML diagram generation
- technical and user documentation
- Dart and Flutter development
- deployment and release workflows
- security-oriented software review

## General Working Rules
- Prefer scoped, maintainable, and production-aware solutions.
- Do not make unrelated changes outside the requested scope.
- Preserve existing conventions unless explicitly asked to refactor them.
- Prefer small, traceable changes over broad rewrites.
- Keep outputs practical and implementation-aware.
- Ask for clarification only when the request is too ambiguous to execute safely or correctly.

## Architecture Rules
- Use PlantUML by default for generated diagrams unless another format is explicitly requested.
- Keep diagrams scoped to the requested module, feature, or bounded context.
- Prefer one diagram type per request unless multiple views are explicitly requested.
- Use the architecture workflow for:
  - class diagrams
  - sequence diagrams
  - use case diagrams
  - database diagrams
  - component diagrams
  - flow diagrams
  - module communication mapping

## Documentation Rules
- Installation guides must be step-by-step and reproducible.
- User documentation must explain how the system is used from the user perspective.
- Technical documentation must explain responsibilities, dependencies, flows, and integration points.
- Prefer Markdown for generated documentation unless another format is explicitly requested.

## Security Rules
- Never expose `.env` values, secrets, tokens, API keys, passwords, or credentials.
- Never hardcode sensitive values into code, configuration examples, or documentation.
- Mask secrets when referencing them.
- Treat authentication, authorization, environment configuration, and secret handling as security-sensitive areas.
- Avoid unsafe logging of tokens, credentials, or internal configuration.
- Prefer secure defaults and explicit validation.
- If a task involves security-sensitive behavior, route it through the security workflow.

## Django Rules
- Keep concerns separated across models, views, serializers, forms, admin, and URLs.
- Prefer clear app boundaries and maintainable project structure.
- Follow Django conventions before introducing unnecessary abstractions.
- Use Django REST Framework patterns consistently when applicable.
- Keep migrations intentional and aligned with model changes.

## Python and FastAPI Rules
- Prefer typed, maintainable, modular Python code.
- Use clear request/response validation boundaries.
- Keep routers, services, and persistence concerns separated.
- Avoid framework leakage across unrelated layers.
- Prefer explicit error handling and structured validation.

## Dart and Flutter Rules
- Keep Flutter code organized by feature or module when possible.
- Prefer readable widget composition and maintainable state handling.
- Separate UI, domain logic, and data access clearly.
- Avoid unclear coupling between widgets and infrastructure logic.

## Deployment Rules
- Prefer reproducible deployment steps.
- Keep environment-specific settings separated from code.
- Validate production-readiness before deployment changes.
- Treat CI/CD, runtime configuration, secrets injection, and infrastructure settings as controlled areas.
- Avoid changes that could break deployment consistency without explicit reason.

## Output Conventions
- Store generated diagrams in `docs/diagrams/` unless another path is requested.
- Store generated technical documents in `docs/`.
- Use clear, scope-based file names for generated artifacts.
- Prefer Markdown for text artifacts and `.puml` for PlantUML diagrams.

## Agent Routing Guidance
- Use the architecture agent for architecture analysis, diagrams, and module communication mapping.
- Use the Django agent for Django-specific implementation work.
- Use the Python agent for FastAPI and general Python backend work outside Django specialization.
- Use the security agent for vulnerability review, secure coding checks, secret handling, and security-sensitive analysis.
- Use the Dart agent for Dart and Flutter development tasks.
- Use the deployment agent for CI/CD, packaging, runtime configuration, and release workflows.
- Use the documentation agent for installation guides, manuals, and technical documentation.

## Expected Working Style
- Identify the primary domain of the request first.
- Delegate specialist work to the appropriate workflow when needed.
- Keep results aligned with real software engineering practice.
- Prefer clarity, correctness, and maintainability over unnecessary complexity.
- Surface assumptions explicitly when context is incomplete.

## Project Commands
Add project-specific commands here, for example:
- `python manage.py test`
- `python manage.py migrate`
- `python manage.py runserver`
- `uvicorn app.main:app --reload`
- `pytest`
- `flutter test`
- `flutter build apk`

## Project Notes
Add stable project-specific conventions here, such as:
- naming conventions
- folder structure rules
- deployment environment notes
- approved architecture decisions
- documentation standards