# Potato

Potato is a personal assistant infrastructure operating framework for Codex.

It gives Codex a visible, disciplined workflow for meaningful tasks: observe the situation, summarize the strategy, plan, act carefully, verify the result, and capture useful learning. It started as a Codex-native take on PAI-style workflows, but the primary name is now Potato.

## What It Does

For non-trivial work, Potato guides Codex through a visible algorithm:

```text
POTATO ALGORITHM

OBSERVE: What the user wants, important facts, constraints, and risk level.
THINK: A short reasoning summary and selected strategy.
PLAN: Concrete next steps.
BUILD: What Codex is doing now.
EXECUTE: What happened after action or inspection.
VERIFY: Checks performed and resulting state.
LEARN: Durable note, session caveat, or memory update if any.
POTATO: Final concise outcome.
```

It also adds:

- Automatic work-mode selection.
- Confirmation gates before destructive or hard-to-reverse actions.
- Explicit verification before completion.
- File-based global and project memory conventions.
- Guardrails for secrets, user changes, and risky operations.

## Install Globally

Clone or copy this repository into your Codex skills folder:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/hoangtuongvi/potato.git ~/.codex/skills/potato
```

Restart or open a new Codex session so the skill list refreshes.

## Usage

Guaranteed trigger:

```text
Use $potato. Help me fix this app.
```

Natural trigger:

```text
Use Potato. Merge this folder into the project.
```

The user should not need to choose a mode. Potato infers the right working style from the task.

## Example Prompts

```text
Use Potato. Inspect this project and summarize what it is. Do not edit files.
```

```text
Use Potato. Merge /source/path into /destination/path.
```

```text
Use Potato. Review this change for bugs and missing tests.
```

```text
Use Potato. Remember that I prefer concise final answers with verification called out.
```

## Memory

Potato memory is explicit and file-based. The skill does not create hidden memory.

Recommended global memory:

```text
~/.codex/potato/
  preferences.md
  tools.md
  workflows.md
```

Recommended project memory:

```text
.potato/
  project.md
  preferences.md
  decisions.md
  workflows.md
```

Codex should only update memory when asked or when a durable note is clearly useful and appropriate. Secrets, tokens, passwords, private keys, and sensitive records should never be stored in memory files.

## Project Files

```text
SKILL.md
agents/openai.yaml
references/memory.md
references/modes.md
```

## Notes

- `$potato` is the strongest trigger.
- `Use Potato` should usually work.
- `PAI` is kept as a legacy alias in the skill description.
- Misspellings like `usepotato` or `@potato` are not guaranteed.
- To make Potato behavior default without saying "Use Potato", add an `AGENTS.md` rule in your project that tells Codex to use the Potato algorithm for non-trivial work.
