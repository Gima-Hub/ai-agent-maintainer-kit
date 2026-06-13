# AI Agent Maintainer Kit

Reusable templates and safety rules for open-source maintainers working with AI coding agents.

## What this is

AI Agent Maintainer Kit is an early-stage open-source template kit for maintainers who want to delegate limited repository tasks to AI coding agents while keeping human control.

It provides reusable Markdown templates for defining:

- what an AI worker may and may not do,
- how a human maintainer approves risky actions,
- how to protect sensitive files and private data,
- when Git operations are allowed,
- how AI workers should plan, report, and stop for review.

The goal is not to replace maintainers. The goal is to make AI-assisted maintenance safer, more reviewable, and easier to reproduce.

## Why this matters

AI coding agents are becoming common in open-source work, but many maintainers still face practical risks:

- agents may edit files outside the intended scope,
- agents may expose private data or logs,
- agents may run commands without clear explanation,
- maintainers may lose track of what was changed and why,
- Git operations may happen before human review.

This project helps maintainers set clear boundaries before delegating work to tools such as Codex, Antigravity CLI, Gemini CLI, Claude Code, or other AI coding agents.

## Who this is for

This kit is intended for:

- individual OSS maintainers,
- small open-source teams,
- projects experimenting with AI coding agents,
- maintainers who want documentation-only, read-only, or small bugfix workflows with explicit human approval.

## Current status

This project is early-stage and actively maintained.

The first goal is to publish a practical v0.1.0 template set for safe AI-worker usage in small open-source repositories.

## Planned template areas

- Worker rules
- Active task tracking
- Human approval rules
- Git operation policy
- Sensitive data policy
- Plan template
- Report template
- Review template
- Example workflows

## Safety model

The default safety model is conservative:

1. Human maintainers define the task and allowed scope.
2. AI workers read only what is needed.
3. AI workers explain risky actions before asking for approval.
4. Git write operations require explicit human permission.
5. Sensitive data is never displayed or copied into reports.
6. Work stops after the report until a human reviews it.

## Quick start

This repository is still being initialized. The intended usage will be:

1. Copy the templates into your repository.
2. Fill in your project-specific allowed scope and blocked scope.
3. Start with read-only or documentation-only tasks.
4. Require human approval before file edits, Git staging, commits, or pushes.
5. Keep reports and reviews in version control.

## Relationship to AIriProject

This project was inspired by recovery-first AI-assisted development practices explored in AIriProject. It is intentionally separated as a smaller, reusable template kit for other maintainers.

## Non-goals

This project does not provide autonomous repository control.

It does not encourage fully automated write access, unattended commits, or unrestricted agent execution.

It is designed for human-supervised maintenance workflows.

## License

MIT License.
