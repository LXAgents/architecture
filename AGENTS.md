---
name: Documentation Guidelines
description: Rules and conventions for creating new Markdown documentation files within this repository.
---

# 📝 Documentation Guidelines

To maintain a highly organized and easily maintainable structure, all documentation in the `LXAgents/architecture` repository must strictly adhere to the following rules.

## 1. Strict Scoping Rule
- **1 File = 1 Scope Only:** Never mix multiple system scopes or topics into a single file.
- If a system has distinct, separable processes (e.g., Database logic vs. API logic), **you must create a new file**.
- File Organization Example:
  - `README.md` - Overview and index for the current directory.
  - `wiki/{type}/{file-name}.md` - In-depth documentation categorized by type (e.g., `system`, `database`, `api`).

## 2. File Header Structure
Every new `.md` file **must** include a YAML Frontmatter block at the very top to define its name and scope.

**Required Format:**
```text
---
name: {Concise and clear title}
description: {A 1-2 sentence description of the file's scope}
---
