# Parallelism Policy

Parallelism is allowed only when it preserves independent ownership, clear evidence, and non-overlapping scope.

## Allowed Parallel Work

- Independent read-only discovery with disjoint source sets
- Independent neutral reviews that do not edit files
- Separate implementation tasks with no file overlap and no data dependencies
- Tasks in different domains (frontend vs backend, styling vs logic)

## Disallowed Parallel Work

- Overlapping implementation writes
- Multiple owners modifying the same file
- Tasks that depend on unresolved identity, safety, or authorization questions
- Mixed ownership where one agent changes scope while another implements

## Coordination Rules

1. The orchestrator assigns parallel work and defines merge points
2. Each parallel owner reports evidence separately
3. File conflicts are prevented by explicit file assignment in each brief
4. When in doubt about overlap, run sequentially

## Phase Strategy

```
Phase 1: [independent tasks in parallel]
  ├── Slice 1.1 → Coder (files: A, B)
  └── Slice 1.2 → Designer (files: C, D)

Phase 2: [depends on Phase 1]
  └── Slice 2.1 → Coder (files: E, F)
```
