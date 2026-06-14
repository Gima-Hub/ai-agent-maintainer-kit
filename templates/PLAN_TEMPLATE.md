# Plan Template

Use this template before allowing a Worker AI to make changes.

## 1. Purpose

Describe the goal of this task.

```text
TBD
```

## 2. Background

Explain why this task is needed.

```text
TBD
```

## 3. Allowed scope

List files, directories, or actions the Worker AI may use.

```text
- TBD
```

## 4. Blocked scope

List files, directories, or actions the Worker AI must not use.

```text
- secrets
- private data
- unrelated files
- Git write operations unless explicitly approved
```

## 5. Proposed steps

1. Read the relevant files.
2. Summarize current state.
3. Make only approved changes.
4. Review changed files.
5. Report results.
6. Stop for human review.

## 6. Risk level

Choose one:

```text
LOW / MEDIUM / HIGH
```

## 7. Approval needed

Describe what human approval is required before work starts.

```text
TBD
```

## 8. Expected output

Describe the expected final report or file changes.

```text
TBD
```

## 9. Stop condition

The Worker AI must stop when:

- the requested plan is complete,
- the requested patch is complete,
- unexpected files would need to be touched,
- sensitive data is encountered,
- the task scope becomes unclear.
