# Humanities-AI Methodology — Articulation Pass v0.5

*Working draft. Status: draft 2026-05-21. Language: EN per [ADR-0014](https://github.com/mentalpinG-Ops/humanities-ai-methodology) (local workspace artefact). Repo source-of-truth README. TBD markers are explicit and concern Strategic Open Questions S1 / S2 / S3 / S5, whose resolution is pending.*

---

## 1. Statement

**humanities-ai-methodology** is a meta-project developing an **AI-agnostic methodology** for **humanities students and humanities scholars** working with AI tools toward **responsible, publishable outcomes**. It transcends individual fields and specific AI tools; the methodology aims to be portable across AI generations.

Audience specification (early-career vs. established vs. mixed) pending S1.

## 2. Motivation

The trigger was not a theoretical need but an empirical diagnosis. During the publication of an analytical op-ed (case AX-006, Body-Worlds Wrocław, May 2026), *descriptive-accuracy* errors appeared that required manual post-publication correction. The methodological reconstruction yielded a finding: the disciplines that would have prevented such errors did exist fragmentarily in individual project checklists, but not as a coherent workflow. The question *"do we have a consistent workflow, or piecework?"* had to be answered with *piecework*.

From this emerged the reframing: **methodology is not a side effect of project work; it is a primary research object**. Concrete projects (Ideologiekritik, Studium, Rosenkranz, knowledge-representation, aXIOM) are ad-hoc test cases against which the methodology develops and is stress-tested — not its telos.

## 3. What is delivered

The methodology is delivered in **γ-shape**: two coupled layers.

- **β** — the abstract methodology, tool-portable. Describes what a humanities-scholar AI-working environment should contain: positionality, material boundaries, source discipline, memory discipline, attribution hygiene. Resides in **this repository (Repo A)** — private initially per [ADR-0013](https://github.com/mentalpinG-Ops/humanities-ai-methodology) (workspace), public-flip trigger TBD; intended licence CC BY-SA 4.0 on public flip; EN.

- **α** — a concrete reference implementation, Claude-Code-specific but architecturally portable: CLAUDE.md layering, auto-memory, workspace structure, skills, hooks. Demonstrates that β is implementable. Reference documentation lives in this repo; the running α is the working environment itself.

Project-internal material, project-specific runbooks, and research-internal notes live in **Repo B** (`humanities-ai-methodology-runbooks`, private always, DE), structurally separated from the publishable layer. This two-repo architecture makes the material boundary clean by construction. Repo B will be created on first project-convergence-sync trigger; it does not yet exist.

**Publication strategy** is *phased*: working draft (this repo + a companion blog format) without peer-review gate as the initial form; methodologically citable from day one. Escalation to peer review (a methods paper for β, a tools paper or workshop submission for α) when a maturity threshold is reached — maturity criteria pending S5.

## 4. Normative grounding *[TBD — S2]*

The normative grounding of *"responsible"* is not yet fixed. Candidates on the table:

- **Frankfurt School / Critical Theory** — consistent with the ideology-critical orientation of the op-ed work that triggered the meta-project.
- **Discourse ethics (Habermas)** — procedural; well-matched to a working-draft plus community-feedback mode.
- **Care ethics** — relational; fits the reader-audience relation.
- **Pragmatism (Dewey, Peirce)** — a hypothesis-test-revision cycle that is naturally compatible with phased publication.
- **Deliberate eclecticism** — methodological pluralism rather than single-tradition commitment.

Decision pending. Recursively coupled to the backlog question *"which methodology for the meta-project itself"* (LEAN vs. Action Research vs. TQM/PDCA vs. Pragmatist Inquiry vs. Reflective Practice). Both questions likely require joint resolution so that methodological consistency is preserved between norm and norm-development.

## 5. Position in existing literature *[TBD — S3]*

Positioning to be checked against:

- **Digital Humanities** (method reflection, tool critique, workflow documentation).
- **Critical Algorithm Studies** (AI as object of investigation, not only as tool).
- **AI Ethics** (responsible-AI discourse, disclosure standards).
- **Reflective Practice / Action Research** (self-documenting methodology development).
- **Methods Papers in Humanities Journals** (formal home in the publishing ecosystem).

Pending: a literature survey to determine whether established standards or best practices exist that the meta-project can be *extending*, *critiquing*, *complementing*, or *replacing*. Without this positioning, the contribution claim remains underspecified.

## 6. Case studies and skin in the game

The five active projects are test cases in which the methodology either holds up or produces failure modes:

- **Ideologiekritik** — op-ed pipeline and multimodal artefact analysis; AX-006 is the first empirical failure-to-methodology lift (pre-publication checklist as the first β-material).
- **Studium** — bibliography management and cross-disciplinary methods inventory.
- **Rosenkranz** — translation workflow German → Polish with glossary discipline.
- **knowledge-representation** — retrieval tooling over a library corpus; evaluation methodology.
- **aXIOM** — DFS-IP track; methodological self-description.

Contribution is *ad-hoc*: an artefact yields methodology material when it does so naturally, not prophylactically per project.

**Skin-in-the-game principle:** the methodology tests itself in real publication events. AX-006 errors are not an argument against the methodology but an argument for it — they make gaps visible that can be corrected. A methodology that never fails under live load has not yet carried enough weight.

## 7. Status and maturity signals *[TBD — S5]*

**Current status:** working draft. Codified in ADR-0009 (*Project-Identity + Two-Repo Methodology Architecture*, 18 May 2026, Status Accepted) and ADR-0014 (DTrans pivot to EN-first, 21 May 2026, Status Accepted). The cross-project baseline (Layer 1 of the reference implementation) embedded four β-candidate sections — source discipline, writing discipline, actant self-check, tool discipline — all of which have been extracted into this repo, with a fifth (interpretive-frame discipline) added 2026-05-21 after the AX-006 cascade audit distinguished class-one (composition-drift) from class-two (frame-imposition) failure modes, and a sixth (falsification discipline) added 2026-05-21 as the meta-level discipline operationalising Popper-falsifiability across the methodology itself:

- [`disciplines/source-discipline.md`](disciplines/source-discipline.md) — source intake; the three patterns are *Snippets ≠ Primary*, *Secondary ≠ Primary*, *Search-Absence ≠ Proof-of-Absence*.
- [`disciplines/interpretive-frame-discipline.md`](disciplines/interpretive-frame-discipline.md) — analytical stage between source intake and composition; the two patterns are *Lexicon Stability Across Analytical Stages* and *Frame Plurality Check at the Coding Step*.
- [`disciplines/writing-discipline.md`](disciplines/writing-discipline.md) — composition stage; the two patterns are *Composition Drift* and *Descriptive Accuracy*.
- [`disciplines/actant-self-check.md`](disciplines/actant-self-check.md) — author positionality in author-voiced texts; the three audits are *Verb Audit*, *Addressee Audit*, *Discrediting-Frame Inoculation*.
- [`disciplines/tool-discipline.md`](disciplines/tool-discipline.md) — tool fidelity at the infrastructure layer; the three patterns are *Encoding Fidelity*, *Read Fidelity*, *Pre-Production Tool Validation*.
- [`disciplines/falsification-discipline.md`](disciplines/falsification-discipline.md) — meta-level claim-status discipline; the three patterns are *Demarcation at the Claim Level*, *Methodology as Pile-Driver Work*, *Test Mode over Defense Mode*. Provides seven operational tests usable as a methodology self-audit pass.

The six modules are orthogonal layers. Tool discipline is *infrastructure-upstream* of the other five (its failures invalidate them); falsification discipline is *meta-level* across the other five (it tests how each handles its own failure modes). The remaining four run sequentially along the source-to-publication pipeline (source intake → interpretive coding → composition → author voice).

**Maturity signals for Q3 escalation** (peer-review-ready) are not yet operationalised. Candidates:

- ≥ N case studies in which the methodology intervened *before* the failure (not only retrospective lift).
- External read-tests by ≥ M humanities scholars with substantive feedback.
- β stable across ≥ X months without structural re-articulation.

Operationalisation of N / M / X pending.

---

## Frozen Anchors

- **ADR-0009** — project-identity + two-repo methodology architecture (local workspace).
- **ADR-0011** — repo-split conventions (local workspace).
- **ADR-0013** — Repo A naming, visibility, organisational placement (local workspace).
- **ADR-0014** — DTrans pivot, EN-first for Repo A (local workspace).
- **DE source record** (pre-pivot Articulation Pass v0): `workspace/methodology-development/2026-05-19-articulation-pass-v0.md` — superseded by this README per ADR-0014; preserved as a translation source-record for any future bilingual edition.
- **State-anchor memory:** `project_methodology_development.md` (local).
- **Trilingual glossary (DE/PL/EN):** `workspace/methodology-development/glossary-de-pl-en.md` (local; PL native review pending).

---

*Versioning: v0.5 — intermediate working draft post-DTrans-pivot, after the DE Articulation Pass v0 (workspace) was superseded by this EN rewrite. v1 follows after S2 / S3 resolution. Substantial structural changes trigger a version bump; inline patch edits do not.*
