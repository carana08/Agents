# Tech Stack

## Purpose
Define the approved technical stack, compatibility boundaries, and execution rules for a spec-driven implementation focused on Django, FastAPI, Flutter, and deployment workflows.

## Source of Truth
- Use `specs/`, `features/`, `research/`, command files, and project lockfiles as the authoritative source.
- Use `context7` when version-specific framework behavior, syntax, or migration guidance is required.
- If external documentation conflicts with repository state, repository state wins and the mismatch must be reported.

## Supported Primary Stack
This project is centered on:
- Django for Django-native backend concerns
- FastAPI for Python API service concerns outside Django-native ownership
- Flutter for mobile client implementation and validation
- Python for backend and automation workflows
- Markdown for specs, planning, commands, and research artifacts

Any expansion beyond this stack must be justified in `research/` and approved through active specs or features.

## Supported Versions
- Python: `3.12.x` as the baseline target for project execution and automation.
- Django: `5.x` line for Django-owned backend workflows.
- FastAPI: `0.110+` line with Pydantic v2-compatible patterns.
- Pydantic: `2.x` line for schema and validation behavior.
- Flutter: stable `3.x` channel for mobile delivery workflows.
- Dart: `3.x` line aligned with the active Flutter stable version.

If a target repository declares stricter versions in lockfiles or manifests, those declarations override these defaults.

## Compatibility Rules
- Python compatibility must be validated before dependency installation or runtime execution.
- Django and FastAPI patterns must align with their declared major versions.
- FastAPI and Pydantic usage must stay consistent with Pydantic v2 semantics unless an explicit project exception exists.
- Flutter and Dart versions must be mutually compatible according to the installed Flutter SDK.
- Version upgrades across major lines require accepted research and explicit approval.

## Dependency and Tooling Policy
- Do not install dependencies outside declared manifests and approved specs.
- Do not replace approved libraries with similar alternatives without accepted technical justification.
- Avoid unpinned or open-ended versions when reproducibility is required.
- Prefer project-local tooling and wrappers before introducing new command flows.

## Environment Policy
- Use local isolated environments.
- For Python, use `.venv` in the project root when Python work is involved.
- Never install Python project dependencies globally.
- If Python is missing, stop and request installation before creating `.venv`.
- If `.venv` is corrupted, recreate it instead of mutating the host interpreter.

## Stack Boundaries
- Django owns apps, models, migrations, admin, forms, serializers, URLs, and Django-specific test workflows.
- FastAPI owns API routers, request/response schemas, service-level API flows, and API contract validation outside Django-native ownership.
- Flutter owns UI, navigation, state handling, client integration behavior, and mobile test surfaces.
- Deployment concerns are shared but must remain framework-aware and repository-aware.

## Django Execution Expectations
- Preserve clear boundaries across models, serializers/forms, views, admin, and URLs.
- Treat migrations as controlled and reviewable change artifacts.
- Use Django-native test and management command workflows for Django-owned behavior.
- Route Django implementation decisions to the Django specialist by default.

## FastAPI Execution Expectations
- Preserve boundaries across routes, schemas, services, validation, and data access integration points.
- Keep endpoint behavior aligned with explicit request/response contracts.
- Use version-aware guidance for FastAPI and Pydantic syntax when behavior is version-sensitive.
- Route FastAPI implementation decisions to Python/FastAPI specialization.

## Flutter Execution Expectations
- Preserve boundaries across presentation, state, domain logic, and client data layers.
- Keep screen and widget changes scoped to accepted feature definitions.
- Treat API usage from Flutter as client integration behavior unless contract ownership is explicitly assigned.
- Use Flutter-specific test and validation patterns for UI behavior.

## Testing and Validation Expectations
- Validation must be framework-aware.
- Django validation includes model behavior, migrations, admin/forms/serializers consistency, and Django test execution.
- FastAPI validation includes status codes, payload schemas, auth expectations, error handling, and API contract consistency.
- Flutter validation includes widget behavior, navigation flows, async state handling, and client-side integration expectations.
- Cross-stack changes require explicit contract checks between backend and mobile surfaces.

## Build and Deployment Expectations
- Inspect the real project structure before suggesting build, run, or deploy commands.
- Prefer existing project scripts, lockfiles, and reproducible command paths.
- Stop dependent execution when hard prerequisites fail, including missing Python, Docker access, DB access, missing SDKs, or missing binaries.
- For web/mobile delivery, keep deployment guidance explicit by surface:
  - backend service readiness
  - API readiness
  - mobile build readiness
  - environment and secret readiness

## Artifact and Routing Alignment
- `features/` defines what capabilities must be delivered.
- `research/` justifies technical decisions and compatibility choices.
- `commands/` executes approved operational flows.
- `agents/` and memory artifacts route ownership to the most specific specialist.
- Implementation in `src/` must remain traceable to active features and this tech stack.

## Change Control
Any change to stack ownership, supported versions, compatibility policy, or dependency strategy must be documented through accepted research and reflected in the relevant feature/spec artifacts before implementation proceeds.
