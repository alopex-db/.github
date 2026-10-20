<p align="center">
  <a href="https://alopex-db.github.io">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/alopex-db/alopex-db.github.io/main/docs/assets/images/brand/lockup-horizontal-dark-800.png">
      <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/alopex-db/alopex-db.github.io/main/docs/assets/images/brand/lockup-horizontal-light-800.png">
      <img alt="Alopex DB" src="https://raw.githubusercontent.com/alopex-db/alopex-db.github.io/main/docs/assets/images/brand/lockup-horizontal-light-800.png" width="420">
    </picture>
  </a>
</p>

<h3 align="center">Silent. Adaptive. Unbreakable.</h3>

<p align="center">
  <b>One Rust engine: SQL + vector search (HNSW) + columnar storage.</b><br>
  From a single embedded file to a distributed cluster — same data model, same API.
</p>

<p align="center">
  <a href="https://alopex-db.github.io">Documentation</a> &bull;
  <a href="https://alopex-db.github.io/getting-started/quickstart/">Quick Start</a> &bull;
  <a href="https://alopex-db.github.io/roadmap/">Roadmap</a> &bull;
  <a href="https://alopex-db.github.io/releases/">Releases</a> &bull;
  <a href="https://github.com/sponsors/asopitech">Sponsor</a>
</p>

<p align="center">
  <a href="https://github.com/alopex-db/alopex/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/alopex-db/alopex?sort=semver&label=release&color=1E3A5F"></a>
  <a href="https://crates.io/crates/alopex-embedded"><img alt="crates.io" src="https://img.shields.io/crates/v/alopex-embedded.svg?label=crates.io&color=5FB4C9"></a>
  <a href="https://pypi.org/project/alopex/"><img alt="PyPI" src="https://img.shields.io/pypi/v/alopex.svg?label=PyPI&color=5FB4C9"></a>
  <a href="https://github.com/alopex-db/alopex/blob/main/LICENSE"><img alt="License" src="https://img.shields.io/github/license/alopex-db/alopex?color=blue"></a>
  <a href="https://github.com/sponsors/asopitech"><img alt="Sponsor" src="https://img.shields.io/badge/sponsor-%E2%9D%A4-db61a2"></a>
</p>

---

## Start here

```bash
# Rust — embedded, like SQLite
cargo add alopex-embedded alopex-sql

# Python
pip install alopex

# Command line (TUI + batch)
cargo install alopex-cli
```

```sql
-- Vectors are a column type. Filter with SQL, rank by similarity, one transaction.
SELECT content, vector_similarity(embedding, ?) AS score
FROM knowledge_chunks
WHERE category = 'research'
ORDER BY score DESC
LIMIT 5;
```

**New here?** → [Quick Start](https://alopex-db.github.io/getting-started/quickstart/) ·
[SQL + Vector guide](https://alopex-db.github.io/guides/sql-vector/) ·
[Deployment modes](https://alopex-db.github.io/concepts/modes/)

## The family

One core, two databases, one mesh — plus the interface layer on top.

| Repository | What it is | Latest |
|:--|:--|:--|
| [**alopex**](https://github.com/alopex-db/alopex) | The unified engine — SQL + vector (HNSW) + columnar, embedded → cluster. Ships CLI binaries and Python wheels with every release | [![release](https://img.shields.io/github/v/release/alopex-db/alopex?sort=semver&label=%20)](https://github.com/alopex-db/alopex/releases/latest) |
| [**alopex-skulk**](https://github.com/alopex-db/alopex-skulk) | Time-series database on the same core — Parquet columnar, TTL and downsampling, embedded PromQL and SQL-TS ([docs](https://alopex-db.github.io/concepts/skulk/)) | [![crates.io](https://img.shields.io/crates/v/alopex-skulk.svg?label=%20)](https://crates.io/crates/alopex-skulk) |
| [**alopex-chirps**](https://github.com/alopex-db/alopex-chirps) | Gossip and messaging mesh over UDP/QUIC — the control plane for distributed Alopex ([docs](https://alopex-db.github.io/concepts/chirps/)) | [![crates.io](https://img.shields.io/crates/v/alopex-chirps.svg?label=%20)](https://crates.io/crates/alopex-chirps) |
| [**alopex-ui**](https://github.com/alopex-db/alopex-ui) | Alopex Data UI — one DataSource contract for forms, grids, charts, graphs, and maps ([concept site](https://alopex-db.github.io/alopex-ui-pages/)) | In development |
| [**alopex-db.github.io**](https://github.com/alopex-db/alopex-db.github.io) | The documentation site | — |

**Alopex DB** holds long-lived data you change — RAG and AI, knowledge bases,
OLTP. **Skulk** holds numeric series that arrive on a schedule — monitoring,
IoT, metrics. Both are built on the same WAL / MemTable / compaction foundation.

### Designed in the open

Two more members are published as designs, before the code is frozen — comments
still change them:

- **[Trail](https://alopex-db.github.io/concepts/trail/)** — logs, audit trails,
  and events. Write first; the schema binds when you read. New columns appear on
  arrival, and a type change does not stop ingestion at 3am.
- **[Alopex OTel](https://alopex-db.github.io/concepts/otel/)** — OpenTelemetry
  storage *and* dashboards as one product, from embedded to cluster. Speaks the
  Prometheus query API, so Grafana connects with no plugin.

## Project status

Pre-1.0 and under active development, published often, explicit about the edges.
The Rust crates and the Python package move as one aligned version; APIs can
still change between minor versions, so pin exact versions in production.
Distributed capability parity (v0.9) is deliberately frozen until the current
release train is published and verified — the
[roadmap](https://alopex-db.github.io/roadmap/) states what is complete, what is
active, and what is on hold.

## Beyond OSS: Alopex Enterprise

A commercial feature package built on the OSS foundation, currently **in
architecture design** — not a support tier, and not generally available:

- 🔒 **Security Suite** — storage and logical encryption, JWT / OIDC / RBAC identity, policy and classification
- 🔍 **Unified Query Model** — one engine for SQL / AQL / PromQL with enterprise search
- 📈 **Observe (SRE)** — SLO engine, error budgets, burn rates, automated actions
- ⚙️ **Infrastructure Packages** — distributed config store, service discovery, internal DNS

[Discuss an Enterprise use case](https://asopi.tech/en/services/alopex-enterprise) ·
[Get in touch](https://asopi.tech/contact)

## Community and support

- 🐛 **Bugs and feature requests** — the Issues of the repository involved; start from [SUPPORT](https://github.com/alopex-db/.github/blob/main/SUPPORT.md) if you are not sure which
- 📚 **Documentation** — <https://alopex-db.github.io>
- 🐦 **X** — [@asopitech_iot](https://x.com/asopitech_iot)
- 🌐 **Project overview** — <https://asopi.tech/services/alopex-db>
- ⭐ **Star [alopex](https://github.com/alopex-db/alopex)** — it is the single biggest thing that helps other engineers find the project

## Sponsor the work

Alopex is built in the open by [@asopitech](https://github.com/asopitech). GitHub
Sponsors funds continued development across Alopex DB, jv-lang, GraphRAG, and
related tools — and higher tiers let you follow the work before it is public.

| Tier | What you get |
|:--|:--|
| **$3 / month** | OSS Support — back ongoing development, updates, and releases |
| **$12 / month** | Early Access — experiments, design drafts, internal notes, and prototypes long before they are public |
| **$99 / month** | Enterprise-focused Early Access — pre-release capabilities aimed at security and deployment across the asopitech ecosystem |

Sponsorship is not an Alopex Enterprise license, SLA, or commercial support
contract; current benefits are defined on the Sponsors page.

<p align="center">
  <a href="https://github.com/sponsors/asopitech?metadata_source=alopex_org_profile&metadata_campaign=sponsor_early_access&metadata_content=org_profile_sponsor_section"><img alt="Sponsor @asopitech on GitHub Sponsors" src="https://img.shields.io/badge/GitHub%20Sponsors-%E2%9D%A4%20Sponsor%20%40asopitech-db61a2?logo=githubsponsors&logoColor=white&style=for-the-badge"></a>
  <a href="https://buymeacoffee.com/asopitechia"><img alt="Buy Me a Coffee" src="https://img.shields.io/badge/Buy%20Me%20a%20Coffee-%E2%98%95-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>
</p>

<p align="center">
  <sub>Apache-2.0 · Built with 🦀 Rust and ❤️ by the Alopex DB team · <a href="https://alopex-db.github.io">alopex-db.github.io</a></sub>
</p>
