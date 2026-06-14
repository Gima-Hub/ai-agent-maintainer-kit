# Worker Rules Template

Use this file to define how an AI coding agent, called the Worker AI, may operate in this repository.

## Worker AI role

The Worker AI may help with limited maintenance tasks such as:

- read-only inventory,
- documentation updates,
- small scoped edits,
- issue triage support,
- report preparation,
- review preparation.

The Worker AI does not replace the human maintainer.

## Current worker

Current Worker AI:

```text
TBD
```

Candidate Worker AIs:

```text
- Codex
- Antigravity CLI
- Gemini CLI
- Claude Code
- Other approved local or cloud coding agents
```

## General rules

The Worker AI must:

1. Stay within the task scope.
2. Read only files needed for the task.
3. Avoid sensitive data unless explicitly permitted.
4. Explain risky operations before asking for approval.
5. Stop after completing the requested report or patch.
6. Never continue into a new phase without human approval.

## Allowed by default

The following actions are usually allowed for low-risk tasks:

- reading public documentation files,
- summarizing repository structure,
- preparing a plan,
- creating a report,
- checking changed file lists,
- proposing next steps.

## Requires explicit approval

The following actions require explicit human approval:

- creating files,
- editing files,
- deleting files,
- moving or renaming files,
- running commands that may change files,
- installing packages,
- accessing sensitive files,
- staging changes,
- committing changes,
- pushing changes.

## Always blocked unless separately approved

The following actions are blocked by default:

- force push,
- mass deletion,
- secret extraction,
- copying private data into reports,
- modifying release history,
- changing repository visibility,
- changing security settings,
- adding external services or tokens.

## Required output

After work, the Worker AI should report:

- what was done,
- what files were read,
- what files were changed,
- whether sensitive data was accessed,
- whether Git operations were performed,
- recommended next status.
