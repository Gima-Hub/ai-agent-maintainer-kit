# Safety Boundaries

This document explains the safety boundaries recommended by AI Agent Maintainer Kit.

## Principle

A Worker AI should only do what the human maintainer has approved.

When the task scope is unclear, the Worker AI should stop and ask for review.

## Start with low-risk work

Recommended progression:

1. Read-only inventory.
2. Documentation-only changes.
3. Small scoped patches.
4. Git staging or commits only after explicit approval.
5. Push or release only under maintainer control.

## Low-risk actions

Low-risk actions usually include:

- reading public documentation,
- summarizing repository structure,
- preparing plans,
- writing reports,
- checking a diff,
- reviewing issue text.

Even low-risk actions should stay within task scope.

## Medium-risk actions

Medium-risk actions include:

- creating files,
- editing documentation,
- updating templates,
- running inspection commands,
- comparing changes.

These actions should be explained before approval.

## High-risk actions

High-risk actions include:

- editing source code,
- deleting files,
- moving or renaming files,
- installing dependencies,
- accessing sensitive data,
- staging changes,
- committing changes,
- pushing changes,
- changing repository settings.

These actions require explicit approval and review.

## Sensitive data boundary

Worker AI should not read or print sensitive data by default.

Sensitive data may include:

- secrets,
- tokens,
- private logs,
- databases,
- CSV exports with real personal or business data,
- screenshots with private information,
- images and videos from private workflows,
- OCR cache files,
- local paths that reveal private context.

If possible sensitive data is found, the Worker AI should report the path, file type, and risk category only.

## Git boundary

Git inspection is different from Git writing.

Inspection examples:

```text
git status
git diff
git log --oneline -n 5
```

Git write operations need explicit approval:

```text
git add
git commit
git push
git rm
git mv
git reset
git clean
```

## Stop conditions

The Worker AI should stop when:

- the task is complete,
- a required file is outside allowed scope,
- sensitive data is encountered,
- unexpected changes appear,
- commands fail in an unclear way,
- the next step would require a higher permission level.

## Safe default

If unsure, stop and ask for human review.
