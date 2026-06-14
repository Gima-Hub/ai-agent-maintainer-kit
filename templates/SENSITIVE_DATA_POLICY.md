# Sensitive Data Policy Template

Use this file to define what the Worker AI must avoid reading, copying, or exposing.

## Principle

The Worker AI should not access sensitive data unless the human maintainer explicitly approves it for a specific task.

Even when sensitive data is approved for inspection, it should not be copied into reports, issues, pull requests, prompts, or examples.

## Sensitive data examples

Treat the following as sensitive by default:

```text
.env files
API keys
tokens
private logs
databases
CSV exports with real user or business data
spreadsheets with private data
screenshots with private information
images and videos from private workflows
OCR cache files
configuration files containing credentials
local machine paths that reveal private context
```

## Default blocked paths

Project maintainers should list repository-specific blocked paths here.

```text
- .env
- .env.*
- secrets/
- private/
- data/private/
- logs/
- cache/
- *.db
- *.sqlite
- *.sqlite3
```

## Reporting rule

If the Worker AI encounters possible sensitive data, it should report only:

- file path,
- file type,
- risk category,
- recommended handling.

It must not print the sensitive content.

## Example safe report

```text
Potential sensitive file found:
Path: data/private/export.csv
Type: CSV export
Risk: may contain real user or business data
Recommendation: do not open or copy contents without explicit approval
```

## Example unsafe report

Do not paste real secrets, keys, database rows, account data, or private logs into a report.

## Human approval

A human maintainer may approve limited sensitive data inspection only when:

- the task cannot be completed otherwise,
- the exact file is named,
- the purpose is clear,
- the Worker AI is instructed not to copy raw contents,
- the report will summarize only risk and handling.
