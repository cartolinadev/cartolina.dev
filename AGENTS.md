# Agent Instructions

## Session Log

At the start of each working session, read
[docs/session-log.md](docs/session-log.md).

Before every commit, review and update the session log so it reflects the
current state of things. Then commit the session log together with the
other changes (or in a follow-up commit immediately after).

On a feature branch, commit freely — at milestones during implementation
or after completing a step — without asking first. On the main branch,
always ask before committing.

During and after work, append any nontrivial observations to the session
log:
- Surprising project structure or configuration details
- Non-obvious constraints, workarounds, or decisions
- Bugs found (even if not fixed yet)
- Patterns that will affect future work in this repo

Keep entries concise — one or two sentences each. Date every entry
(`YYYY-MM-DD`). Do not log routine progress or ephemeral task state; only
log what would genuinely help a future session start faster or avoid a
mistake.

## Examples page ordering

In `pages/examples.md`, implemented example links must always appear
before unimplemented placeholder lines. When adding a new implemented
example, insert it after the last linked entry and before any plain-text
placeholders.

## Source file line length

Wrap continuous prose in all source files at 80 characters per line.
Applies to Markdown pages, READMEs, and similar text files. Does not
apply to YAML front matter values, URLs, code blocks, or HTML attribute
strings that cannot be meaningfully split.

## Documentation style

README and other user-facing docs are for anyone who checks out the
repo, not for this specific machine or environment. Write generically:
describe constraints and workarounds in terms any developer might
encounter, not in terms of the local setup (e.g. avoid "the system has
X" — say "if your system has X" or just state the constraint directly).
