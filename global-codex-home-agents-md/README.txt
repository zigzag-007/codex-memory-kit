This AGENTS.md is not for a project. It goes on your own computer, not in any repository.

Where to put it:

  Windows:  C:\Users\<you>\.codex\AGENTS.md
  Mac/Linux: ~/.codex/AGENTS.md

What it does:

This file loads before every Codex session, on every project, no matter what repo you open. It carries your general working style, plus a "Project Memory Discovery" section that tells Codex, on its own, without being asked, to check for a `.agents` folder and read the memory inside it, even when the project root has no AGENTS.md at all.

Why this matters if you keep memory files out of git:

If you never want an AGENTS.md tracked inside a public repo, this is the fix. Since the file lives on your machine only, it never gets pushed anywhere, and every project you open gets the automatic behavior for free.

If you already have a file at that path, do not just overwrite it blindly, merge the "Project Memory Discovery" section from this file into your existing one instead.
