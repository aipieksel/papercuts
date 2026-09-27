# Papercuts

Maintained by [aipieksel](https://github.com/aipieksel).

Papercuts is a small Codex skill for noticing the repository problems that repeatedly slow contributors down: a stale command, confusing setup, misleading error, or similar friction the project itself can fix. It records concise, actionable notes in the project's `.agents/PAPERCUTS.md` while the main task continues.

Use it during ordinary work when you can reproduce a repository-owned problem, or ask it to review existing notes and remove duplicates. Its filter keeps transient machine failures, secrets, and unrelated product bugs out of the list. The output is a maintenance queue, not an automatic code change.

## Example workflow

1. Reproduce a source- or documentation-owned obstacle.
2. Check that a repository change could prevent it for the next contributor.
3. Record a short note with the evidence and the likely fix.

## Install and use

Copy this whole folder into your assistant's supported skill directory, preserving [SKILL.md](SKILL.md). The skill retains `metadata.internal: true`; availability in a public skill picker depends on your host. Attach the instructions explicitly if needed.

Example: “Use papercuts while fixing this repository. Record only reproducible repository friction, and continue the original task.” For review: “Review and deduplicate this project's `.agents/PAPERCUTS.md`, verifying each surviving issue.”

A suitable synthetic entry is:

```markdown
- [ ] `2026-09-13T12:00:00Z` — `codex` — The documented build command names a removed script; update the README to the current package command.
```

The skill does not install a daemon or run a test suite. Verify a note by reproducing the repository issue and checking that a repository change can fix it. This package is licensed under [MIT](LICENSE).
