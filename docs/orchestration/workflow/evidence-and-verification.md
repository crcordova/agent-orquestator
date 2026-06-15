# Evidence & Verification

Evidence must be current, scoped, and reproducible. Verification passes only when evidence matches the assigned slice.

## Required Evidence

Every report must state:
- Files read, or `none`
- Files written, or `none`
- Commands run, or `none`
- Verification performed, or why verification was skipped
- Findings, risks, blockers, and residual limitations
- Next recommended action (when applicable)

## Verification Rules

- Run only commands explicitly authorized for the current slice
- Record exact command text and outcome
- Treat permission/environment failures separately from product failures
- Do not use prior slice evidence as current proof
- Use `blocked` when evidence is missing, stale, ambiguous, or outside scope

## Skipped Verification

Acceptable only when explicit. The report must state:
- What was not run
- Why it was not authorized or not applicable
- What residual risk remains

## Common Verification Commands

| Action | Command |
|--------|---------|
| Type check | `npm run typecheck` or `npx tsc --noEmit` |
| Lint | `npm run lint` |
| Tests | `npm test` or `npm run test` |
| Build | `npm run build` |
| Python lint | `ruff check .` or `flake8 .` |
| Python test | `pytest` or `python -m pytest` |
| Go build | `go build ./...` |
| Go test | `go test ./...` |

Always check the project's `package.json`, `Makefile`, or `pyproject.toml` for the correct commands.
