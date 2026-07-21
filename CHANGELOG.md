# Changelog

All notable changes to this methodology are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html) per the rules in [`GOVERNANCE.md`](GOVERNANCE.md).

## [Unreleased]

### Added

- **Falsification Protocol 0.2.0 — Pattern 2.4 *Instrument Validation and Test-Material Design*** (+ OT-8/9/10, two failure-mode gallery entries): pre-registered instrument validation with a hypothesis-independent reference key ("the prediction table is not the reference key"), minimal-pair gates for property toggles, material difficulty as a declared and varied design variable, pre-registered consequence matrices. Promoted from a documented test family in the maintainer's practice corpus (July 2026) in which a clean null finding was overturned by varying only the material difficulty.
- **Tool Protocol 0.2.0 — Pattern 2.4 *Declare vs. Enforce for Encoded Analytical Rules***: a tool may declare (mark, recommend) on the basis of untested encoded rules, but may enforce (block, reject) only rules that have passed a material test, per operationalisation; the evidence status travels in the tool's output; a shared evidence field is written by the test regime and read by the tool; applying is not testing. Promoted from a documented tool-governance decision (July 2026).
- **Interpretive-Frame Protocol 0.2.0 — Pattern 2.3 *Operation Declaration — the Smallest Auditable Unit***: auditable AI-assisted interpretation declares not only the framework but the specific analytical operation performed, including its non-deliverables. Promoted from the same practice corpus (July 2026).

## [0.1.0] — 2026-07-05

**First version freeze — tag `version-0.1`.** Certifies the seven original protocols (source, writing, tool, interpretive-frame, actant-self-check, falsification, provenance) after a stability window of no major edits since 2026-06-17. The eighth module (read-write-boundary) is present in this tree as `draft`; it is not part of the certified set and matures toward a later tag. Per [`GOVERNANCE.md`](GOVERNANCE.md) §Versioning, a version tag is a fixed reference point: it publishes nothing and changes no protocol's status.

### Changed

- **Governance corrected to the real two-repo architecture.** README §3 was rewritten from the obsolete three-tier framing (an in-repo "Level-II Practice" reference implementation + a never-finalised companion "runbooks" repository) to a two-layer model in plain, universal language: the methodology is distilled one-way from a separate, private practice repository, under the constitutive rule that no protocol enters without an empirical anchor in documented practice. `CONTRIBUTING.md` switched from an open-authoring model to a **curated-derivation** model (protocols are promoted, not authored here). Internal layer-numbering was removed from the public files. No protocol content changed.

- **Terminology rename: `-discipline` → `-protocol`; `intellectual-hygiene` → `provenance`.** The module directory `disciplines/` became `protocols/`; the six `-discipline.md` modules became `-protocol.md`; `intellectual-hygiene-discipline.md` became `provenance-protocol.md` (with *intellectual hygiene* → *provenance* throughout). `actant-self-check.md` kept its name (path moved only). All renames via `git mv` (history preserved). Internal `[[wiki]]` cross-references converted to standard Markdown links. The `README.md` §7 module list and prose, and all cross-references, were updated. Rationale recorded in [`decisions/0001-discipline-to-protocol-rename.md`](decisions/0001-discipline-to-protocol-rename.md). De-Germanises the module naming and names the provenance protocol for what it does.

### Added

- **Read-Write Boundary protocol (eighth module).** A meta-level protocol on a third audit axis (authority/currency, alongside falsification's validity and provenance's origin): every durable-artefact field is classed COMPUTED / MECHANICAL / HUMAN / EXTERNAL; automation may *invalidate* a human judgement (force re-decision) but never *author* one; a mechanically-derivable field maintained by hand is a drift bug. Promoted from a recurrent artefact-drift pattern — a recorded judgement outliving the premises it was decided under. Added to `protocols/`, the `METHODOLOGY_SPEC.md` §1 table and §2 layering, `README.md` §7, and the `CLAUDE.md` module count; recorded in [`decisions/0002-add-read-write-boundary-protocol.md`](decisions/0002-add-read-write-boundary-protocol.md).

- **Public governance.** The repository now carries its own public governance, mirroring the maintainer's `prompt-library` pattern: `GOVERNANCE.md` (versioning, status pipeline, a Document-Classes-and-Currency taxonomy, material boundaries), `CONTRIBUTING.md`, `CLAUDE.md`, and `.github/copilot-instructions.md` (all `status: living`); `METHODOLOGY_SPEC.md` (the protocol stack — layers, required sections, composition rules; `status: current`); this `CHANGELOG.md`; and a public `decisions/` log. Resolves the prior state in which the methodology's design-rationale lived only in the maintainer's private workspace.
- **Four-field frontmatter on every protocol** (`name`, `version`, `status`, `last_changed`) — each protocol stamped `version: 0.1.0`, `status: draft`, `last_changed: 2026-06-17`.
