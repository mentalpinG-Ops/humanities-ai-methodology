---
status: living
---

# Contributing to humanities-ai-methodology

Thank you for your interest in contributing. Please read this document before opening a pull request or issue.

## License

All contributions to this repository are made under **Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**. By submitting a contribution, you agree to license your work under the same terms. See [`LICENSE`](LICENSE) for the full text. A separate Commercial Licence is available by arrangement (see [`LICENSE-COMMERCIAL.md`](LICENSE-COMMERCIAL.md)).

## Material Boundaries — Employer and Client Content

**This is a hard rule with no exceptions:**

- No employer, client, or institution material (notes, data, outputs, files, artefacts) may ever enter this repository in any form.
- Methodological insights or distilled generalisations derived from professional contexts may inform the protocols, but must be fully de-identified and generalised before inclusion. No specific cases, clients, employers, institutions, cities, or persons may be named in any public file, commit, issue, or PR.
- This rule applies to all professional contexts — current and future employers or clients alike.

If in doubt, do not include it. Generalise first, then contribute.

## How to Contribute

1. Fork the repository and create a feature branch.
2. For a **new protocol**:
   - Create a Markdown file in `protocols/`, named `<topic>-protocol.md` (or keep an established name where the suffix would be redundant, as `actant-self-check.md` does).
   - Follow the existing protocol structure: **Position → The Patterns (or Audits) → Operationalisation → Failure-Mode Gallery → What This Protocol Does Not Provide → Cross-Refs**.
   - Add the four-field **frontmatter** at the top (`name`, `version`, `status`, `last_changed`). See the *Versioning* section in [`GOVERNANCE.md`](GOVERNANCE.md).
   - Cross-reference the related protocols with standard Markdown links (`[text](other-protocol.md)`), and add the protocol to the module list in [`README.md`](README.md) §7 and to the table in [`METHODOLOGY_SPEC.md`](METHODOLOGY_SPEC.md).
3. For **edits to an existing protocol**:
   - **Bump the file's `version`** per the patch/minor/major rules in `GOVERNANCE.md`, and update `last_changed` to the current date.
4. For a **design decision** about the methodology (a rename, a new layer, a scope change): add a numbered record in `decisions/` (see [`decisions/0001-discipline-to-protocol-rename.md`](decisions/0001-discipline-to-protocol-rename.md) for the format).
5. Open a pull request with a clear description of the change and its rationale, and add a `CHANGELOG.md` entry under `[Unreleased]`.

## Versioning

All protocols carry four-field semantic-version frontmatter (`name`, `version`, `status`, `last_changed`). The rules for bumping them are documented in the *Versioning* section of [`GOVERNANCE.md`](GOVERNANCE.md). When in doubt, that document is authoritative.

## Attribution

When deriving work from this repository, you must provide appropriate credit (author / repository), a link to the license, and indicate if changes were made. Derivatives must be shared under the same license (CC BY-SA 4.0).
