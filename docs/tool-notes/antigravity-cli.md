# Antigravity CLI Usage Notes

These notes explain how an open-source maintainer can apply AI Agent Maintainer Kit when testing or using Antigravity CLI.

The goal is to use Antigravity CLI as a Worker AI while keeping human control over repository changes.

## Role

In this kit, Antigravity CLI can be treated as a Worker AI.

That means it may help with scoped maintenance tasks, such as:

- reading approved repository files,
- preparing plans,
- creating documentation-only changes,
- writing reports,
- reviewing Git diffs,
- proposing next steps.

Antigravity CLI should not be treated as an autonomous maintainer.

## Trusted folder consideration

When using a local agent, the folder trusted by the tool matters.

Before starting work, confirm:

- the trusted folder is the intended repository,
- the task scope is limited to approved files,
- private or unrelated folders are outside scope,
- sensitive data paths are blocked by default.

Do not rely only on tool trust settings. Also define task-level boundaries in writing.

## Recommended starting point

Start with a read-only validation task.

Example:

```text
Inspect README.md, ROADMAP.md, docs/, and templates/.
Summarize repository structure and identify unclear areas.
Do not edit files.
Do not access secrets or private data.
Do not run Git write operations.
Stop after the report.
```

This verifies that the Worker AI can follow scope before allowing file creation or edits.

## Documentation-only validation

After a successful read-only task, a documentation-only task can be used as the next validation step.

Examples:

- create a short Markdown report,
- add a small docs page,
- improve wording in a template,
- summarize a maintenance issue.

Keep the allowed scope narrow.

## Approval explanation rule

Before asking for approval, Antigravity CLI should explain the action in plain language.

A good approval request should include:

```text
Action:
Reason:
Files or commands:
Will files change: YES / NO
Risk level: LOW / MEDIUM / HIGH
Approve only if:
Stop if:
```

For simple read-only operations, a short explanation is usually enough.

For file edits, deletion, moves, installs, sensitive data access, or Git write operations, a detailed explanation is required.

## Git operation boundary

Keep Git inspection and Git writing separate.

Usually allowed for inspection:

```text
git status
git diff
git log --oneline -n 5
```

Requires explicit approval:

```text
git add
git commit
git push
git rm
git mv
git reset
git clean
```

Do not treat permission to edit a file as permission to stage, commit, or push.

## Sensitive data boundary

Antigravity CLI should not access sensitive data by default.

Blocked by default:

- `.env` files,
- API keys,
- tokens,
- private logs,
- databases,
- personal or business data exports,
- screenshots with private information,
- images or videos from private workflows,
- OCR cache files,
- unrelated local folders.

If possible sensitive data is encountered, report only:

- path,
- file type,
- risk category,
- recommended handling.

Do not print the sensitive contents.

## Example safe request

```text
Antigravity CLI,

Perform a documentation-only task.

Allowed:
- read README.md
- read docs/maintainer-workflow.md
- create docs/tool-notes/example.md
- run git status
- run git diff for the created file

Not allowed:
- edit source code
- access secrets or private data
- delete or rename files
- git add
- git commit
- git push

After the task, report:
1. Summary
2. Files read
3. Files changed
4. Git status summary
5. Git diff summary
6. Safety check
7. Recommended next status

Stop after the report.
```

## Stop conditions

Antigravity CLI should stop when:

- the task is complete,
- the requested work needs files outside allowed scope,
- sensitive data is encountered,
- unexpected files would be changed,
- a Git write operation would be needed,
- the next step is unclear.

## Maintainer responsibility

The maintainer remains responsible for:

- deciding the task,
- approving risky actions,
- reviewing diffs,
- approving Git operations,
- deciding whether to release,
- protecting private data.

Antigravity CLI can assist with scoped work, but the maintainer stays in control.
