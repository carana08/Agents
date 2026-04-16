# Research: Documentation Format

## Context
The repository uses Markdown as the primary format for specs, commands, research, and agent definitions. A decision is still needed on whether Markdown should remain the default documentation medium.

## Question
What documentation format should be preferred for repository-controlled operational and planning artifacts?

## Options Considered
- Option A: Markdown as the default format
- Option B: LaTeX as the default format
- Option C: multiple equal-default formats without a clear preference

## Evaluation Criteria
- human readability
- agent readability
- maintainability
- collaboration fit
- implementation complexity

## Findings
- Markdown is the most readable format for both humans and agents in this repository.
- LaTeX is still valuable for delivery-ready documents in specialized documentation flows.
- Multiple equal defaults would reduce consistency.

## Decision
Use Markdown as the repository default for specs, research, commands, and planning artifacts, while allowing specialized documentation flows to choose other formats when explicitly needed.

## Rationale
This matches the PDF guidance and the repository's current artifact structure.

## Constraints
- Markdown default does not forbid LaTeX or other formats when explicitly requested.
- Specialized documentation should be scoped to the relevant workflow.

## Implications
- `documentation-agent` may still produce LaTeX when the deliverable needs it.
- Core SDD artifacts should remain in Markdown.

## Validation
- Confirm that specs, features, research, and commands remain in Markdown.
- Confirm that non-Markdown outputs are justified by an explicit deliverable need.

## Status
Accepted
