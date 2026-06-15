# Small Bugfix Flow Example

This example shows how an OSS maintainer can allow a Worker AI to help with a small bugfix while keeping human control.

Use this only after the Worker AI has successfully completed lower-risk tasks such as:

1. read-only inventory,
2. documentation-only changes,
3. report and review cycles.

A small bugfix is more risky than a documentation-only task, so the scope must be narrow and reviewable.

## Goal

Fix one small, well-understood issue without giving the Worker AI broad repository access.

Good examples:

- fix a typo in a configuration example,
- adjust a small validation condition,
- update one test fixture,
- correct one broken Markdown link,
- fix one clearly identified error message.

Bad examples:

- refactor a module,
- redesign architecture,
- update many files,
- change authentication or permission logic,
- modify release automation,
- touch sensitive data handling without review.

## Recommended workflow

```text
1. Human maintainer defines the bug.
2. Worker AI reads only the approved files.
3. Worker AI proposes a short plan.
4. Human maintainer approves or narrows the plan.
5. Worker AI makes the smallest possible change.
6. Worker AI reports the diff and safety check.
7. Human maintainer reviews before any Git write operation.
8. Git add, commit, and push require separate approval.
```

## Example task definition

```text
Task title:
Fix one broken documentation link.

Goal:
Update one broken link in README.md.

Allowed files:
- README.md

Blocked files:
- source code
- tests
- configuration files
- secrets
- private data
- repository settings

Allowed commands:
- git status
- git diff README.md

Not allowed:
- git add
- git commit
- git push
- package installation
- broad search outside the allowed file

Expected output:
- summary
- files read
- files changed
- diff summary
- safety check
- recommended next status

Stop condition:
Stop after reporting the change. Do not stage, commit, or push.
```

## Example Worker AI instruction

```text
Worker AI, please fix one broken documentation link in README.md.

Allowed:
- read README.md
- edit README.md only
- run git status
- run git diff README.md

Not allowed:
- edit any other file
- access secrets or private data
- install packages
- run tests unless separately approved
- git add
- git commit
- git push

After the change, report:
1. What was changed
2. Files read
3. Files changed
4. Git diff summary
5. Whether sensitive data was accessed
6. Whether Git operations were performed
7. Recommended next status

Stop after the report.
```

## Review checklist

Before approving Git operations, the maintainer should check:

```text
[ ] The changed file was allowed.
[ ] The change is limited to the requested bugfix.
[ ] No unrelated files changed.
[ ] No sensitive data was accessed or printed.
[ ] No Git write operation was performed without approval.
[ ] The diff is small enough to review manually.
[ ] The task result matches the original request.
```

## Good report example

```text
Summary:
Fixed one broken documentation link in README.md.

Files read:
- README.md

Files changed:
- README.md

Commands run:
- git status
- git diff README.md

Safety check:
Sensitive data accessed: NO
Files outside scope changed: NO
Git add executed: NO
Git commit executed: NO
Git push executed: NO

Recommended next status:
READY_FOR_REVIEW
```

## Stop conditions

The Worker AI must stop if:

- more files need to be changed,
- the bug is unclear,
- the fix requires source code changes outside the approved scope,
- sensitive data is encountered,
- tests or commands would modify files,
- Git write operations would be needed,
- the maintainer has not approved the next step.

## Maintainer note

A small bugfix flow should remain small.

If the Worker AI discovers a larger problem, stop the task and create a new issue or plan instead of expanding the current task automatically.
