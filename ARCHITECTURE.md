# sync-rs Architecture

## Overview

sync-rs is designed as a distributed state synchronization system, not a file copier.

Core layers:

```
Filesystem
    |
Watcher
    |
Event Journal
    |
State Index
    |
Sync Engine
    |
Transfer Engine
    |
Peer Network
```

## Core Modules

### sync-core

Contains:
- file state model
- version tracking
- conflict model
- synchronization decisions

### sync-storage

Requirements:
- crash recovery
- atomic updates
- durable event log
- transactional metadata

### sync-network

Requirements:
- authenticated peers
- encrypted transport
- explicit connection state machine

### sync-daemon

Long-running service process.

## Lessons from Syncthing History

Known classes of failures:

1. Index inconsistency
2. Interrupted file writes
3. Concurrent modification conflicts
4. Network state transitions
5. Large directory performance

Design must prevent these classes instead of patching symptoms.
