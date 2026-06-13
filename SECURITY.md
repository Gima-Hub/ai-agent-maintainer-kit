# Security Policy

AI Agent Maintainer Kit is a documentation and template project for safer AI-assisted repository maintenance.

## Supported versions

This project is currently pre-1.0. Security-related improvements are handled on the main branch until the first stable release process is defined.

## Sensitive data policy

Do not include private or sensitive data in issues, pull requests, examples, prompts, reports, or templates.

Examples of sensitive data include:

- API keys and tokens,
- `.env` files,
- private logs,
- databases,
- CSV exports with real personal or business data,
- screenshots containing private information,
- images, videos, or OCR cache files from private workflows,
- internal repository paths that reveal private system details.

## Reporting a security issue

If you find a security concern in these templates, please open a GitHub issue if it can be discussed publicly without exposing sensitive details.

If the issue includes sensitive information, do not post the details publicly. Contact the maintainer through GitHub profile information or another private channel first.

## Security philosophy

The default policy is conservative:

- avoid unrestricted AI access,
- require human approval for risky operations,
- keep sensitive data out of reports,
- prefer read-only or documentation-only tasks when starting with a new AI worker,
- require explicit permission before Git staging, commits, pushes, file deletion, or file moves.
