# AGENTS.md

## Project Scope
This repository defines reusable OpenCode agents and skills for software work.

Primary domains:
- software architecture and UML
- Django development
- general Python and FastAPI backend work
- Flutter development
- deployment and build workflows
- security review
- technical and user documentation

## Global Rules
- Prefer the most specialized agent available.
- Keep outputs scoped to the user's actual goal.
- Do not make unrelated changes.
- Preserve maintainable, production-aware solutions.
- Ask only when ambiguity would make execution unsafe.
- Never expose secrets, tokens, credentials, API keys, or `.env` values.
- Do not let `research/` redefine mission, roadmap, or constitution artifacts.
- Use accepted research files as decision-support artifacts during planning, not as replacements for the core spec files.

## Architecture Rules
- Prefer PlantUML for diagrams.
- Keep diagrams bounded to one feature, module, or scenario unless the user requests more.
- Use the architecture workflow for:
  - class diagrams
  - sequence diagrams
  - use case diagrams
  - database diagrams
  - bounded software structure analysis

## Documentation Rules
- Installation guides should be reproducible.
- User docs should explain usage from the user's perspective.
- Technical docs should describe responsibilities, dependencies, and flows.
- Prefer Markdown unless the user requests another format.

## Documentation And Library Guidance
- Use the `context7` MCP server as the preferred source for library documentation, version-specific references, examples, migration notes, and current API usage.
- When working with frameworks, SDKs, or third-party libraries, consult `context7` before relying on memory or generic examples.
- Prefer version-aware documentation and examples that match the project dependencies when that information is available.
- If the project's installed version is unknown, inspect the real dependency files first and then use `context7` to align guidance with that version.
- When recommending a library or integration pattern, prioritize current official guidance and current stable practices available through `context7`.

## Framework Rules
- Django work should preserve separation across models, views, serializers, forms, admin, and URLs.
- Python work should preserve separation across services, validation, transport, and data access.
- Flutter work should preserve separation across UI, state, domain logic, and data access.

## Deployment Rules
- Inspect the real project structure before suggesting install or build commands.
- Prefer reproducible build steps and existing project scripts.
- Ask before creating environments or installing dependencies.

## Routing Guidance
- Use `software-orchestrator` as the primary router.
- Use `architect-agent` for architecture and diagram work.
- Use `django-agent` for Django-specific implementation.
- Use `python-agent` for general Python and FastAPI-oriented work outside Django.
- Use `dart-agent` for Dart and Flutter tasks.
- Use `deployment-agent` for install, build, runtime, and release workflows.
- Use `security-agent` for secret handling, validation, auth, and attack-surface review.
- Use `documentation-agent` for manuals and technical documentation.

## Agent Directory Layout
- Keep agent definitions grouped by domain under `agents/`.
- Use `agents/orchestration/software-orchestrator.md` for the primary router.
- Use `agents/arq/architect-agent.md` for architecture and UML specialization.
- Use `agents/dev/django-agent.md`, `agents/dev/python-agent.md`, and `agents/dev/dart-agent.md` for implementation-focused agents.
- Use `agents/qa/security-agent.md` and `agents/qa/documentation-agent.md` for quality-focused agents.
- Use `agents/ops/deployment-agent.md` and `agents/ops/read-instructions-agent.md` for operational execution and runbook delegation.
- Keep naming and folder conventions consistent across repositories to avoid routing drift.

## Precedence Order
When there is a conflict, prefer the highest-level project artifact first:
1. `specs/constitution.md`
2. `specs/mission.md`
3. `specs/tech-stack.md`
4. `features/*.md`
5. `research/*.md`
6. `AGENTS.md`
7. `commands/*.md`
8. `agent-memory/*.md`
9. `src/`

## Project Notes
Add stable project-specific conventions here when they are truly reusable.

## Task Artifact Rules
- Use `tasks/task.md` as the base template for execution-level task definitions.
- Every implementation task must declare one primary subagent owner.
- Tasks may include supporting subagents, but ownership must remain explicit.
- Tasks must link back to one active feature and relevant spec artifacts.
- Do not execute implementation tasks without a task artifact and subagent assignment.

## Spec Run Rules
- Use `/new-spec <feature-or-scope>` to initialize each new execution cycle.
- `/new-spec` must create a timestamped run folder under `specs/runs/`.
- Every run must be registered in `specs/index.md` before implementation begins.
- If `specs/index.md` reports a conflict for the new run, implementation must stay blocked until resolved.
- New runs must not overwrite previous runs; use `supersedes` semantics in `specs/index.md` when replacing prior work.
