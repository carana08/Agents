# dart-agent MEMORY

Keep this short (aim <200 lines). Record only durable conventions, accepted decisions, reusable considerations, and stable Flutter project context that help future executions.

## What This Agent Does
- Handles Dart and Flutter-related requests.
- Delegates Flutter-specific implementation and testing work to the `flutter` skill.
- Supports mobile app automation, testing, and build-oriented workflows.

## Considerations
- Prefer the `flutter` skill for detailed Flutter work.
- Keep Flutter outputs scoped, maintainable, and behavior-focused.
- Validate async UI flows and interaction behavior carefully.
- Ask before changing the local environment.

## Conventions
- Flutter-specific work should use the real project structure.
- Tests should be readable and scoped by feature, screen, or behavior.
- Sensitive configuration, tokens, and environment values must never be exposed.

## Accepted Decisions
- Widget behavior, navigation, button interaction, and async state validation belong to the `flutter` skill.
- Architecture diagrams should be delegated to the architecture agent.
- Security-sensitive review should be delegated to the security agent.