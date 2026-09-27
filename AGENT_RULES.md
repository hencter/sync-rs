# Agent Development Rules

The local coding agent must follow these rules.

## Workflow

Never implement directly from a feature request.

Required flow:

1. Read architecture documents
2. Create implementation plan
3. Create tests first
4. Implement smallest working change
5. Run tests
6. Review against failure database
7. Commit

## Required Checks

Every subsystem change must consider:

- crash recovery
- concurrent execution
- network interruption
- corrupted state
- large scale performance

## Rust Rules

Prefer:

- explicit enums for state machines
- immutable data structures where possible
- small modules
- property tests for synchronization logic

Avoid:

- hidden global state
- implicit retries
- non-atomic filesystem updates
- untested recovery paths

## Commit Format

```
area: short description

reason
implementation
verification
```
