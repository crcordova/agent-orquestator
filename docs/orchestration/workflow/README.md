# Workflow Principles

Portable orchestration is a staged, evidence-led workflow for scoped work. It favors explicit authorization, small units of work, durable records, and neutral review.

## Principles

- **Security first**: do not read, write, run, or close anything unless explicitly authorized
- **Small slices**: define the next smallest verifiable unit of work
- **One owner**: one accountable owner per slice
- **Explicit boundaries**: list allowed reads, writes, commands, forbidden areas, and stop rules before execution
- **Evidence before advancement**: do not mark work complete without current evidence matching the scope
- **No ambient authorization**: prior work does not grant current permission
- **No hidden scope expansion**: when more scope is needed, stop with `blocked`
- **Durable records**: preserve accepted decisions and evidence in slice records
- **Portable core**: define work in terms of roles, evidence, and boundaries — not specific tools or models

## Policy Docs

| Doc | Governs |
|-----|---------|
| [Slice Lifecycle](slice-lifecycle.md) | Lifecycle states and advancement |
| [Delegation Protocol](delegation-protocol.md) | Brief structure and scope rules |
| [Evidence & Verification](evidence-and-verification.md) | Evidence standards |
| [Blockers & Stoppers](blockers-and-stoppers.md) | Stopper taxonomy and handling |
| [Closure Protocol](closure-protocol.md) | Closure requirements and cleanup |
| [Parallelism Policy](parallelism-policy.md) | When parallel work is allowed |
| [Context Budgeting](context-budgeting.md) | Read strategy and compaction |
