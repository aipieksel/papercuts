# Papercuts

Maintained by [aipieksel](https://github.com/aipieksel).

A small instruction skill for recording recurring, repository-fixable contributor friction. It writes concise entries to `.agents/PAPERCUTS.md` in the project being worked on, with a two-question filter that excludes machine failures, shell mistakes, transient flakiness, secrets and unrelated product bugs.

## Install and use

Copy this whole folder into your assistant's supported skill directory, preserving [SKILL.md](SKILL.md). The skill retains `metadata.internal: true`; availability in a public skill picker depends on your host. Attach the instructions explicitly if needed.

Example: “Use papercuts while fixing this repository. Record only reproducible repository friction, and continue the original task.” For review: “Review and deduplicate this project's `.agents/PAPERCUTS.md`, verifying each surviving issue.”

A suitable synthetic entry is:

```markdown
- [ ] `2026-09-13T12:00:00Z` — `codex` — The documented build command names a removed script; update the README to the current package command.
```

The skill does not install a daemon or run a test suite. Verify a note by reproducing the repository issue and checking that a repository change can fix it. This package is licensed under [MIT](LICENSE).
