# Maintainer Workflow

This document describes a practical workflow for maintainers using AI Agent Maintainer Kit.

## 1. Define the task

Start by writing a clear task.

Include:

- goal,
- allowed files,
- blocked files,
- risk level,
- expected output,
- stop condition.

Use `templates/PLAN_TEMPLATE.md` when the task needs planning.

## 2. Set the active task

Use `templates/ACTIVE_TASK.md` as a shared pointer.

Keep it short and update it when the task changes.

It should show:

- current focus,
- current worker,
- allowed scope,
- blocked scope,
- latest plan,
- latest report,
- next action.

## 3. Start with read-only work

For a new Worker AI, start with read-only inventory.

Ask it to:

- inspect only documentation or explicitly allowed files,
- summarize structure,
- identify risks,
- avoid private data,
- report and stop.

## 4. Move to documentation-only work

After read-only work is safe, allow small documentation-only changes.

Examples:

- create a short report,
- update a README section,
- add a documentation template,
- improve wording in a policy file.

Do not allow source code edits yet.

## 5. Review every change

Review the report and diff before approving the next step.

Use `templates/REVIEW_TEMPLATE.md` to check:

- scope,
- changed files,
- sensitive data exposure,
- unexpected Git operations,
- quality and clarity.

## 6. Approve Git operations separately

Do not treat file editing approval as Git approval.

Approve each level separately:

1. file read,
2. file edit,
3. diff review,
4. git add,
5. git commit,
6. git push.

This separation helps prevent accidental commits or pushes.

## 7. Record the result

After a task finishes, keep a short report.

The report should include:

- files read,
- files changed,
- commands run,
- safety check,
- recommended next status.

## 8. Increase permissions slowly

Only increase Worker AI permissions after successful lower-risk tasks.

Recommended progression:

```text
read-only
-> docs-only write
-> small scoped patch
-> git diff review
-> git add with approval
-> git commit with approval
-> git push with approval
```

## 9. Keep the human in control

The human maintainer remains responsible for project direction, security, release decisions, and final approval.

The Worker AI helps execute scoped work. It does not own the repository.
