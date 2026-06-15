# Context Budgeting

Context is a scoped resource. Load only the smallest authorized set of files needed for the current slice.

## Read Strategy

- Start from the active slice brief and durable records
- Prefer targeted reads over broad repository ingestion
- Split oversized work into smaller slices before execution
- Ask for or report the smallest missing read authorization instead of expanding scope
- Keep temporary notes concise

## Compaction & Handoff

After compaction or handoff between agents:
- Re-read only the smallest authorized sources needed
- Preserve slice boundaries rather than reconstructing broad history
- Name exact pending work, blockers, and required report format
- Record what is complete, what is not, and what authorization is missing
- Return `blocked` if current authorization cannot be proven

## Context Stopper

A context stopper exists when prior context cannot prove current authorization, scope, or evidence. Do not compensate by loading broad context unless explicitly authorized.
