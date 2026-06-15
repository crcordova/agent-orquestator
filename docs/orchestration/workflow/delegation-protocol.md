# Delegation Protocol

Every delegated task must be scoped before execution. A brief is valid only when it contains enough boundary and evidence detail for the owner to complete the slice or return `blocked` without guessing.

## Required Brief Fields

| Field | Description |
|-------|-------------|
| **Role** | One capability class: coder, designer, or reviewer |
| **Objective** | One sentence describing the outcome |
| **Allowed reads** | Exact files/directories the owner may inspect |
| **Allowed writes** | Exact files the owner may modify, or `none` |
| **Allowed commands** | Exact commands the owner may run, or `none` |
| **Forbidden** | Paths, actions, or mutations outside scope |
| **Non-goals** | Adjacent work the owner must not perform |
| **Stop rules** | Conditions requiring a `blocked` report |
| **Evidence required** | Files read, files changed, commands run, verification, blockers |

## Scope Rules

- Allowed reads do NOT imply allowed writes
- Allowed writes do NOT imply access to sibling files
- Authorized commands do NOT imply formatting, cleanup, or version-control actions
- If a needed file, command, or action is not listed, the owner must stop and report `blocked`

## Report Format

```text
status: pass|blocked
summary: one sentence
findings:
- blocker, risk, evidence note, or none
files:
- path or none
```

## Example Brief

```
You are the Coder for slice "implement-auth-middleware".

Objective: Implement JWT authentication middleware for API routes.

Allowed reads:
- src/middleware/
- src/utils/
- package.json

Allowed writes:
- src/middleware/auth.ts
- src/utils/jwt.ts

Allowed commands:
- npm run typecheck

Forbidden:
- src/routes/ (do not modify routes)
- package.json (do not add dependencies)

Non-goals:
- Do not implement login/register endpoints
- Do not modify existing middleware

Stop rules:
- Stop if you need to add a dependency
- Stop if you need to modify files outside allowed writes
- Stop if JWT library behavior is unclear

Return format:
status: pass|blocked
summary: one sentence
findings:
- max 4 bullets
files:
- path or none
```
