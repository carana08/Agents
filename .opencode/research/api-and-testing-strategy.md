# Research: API and Testing Strategy

## Context
The repository supports Django, FastAPI, and Flutter. Validation and testing responsibilities can easily become blurred between backend agents, mobile agents, and reusable skills.

## Question
How should API validation and testing concerns be separated across agents and skills?

## Options Considered
- Option A: let implementation agents own all API validation directly
- Option B: keep implementation ownership in agents and use reusable skills for focused API validation workflows
- Option C: centralize all testing in one generic testing agent

## Evaluation Criteria
- separation of concerns
- reuse
- routing clarity
- maintainability
- implementation complexity

## Findings
- A single testing agent would weaken framework ownership boundaries.
- Letting every implementation agent redefine testing behavior reduces consistency.
- Focused skills are a good fit for reusable validation workflows, while implementation agents keep ownership of the framework-specific code.

## Decision
Keep framework ownership in agents and use reusable skills for focused validation flows where appropriate.

## Rationale
This matches the current structure where API validation can be a skill while Django and Python agents retain implementation responsibility.

## Constraints
- A skill should not become a hidden replacement for an implementation agent.
- Validation skills must remain reusable and scoped.

## Implications
- Django and Python agents should own the code changes.
- Validation workflows may be extracted into skills when they are reusable.
- Research should be updated if new validation boundaries are introduced.

## Validation
- Review current skills and agents for overlap.
- Confirm that testing ownership and validation reuse remain distinct.

## Status
Accepted
