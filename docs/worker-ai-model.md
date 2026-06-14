# Worker AI Model

This document explains the basic model used by AI Agent Maintainer Kit.

## Overview

A Worker AI is an AI coding agent that helps with limited repository maintenance tasks under human supervision.

Examples include:

- Codex,
- Antigravity CLI,
- Gemini CLI,
- Claude Code,
- other approved coding agents.

The name of the tool can change. The role stays the same: the Worker AI performs scoped work while the human maintainer keeps final control.

## Roles

### Human maintainer

The human maintainer is responsible for:

- deciding the goal,
- defining allowed scope,
- approving risky actions,
- reviewing changes,
- deciding whether to merge or release,
- protecting private data and project direction.

### Worker AI

The Worker AI may help with:

- repository inventory,
- documentation updates,
- issue triage support,
- small scoped patches,
- report writing,
- review preparation.

The Worker AI must follow repository-specific rules.

### Reviewer

The reviewer may be the maintainer, another human contributor, or another AI-assisted review step.

The reviewer checks whether the work stayed in scope and whether the output is safe to use.

## Basic workflow

1. The human maintainer defines a task.
2. The Worker AI prepares a plan or follows an approved plan.
3. The Worker AI performs only the allowed work.
4. The Worker AI reports what it read, changed, and did not do.
5. The human maintainer reviews the report and diff.
6. Git write operations happen only when explicitly approved.

## Why use this model

Without clear boundaries, AI coding agents may do too much, touch unrelated files, or expose sensitive data.

This model gives maintainers a repeatable way to start small:

- read-only first,
- documentation-only next,
- small scoped changes later,
- Git operations only after review.

## Tool-neutral design

This kit is not tied to one AI tool.

The same templates can be adapted for different agents by changing the current worker and allowed scope.

The important part is not the tool name. The important part is the boundary between human authority and AI execution.
