# Roadmap

This roadmap describes the initial direction for AI Agent Maintainer Kit.

The project is intentionally conservative. It focuses on human-supervised AI maintenance workflows, not autonomous repository control.

## v0.1.0 - Initial template kit

Goals:

- Publish the first reusable template set.
- Define the Worker AI role.
- Define human approval rules.
- Define sensitive data boundaries.
- Define basic Git operation policy.
- Provide read-only and documentation-only workflow examples.

Planned files:

- `templates/WORKER_RULES.md`
- `templates/ACTIVE_TASK.md`
- `templates/PLAN_TEMPLATE.md`
- `templates/REPORT_TEMPLATE.md`
- `templates/REVIEW_TEMPLATE.md`
- `templates/HUMAN_APPROVAL_RULES.md`
- `templates/GIT_OPERATION_POLICY.md`
- `templates/SENSITIVE_DATA_POLICY.md`
- `examples/read_only_inventory/`
- `examples/docs_only_task/`

## v0.2.0 - Practical maintainer workflows

Goals:

- Add a small bugfix workflow example.
- Add examples for issue triage and documentation maintenance.
- Add maintainer checklist templates.
- Add tool-specific notes for common AI coding agents.

Potential areas:

- Codex usage notes
- Antigravity CLI usage notes
- Gemini CLI usage notes
- Claude Code usage notes

## Future ideas

- Repository setup checklist.
- Pull request review workflow.
- Release preparation workflow.
- Policy examples for small teams.
- Optional validation scripts for checking template completeness.

## Non-goals

This project does not aim to create a fully autonomous agent runtime.

It does not provide unrestricted AI write access.

It does not replace human maintainers, code review, security review, or release ownership.
