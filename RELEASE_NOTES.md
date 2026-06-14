# Release Notes

## v0.1.0 - Draft

AI Agent Maintainer Kit v0.1.0 is the first usable template set for open-source maintainers who want to work with AI coding agents while keeping human control.

This release focuses on safe, reviewable, human-supervised workflows.

## Included in this release

### Core templates

- `templates/WORKER_RULES.md`
- `templates/ACTIVE_TASK.md`
- `templates/PLAN_TEMPLATE.md`
- `templates/REPORT_TEMPLATE.md`
- `templates/REVIEW_TEMPLATE.md`
- `templates/HUMAN_APPROVAL_RULES.md`
- `templates/GIT_OPERATION_POLICY.md`
- `templates/SENSITIVE_DATA_POLICY.md`

### Documentation

- `docs/worker-ai-model.md`
- `docs/safety-boundaries.md`
- `docs/maintainer-workflow.md`

### Examples

- `examples/read_only_inventory/README.md`
- `examples/docs_only_task/README.md`

### Repository maintenance files

- `README.md`
- `ROADMAP.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `SECURITY.md`
- `LICENSE.md`
- GitHub issue templates

## Recommended use

Start with the lowest-risk workflow:

```text
read-only inventory
-> documentation-only task
-> small scoped patch
-> Git operations only after explicit human approval
```

## Safety model

The default safety model is conservative:

- human maintainers define scope,
- Worker AI reads only what is needed,
- sensitive data is blocked by default,
- risky operations require explanation and approval,
- Git write operations are separate from file edit approval,
- work stops for human review.

## Non-goals

This release does not provide:

- autonomous repository control,
- unattended commits,
- unrestricted agent execution,
- replacement of human maintainers.

## Before final release

Open follow-up tasks:

- review all templates for consistency,
- add tool-specific notes for Codex,
- add tool-specific notes for Antigravity CLI,
- add a small bugfix workflow example.
