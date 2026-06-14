# Example: Read-only Inventory

This example shows how to ask a Worker AI to inspect a repository without making changes.

Use this as the first task when testing a new AI coding agent.

## Goal

Understand repository structure and maintenance risks without editing files.

## Allowed scope

```text
- README.md
- ROADMAP.md
- CHANGELOG.md
- CONTRIBUTING.md
- SECURITY.md
- docs/
- templates/
```

## Blocked scope

```text
- source code unless explicitly listed
- secrets
- private data
- logs
- databases
- CSV exports with real data
- images or videos from private workflows
- repository settings
```

## Example instruction

```text
Worker AI,

Perform a read-only inventory of this repository.

Allowed:
- read README.md, ROADMAP.md, CHANGELOG.md, CONTRIBUTING.md, SECURITY.md
- read docs/ and templates/
- summarize repository purpose and current structure
- identify missing documentation or safety gaps

Not allowed:
- create files
- edit files
- delete files
- move files
- run commands that change files
- access sensitive data
- git add
- git commit
- git push

Report:
1. Summary
2. Files read
3. Repository structure
4. Missing or unclear areas
5. Safety risks
6. Recommended next action

Stop after the report.
```

## Expected output

The Worker AI should produce a short report.

It should not create commits, edit files, or paste sensitive content.

## Recommended status

```text
READY_FOR_DOCS_ONLY_PLAN
```
