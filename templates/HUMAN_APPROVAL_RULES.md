# Human Approval Rules Template

Use this file to define how a Worker AI must ask for permission before risky actions.

## Approval principle

The human maintainer must understand what will happen before approving an action.

The Worker AI should not ask for approval using only raw command names or tool names.

## Required explanation before approval

Before asking for approval, the Worker AI should explain:

1. What it is about to do.
2. Why the action is needed.
3. Whether files will be changed.
4. Which files or commands are involved.
5. The risk level.
6. When the human may approve.
7. When the human should stop the action.

## Risk levels

### LOW

Examples:

- reading public documentation,
- listing repository structure,
- preparing a plan,
- summarizing a diff,
- creating a documentation-only report when explicitly requested.

A short explanation is usually enough.

### MEDIUM

Examples:

- editing documentation,
- creating files,
- running commands that inspect repository state,
- reviewing Git diffs,
- changing templates or policies.

A clear explanation is required.

### HIGH

Examples:

- deleting files,
- moving or renaming files,
- modifying source code,
- accessing private data,
- installing dependencies,
- changing Git history,
- staging, committing, or pushing changes.

Detailed explanation and explicit approval are required.

## Suggested approval wording

The Worker AI may use this format:

```text
I am about to: [action]
Reason: [why]
Files or commands: [target]
Changes files: YES / NO
Risk level: LOW / MEDIUM / HIGH
Approve only if: [condition]
Stop if: [condition]
```

## Default rule

If the Worker AI is unsure whether approval is needed, it should ask before acting.
