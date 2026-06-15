# Slice Lifecycle

A slice is one narrow unit of work with one accountable owner, explicit boundaries, evidence requirements, and stop rules.

## States

### 1. Intake
- Read only authorized state
- Confirm purpose, exclusions, and current authorization
- Identify the next action: discovery, planning, implementation, verification, audit, or closure

### 2. Definition
- Define one objective
- Assign one owner role (coder, designer, reviewer)
- State allowed reads, writes, commands, forbidden areas, non-goals, evidence requirements, and stoppers
- Parallel work allowed only when independent and read-only

### 3. Execution
- Complete only the assigned scope
- Report new risks rather than absorbing them silently
- Stop with `blocked` if broader scope, missing authorization, or ambiguous ownership appears

### 4. Verification
- Run only authorized verification commands
- Record exact commands and outcomes
- Distinguish environment failures from product failures
- Record skipped verification and why

### 5. Review
- Check authorization, scope, evidence quality, stopper handling, and closure readiness
- Do not implement fixes during review
- Do not expand scope to clear a blocker

### 6. Closure
- Close only when all reports are received, blockers resolved, and evidence is sufficient
- Record accepted decisions in durable slice records (`docs/orchestration/slices/`)

## Advancement Rule

A slice advances only when current evidence is sufficient for the next state. If evidence is missing, stale, or outside authorization, the slice is `blocked`.
