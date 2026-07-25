# Codebase Memory

## Architecture Overview

``[Short description of the overall shape of the project. Is it a single page site, a multi service backend, a mobile app, etc. Include a simple folder tree if it helps.]``

```
[folder tree goes here]
```

## Key Files

``[List the files an agent must understand before making changes, with one line each on what they do.]``

- `[path]` — `[what it does]`

## Third Party Dependencies

``[List important libraries, frameworks, or services this project relies on, and what each one is used for.]``

| Name | Version | Purpose |
|------|---------|---------|
| `[library]` | `[version]` | `[purpose]` |

## Consistency Principle

``[Only fill this in if the project has more than one output path that should behave the same way, for example a preview and an export, or a web app and a mobile app sharing logic. If not, delete this section.]``

When fixing a bug in one output path, first check whether it should be fixed in shared code instead, so the other paths do not quietly drift out of sync. If a fix only touches one path, that is a signal to ask why the shared path could not be used, before accepting the fix as final.

## Known Design Decisions

``[List decisions that are not obvious from reading the code alone, so future agents do not accidentally undo them. Example: why a certain pattern was chosen, or a quirk that must be preserved.]``

## Common Verification

``[List the commands used to check that a change did not break anything, such as running tests, starting a local server, or a build command.]``

```
[commands go here]
```

