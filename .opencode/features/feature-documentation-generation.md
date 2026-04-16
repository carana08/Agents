# Feature: Documentation Generation

## Purpose
Generate structured technical and user-facing documentation for software projects.

## User Value
Reduce manual documentation effort and improve consistency in delivery artifacts for web and mobile projects.

## Scope
This feature covers:
- project summaries
- installation guides
- user manuals
- technical guides
- screenshot placeholder insertion
- delivery-ready documentation generation

## Inputs
- project structure
- codebase context
- existing documentation when available
- requested document type

## Preconditions
- the documentation goal is defined
- repository context exists for the requested document type

## Expected Outputs
- documentation files
- structured sections
- placeholders where visuals improve understanding
- redacted examples instead of real secrets

## Artifacts Produced
- Markdown or other requested documentation outputs
- support notes for screenshots or delivery context

## Agents and Skills Involved
- documentation-agent

## Execution Flow
1. Inspect project context and requested documentation type.
2. Separate technical and end-user concerns.
3. Generate the document structure.
4. Add examples, placeholders, and safe references.
5. Validate that no sensitive data is exposed.

## Constraints
- must not expose real credentials or environment values
- should default to Markdown unless another output format is explicitly requested by the spec or user

## Security Considerations
- redact secrets, tokens, and sensitive environment values
- avoid operational instructions that reveal unsafe production details

## Failure Conditions
- stop if the requested document type lacks enough source context to produce a reliable draft

## Acceptance Criteria
- document structure is clear
- output is editable and delivery-ready
- placeholders are meaningful where useful
- sensitive values are redacted

## Verification
- confirm the document matches the requested audience and purpose
- confirm no secrets or unsafe values appear

## Non-Goals
- direct feature implementation
- replacement for architecture-specific diagram generation
