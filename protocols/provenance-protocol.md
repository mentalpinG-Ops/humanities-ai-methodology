---
name: Provenance Protocol
version: 0.1.0
status: draft
last_changed: 2026-06-17
---

# Provenance Protocol

*Methodology module. Audience: humanities scholar.*

---

## 1. Position

In AI-assisted scholarly work, ideas, claims, frameworks, and conceptual moves enter the project from two distinct sources: the human researcher and the AI assistant. Without explicit tracking, the two sources blur. Within a few weeks, the researcher cannot reliably answer the question *"where did this idea come from — me or the assistant?"* Within a few months, the question becomes structurally unanswerable: the working text shows only the result, not the genealogy.

This blurring has consequences that other protocols in this repository do not address. Source protocol tracks where *external sources* came from; it does not track where *the researcher's own working ideas* came from. Writing protocol tracks fidelity between source and final text; it does not track who first proposed a phrase or framework. Actant self-check tracks the *voice* of the asserting researcher; it does not track whether that voice's content was suggested by an assistant. Falsification protocol tests whether claims could be wrong; it does not test whether claims are the researcher's own.

Provenance protocol addresses the gap. Its purpose is threefold:

1. **Intellectual-property clarity** — across a scientific project (or any AI-assisted portion of one), the researcher must be able to demonstrate which contributions are theirs and which are AI-introduced or AI-amplified. This matters for authorship, attribution to funding bodies, academic-integrity audits, and the researcher's own integrity-of-record.
2. **Audit traceability** — the project span must be auditable in retrospect. A reviewer (the researcher themselves, a co-author, an evaluator, an editor) must be able to reconstruct the provenance of any specific idea or framework.
3. **Learning-progress verifiability** — when AI assistance is used, the question *"did I learn this, or am I scaffolded by it?"* must remain answerable. A protocol that tracks introduction-source enables retrospective verification: ideas the researcher used once and could not reproduce independently are still scaffolded; ideas the researcher has internalised and can reproduce, defend, and extend without re-prompting are learned. The same tracking enables verification of the opposite — apparent learning that on re-test turns out to be sustained AI dependency.

The protocol does not constrain *how* AI assistance is used; it constrains how the use is *recorded*. The recording is what makes the other three goals operational.

---

## 2. The Three Patterns

### 2.1 Provenance Marking at Introduction-Time

**Rule.** Every load-bearing concept, framework, claim, term, or methodological move that enters a project's working materials must carry a provenance marker at the point of first introduction. The marker distinguishes at minimum four categories: *human-originated* (the researcher proposed this independently), *AI-introduced* (the assistant first surfaced this), *AI-amplified* (the researcher had the seed; the assistant elaborated, extended, or systematised), *co-developed* (the contribution is genuinely joint and cannot be cleanly attributed). Markers persist in the working materials, not just in conversation memory.

**Why.** The introduction moment is the only moment at which provenance is reliably observable. After introduction, the idea integrates into the working text, gets re-cited, gets revised, and the genealogy becomes invisible. A marker placed at introduction-time survives subsequent integration; a marker reconstructed retrospectively requires memory of conversational context that decays within days. The cost of marking at introduction is low (one phrase or footnote); the cost of failing to mark is unrecoverable.

The four-category distinction matters because the categories carry different attribution weights. *Human-originated* is the strongest claim to authorship; *AI-introduced* is the weakest; *AI-amplified* and *co-developed* sit between and require honest assessment of which side did the load-bearing work. Conflating them — treating all AI-touched ideas as "mine" or all touched ideas as "the AI's" — produces misattribution in opposite directions, both equally problematic.

**How to apply.**
- For each new concept, term, or framework that enters a working file, attach a brief provenance tag at first appearance: `[H]` (human-originated), `[AI]` (AI-introduced), `[AI+]` (AI-amplified), `[H+AI]` (co-developed). Or use full-word equivalents in a project-decision-log.
- For methodological moves, ADRs, and protocol-additions, name the originating side in the document body (*"This pattern was first surfaced by [the assistant / by me / jointly]"*).
- For text passages, mark provenance at paragraph-granularity where origins differ; uniform-origin texts can be marked once at document-level.
- When in doubt about category, use the more conservative attribution (prefer *AI-introduced* over *AI-amplified*; prefer *AI-amplified* over *human-originated*). Over-attribution to AI is a less costly error than over-attribution to self.

### 2.2 Audit-Trail Across Project-Span

**Rule.** Provenance markers must persist across the full span of a project, not only within a single working session. A project-decision-log (or equivalent persistent record) maintains the introduction-history. Retrospective audits — by the researcher, by co-authors, by reviewers — must be possible without reconstructing from memory or chat-transcripts.

**Why.** A scientific project spans weeks to years. Working sessions are episodic; the project is continuous. Markers that exist only in chat-transcripts or session-memory are not durable — chat services delete, memory rotates, contexts compact, exports get lost. A protocol that depends on transient records produces an audit-trail that is in principle but not in practice reconstructable. The protocol therefore requires *durable* markers in the project's own working materials: file commits, decision-log entries, glossary annotations, footnotes in working drafts.

The audit-trail's function is not only external (defending authorship to a reviewer or funding body). It is also internal: the researcher's own ability to answer their own question *"did I think of this, or did the assistant?"* depends on the same durable record. Self-audit is the more frequent use; external-audit is the more consequential one when it occurs.

**How to apply.**
- Maintain a project-decision-log (an append-only file, e.g. `decisions.md` or `methodology-log.md` in the project root) recording introduction-events for load-bearing concepts. Entry format: date, concept/term/move, originating side, brief note on the seed (the conversation move, the cited source, the prior thought).
- For long-running projects, log entries at session-end as part of session-close routine — this is the moment when the session's introductions are still fresh.
- Glossary entries (where present) include an origin field naming the originating side and the introduction-event reference.
- Git history alone is insufficient for AI-provenance: commits show who wrote the file but not who first surfaced the content. A separate decision-log is therefore required even for git-tracked projects.

### 2.3 Learning-Progress Verifiability

**Rule.** The protocol distinguishes *scaffolded* use (the researcher applies an idea but cannot reproduce it without re-prompting the assistant) from *internalised* use (the researcher can reproduce, defend, and extend the idea independently). Tracking introduction-events plus subsequent independent-uses enables retrospective verification of which side a particular idea sits on.

**Why.** AI assistance can produce two superficially-identical outcomes that differ in their long-term value: durable learning (the researcher now possesses the capability) and sustained scaffolding (the researcher continues to require the assistant for the same operation). The two are hard to distinguish from the working output alone — both produce competent-looking text. They become distinguishable only over time, when the researcher returns to the same conceptual territory without AI access.

A protocol that tracks introduction-events plus independent re-uses makes this distinguishability operational. An idea introduced by the assistant and subsequently re-deployed by the researcher across new contexts without re-prompting is durable learning. An idea introduced by the assistant and only deployed in identical re-prompting situations is sustained scaffolding. Both are legitimate AI-uses; conflating them is not.

The protocol also enables verification of *negative* learning-progress — apparent independence that turns out, on re-test, to depend on prior AI exposure. This is methodologically important: the researcher's own model of their own capabilities is a key research instrument, and unverified self-assessment is unreliable.

**How to apply.**
- For ideas introduced by AI, record the introduction-event (per 2.2) plus subsequent independent-deployments. Independent-deployment means: the researcher used the idea in a new context, in a new file, after sufficient time-gap that recall from short-term context is implausible.
- Periodically (every few months, or at project milestones) review the AI-introduced concepts and ask: *"Can I reproduce, defend, and extend each of these without the assistant present?"* The answer differentiates learned from scaffolded.
- For methodological commitments and theoretical frameworks specifically, conduct periodic *re-derivation* tests — write out the reasoning from first principles without consulting the assistant or the prior working materials. Successful re-derivation is strong evidence of internalisation; struggle is evidence of continued scaffolding.
- Failures to re-derive are not failures of the protocol. They are exactly the data the protocol exists to surface — the researcher now knows where their dependency sits and can either deepen the learning or accept the dependency knowingly.

---

## 3. Operationalisation in the Workflow

The protocol integrates into existing project workflows rather than requiring separate tooling:

- **At session-start:** review the previous session's decision-log entries for any introduction-events that need clarification or category-revision now that some time has passed.
- **During session:** as new concepts enter the working materials, attach provenance markers in-line (using the `[H] / [AI] / [AI+] / [H+AI]` convention or project-specific equivalent).
- **At session-end:** append to the project-decision-log the load-bearing introductions of the session — concepts, terms, methodological moves, ADR-decisions, and protocol-additions. Note for each: originating side, brief seed-note.
- **At project-milestones (months, deliverables, publication-points):** conduct learning-progress reviews. List the AI-introduced concepts in the project; for each, mark *learned* or *scaffolded* based on the independent-deployment-test. Update the project-decision-log with the review-date and findings.
- **At authorship-attribution events** (paper drafting, grant applications, public-talk preparation): the project-decision-log is the authoritative reference for attribution decisions. Concepts and frameworks marked *AI-introduced* require explicit attribution in the output; concepts marked *human-originated* or *AI-amplified* with substantive human-development are author-credit-bearing without separate AI-attribution (subject to the venue's specific rules).

The protocol does not require a separate file *if* the project's existing decision-log or methodology-log can carry the additional structure. For projects without such a file, a minimal `provenance-log.md` at the project root serves the purpose.

---

## 4. Failure-Mode Gallery

Three failure modes the protocol guards against, drawn from observed patterns in AI-assisted humanities work:

- **Retroactive self-attribution drift.** An idea was AI-introduced six weeks ago. The researcher has worked with it since, integrated it into the project's framework, and now feels it as their own. When asked, they answer *"I came up with that"* — sincerely, but inaccurately. The decision-log entry from six weeks ago is the corrective. Without the log, the drift is undetectable from within. *Lift: Pattern 2.1 + 2.2.*

- **Scaffolded competence mistaken for learning.** A researcher uses an AI-introduced framework competently across several projects, concludes they have learned it, and presents it at a conference. The framework collapses under a question they cannot answer without consulting the assistant. The competence was sustained scaffolding; the learning hypothesis was unverified. *Lift: Pattern 2.3.*

- **Unauditable IP in collaborative work.** A researcher publishes a co-authored paper. A reviewer asks which sections were AI-assisted, which co-author proposed which framework, which contributions are independent. The team cannot answer because no provenance was recorded during the work. The paper is correct, but the integrity-of-record is missing. *Lift: Pattern 2.1 + 2.2 + project-decision-log infrastructure.*

In all three cases, the failure is *recoverable* only with a pre-existing record. After-the-fact reconstruction is unreliable. The protocol's value is its before-the-fact protocol.

---

## 5. Relation to Other Protocols

Provenance protocol is a *meta-level* protocol, operating across the full source-to-publication chain rather than at a single pipeline stage. Like falsification protocol, it tests an attribute of the methodology's outputs — in falsification's case *"could this claim be wrong?"*, in provenance's case *"where did this claim come from?"*. The two meta-protocols are complementary axes of audit: falsification audits *validity*, provenance audits *provenance*.

- **Source protocol** tracks the provenance of *external sources*. Provenance tracks the provenance of *the researcher's own developing ideas*, including the AI's contributions to those ideas. The two protocols are orthogonal; both are required.
- **Interpretive-frame protocol** tracks lexicon-stability across stage transitions. Provenance tracks attribution-stability across the same transitions, on a different axis (origin, not lemma).
- **Writing protocol** tracks fidelity between source and text. Provenance tracks fidelity between *who introduced an idea* and *who is credited for it*.
- **Actant self-check** audits the *voice* of the asserting researcher. Provenance audits whether that voice's content was the researcher's own — closely related, but distinct: voice-positionality can be intact while attribution-record is missing.
- **Tool protocol** is infrastructure-upstream. Provenance depends on it: if the tools used to record provenance are themselves unreliable, the record is unreliable.
- **Falsification protocol** tests *whether* commitments can be wrong. Provenance tests *whose* commitments they are. Both are meta-level.

---

## 6. What This Protocol Does **Not** Provide

- It does not prescribe how AI assistance should be used. The protocol operates on the *recording* of use, not the *amount* or *kind* of use. A researcher may rely heavily or lightly on AI; the protocol applies in both cases identically.
- It does not adjudicate attribution disputes. Where the originating side is genuinely ambiguous, the protocol requires the ambiguity to be *recorded* (category *co-developed* or explicit note); it does not provide a procedure for resolving the ambiguity into a clean attribution.
- It does not measure learning-progress quantitatively. The independent-deployment-test is qualitative; the protocol produces a *learned* or *scaffolded* judgement per concept, not a metric.
- It does not address authorship policies of specific venues. Different journals, conferences, and funding bodies have different AI-attribution rules; the protocol's records are *inputs* to those policies, not substitutes for them.
- It does not address the question of whether AI-introduced ideas are *valuable*. That is the falsification protocol's territory and the analyst's own intellectual judgement; the provenance protocol records the origin without evaluating the worth.

---

## 7. Cross-Refs

- [source protocol](source-protocol.md) — external-source provenance (complementary axis).
- [interpretive-frame protocol](interpretive-frame-protocol.md) — lexicon-stability across stage transitions (orthogonal axis).
- [writing protocol](writing-protocol.md) — composition-stage fidelity (different layer).
- [actant self-check](actant-self-check.md) — voice-positionality (closely related, distinct scope).
- [tool protocol](tool-protocol.md) — infrastructure upstream of provenance-recording.
- [falsification protocol](falsification-protocol.md) — meta-level companion (validity-axis; this protocol is provenance-axis).
- Project-baseline attribution-hygiene rule (held in the project's cross-project instructions, in German) — the baseline rule from which this protocol expands. In English paraphrase: strict separation between the researcher's own knowledge or intuitions and AI-introduced sources; AI-introduced material must be explicitly marked and not retroactively attributed as prior knowledge.

---

*Versioning: working-draft. The protocol emerged 2026-05-21 as a methodology-lift from a user-stated requirement: tracking of human-introduced vs. AI-introduced ideas across a scientific project's span, to support IP-clarity, audit-traceability, and learning-progress verifiability. Per the auxiliary-hypothesis admissibility test (falsification-protocol §3 OT-3): the addition increases the methodology's forbidden set by three items — unrecorded provenance at introduction-time, unrecoverable audit-trails over project-span, and unverified learning-progress claims. Substantial structural re-articulation triggers a status update. Inline patch edits do not.*
