<div align="center">

# 🧠 Codex Memory Kit

**A portable, git-optional memory system for OpenAI Codex.**
Give Codex real project memory across sessions, without relying on its hidden auto memory, and without ever tracking a single file if you don't want to.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)
[![Made for Codex](https://img.shields.io/badge/Made%20for-Codex%20CLI-black.svg)](https://developers.openai.com/codex)
[![Format](https://img.shields.io/badge/Format-AGENTS.md-blue.svg)](https://agents.md)

</div>

---

## Why this exists

Codex forgets everything between sessions by default. `AGENTS.md` helps, but on its own it's just one static file. Codex also ships its own hidden memory system, but that one is auto generated, hard to inspect, and not meant to be hand edited.

This kit is a third option: a small set of plain markdown files, fully under your control, fully readable, fully editable, that give Codex durable project memory, your git rules, your commit style, your architecture notes, your preferences, without depending on anything Codex manages for you behind the scenes.

## What's inside

```
codex-memory-kit/
├── AGENTS.md                          Root memory file (flat layout)
├── .agents/
│   └── agent-memory/
│       ├── workflow.md                Git rules, branching, commit style
│       ├── project-preferences.md     How you like to work
│       ├── codebase.md                Architecture and key files
│       ├── release-history.md         Tags, releases, history notes
│       └── task.md                    Small active checklist
├── nested-layout-pointer/
│   └── AGENTS.md                      Root pointer file (nested layout, option B)
├── global-codex-home-agents-md/
│   ├── AGENTS.md                      Global file for ~/.codex/AGENTS.md
│   └── README.txt                     Setup instructions (nested layout, option A)
├── example-batch-powershell-conversion/
│   ├── HOW_THIS_WAS_CONVERTED.md      How a Cursor rule becomes a nested AGENTS.md
│   └── scripts/AGENTS.md              The converted result
└── HOW-TO-USE.txt                     Full setup guide, human and agent readable
```

## Two ways to use it

### Flat layout
`AGENTS.md` and the memory files sit right at your project root. Codex finds everything automatically, no extra setup.

### Nested layout, keep it out of git
Everything lives inside a `.agents` folder instead. This is the layout to use if you never want your memory system tracked in a public repo. Codex does not automatically look inside `.agents` on its own, so pick one fix:

| Option | What it does | Footprint in your repo |
|---|---|---|
| **A, recommended** | One global file at `~/.codex/AGENTS.md` on your own machine tells Codex to always check for `.agents` and read it | None, zero files added to any repo |
| **B** | One small pointer `AGENTS.md` at your project root, tells Codex to go read `.agents/AGENTS.md` | One small file, gitignore it if needed |

Full setup for both is in [`HOW-TO-USE.txt`](./HOW-TO-USE.txt).

## Quick start

1. Clone or download this kit.
2. Copy `AGENTS.md` and `.agents/` into your project.
3. Pick flat or nested layout, see above.
4. Open Codex in your project and say:
   > Read AGENTS.md, then inspect the repo and fill in codebase.md.
5. Work normally. Update the memory files only after you approve a commit that changes something durable, not after every small edit.

## Branching and commits

The included `workflow.md` template ships with a **light two branch model**, borrowing the core idea of [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) without the extra release and hotfix branches, plus [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) as the commit format. Both are easy to swap out for your own convention if you prefer something else.

## Bringing over rules from Cursor

If you're moving from Cursor, the `example-batch-powershell-conversion/` folder walks through converting a real `.cursor/rules/*.mdc` file, with glob scoping, into a nested Codex `AGENTS.md`. The same method works for any Cursor rule you want to port.

## Adding a topic file

Most projects are fine with the standard five files. If one area of your project keeps needing deep notes, rendering, payments, auth, whatever it is, give it its own file in `.agents/agent-memory/`, named after the topic, and list it in the read order inside `AGENTS.md`.

## Contributing

Issues and pull requests are welcome. If you have a pattern that made your own `AGENTS.md` setup stronger, open a PR.

## License

MIT. See [`LICENSE`](./LICENSE) for details.

---

<div align="center">

Built for people who want their AI coding agent to actually remember things, without giving up control over what it remembers.

</div>