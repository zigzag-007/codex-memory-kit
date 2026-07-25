# [Project Name] — Agent Memory

This is local project memory for agents working on this repository. Keep it short, true, and useful. Do not turn it into a chat transcript.

## Read Order

Start here, then read only the file you need for the task:

- `.agents/agent-memory/workflow.md` — git, commit, push, branch, and review rules.
- `.agents/agent-memory/project-preferences.md` — how the user likes to work and communicate.
- `.agents/agent-memory/codebase.md` — architecture, key files, and how the project fits together.
- `.agents/agent-memory/release-history.md` — release and version history rules, if this project has them.
- `.agents/agent-memory/task.md` — a small active checklist, only if one exists right now.
- `.agents/agent-memory/[topic].md` — optional. See "Optional Topic File" below.

## Optional Topic File

Most projects are fine with just the four standard files above. But if this project has one area that keeps causing bugs, keeps needing deep decisions, or keeps drifting out of sync, such as rendering, exports, payments, or auth, give that area its own file, named after the topic, for example `export-rendering.md` or `payments.md`. Put it in `.agents/agent-memory/` next to the others and add it to the read order above. Keep the standard four files general, and let the topic file hold the deep, specific lessons for that one hard area.

## Project

- Repo path: `[path]`
- Remote: `[git remote url]`
- What this project is: `[one or two sentences]`
- Stack: `[languages, frameworks, build tools]`
- How to run it locally: `[command]`
- Live site or app, if any: `[url]`

## Core Rule

Write one or two sentences here about the single most important structural fact of this codebase. For example, where the main logic lives, or what must never be duplicated. This is the one thing every agent must know before touching code.

## Tool Rule

All file changes must be made with the native file editing tool (`apply_patch` in Codex), never with Python, PowerShell, or shell tricks that bypass it. This keeps the revert feature working. See the root coding standards file for the full rule if one exists in this project.

## Memory Maintenance

Update the files in `.agents/agent-memory/` only after the user approves a commit, and only when something durable changed, like architecture, a workflow rule, or a real preference. Do not update memory after every small edit or failed attempt.

If `.agents/agent-memory/` does not exist yet in a fresh project, read the README, package files, CI config, git history, and main source folders first, then create the starter files listed above before doing any real work.
