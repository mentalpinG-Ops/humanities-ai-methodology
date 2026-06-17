---
status: living
---

# CLAUDE.md — humanities-ai-methodology

This file provides context for Claude (and other AI assistants) working in this repository.

## Repository Purpose

`humanities-ai-methodology` develops an **AI-agnostic methodology** for humanities students and scholars working with AI tools toward responsible, publishable outcomes. It holds the methodology itself: an abstract, tool-portable stack of composable **protocols** under `protocols/`. Each protocol is promoted here from documented practice after empirical grounding — not authored in isolation. This repository documents no running system.

**License:** dual-licensed — Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) by default, with a Commercial Licence by arrangement. See [`LICENSE`](LICENSE) and [`LICENSE-COMMERCIAL.md`](LICENSE-COMMERCIAL.md).

## Material Boundaries

**Hard rule — no exceptions:**

- No employer, client, or institution material (notes, data, outputs, files, artefacts) may ever enter this repository in any form.
- Methodological insights or distilled generalisations from professional contexts may inform the protocols, but must be fully de-identified and generalised before inclusion.
- No employer, institution, city, or person may be named in any public file, commit, issue, or PR.
- This rule applies to all professional contexts — current and future employers or clients alike.

When assisting in this repository, do not include, suggest, or infer any employer- or client-specific content, even if provided as context.

## Operational Concerns Live Outside This Repo

This public repository carries its own **public decision-records** (`decisions/`) for design decisions about the methodology itself. What stays *out*:

- Session logs, transcript audits, usage tracking, and cross-project operational decision-records that reference private working context (session identifiers, project-internal material, the maintainer's other projects) live in the maintainer's **private workspace**, not here. They cannot be published; the public `decisions/` records the methodology-facing rationale without that context.
- The canonical practice documentation (private — the empirical anchor protocols are promoted from) and the maintainer's private working context live outside this repository.

Keep this repository focused on the methodology: the protocol stack and its public governance. Protocols are promoted here after empirical grounding, not authored in isolation.

## Repository Structure

- `protocols/` — the methodology protocol stack (seven modules; see `METHODOLOGY_SPEC.md`)
- `METHODOLOGY_SPEC.md` — the protocol stack: orthogonal layers, per-protocol required sections, composition rules
- `GOVERNANCE.md` — versioning, status pipeline, document classes, material boundaries
- `decisions/` — public decision-records for the methodology's design (e.g. the protocol-naming decision)
- `CONTRIBUTING.md` — contribution guidelines
- `CHANGELOG.md` — release notes (Keep a Changelog format)
- `README.md` — statement, motivation, two-repo architecture, status, license

## Protocols and Versioning

Each protocol in `protocols/` carries a four-field YAML frontmatter block:

```
---
name: Source Protocol         # human-readable display name
version: 0.1.0                # semver; 0.x while working-draft
status: draft                # draft / current / stable / deprecated
last_changed: 2026-06-17     # ISO date; bump on every meaningful edit
---
```

When editing a protocol, bump `version` per the patch/minor/major rules in [`GOVERNANCE.md`](GOVERNANCE.md), update `last_changed`, and add an entry to [`CHANGELOG.md`](CHANGELOG.md) under `[Unreleased]`.

## License and Dual Use

- All content is licensed under **CC BY-SA 4.0** by default; a **Commercial Licence** is available by arrangement (it waives the ShareAlike obligation). See [`LICENSE-COMMERCIAL.md`](LICENSE-COMMERCIAL.md).
- Practitioner (in-house / employer) use of CC BY-SA 4.0 material is permissible without dual licensing.
- Attribution is required for derivative works; CC BY-SA derivatives must be shared under the same license.
