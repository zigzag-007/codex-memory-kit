# Release and History Memory

Only keep this file if the project has real release or version history to track. Delete it if not needed.

## Source of Truth

- `[State what counts as the real record of releases. Example: git tags and GitHub Releases.]`
- `[State whether a root CHANGELOG.md exists or is deliberately avoided, and why.]`

## Current Public Branch Policy

Origin should only have:

- `[branch name, e.g. main]`
- `[branch name, e.g. dev]`

Current known ref for each, update only after verifying with git, do not guess:

```text
[branch] -> [commit hash]
[branch] -> [commit hash]
```

Feature branches stay local unless the user explicitly asks to push them.

## Release Tags

List real tags and what commit they point to. Check current tag targets before making release changes, do not trust old notes blindly.

```text
[tag] -> [commit hash] [date] [commit subject]
[tag] -> [commit hash] [date] [commit subject]
```

Record the meaning of any tag that is not obvious, for example if the first tag does not correspond to the first commit.

## GitHub Releases

List releases with a one line description and the URL:

```text
[tag] - [short description]
[url]
```

Release decisions worth recording:

- `[Any deliberate choice about what does or does not get a release, e.g. skipping a license-only first commit.]`
- `[Whether release notes live in GitHub Releases rather than annotated tag messages.]`

## Version Bump Pattern

- `[Where the version number or badge lives in the codebase, e.g. index.html, a config file, or a constants file.]`
- `[What to check every time the version is bumped, so nothing is missed.]`

## History Rewrite Log

Only fill this in if the project's git history has ever been rewritten, for example to remove a file or fix commit identities. Keep a dated entry for each rewrite:

```text
[date] - [what was changed and why]
Command used: [e.g. git-filter-repo ...]
Verification performed: [e.g. git log --all -- <file> returned nothing]
```

Caveat to remember: a host like GitHub may keep old objects reachable for a while after a rewrite, and old clones or forks may still hold the old history.

## History Rewrite Caution

Before doing any future history rewrite:

- Verify exact refs first, do not assume.
- Create a backup branch or bundle before starting.
- Prefer `git-filter-repo` over `git filter-branch` if both are available.
- Use explicit `--force-with-lease` with the expected hash when pushing the result.
- Verify the branch list on the remote afterward.

