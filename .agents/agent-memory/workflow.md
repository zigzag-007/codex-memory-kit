# Workflow Memory

## Branching Strategy

This project uses a **light two branch model**. It borrows the core idea of Gitflow, keeping finished work on `main` and active work on `dev`, but drops the extra branch types Gitflow defines, no `release/*`, no `hotfix/*`, no `support/*`. Reference for the full Gitflow model, in case a project ever needs to grow into it: <https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow>

- `main` holds finished, working code.
- `dev` is the default branch for day to day work.
- `feature/*` or `fix/*` branches are created locally for anything risky, experimental, or multi step. They stay local and are never pushed unless the user explicitly asks.
- The remote (`origin`) should only ever contain `main` and `dev`. Nothing else belongs there by default.
- There is no dedicated release branch. When it's time to release, tag a commit on `main` directly. See `release-history.md` for the tagging pattern.
- There is no dedicated hotfix branch. An urgent fix is just a normal `fix/*` branch merged the usual way, only faster.

## Git Rules

- Do not commit unless the user explicitly approves.
- Do not push unless the user explicitly approves.
- Do not force push unless the user explicitly asks and the exact target branch is confirmed first.
- Default working branch: `[branch name, e.g. dev]`
- Feature or fix branches stay local unless the user asks to push them.
- Use `git status --short --branch` before and after git actions.
- Stage only the relevant files. Do not use `git add .` unless asked.
- Preserve the user's existing changes. Do not revert, reset, stash, or clean anything that is not part of the current task.

## Commit Style

This project uses **Conventional Commits**. Full spec: <https://www.conventionalcommits.org/en/v1.0.0/>

Format:

```text
type(scope): short imperative description
```

Common types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `chore`, `ci`.

Subject line rules:
- Imperative mood, "add" not "added" or "adds"
- No capital letter right after the colon
- No period at the end
- Keep it under about 72 characters
- Scope is optional but helpful, use a module or section name

A few real examples from this project, once you have some, are more useful than a rule alone:

```text
[type(scope): imperative subject]
[type(scope): imperative subject]
```

If a commit body should credit someone outside the project, for example someone who reported a bug, keep it factual and short:

```text
Thanks to [name] for [what they did, in one short clause].
```

Commit identity to use unless told otherwise:

```text
[Name] <[email]>
```

## Before Every Commit

- Read this file again.
- Check git status and the staged diff carefully.
- Run the project's tests, linter, or build check if one exists.
- Keep commits focused. Split unrelated changes into separate commits.

## After Committing

Report back with:
- the short commit hash and subject
- current branch
- whether the working tree is clean
- whether anything was pushed, stated plainly and only if it actually happened

## Push Policy

- See Branching Strategy above for which branches belong on `origin`.
- Verify remote branch shape before and after any push: `git ls-remote --heads origin`

If something ever goes wrong with a push, for example a branch that should have stayed local getting pushed by accident, write it down here with the date, so it does not quietly repeat:

```text
[date] - [what happened, and what was done about it]
```

## Subagents

`[Only fill this in if the project uses subagents or deep trace workflows. Otherwise delete this section.]`

- Do not blindly trust subagent patches. Review and verify their work locally before treating it as done.

## Communication

- Report the original issue, any extra issues found, the exact changes made, why they were made, and what was verified.
- Do not guess. If something is unclear, inspect the code or ask.

