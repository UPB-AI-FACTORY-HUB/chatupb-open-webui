---
name: git-conventions
description: Team conventions for branch names, commit messages, and pull requests, all tied to a Linear ticket ID (e.g. AI-73). Use whenever creating a branch, writing a commit, or opening a PR, or when the user asks to start work on a ticket.
---

# Branches, Commits, and PRs

Every change belongs to a Linear ticket, like `AI-73`. If you don't know the ticket, ask.

## Quick reference

| What | Format | Example |
|---|---|---|
| Branch | `type/TICKET` | `feature/AI-73` |
| Commit | `TICKET: message` | `AI-73: add user validation` |
| PR title | `TICKET: main message` | `AI-73: Reduce build time` |

## Branch types

- `issue/` – fix a bug
- `feature/` – new feature or improvement
- `chore/` – maintenance: dependencies, config, CI/CD, scripts, docs, cleanup
- `hotfix/` – urgent production fix (rare)

Not sure which? Check the ticket's labels. Still unsure? Ask.

## Rules

- Branch from the latest `main`.
- Branch name is only `type/TICKET`. Don't use Linear's suggested names.
- Commit messages: short, lowercase, start with a verb. No `feature:` or `fix:` prefix.
- The commit's ticket must match the branch's ticket.
- If a PR covers several tasks, list them as bullets in the body.
- Add a reviewer when creating the PR. Ask who if you don't know.
- Resolve all review comments before merging.

## Example

```bash
git fetch origin
git switch -c chore/AI-73 origin/main
git commit -m "AI-73: cache node_modules in docker build"
gh pr create --base main --title "AI-73: Reduce build time" --reviewer <username>
```
