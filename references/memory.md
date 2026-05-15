# PAI Memory

PAI memory is explicit, file-based, and editable by the user. It should make future work easier without creating a hidden profile or stale mythology.

## Recommended Locations

Project memory:

```text
.pai/
  project.md
  preferences.md
  decisions.md
  workflows.md
```

Global memory:

```text
~/.codex/pai/
  preferences.md
  tools.md
  workflows.md
```

Use project memory for repo-specific facts. Use global memory only for stable user preferences and reusable workflows that apply across projects.

## Initialization

Create memory files only when the user asks for PAI memory, project setup, or persistent preferences. Do not create them just because the skill was invoked.

Minimal project `project.md`:

```markdown
# Project Memory

## Purpose

## Current Shape

## Important Constraints

## Verification
```

Minimal global `preferences.md`:

```markdown
# Global Preferences

## Collaboration

## Coding Style

## Verification Preferences

## Tools And Environments
```

## Update Rules

- Ask before storing personal information.
- Never store secrets, tokens, passwords, private keys, or sensitive records.
- Prefer facts observed in files, commands, or user statements.
- Mark uncertainty clearly.
- Keep entries short and scannable.
- Include dates for decisions or facts likely to age.
- Remove or revise stale memory when discovered.

## Suggested Entry Formats

Decision:

```markdown
- 2026-05-15: Chose X over Y because Z. Revisit if condition changes.
```

Workflow:

```markdown
## Run Local App

1. Install dependencies with ...
2. Start the app with ...
3. Verify at ...
```

Preference:

```markdown
- User prefers short final answers with verification called out.
```

## Reading Memory

Before using a memory file, check that it exists and skim only the relevant section. Treat memory as helpful context, not unquestionable truth.

## Writing Memory

When updating memory, state exactly which file changed. Keep the final answer focused on the work, not on the mechanics of memory.
