# Security Policy

## Supported versions

Alopex projects are pre-1.0 and move quickly. Security fixes land on the
**latest published release** of each project; there are no long-term support
branches yet.

| Project | Supported |
|:--|:--|
| [alopex](https://github.com/alopex-db/alopex) (engine, CLI, server, Python) | Latest release |
| [alopex-skulk](https://github.com/alopex-db/alopex-skulk) | Latest release |
| [alopex-chirps](https://github.com/alopex-db/alopex-chirps) | Latest release |

## Reporting a vulnerability

**Please do not open a public issue for a security problem.**

Report it privately through GitHub's
[security advisory form](https://github.com/alopex-db/alopex/security/advisories/new)
on the repository involved. If that is not available to you, contact us through
<https://asopi.tech/contact> and say that the message is a security report —
do not include exploit details in that first message.

Please include, as far as you can:

- the affected project and version,
- the deployment mode (embedded, single-node server, or cluster),
- what an attacker can do with it, and
- a reproduction, or the smallest description that lets us reproduce it.

## What to expect

- We aim to acknowledge a report within a few business days.
- We will tell you whether we consider it a vulnerability, and our planned fix
  and release path.
- We will credit you in the advisory unless you prefer otherwise.

Please give us a reasonable window to publish a fix before disclosing publicly.

## Scope notes

These are known, documented behaviors rather than vulnerabilities:

- A data directory can be opened by exactly one process. Pointing a second
  process at a running server's `data_dir` is rejected by design.
- Pre-1.0 APIs and on-disk formats change between releases; migration notes are
  in each release and in the CHANGELOG.
- Capability boundaries for distributed deployments are stated on the
  [roadmap](https://alopex-db.github.io/roadmap/). Using an unsupported
  combination is a limitation, not a security issue.
