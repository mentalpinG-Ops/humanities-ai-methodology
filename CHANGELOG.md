# Changelog

All notable changes to this methodology are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html) per the rules in [`GOVERNANCE.md`](GOVERNANCE.md).

## [Unreleased]

### Changed

- **Terminology rename: `-discipline` → `-protocol`; `intellectual-hygiene` → `provenance`.** The module directory `disciplines/` became `protocols/`; the six `-discipline.md` modules became `-protocol.md`; `intellectual-hygiene-discipline.md` became `provenance-protocol.md` (with *intellectual hygiene* → *provenance* throughout). `actant-self-check.md` kept its name (path moved only). All renames via `git mv` (history preserved). Internal `[[wiki]]` cross-references converted to standard Markdown links. The `README.md` §7 module list and prose, and all cross-references, were updated. Rationale recorded in [`decisions/0001-discipline-to-protocol-rename.md`](decisions/0001-discipline-to-protocol-rename.md). De-Germanises the module naming and names the provenance protocol for what it does.

### Added

- **Public governance.** The repository now carries its own public governance, mirroring the maintainer's `prompt-library` pattern: `GOVERNANCE.md` (versioning, status pipeline, a Document-Classes-and-Currency taxonomy, material boundaries), `CONTRIBUTING.md`, `CLAUDE.md`, and `.github/copilot-instructions.md` (all `status: living`); `METHODOLOGY_SPEC.md` (the protocol stack — layers, required sections, composition rules; `status: current`); this `CHANGELOG.md`; and a public `decisions/` log. Resolves the prior state in which the methodology's design-rationale lived only in the maintainer's private workspace.
- **Four-field frontmatter on every protocol** (`name`, `version`, `status`, `last_changed`) — each protocol stamped `version: 0.1.0`, `status: draft`, `last_changed: 2026-06-17`.
