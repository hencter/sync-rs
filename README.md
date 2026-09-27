# sync-rs

A Rust-native distributed file synchronization system inspired by Syncthing.

## Goal

Build a reliable, secure, peer-to-peer synchronization daemon with an AI-assisted engineering workflow.

## Design Principles

- Crash safety before performance
- Explicit state machines instead of implicit state
- Event-driven indexing instead of repeated full scans
- Reproducible failures through chaos testing
- Documentation-driven agent development

## Development Model

Each feature follows:

```
DESIGN -> TASK -> IMPLEMENT -> TEST -> REVIEW -> MERGE
```

See `AGENT_RULES.md` and `ARCHITECTURE.md`.
