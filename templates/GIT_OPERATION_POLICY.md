# Git Operation Policy Template

Use this file to define which Git operations a Worker AI may perform.

## Default policy

The default policy is conservative.

The Worker AI may inspect repository state, but Git write operations require explicit human approval.

## Usually allowed

The following commands are usually allowed for inspection:

```text
git status
git diff
git branch
git log --oneline -n 5
```

## Requires explicit approval

The following commands require explicit human approval:

```text
git add
git commit
git push
git restore
git checkout
git switch
git merge
git rebase
git tag
git mv
git rm
```

## Blocked by default

The following operations are blocked unless separately approved by a maintainer:

```text
git push --force
git reset --hard
git clean
history rewriting
branch deletion
tag deletion
remote changes
submodule changes
```

## Before Git write operations

Before any Git write operation, the Worker AI must report:

- current branch,
- files changed,
- whether changes are in scope,
- whether sensitive files were touched,
- proposed commit message,
- exact Git command requested.

## Commit message guidance

Commit messages should be short and specific.

Examples:

```text
Add worker rules template
Update sensitive data policy
Document read-only inventory workflow
```

## Human review checkpoint

The Worker AI should stop before staging or committing if:

- the diff includes unexpected files,
- sensitive data may be present,
- the task scope changed,
- tests or checks were not run when expected,
- the maintainer has not explicitly approved Git write operations.
