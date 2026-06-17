---
status: living
---

# Copilot Instructions — humanities-ai-methodology

## Purpose

This repository (`humanities-ai-methodology`) develops an AI-agnostic methodology for humanities students and scholars working with AI tools toward responsible, publishable outcomes. It holds the **Level-I Methodology**: a stack of composable **protocols** under `protocols/`. It is dual-licensed (**CC BY-SA 4.0** by default; Commercial by arrangement).

## Material Boundaries

**Hard rule — no exceptions:**

- No employer, client, or institution material (notes, data, outputs, files, artefacts) may ever enter this repository in any form.
- Methodological insights or distilled generalisations from professional contexts may inform the protocols but must be fully de-identified and generalised before inclusion.
- No employer, institution, city, or person may be named in any public file, commit, issue, or PR.
- This rule applies to all professional contexts — current and future employers or clients alike.

## Content Standards

- Each protocol in `protocols/` carries four-field YAML frontmatter (`name`, `version`, `status`, `last_changed`) at the top. See [`GOVERNANCE.md`](../GOVERNANCE.md) §Versioning.
- Protocol structure: **Position → Patterns/Audits → Operationalisation → Failure-Mode Gallery → What This Protocol Does Not Provide → Cross-Refs**. See [`METHODOLOGY_SPEC.md`](../METHODOLOGY_SPEC.md).
- Cross-reference protocols with standard Markdown links (`[text](other-protocol.md)`), not `[[wiki]]` syntax.
- When editing a protocol, bump its `version` and update `last_changed`, then add a `CHANGELOG.md` entry under `[Unreleased]`.
- Record methodology-design decisions (renames, new layers, scope changes) in `decisions/`.
- Do not add identifying information (names, institutions, locations) to any file.
- Maintain the existing register: grounded, failure-mode-anchored, scholarly.

## License and Attribution

- All content is licensed under CC BY-SA 4.0 (a Commercial Licence is available by arrangement).
- Attribution is required for derivative works; CC BY-SA derivatives must be shared under the same license.
