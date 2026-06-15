# Closure Protocol

Closure is the controlled end of a slice or phase. It requires reviewed evidence, blocker resolution, and durable records.

## Closure Requirements

Before closure:
- All assigned owners have returned machine-scannable reports
- Reports include files read, files written, commands run, verification, findings, and blockers
- Raised blockers are resolved by orchestrator review or explicit authorization
- Accepted decisions and evidence are recorded in durable slice records
- Verification has been performed or explicitly skipped with justification

## Durable Records

Before closing, record in `docs/orchestration/slices/`:
- Objective and scope
- Owner reports and accepted findings
- Files changed or confirmed unchanged
- Verification evidence and skipped verification
- Blockers, decisions, and residual risks
- Next recommended slice

## Cleanup Rules

- Do not delete evidence of blockers, authorization violations, or unresolved risks
- Historical agent output is evidence only, not authorization for future work
- Completed work may be closed after reports are read and recorded

## Naming Convention

Use dated records: `YYYY-MM-DD-slice-slug.md`
