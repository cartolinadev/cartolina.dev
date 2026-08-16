# Agent Instructions

## Git workflow

On a feature branch, commit freely — at milestones during implementation
or after completing a step — without asking first.

**NEVER commit, merge, or push to main without explicit user confirmation.
This means no `git checkout main`, no `git merge`, no `git commit` while on
main, no `git push` to main — nothing — until the user says to do it.**

**All work happens on a feature branch. If you are on main, stop and switch
to a feature branch before touching any files.**

## Public/private boundary

This repository and the website it publishes are public. Never commit
secrets, credentials, tokens, personal data, or non-public application,
customer, partner, hostname, URL, dataset, measurement, screenshot, or
validation details. Do not include local filesystem paths, scratch plans,
agent artifacts, or references to private repositories.

Public prose and examples must be self-contained and verifiable from this
repository or other public sources. When private work informs a change,
retain only a generic conclusion supported by public code.

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
