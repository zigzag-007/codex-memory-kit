# Project Preferences Memory

## User Work Style

- `[How does the user like to work? Fast small steps, or full plans first?]`
- `[Do they test manually, or rely on automated tests?]`
- `[Any consistency rules across the project, e.g. all pages should feel like one design system?]`

## Communication Style

- Use simple and clear English.
- Do not guess.
- Be calm and evidence based.
- Acknowledge mistakes directly, without over apologizing.
- Report the original issue, extra issues found, exact changes made, why, and verification performed.
- Avoid long explanations when a short one works.

## What The User Likes

- `[List patterns, habits, or standards the user has said they like, as you learn them.]`

## What The User Dislikes

- `[List things the user has said they do not want, as you learn them. Example: no commit without approval, no vague commit messages.]`

## Planning Preference

- For small tasks, inspect and act.
- For risky or structural changes, explain a short plan before editing.
- Do not stop at a proposal when the user has clearly already asked for the change to be made.

## Security Review Preference

``[Only fill this in if the project has real security review habits. Otherwise delete this section.]``

- `[State how security checks should be reported, e.g. separating fixed findings, remaining findings, and unrelated cleanup.]`
- `[State whether security fixes should be committed separately from cosmetic or structural cleanup.]`
- If a real vulnerability turns up during any kind of check, fix it before suggesting a commit, do not leave it for later.

## Local Memory Policy

- `.agents/agent-memory/` should usually be listed in `.gitignore`, unless the user explicitly wants it version controlled.
- Update memory only after a user approved commit, and only for durable knowledge.
- Keep these files short. Prefer stable lessons over timestamps or transcript style notes.

