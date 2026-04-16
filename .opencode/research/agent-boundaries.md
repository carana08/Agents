# Research: Agent Boundaries

## Context
The repository uses multiple specialists. Without explicit technical reasoning for their boundaries, the orchestrator may overlap responsibilities or let one agent execute too much work directly.

## Question
How should responsibilities be separated between agents, and when should a capability be a skill instead of an agent?

## Options Considered
- Option A: broad agents with overlapping responsibilities
- Option B: narrow specialist agents with explicit delegation rules
- Option C: collapse most work into one primary agent with skills only

## Evaluation Criteria
- routing clarity
- maintainability
- transparency
- implementation complexity
- quality of delegation
- risk of arbitrary behavior

## Findings
- Overlapping agents create ambiguity and reduce traceability.
- One broad agent increases arbitrary execution and weakens specialization.
- Narrow specialist agents with explicit delegation rules best match spec-driven control.
- Skills fit reusable framework-specific or tool-specific behavior better than broad ownership boundaries.

## Decision
Use narrow specialist agents for ownership boundaries and use skills for reusable capabilities.

## Rationale
This keeps routing deterministic and lets the orchestrator act as a policy-aware router instead of a catch-all executor.

## Constraints
- A new agent should not be added without a clear unique boundary.
- A skill should not replace a specialist agent when the behavior implies ownership and routing.

## Implications
- `software-orchestrator` should route rather than absorb specialist work.
- `read-instructions-agent` should orchestrate and delegate, not become a universal executor.
- Skills should remain in `skills/` and stay reusable across agents.

## Validation
- Review each agent file for explicit scope and explicit delegation away from itself.
- Confirm that reusable framework helpers live in `skills/`, not in agent prompts.

## Status
Accepted
