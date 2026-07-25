# How your Cursor rule becomes a nested Codex AGENTS.md

## What you had in Cursor

File: `.cursor/rules/batch-powershell-coding-standards.md`

```
---
description: Coding standards and patterns for Batch (.bat, .cmd) and PowerShell (.ps1) scripting
globs: "**/*.bat,**/*.cmd,**/*.ps1"
alwaysApply: false
---
```

The `globs` line is what made this rule only load when Cursor was working on a `.bat`, `.cmd`, or `.ps1` file. Codex has no matching frontmatter field, so this part cannot be copied directly.

## What changes for Codex

Codex loads AGENTS.md files based on folder location, not file type. The AGENTS.md closest to the file being edited wins. So the fix is simple: put the batch and PowerShell rules inside an AGENTS.md file that lives in the same folder as your `.bat`, `.cmd`, and `.ps1` scripts. This folder in the example is called `scripts`, use your real folder name instead.

- Drop the frontmatter block completely, Codex does not read it.
- Keep the body content as is, since the actual rules do not need to change.
- Place the file at `scripts/AGENTS.md` in your real project, right next to the scripts it applies to.

See `scripts/AGENTS.md` in this folder for the converted result.

## The general rule for converting any Cursor rule

- `alwaysApply: true` in Cursor → put the content in your root AGENTS.md, or in `project-preferences.md`, since it should apply everywhere.
- `globs: "some/path/**"` in Cursor → put the content in a nested AGENTS.md inside that same folder path.
- `alwaysApply: false` with no globs, meant to be manually triggered → these do not have a clean Codex equivalent yet, since Codex has no manual trigger system like Cursor's `@rule-name`. The safest move is to fold these into the relevant nested AGENTS.md, or keep them as a plain note in `codebase.md` for the agent to read when relevant.
