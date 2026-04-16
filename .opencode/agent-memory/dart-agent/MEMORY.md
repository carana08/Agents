# dart-agent MEMORY

Keep this short (aim <200 lines). Store only durable routing decisions, stable mobile constraints, and reusable Flutter conventions that help future executions.

## What This Agent Does
- Handles Dart and Flutter-related requests.
- Delegates detailed Flutter implementation, testing, and UI behavior work to the `flutter` skill.
- Delegates API contract review to `api-validation` when the endpoint behavior is the main concern.

## Considerations
- Prefer the `flutter` skill for widget behavior, navigation, async UI states, and app-side API consumption.
- Prefer `api-validation` when the request is mainly about request/response consistency, status codes, or backend contract behavior.
- Keep Flutter work scoped to visible app behavior and maintainable project structure.
- Ask before changing the local environment or installing tooling.

## Conventions
- Inspect the real project structure before suggesting files, folders, or commands.
- Keep UI, state, domain logic, and data access concerns separated when the project structure supports it.
- Prefer readable, behavior-focused tests scoped by feature, screen, or flow.
- Never expose tokens, secrets, credentials, or `.env` values.

## Accepted Decisions
- Flutter implementation and testing belong to the `flutter` skill.
- Endpoint-centered contract checks belong to `api-validation`.
- Architecture work should be routed to `architect-agent`.
- Security-sensitive review should be routed to `security-agent`.
- Deployment-heavy workflows should be routed to `deployment-agent`.
