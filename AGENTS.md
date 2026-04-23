# Agent Instructions

## Session Log

At the start of each working session, read
[docs/session-log.md](docs/session-log.md).

**Before every commit** — without exception — update the session log to
reflect the current state of things. Commit the session log together with
the other changes. This is mandatory; do not skip it even for small or
"obvious" changes.

On a feature branch, commit freely — at milestones during implementation
or after completing a step — without asking first.

**NEVER commit, merge, or push to main without explicit user confirmation.
This means no `git checkout main`, no `git merge`, no `git commit` while on
main, no `git push` to main — nothing — until the user says to do it.**

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
