---
status: historical
last_changed: 2026-06-17
---

# 0001 — Rename: `-discipline` modules → `-protocol`; `intellectual-hygiene` → `provenance`

**Date:** 2026-06-17
**Status:** historical (a frozen account of the decision as taken)

## Context

The methodology's modules were originally named with a `-discipline` suffix (`source-discipline.md`, `writing-discipline.md`, …) under a `disciplines/` directory, with one module named `intellectual-hygiene-discipline.md`. Two naming problems were identified in review:

1. **`-discipline` as a uniform suffix reads as a calque.** The convention echoes the German *Disziplin* / *Quellendisziplin* more than idiomatic English module-naming. "Discipline" is a real English word for a rigorous practice, but as a repeated file-suffix it carried a Germanic register the methodology did not intend.
2. **`intellectual-hygiene` was both imprecise and off-register.** The module is about *provenance* — `[H]/[AI]/[AI+]/[H+AI]` markers, idea-genealogy across a project span, and learning-verification. "Provenance" names exactly that; "intellectual hygiene" named it obliquely.

## Decision

- Rename the directory `disciplines/` → `protocols/`.
- Rename the six `-discipline.md` modules to `-protocol.md`.
- Rename `intellectual-hygiene-discipline.md` → `provenance-protocol.md`, and replace the term *intellectual hygiene* with *provenance* throughout.
- `actant-self-check.md` keeps its name (it never carried the `-discipline` suffix); only its path moved into `protocols/`.
- Convert the modules' internal `[[wiki-style]]` cross-references to standard Markdown links (`[text](other-protocol.md)`) so they render on GitHub.

The renames were performed with `git mv`, preserving file history.

## Consequences

- Public-facing terminology is now consistent: titles, prose, cross-references, the `README.md` §7 module list, and `METHODOLOGY_SPEC.md` all read *protocol* / *provenance*.
- External references in the maintainer's private working context were updated in the same change; frozen historical records (dated logs, snapshot builds, prior decision-records) were **left unchanged**, since rewriting them would falsify the record of what the names were when those records were written.
- This is the first record in the repository's own public `decisions/` log. Going forward, methodology-design decisions are recorded here rather than only in the maintainer's private workspace.

## Falsifier

This naming would be revisited if *protocol* proved to collide with a more established sense in the target literature in a way that misleads humanities readers (e.g. a network- or clinical-protocol reading), or if external read-tests showed *provenance* being consistently misread against its archival / source-criticism sense. No such evidence existed at the time of the decision.
