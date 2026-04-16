# Feature: Architecture Diagram Generation

## Purpose
Provide structured generation and review of architecture diagrams for web and mobile delivery systems.

## User Value
Help teams understand system boundaries, component responsibilities, and interaction flows before or during implementation.

## Scope
This feature covers:
- class diagrams
- sequence diagrams
- use case diagrams
- database diagrams
- bounded architecture analysis for Django, FastAPI, Flutter, and deployment flows

## Inputs
- repository structure
- active feature or module context
- requested diagram type
- existing architecture notes when available

## Preconditions
- the diagram goal is defined
- the feature or module scope is known
- relevant source files or specs exist

## Expected Outputs
- a scoped architecture diagram
- explanation of diagram boundaries
- identified assumptions and unknowns

## Artifacts Produced
- PlantUML or Markdown-based diagram artifacts
- supporting explanatory notes when needed

## Agents and Skills Involved
- architect-agent
- class-diagram skill
- sequence-diagram skill
- use-case-diagram skill
- database-diagram skill

## Execution Flow
1. Inspect the relevant spec and repository area.
2. Select the right diagram type.
3. Bound the diagram to one feature, module, or scenario.
4. Generate the diagram artifact.
5. Explain assumptions and unresolved gaps.

## Constraints
- diagrams must stay scoped
- implementation should not be invented to fill unknown areas
- PlantUML is preferred unless another format is explicitly requested

## Security Considerations
- do not expose secrets, internal credentials, or sensitive environment data in diagrams

## Failure Conditions
- stop if the diagram target is too ambiguous to scope safely
- stop if the repository lacks enough context and assumptions would dominate the output

## Acceptance Criteria
- the diagram type matches the requested need
- the scope is bounded and explicit
- repository structure is reflected accurately
- assumptions are called out clearly

## Verification
- confirm the diagram matches the relevant spec and code boundaries
- confirm no sensitive values are exposed

## Non-Goals
- full system reverse engineering without a bounded scope
- implementation of unrelated code changes
