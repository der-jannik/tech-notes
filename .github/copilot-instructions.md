# Copilot Instructions for Tech Notes

## Repository Overview

This is a personal technology knowledge base built with Foam and VS Code. It contains markdown notes organized for learning and reference, published to GitHub Pages. The workspace uses wikilinks (`[[file]]`) for navigation and cross-referencing.

## Key Directory Structure

- **`tech-notes/`**: Permanent knowledge base. Notes here are formally correct, well-structured, and organized for reference. This is the primary destination for polished content.
- **`journal/`**: Research and learning notes. Unstructured, informal, and potentially incomplete—used to capture learning from research, videos, and reading. Content here may have typos or logical inconsistencies.
- **`docs/`**: Foam template documentation (may be removed; not core to the workflow).
- Other folders exist but their usage is evolving.

## Linking and Organization

- **Use wikilinks** (`[[note-name]]`) to connect related content. Always include the reference definition at the end of the file.
- **Hierarchy is determined by links, not folder structure** (except `journal/` and `tech-notes/`).
- **Update thematic index notes** when adding new content. For example:
  - New programming language? Add it to `tech-notes/software-development.md`
  - New OS concept? Add it to `tech-notes/operating-systems.md`
  - Check `tech-notes/index.md` for top-level organizational patterns

## Working with Notes

### When Writing or Editing Notes

1. **Prioritize formal correctness**: Clear definitions, proper grammar, accurate technical content.
2. **Be concise and precise**: Avoid overcomplicated explanations.
3. **Distinguish concepts from technologies**: Group related ideas together, but separate abstract concepts from concrete implementations.
4. **Question assumptions**: Challenge logic and verify facts—don't assume correctness.
5. **Focus on fundamentals**: Emphasize core concepts and best practices over edge cases.

### Journal vs. Tech Notes

- **Journal**: Dump raw research notes here without concern for polish. Use when learning from external sources. 
- **Tech Notes**: Refactor journal entries into structured, formally correct notes for long-term reference. Reorganize, verify facts, and improve clarity.
- **Never mix**: Keep journal entries separate from permanent knowledge base entries.

### Linking Best Practices

- Link new notes to related thematic index notes (e.g., `software-development.md` for new languages).
- Create bidirectional connections when notes are peers or related concepts.
- Use descriptive link titles: `[[file]] "Clear descriptive title"`
- Always maintain reference definitions at the file's end to support GitHub web UI navigation.

## Content Quality Standards

- **Tech Notes** should be publication-ready: clear title, logical flow, minimal errors.
- **Concepts** should define core ideas before discussing implementations.
- **Code or technical details** should be precise and accurate.
- Verify or question claims that seem uncertain—flag ambiguities for later research.

## Tasks You Can Help With

- Writing and refining notes in `tech-notes/`
- Reorganizing and linking content
- Converting journal entries into structured tech notes
- Checking for broken or missing links
- Ensuring new notes are connected to relevant thematic indices
- Improving clarity, grammar, and technical accuracy
- Structuring complex topics hierarchically through links

---

**Remember**: Take time to understand the repository structure before making changes. When in doubt, ask clarifying questions about organization or content placement.
