# Codex Usage Notes

These notes explain how an open-source maintainer can apply AI Agent Maintainer Kit when working with Codex.

The goal is to keep Codex useful while preserving human control over repository changes.

## Role

In this kit, Codex can be treated as a Worker AI.

That means Codex may help with scoped maintenance tasks, such as:

- reading project documentation,
- preparing plans,
- improving Markdown files,
- drafting reports,
- reviewing diffs,
- proposing small changes.

Codex should not be treated as an autonomous repository owner.

## Recommended starting point

Start with a read-only task.

Example:

```text
Review README.md, ROADMAP.md, docs/, and templates/.
Summarize the repository structure and identify unclear documentation.
Do not edit files.
Do not access private data.
Do not run Git write operations.
Stop after the report.
```

This validates that the task scope is clear before allowing file changes.

## Before allowing edits

Before Codex edits files, define:

- the task goal,
- allowed files,
- blocked files,
- whether commands may be run,
- expected output,
- stop condition.

Use:

- `templates/PLAN_TEMPLATE.md`
- `templates/ACTIVE_TASK.md`
- `templates/HUMAN_APPROVAL_RULES.md`

## Documentation-only tasks

Documentation-only tasks are a good next step after read-only validation.

Examples:

- improve a README section,
- add a short docs page,
- update a template wording issue,
- prepare release notes,
- summarize an issue.

Even for documentation-only work, keep the allowed scope explicit.

## Git operation boundary

File editing approval is not the same as Git approval.

Keep these approvals separate:

```text
read files
-> edit files
-> review diff
-> git add
-> git commit
-> git push
```

Codex should not stage, commit, or push changes unless the human maintainer explicitly approves that specific Git operation.

Use:

- `templates/GIT_OPERATION_POLICY.md`
- `templates/REVIEW_TEMPLATE.md`

## Sensitive data boundary

Codex should not read or copy sensitive data by default.

Blocked by default:

- secrets,
- tokens,
- `.env` files,
- private logs,
- databases,
- personal or business data exports,
- screenshots with private information,
- unrelated local files.

If sensitive data may be present, Codex should report only the path, file type, and risk category. It should not print the sensitive contents.

Use:

- `templates/SENSITIVE_DATA_POLICY.md`

## Good Codex task pattern

A safe task request should include:

```text
Goal:
Allowed files:
Blocked files:
Allowed commands:
Git operations:
Expected report:
Stop condition:
```

## Example safe request

```text
Codex, please improve docs/maintainer-workflow.md for clarity.

Allowed:
- read README.md
- read docs/maintainer-workflow.md
- edit docs/maintainer-workflow.md only
- run git diff after editing

Not allowed:
- edit source code
- access secrets or private data
- git add
- git commit
- git push

After editing, report:
1. Summary
2. Files changed
3. Git diff summary
4. Safety check
5. Recommended next status

Stop after the report.
```

## Stop conditions

Codex should stop when:

- the task is complete,
- the requested change needs files outside the allowed scope,
- sensitive data is encountered,
- the diff contains unexpected files,
- a Git write operation would be needed,
- the next step is unclear.

## Maintainer responsibility

The maintainer remains responsible for:

- reviewing changes,
- approving Git operations,
- deciding whether to merge,
- deciding whether to release,
- protecting private data,
- setting project direction.

Codex can assist, but the maintainer stays in control.
