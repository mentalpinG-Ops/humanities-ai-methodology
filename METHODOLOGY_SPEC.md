---
status: current
last_changed: 2026-06-17
---

# Methodology Specification — the protocol stack

This document specifies the methodology's protocol stack: the seven protocols under `protocols/`, how they layer, the sections each one declares, and the rules for composing them. It is the structural companion to [`README.md`](README.md) (statement, motivation, status) and [`GOVERNANCE.md`](GOVERNANCE.md) (versioning, document classes).

## 1. The seven protocols

| Protocol | File | Layer | Covers |
|---|---|---|---|
| Source | [`protocols/source-protocol.md`](protocols/source-protocol.md) | pipeline (intake) | source intake: *Snippets ≠ Primary*, *Secondary ≠ Primary*, *Search-Absence ≠ Proof-of-Absence* |
| Interpretive-Frame | [`protocols/interpretive-frame-protocol.md`](protocols/interpretive-frame-protocol.md) | pipeline (coding) | the analytical coding step: *Lexicon Stability Across Stage Transitions*, *Frame Plurality Check* |
| Writing | [`protocols/writing-protocol.md`](protocols/writing-protocol.md) | pipeline (composition) | composition: *Composition Drift*, *Descriptive Accuracy* |
| Actant Self-Check | [`protocols/actant-self-check.md`](protocols/actant-self-check.md) | pipeline (voice) | author positionality: *Verb Audit*, *Addressee Audit*, *Discrediting-Frame Inoculation* |
| Tool | [`protocols/tool-protocol.md`](protocols/tool-protocol.md) | infrastructure (upstream) | tool fidelity: *Encoding Fidelity*, *Read Fidelity*, *Pre-Production Tool Validation* |
| Falsification | [`protocols/falsification-protocol.md`](protocols/falsification-protocol.md) | meta (validity axis) | claim-status: *Demarcation at the Claim Level*, *Methodology as Pile-Driver Work*, *Test Mode over Defense Mode* (+ seven operational tests) |
| Provenance | [`protocols/provenance-protocol.md`](protocols/provenance-protocol.md) | meta (provenance axis) | human-vs-AI provenance: *Provenance Marking at Introduction-Time*, *Audit-Trail Across Project-Span*, *Learning-Progress Verifiability* |

## 2. How the layers relate

The seven protocols are **orthogonal layers**, not a single sequence:

- **Infrastructure-upstream — Tool.** Tool fidelity sits beneath the others: a source "verified" through a tool that silently re-encoded it is not verified. Tool failures invalidate the work of every other protocol, so it is checked first.
- **Pipeline (sequential) — Source → Interpretive-Frame → Writing → Actant Self-Check.** These run along the source-to-publication chain: intake, then the coding step, then composition, then the author's positional voice.
- **Meta (across all of the above) — Falsification and Provenance.** Two audit axes over the whole methodology: Falsification asks *"could this be wrong?"* (validity); Provenance asks *"where did this come from?"* (origin). They are complementary, not redundant.

## 3. Per-protocol required sections

Each protocol declares, in order:

1. **Position** — what gap the protocol addresses and why the existing protocols do not cover it.
2. **The Patterns** (or **Audits**) — the two or three named, rule-bearing patterns, each with **Rule / Why / How to apply**.
3. **Operationalisation in the Workflow** — where the protocol acts across a working session.
4. **Failure-Mode Gallery** — the documented failures the protocol was lifted from (grounded, not prophylactic).
5. **What This Protocol Does Not Provide** — explicit scope limits, with cross-references to the protocols that cover the adjacent surface.
6. **Cross-Refs** — Markdown links to the related protocols.

A protocol also carries the four-field frontmatter (`name`, `version`, `status`, `last_changed`) per [`GOVERNANCE.md`](GOVERNANCE.md).

## 4. Composition rules

- **Tool first.** Validate tool fidelity before relying on any pipeline protocol's output.
- **Pipeline in order.** A downstream protocol assumes the upstream ones have run: Writing assumes Source; Interpretive-Frame sits between them; Actant Self-Check audits the voice once content exists.
- **Meta over the whole.** Falsification and Provenance apply to every load-bearing claim and every methodological commitment, including additions to the methodology itself. A new protocol is admissible only if it increases what the methodology forbids (the falsification protocol's auxiliary-hypothesis test).
- **Scope honestly.** Each protocol's *What This Protocol Does Not Provide* section is binding: do not stretch a protocol past its declared surface; reach for the adjacent protocol instead.

## 5. Adding a protocol

A new protocol enters via [`CONTRIBUTING.md`](CONTRIBUTING.md): a file in `protocols/`, the six required sections, four-field frontmatter, Markdown cross-references, an entry in this spec's table (§1) and in `README.md` §7, and a `CHANGELOG.md` entry. A structural change of this kind is also recorded in `decisions/`.
