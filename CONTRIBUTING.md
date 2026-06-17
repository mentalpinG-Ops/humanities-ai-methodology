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

Protocols are **not authored here.** Each one is *promoted* into this repository only after it has earned its place in documented practice — the constitutive rule: **no protocol enters the methodology without an empirical anchor in at least one real practice sequence.** Generalisation without a practical source is *methodology-from-imagination*, the failure mode this design exists to block. So this repository does **not** accept pull requests that add a new protocol directly.

External contributions are welcome in three forms:

1. **Report a gap** — open an issue describing a failure mode, blind spot, or use-case the current protocols miss. A well-grounded gap is candidate material for a future promotion.
2. **Offer a case study** — provide a **de-identified** reference case (a real working sequence, stripped of any employer/client/personal material per *Material Boundaries* above) that the maintainer can evaluate as promotion material.
3. **Propose a structure change** — a rename, a new layer, or a scope change, submitted as a numbered record in `decisions/` (see [`decisions/0001-discipline-to-protocol-rename.md`](decisions/0001-discipline-to-protocol-rename.md) for the format). Structure proposals are reviewed against the falsification protocol's auxiliary-hypothesis test: a new layer is admissible only if it increases what the methodology *forbids*.

For **edits to an existing protocol** (wording, a new pattern, a failure-mode entry): bump the file's `version` per the patch/minor/major rules in [`GOVERNANCE.md`](GOVERNANCE.md), update `last_changed`, open a pull request describing the change and its rationale, and add a `CHANGELOG.md` entry under `[Unreleased]`.

## Versioning

All protocols carry four-field semantic-version frontmatter (`name`, `version`, `status`, `last_changed`). The rules for bumping them are documented in the *Versioning* section of [`GOVERNANCE.md`](GOVERNANCE.md). When in doubt, that document is authoritative.

## Attribution

When deriving work from this repository, you must provide appropriate credit (author / repository), a link to the license, and indicate if changes were made. Derivatives must be shared under the same license (CC BY-SA 4.0).
