---
status: living
---

# Governance — humanities-ai-methodology

This document is the single source for how this repository is versioned, how its documents declare their currency, and what content may enter it. (What may enter the *methodology* — which protocols, and how — is governed by the constitutive rule; see [`CONTRIBUTING.md`](CONTRIBUTING.md).)

## License

This repository is **dual-licensed**:

- **CC BY-SA 4.0** (default) — see [`LICENSE`](LICENSE) for the full text.
- **Commercial Licence** (by arrangement) — see [`LICENSE-COMMERCIAL.md`](LICENSE-COMMERCIAL.md) for terms.

### When each licence applies

| Use case | Applicable licence |
|---|---|
| Academic research and publication | CC BY-SA 4.0 |
| Personal or non-commercial projects | CC BY-SA 4.0 |
| Open-source projects (compatible licence) | CC BY-SA 4.0 |
| Practitioner / in-house employer use (no product distribution) | CC BY-SA 4.0 |
| Proprietary commercial products or services | **Commercial Licence required** |
| Any use where the ShareAlike obligation cannot be satisfied | **Commercial Licence required** |

The ShareAlike obligation is **waived** under the Commercial Licence. Attribution to the author and this repository is required under both licences.

---

## Versioning

Each protocol in `protocols/` carries a four-field YAML frontmatter block. Four fields are mandatory:

| Field | Meaning |
|---|---|
| `name` | Human-readable display name of the protocol. |
| `version` | Semantic version of the file itself (e.g. `0.1.0`). `0.x.y` while working-draft. |
| `status` | Lifecycle stage: `draft` / `current` / `stable` / `deprecated`. |
| `last_changed` | ISO date (`YYYY-MM-DD`) of the last meaningful edit. Bump on every commit that modifies the file. |

### Version-bump rules

- **Patch** (`0.1.0` → `0.1.1`) — wording clarification, typo fix. Scope unchanged.
- **Minor** (`0.1.0` → `0.2.0`) — additive change: a new pattern, expanded scope, a new failure-mode entry. Backwards-compatible.
- **Major** (`0.1.0` → `1.0.0`) — a pattern removed or reframed, the protocol's scope redrawn. Consumers may need to re-read.

### Status pipeline

```
   draft  →  current  →  stable
                            │
                            ↓
                        deprecated
```

- New protocols start as `draft` — grounded in documented failure modes but not yet externally tested.
- Promotion to `current` means in active methodological use and structurally settled.
- Promotion to `stable` requires external read-tests and a period without structural re-articulation (the maturity signals in [`README.md`](repos/humanities-ai-methodology/README.md) §7). A protocol may not be labelled `stable` without naming the conditions under which it would be revised — the status-vocabulary audit of [`protocols/falsification-protocol.md`](protocols/falsification-protocol.md).
- `deprecated` retires a protocol without removing it from history.

### Repository version tags

A repository-level git tag (`version-0.1`, `version-0.2`, …) freezes a named, immutable reference point for the stack as a whole:

- **What a tag certifies:** the set of protocols named in its annotation went through a stability window (no major edits for at least two weeks) before tagging. External references to the methodology should cite a tag, not the moving `main` branch.
- **What a tag does not do:** it publishes nothing, and it promotes no protocol's `status`. Distribution of any tagged state is a separate, deliberate act.
- **Scope:** a tag may certify fewer modules than the tree contains — modules added after the stability window opened stay outside the certified set and mature toward a later tag. The tag annotation names the certified set.

---

## Document Classes and Currency

Every document in this repository belongs to one of the classes below. Each class has a `status` vocabulary that states — in machine-readable frontmatter — whether the document is current. A reader or tool can always determine a document's standing from its `status` field plus this table.

| Class | Members | `status` values | Frontmatter |
|---|---|---|---|
| **Methodology** | the protocols (`protocols/`) | `draft` → `current` → `stable` → `deprecated` | four-field (`name`, `version`, `status`, `last_changed`) |
| **Specification** | `METHODOLOGY_SPEC.md` | `draft` → `current` → `stable` | `status`, `last_changed` |
| **Process** | maintained reference / process docs (none beyond the spec at present) | `current` (in force) · `draft` (proposed, not yet adopted) · `superseded` (overtaken — see the file's banner for the successor) | `status`, `last_changed` |
| **Archive** | frozen records: public decision-records (`decisions/`) and any frozen prior versions of living docs | `historical` (frozen event record) · `superseded` (frozen prior version — carries `superseded_by`) | `status`, `last_changed` (the record's own content date) |

For **Process** and **Archive** documents, `last_changed` records the date the *content* last changed, not the date a status label was applied — so the field answers "how current is this material?" honestly.

### Living documents (currency = git, not a stamp)

The repository's governance chrome is continuously maintained and authoritative as of `HEAD`; its currency is the git history, not a hand-maintained date. These carry `status: living` and **no** `last_changed`: `GOVERNANCE.md`, `CONTRIBUTING.md`, `CLAUDE.md`, `.github/copilot-instructions.md`.

Three kinds of file are exempt from frontmatter entirely, by their nature: `README.md` (the landing page), `CHANGELOG.md` (it dates every entry itself), and `LICENSE` / `LICENSE-COMMERCIAL.md` (static legal text). **This exempt list is complete** — any other document that carries no recognised `status` is a gap to be fixed, not an intentional omission.

---

## Decision Records

Design decisions about the methodology — a protocol rename, a new layer, a scope change — are recorded as numbered files in `decisions/` (e.g. [`decisions/0001-discipline-to-protocol-rename.md`](decisions/0001-discipline-to-protocol-rename.md)). These are **public** records: they explain *why* the methodology is shaped the way it is, so a reader or contributor does not have to reconstruct the rationale.

Operational and cross-project decision-records that depend on private working context (session identifiers, the maintainer's other projects, project-internal material) are **not** published here; they remain in the maintainer's private workspace. The public `decisions/` log records the methodology-facing rationale without that context. A decision record carries `status: historical` (a frozen account of a decision as taken) and its own `last_changed` content date.

---

## Material Boundaries — Employer and Client Content

**Hard rule — no exceptions:**

- No employer, client, or institution material (notes, data, outputs, files, artefacts) may ever enter this repository in any form.
- Methodological insights or distilled generalisations derived from professional contexts may inform the protocols, but must be fully de-identified and generalised before inclusion. No specific cases, clients, employers, institutions, cities, or persons may be named in any public file, commit, issue, or PR.
- This rule applies to all professional contexts — current and future employers or clients alike.

This boundary exists to protect privacy, prevent IP leakage, and maintain legal clarity. When in doubt, generalise first, then include.

---

## Reference

- The protocol stack: [`METHODOLOGY_SPEC.md`](METHODOLOGY_SPEC.md)
- Statement, motivation, two-repo architecture, status, license: [`README.md`](repos/humanities-ai-methodology/README.md)
- Contribution guidelines (incl. material boundaries): [`CONTRIBUTING.md`](CONTRIBUTING.md)
- AI assistant context: [`CLAUDE.md`](repos/humanities-ai-methodology/CLAUDE.md)
- Copilot instructions: [`.github/copilot-instructions.md`](.github/copilot-instructions.md)
