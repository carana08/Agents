# .software

This repository defines reusable OpenCode agents, skills, commands, and spec-driven delivery artifacts.

## Canonical Structure
- `specs/` for mission, constitution, tech stack, and roadmap
- `features/` for isolated feature specifications and acceptance criteria
- `research/` for technical decision records, evaluated options, findings, and implications
- `agents/` for agent definitions and agent governance
- `skills/` for reusable OpenCode skills consumed from the standard skills directory
- `commands/` for executable Markdown entry points
- `src/` for implementation output only after the spec is defined

## Working Rule
- Write or update the spec first.
- Add research when a decision depends on libraries, versions, compatibility, deployment, security, or testing strategy.
- Break the feature into tasks only after the spec is clear.
- Implement in `src/` only after the spec and acceptance criteria are stable.

## Research Rule
- `research/` does not redefine the mission, roadmap, or global rules.
- `research/` stores question-driven technical analysis that explains why a decision was made and what it implies.
