# Blockers & Stoppers

Use `blocked` whenever continuing would require assumption, scope expansion, missing evidence, or unauthorized action.

## Stopper Types

| Stopper | When |
|---------|------|
| **Authorization** | A required read, write, command, or action is not explicitly authorized |
| **Scope** | Work would touch forbidden files or areas outside the active slice |
| **Evidence** | Work would rely on missing, stale, or ambiguous evidence |
| **Identity** | Ownership of names, routes, storage, or configuration is ambiguous |
| **Safety** | Rollback, compatibility, or destructive potential is unclear |
| **Context** | Prior context cannot prove current authorization or scope |

## Handling Rules

1. Report the smallest missing decision, evidence, or authorization
2. Do NOT broaden scope to resolve a stopper
3. Do NOT infer authorization from previous work
4. Do NOT let the worker who raised a stopper clear it
5. Clear a stopper only through orchestrator review or explicit authorization
6. If an action is ambiguous, it is NOT allowed

## Anti-Patterns

- Editing outside the allowed write set to avoid a blocked report
- Running unlisted commands to collect evidence
- Mixing unrelated concerns in one slice
- Reporting `pass` when evidence is insufficient
- Expanding scope silently to work around a blocker
