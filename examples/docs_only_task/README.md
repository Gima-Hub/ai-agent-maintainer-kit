# Example: Documentation-only Task

This example shows how to let a Worker AI create or edit documentation while keeping source code and Git operations blocked.

Use this after a successful read-only inventory.

## Goal

Allow a small documentation-only change with clear boundaries.

## Allowed scope

```text
- docs/
- templates/
- examples/
- README.md when explicitly named
```

## Blocked scope

```text
- source code
- tests
- package files
- build files
- secrets
- private data
- logs
- databases
- Git write operations
```

## Example instruction

```text
Worker AI,

Create one documentation file under docs/ explaining the project workflow.

Allowed:
- read README.md
- read templates/PLAN_TEMPLATE.md
- create docs/example-workflow.md
- run git status
- run git diff for the created file

Not allowed:
- edit source code
- edit unrelated files
- access sensitive data
- git add
- git commit
- git push
- delete or rename files

After creating the file, report:
1. Summary
2. Created file
3. Files read
4. Git status summary
5. Git diff summary
6. Safety check
7. Recommended next status

Stop after the report.
```

## Review checklist

Before approving the next step, check:

```text
Only approved files changed: YES / NO
Source code changed: YES / NO
Sensitive data accessed: YES / NO
Git add executed: YES / NO
Git commit executed: YES / NO
Git push executed: YES / NO
```

## Recommended status

If the task was successful:

```text
READY_FOR_HUMAN_REVIEW
```

If the task touched unexpected files:

```text
STOP_DUE_TO_SCOPE_RISK
```
