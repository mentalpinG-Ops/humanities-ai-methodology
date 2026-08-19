# Humanities-AI Methodology — Articulation Pass v0.5

*Working draft, 2026-05-21. Language: English. TBD markers in §§1, 4, 5, 7 indicate Strategic Open Questions whose resolution is pending.*

---

## 1. Statement

**humanities-ai-methodology** is a meta-project developing an **AI-agnostic methodology** for **humanities students and humanities scholars** working with AI tools toward **responsible, publishable outcomes**. It transcends individual fields and specific AI tools; the methodology aims to be portable across AI generations.

Audience specification (early-career vs. established vs. mixed) pending S1.

## 2. Motivation

The trigger was not a theoretical need but an empirical diagnosis. During the publication of an analytical op-ed on the Body-Worlds Wrocław travelling exhibition (May 2026), *descriptive-accuracy* errors appeared that required manual post-publication correction. The methodological reconstruction yielded a finding: the protocols that would have prevented such errors did exist fragmentarily in individual project checklists, but not as a coherent workflow. The question *"do we have a consistent workflow, or piecework?"* had to be answered with *piecework*.

From this emerged the reframing: **methodology is not a side effect of project work; it is a primary research object**. Concrete projects (Ideologiekritik, Studium, Rosenkranz, knowledge-representation, aXIOM) are ad-hoc test cases against which the methodology develops and is stress-tested — not its telos.

## 3. What is delivered

This repository holds the methodology itself — an abstract, reusable stack of protocols describing what a responsible humanities-scholar AI-working environment contains: positionality, material boundaries, source intake, interpretive framing, composition, author voice, tool fidelity, falsification, and provenance. It is public-bound (private initially; the public-flip is a separate decision); licence terms are in §8 below; the language is English.

The methodology is not invented here in the abstract. It is **distilled from documented practice**, kept separately in a private working repository. The relationship runs one way: the methodology is derived from practice; practice is never derived from the methodology.

This is enforced by one rule: **no protocol enters the methodology without an empirical anchor in at least one documented practice sequence.** A protocol earns its place here once it has proven itself in real work — it is not written from imagination. Generalisation without a practical source is the failure mode this design exists to prevent. See [`CONTRIBUTING.md`](CONTRIBUTING.md) for what that means for contributions.

This repository therefore documents no running system and holds no project-internal material or case data; those remain in the private practice repository and the maintainer's working context, structurally separated so the material boundary in §8 holds by construction.

**Publication strategy** is *phased*: working draft (this repo + a companion blog format) without peer-review gate as the initial form; methodologically citable from day one. Escalation to peer review (a methods paper) when a maturity threshold is reached — maturity criteria pending S5.

## 4. Normative grounding *[TBD — S2]*

The normative grounding of *"responsible"* is not yet fixed. Candidates on the table:

- **Frankfurt School / Critical Theory** — consistent with the ideology-critical orientation of the op-ed work that triggered the meta-project.
- **Discourse ethics (Habermas)** — procedural; well-matched to a working-draft plus community-feedback mode.
- **Care ethics** — relational; fits the reader-audience relation.
- **Pragmatism (Dewey, Peirce)** — a hypothesis-test-revision cycle that is naturally compatible with phased publication.
- **Deliberate eclecticism** — methodological pluralism rather than single-tradition commitment.

Decision pending. Recursively coupled to the backlog question *"which methodology for the meta-project itself"* (Lean vs. Action Research vs. TQM/PDCA vs. Pragmatist Inquiry vs. Reflective Practice). Both questions likely require joint resolution so that methodological consistency is preserved between norm and norm-development.

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

- **Ideologiekritik** — op-ed pipeline and multimodal artefact analysis; the Body-Worlds-Wrocław op-ed is the first empirical failure-to-methodology lift (pre-publication checklist as the first Methodology-material).
- **Studium** — bibliography management and cross-disciplinary methods inventory.
- **Rosenkranz** — translation workflow German → Polish with glossary protocol.
- **knowledge-representation** — retrieval tooling over a library corpus; evaluation methodology.
- **aXIOM** — schema-development track (Declarative Frame Schema for analytical prompts); methodological self-description.

Contribution is *ad-hoc*: an artefact yields methodology material when it does so naturally, not prophylactically per project.

**Skin-in-the-game principle:** the methodology tests itself in real publication events. The errors from that case are not an argument against the methodology but an argument for it — they make gaps visible that can be corrected. A methodology that never fails under live load has not yet carried enough weight.

*"Skin in the game"* is used here in the sense Eli Kramer develops in [*Get Off Your Philosophical Ass! Having Skin in the AI Game*](https://palinode.substack.com/p/get-off-your-philosophical-ass-having) (Palinode Substack, September 2025) — the contrast between armchair-distance and live exposure to the methodological consequences of one's AI use. The broader phrase originates with Nassim Nicholas Taleb (*Skin in the Game: Hidden Asymmetries in Daily Life*, Random House, 2018); Kramer applies the frame specifically to AI-research practice.

## 7. Status and maturity signals *[TBD — S5]*

**Current status:** working draft. Four of the protocols — source, writing, actant self-check, and tool — were the methodology's first distillations from documented practice, with a fifth (interpretive-frame protocol) added 2026-05-21 after a cascade audit of the first published case distinguished class-one (composition-drift) from class-two (frame-imposition) failure modes, a sixth (falsification protocol) added 2026-05-21 as the meta-level protocol operationalising Popper-falsifiability across the methodology itself, and a seventh (provenance protocol) added 2026-05-21 covering human-vs-AI provenance tracking across a project's span, and an eighth (read-write boundary protocol) added 2026-06-29 governing write-authority over artefact fields and premise-bound invalidation of recorded judgements:

- [`protocols/source-protocol.md`](protocols/source-protocol.md) — source intake; the three patterns are *Snippets ≠ Primary*, *Secondary ≠ Primary*, *Search-Absence ≠ Proof-of-Absence*.
- [`protocols/interpretive-frame-protocol.md`](protocols/interpretive-frame-protocol.md) — analytical stage between source intake and composition; the three patterns are *Lexicon Stability Across Stage Transitions* (covering both analytical-stage and language-stage drift), *Frame Plurality Check at the Coding Step*, and *Operation Declaration — the Smallest Auditable Unit*.
- [`protocols/writing-protocol.md`](protocols/writing-protocol.md) — composition stage; the two patterns are *Composition Drift* and *Descriptive Accuracy*.
- [`protocols/actant-self-check.md`](protocols/actant-self-check.md) — author positionality in author-voiced texts; the three audits are *Verb Audit*, *Addressee Audit*, *Discrediting-Frame Inoculation*.
- [`protocols/tool-protocol.md`](protocols/tool-protocol.md) — tool fidelity at the infrastructure layer; the four patterns are *Encoding Fidelity*, *Read Fidelity*, *Pre-Production Tool Validation*, *Declare vs. Enforce for Encoded Analytical Rules*.
- [`protocols/falsification-protocol.md`](protocols/falsification-protocol.md) — meta-level claim-status protocol (validity-axis); the five patterns are *Demarcation at the Claim Level*, *Methodology as Pile-Driver Work*, *Test Mode over Defense Mode*, *Instrument Validation and Test-Material Design*, *The Referent Is the Privileged Falsifier*. Provides ten operational tests usable as a methodology self-audit pass.
- [`protocols/provenance-protocol.md`](protocols/provenance-protocol.md) — meta-level human-vs-AI provenance protocol (provenance-axis); the three patterns are *Provenance Marking at Introduction-Time*, *Audit-Trail Across Project-Span*, *Learning-Progress Verifiability*. Supports IP-clarity, audit-traceability, and verification of scaffolded-vs-internalised use.
- [`protocols/read-write-boundary-protocol.md`](protocols/read-write-boundary-protocol.md) — meta-level write-authority and currency protocol (authority axis); the three patterns are *The Four Field-Classes*, *Invalidate, Never Author*, and *A Hand-Maintained Derived Field Is a Drift Bug*. Governs which agent may write each artefact field and forces re-decision when a recorded judgement outlives the premises it was decided under.

The eight modules are orthogonal layers. Tool protocol is *infrastructure-upstream* of the other seven (its failures invalidate them); falsification, provenance, and read-write boundary protocols are *meta-level* across the others along three distinct axes (validity vs. provenance vs. authority/currency — falsification asks *"could this be wrong?"*, provenance asks *"where did this come from?"*, read-write boundary asks *"who may write this, and has it outlived its premises?"*). The remaining four run sequentially along the source-to-publication pipeline (source intake → interpretive coding → composition → author voice).

**Maturity signals for peer-review escalation** are not yet operationalised. Candidates:

- ≥ N case studies in which the methodology intervened *before* the failure (not only retrospective lift).
- External read-tests by ≥ M humanities scholars with substantive feedback.
- Methodology stable across ≥ X months without structural re-articulation.

Operationalisation of N / M / X pending.

## 8. License

This repository is **dual-licensed**:

- **CC BY-SA 4.0** (default) — applies to all open, academic, research, and practitioner use. Attribution is required; derivatives must be shared under the same licence. See [`LICENSE`](LICENSE) for the full text.
- **Commercial Licence** (by arrangement) — available for proprietary products, commercial SaaS, and any use where the ShareAlike requirement cannot be satisfied. The commercial licence waives the ShareAlike obligation. See [`LICENSE-COMMERCIAL.md`](LICENSE-COMMERCIAL.md) for terms and contact details.

Practitioner (in-house / employer) use of CC BY-SA 4.0 material is permissible without dual licensing. To obtain a Commercial Licence, see [`LICENSE-COMMERCIAL.md`](LICENSE-COMMERCIAL.md) §6.

---

*Versioning: v0.5 — intermediate working draft after a language pivot from a German predecessor. v1 follows after resolution of the open questions in §4 and §5. Substantial structural changes trigger a version bump; inline patch edits do not.*
