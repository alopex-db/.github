# Contributing to Alopex

Thanks for considering a contribution. This file is the organization default:
if the repository you are working in has its own `CONTRIBUTING.md`, that one
wins.

## Where things live

| You want to | Go to |
|:--|:--|
| Use the engine, CLI, server, or Python package | [alopex](https://github.com/alopex-db/alopex) |
| Work on the time-series database | [alopex-skulk](https://github.com/alopex-db/alopex-skulk) |
| Work on the gossip / QUIC mesh | [alopex-chirps](https://github.com/alopex-db/alopex-chirps) |
| Work on Alopex Data UI | [alopex-ui](https://github.com/alopex-db/alopex-ui) |
| Fix or extend the documentation site | [alopex-db.github.io](https://github.com/alopex-db/alopex-db.github.io) |
| Read the docs | <https://alopex-db.github.io> |

Not sure which repository owns your issue? Open it anywhere in the
organization and say so — it will be moved.

## Before you open a pull request

1. **Open an issue first** for anything larger than a typo or an obvious bug
   fix. It is cheaper to agree on the approach than to rewrite a finished
   branch, and these projects have explicit capability boundaries that are
   easy to cross by accident.
2. **Check the roadmap.** <https://alopex-db.github.io/roadmap/> records what
   is complete, what is active, and what is deliberately frozen. Work against a
   frozen area will be asked to wait.
3. **Read the compatibility policy** if your change touches public API,
   on-disk format, the parser wire contract, or anything a user could pin:
   [reference compatibility development policy](https://github.com/alopex-db/alopex/blob/main/docs/reference-compatibility-development-policy.md).

## Working on the engine

```bash
git clone https://github.com/alopex-db/alopex
cd alopex
cargo test --workspace
cargo clippy --workspace --all-targets
cargo fmt --all
```

- Rust, stable toolchain. `cargo fmt` and a clean `clippy` are expected.
- Add tests with behavior changes. Storage, SQL semantics, and vector search
  are all areas where a regression is expensive and quiet.
- **One data directory, one process.** A directory opened by a running server
  cannot also be opened by the CLI or an embedded test. See
  [single-process-lock](https://github.com/alopex-db/alopex/blob/main/docs/single-process-lock.md).
- Performance claims need evidence produced by the published diagnostic
  contracts, not notebook timings.

## Commits and pull requests

- Imperative subject lines (`fix(sql): reject duplicate PRIMARY KEY`).
- One concern per pull request.
- Describe what you changed, why, and how you verified it. Include the commands
  you ran.
- Note any user-visible change so it can be written into the release notes and
  the compatibility section of the CHANGELOG.

## Reporting bugs

Open an issue in the repository involved, and include the version
(`alopex --version` or the crate version), the platform, the deployment mode
(embedded, server, or cluster), and the smallest reproduction you can manage.
Security issues are different — see [SECURITY.md](./SECURITY.md).

## Licensing

Contributions are accepted under the [Apache License 2.0](https://github.com/alopex-db/alopex/blob/main/LICENSE),
the same license the projects ship under.

## Supporting the work another way

Code is not the only contribution. Reporting a precise bug, improving a page of
documentation, or starring a repository all help. If you want to fund the
work directly, see [GitHub Sponsors](https://github.com/sponsors/asopitech).
