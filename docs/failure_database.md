# Failure Database

This document records historical failure patterns from distributed sync systems.

## FD-001: Metadata and filesystem divergence

Problem:

Metadata says a file is complete but filesystem write was interrupted.

Prevention:

- temporary files
- fsync before commit
- atomic rename
- transactional metadata update

Test:

Simulate process termination during transfer.

---

## FD-002: Concurrent edits

Problem:

Multiple peers modify the same logical file.

Prevention:

- version tracking
- conflict detection
- deterministic resolution

Test:

Two peers modify offline and reconnect.

---

## FD-003: Network interruption

Problem:

Connection disappears during synchronization.

Prevention:

- resumable transfer
- persistent task state
- idempotent operations

Test:

Drop network during every transfer phase.
