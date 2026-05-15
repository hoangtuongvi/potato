# PAI Core for Codex

PAI Core for Codex is a Codex skill that brings a PAI-style operating workflow into Codex. It is inspired by the visible PAI loop used in Claude Code, adapted for Codex skills, Codex tool use, and file-based memory.

It is not a direct Claude PAI port. Claude-specific hooks and command systems do not exist in Codex in the same form, so this skill focuses on the portable behavior: observe, reason clearly, plan, act carefully, verify, and capture useful learning.

## What It Does

For non-trivial work, the skill guides Codex through a visible algorithm:

```text
PAI ALGORITHM

OBSERVE: What the user wants, important facts, constraints, and risk level.
THINK: A short reasoning summary and selected strategy.
PLAN: Concrete next steps.
BUILD: What Codex is doing now.
EXECUTE: What happened after action or inspection.
VERIFY: Checks performed and resulting state.
LEARN: Durable note, session caveat, or memory update if any.
PAI: Final concise outcome.
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
git clone https://github.com/hoangtuongvi/pai-core-codex.git ~/.codex/skills/pai-core-codex
```

Restart or open a new Codex session so the skill list refreshes.

## Usage

Guaranteed trigger:

```text
Use $pai-core-codex. Help me fix this app.
```

Natural trigger:

```text
Use PAI. Merge this folder into the project.
```

The user should not need to choose a mode. The skill infers the right working style from the task.

## Example Prompts

```text
Use PAI. Inspect this project and summarize what it is. Do not edit files.
```

```text
Use PAI. Merge /source/path into /destination/path.
```

```text
Use PAI. Review this change for bugs and missing tests.
```

```text
Use PAI. Remember that I prefer concise final answers with verification called out.
```

## Memory

PAI memory is explicit and file-based. The skill does not create hidden memory.

Recommended global memory:

```text
~/.codex/pai/
  preferences.md
  tools.md
  workflows.md
```

Recommended project memory:

```text
.pai/
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

- `$pai-core-codex` is the strongest trigger.
- `Use PAI` should usually work.
- Misspellings like `usepai` or `@pai` are not guaranteed.
- To make PAI behavior default without saying "Use PAI", add an `AGENTS.md` rule in your project that tells Codex to use the PAI algorithm for non-trivial work.
