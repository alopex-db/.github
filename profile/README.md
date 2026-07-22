# Alopex DB 🦊

**Silent. Adaptive. Unbreakable.**

The unified database engine that scales from a single embedded file to a globally distributed cluster — native SQL, Vector Search (HNSW), and columnar storage in one Rust-based engine.

📚 **Documentation**: <https://alopex-db.github.io>

## The Alopex Family

| Repository | What it is | Latest |
| --- | --- | --- |
| [**alopex**](https://github.com/alopex-db/alopex) | The unified database engine — SQL + Vector (HNSW) + columnar, embedded → cluster. Ships CLI binaries and Python wheels with every release | ![crates.io](https://img.shields.io/crates/v/alopex-core.svg) |
| [**alopex-skulk**](https://github.com/alopex-db/alopex-skulk) | Time-series database built on Alopex Core — Gorilla compression, automatic TTL/downsampling, PromQL & SQL-TS queries | ![crates.io](https://img.shields.io/crates/v/alopex-skulk.svg) |
| [**alopex-chirps**](https://github.com/alopex-db/alopex-chirps) | Lightweight gossip & messaging mesh on UDP/QUIC — the control plane for distributed Alopex | ![crates.io](https://img.shields.io/crates/v/alopex-chirps.svg) |
| [**alopex-db.github.io**](https://github.com/alopex-db/alopex-db.github.io) | The documentation site | — |

**One core, two databases**: Alopex DB for long-lived data (RAG/AI, knowledge bases, OLTP) and Alopex Skulk for streaming time-series data (monitoring, IoT, logs) — both built on the same WAL / MemTable / compaction foundation.

## Install

```bash
# Rust
cargo add alopex-embedded alopex-sql

# Python
pip install alopex

# Time-series
cargo add alopex-skulk
```

Prebuilt CLI binaries for Linux / macOS / Windows are attached to every [release](https://github.com/alopex-db/alopex/releases).

## Support

- ❤️ GitHub Sponsors: <https://github.com/sponsors/asopitech>
- ☕ Buy Me a Coffee: <https://buymeacoffee.com/asopitechia>
