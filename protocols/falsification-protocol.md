---
name: Falsification Protocol
version: 0.2.0
status: draft
last_changed: 2026-07-20
---

# Falsification Protocol

*Methodology module. Audience: humanities scholar.*

---

## 1. Position

The other five pipeline-stage protocols in this repository each address one layer of the source-to-publication chain — source intake, interpretive frames, composition, authorial voice, and tool infrastructure. They make individual practices answerable to particular failure modes. What they do not address is the meta-question that runs across all five: *under what conditions can any of these practices, or the methodology as a whole, be shown to be wrong*?

A methodology that names its rules but does not specify how its rules could fail is a closed system. It can be applied, but it cannot be tested. Failures in such a system are absorbed as application-errors rather than surfaced as methodology-evidence. The result is a protocol-set that drifts further from what it was meant to constrain, with no visible mechanism for self-correction.

Falsification protocol addresses this gap. Its source is Karl Popper's *Logik der Forschung* (1934), specifically the demarcation argument, the anti-ad-hoc methodological rules, and the anti-foundationalist treatment of basic statements. Its purpose in this methodology is not to reproduce Popper's philosophy of natural science but to operationalise its testable-rules core for a humanities-AI-working environment in which the analyst's own methodology is itself an object of failure-mode tracking.

Three Popper-anchors are load-bearing for what follows, given here verbatim from the Polish edition (Niklas 1977; full Popper-translation-provenance held in the project's audit notes):

> „Naturalnie tylko wówczas traktuję pewien system jako empiryczny lub naukowy, gdy poddaje się on sprawdzeniu w doświadczeniu. Z rozważań tych wynika, że za kryterium demarkacji należy przyjąć **nie weryfikowalność, lecz falsyfikowalność systemu**." (§ 6)

> „Zgodnie z moją propozycją dla metody empirycznej charakterystyczne jest to, że **system podlegający sprawdzaniu dostępny jest falsyfikacji na wszystkie dające się pomyśleć sposoby**. **Cel tej metody nie polega na ratowaniu życia nie dających się utrzymać systemów, lecz przeciwnie, na rzuceniu ich wszystkich w wir najzacieklejszej walki o przetrwanie i wybraniu tego, który w porównaniu z innymi okaże się najlepiej przystosowany**." (§ 6)

> „**Empiryczna baza nauki obiektywnej nie kryje nic absolutnego. Nauka nie spoczywa na niewzruszonych podstawach.** Śmiała struktura teorii naukowych jak gdyby wznosi się nad grzęzawiskiem. Przypomina gmach wzniesiony na słupach wbijanych z góry w to grzęzawisko, lecz nie sięgających żadnej naturalnej ani «danej» podstawy. **Wbijanie słupów przerywamy wcale nie dlatego, że osiągnęliśmy twardą ziemię. Przerywamy po prostu wtedy, gdy uznamy, że tkwią one wystarczająco mocno, aby przynajmniej tymczasowo udźwignąć strukturę**." (§ 30)

Falsifiability as criterion; method as anti-ad-hoc selection pressure; methodology itself as pile-driver work, not foundation work. These three commitments shape the three patterns of this protocol.

---

## 2. The Four Patterns

### 2.1 Demarcation at the Claim Level

**Rule.** Before any load-bearing claim is treated as empirical or test-grounded, it must pass a demarcation question: *what observation, finding, or counter-instance would, if it occurred, lead this claim to be revised or withdrawn?* If no such answer can be given, the claim is not empirical, and treating it as if it were is a category error. The claim may still be legitimate (it may be normative, definitional, or methodological), but it must be classified accordingly so that downstream reasoning is calibrated to its actual status.

**Why.** A common failure in humanities-AI work is the implicit treatment of methodologically-grounded claims as if they were empirically tested, and vice versa. A normative claim about how a text *should* be read is not falsified by reading the text differently. A definitional claim about what counts as evidence is not falsified by producing different evidence. Conflating the registers makes the methodology appear empirical when it is not, and lets unfalsifiable claims accumulate authority by association with the falsifiable ones. The Popper-trace is direct: verification/falsification asymmetry (modus tollens, § 6) is the load-bearing anchor, and the source-protocol pattern *Search-Absence ≠ Proof-of-Absence* is already its single explicit instance in this repository. The protocol generalises it across all claim-types.

**How to apply.**
- For each load-bearing claim, answer one of: *what would falsify this?* / *this is normative, grounded in [X]* / *this is definitional, grounded in [Y]*.
- Universal-form claims (*all X are Y*) are reframed as *tested in N cases so far; falsifiable by condition Z* — making the inductive scope explicit and the falsifier specifiable.
- When the falsifier cannot be specified, that is itself a finding: the claim is not yet in test-form, and downstream reasoning must mark it as such.

### 2.2 Methodology as Pile-Driver Work, Not Foundation Work

**Rule.** Protocols, methodological rules, and analytical practices are treated as pilings driven into ground that does not bottom out — they hold provisionally, under specifiable load. They are not foundations; no claim of finality, completeness, or self-evidence is made for them. The status vocabulary of the methodology must reflect this. Labels like *stable*, *canonical*, *final*, or *settled* are admissible only when paired with an explicit falsifier specification (*stable under the following conditions; would be revised upon [...]*); otherwise they overclaim.

**Why.** A methodology that styles itself as foundational invites the failure mode it was meant to prevent. If a protocol is presented as settled, deviations from it look like errors-of-application rather than evidence-against-the-protocol; the methodology then collects only confirming cases. Popper's anti-foundationalist treatment of basic statements (the piles-driven-into-a-swamp image of § 30) and his anti-ad-hoc rules together imply: every methodological commitment must remain testable against its own application history.

A concrete instance from this repository's own short history: a workspace schema file carried `status: stable` in its frontmatter while the title said `_proposal` and the corresponding ADR was still in *Proposed* state. The label overstated the actual status; the catch was post-hoc, and the correction was a manual edit. The failure was small and recoverable, but the failure-mode is structural. Status labels that exceed their supporting evidence will recur unless the protocol names the pattern.

**How to apply.**
- Status-vocabulary audit: for every artefact labelled *stable / canonical / final / settled*, require a paired clause naming the falsifier (*"stable subject to revision if [...]"* / *"canonical against the alternatives [...]"*).
- Protocol-addition audit (per Popper's auxiliary-hypothesis rule § 20): a new protocol or pattern is admissible only if it increases what the methodology forbids — what is now excluded that was not excluded before. If the addition does not sharpen any constraint, it is decoration, not improvement. (This protocol itself was added under that test: it forbids unfalsifiable claim-treatment, unprotocold methodology-additions, and overstated status-labels — three additions to the forbidden set.)
- Theory-vs-basic-statement separation: methodology rules (the protocols) are at the *theory level* and are not arbitrarily revisable; specific applications (user corrections, individual cases) are at the *basic-statement level* and are revisable by rule-governed convention. Confusing the two — treating a protocol as if it were a single case, or treating a single case as if it were a protocol-revision — is the same error in opposite directions.

### 2.3 Test Mode over Defense Mode

**Rule.** For load-bearing claims and load-bearing methodological commitments, the operative question is *how is this tested?*, not *how is this defended?*. Justificatory framing — "this is grounded in [tradition X]" / "this follows from [premise Y]" — does not displace the test question; it can sit alongside it, but it cannot stand in for it.

**Why.** Justificatory framing is the natural register of academic writing, and it can pass for testing because both forms produce reasoned text. The two are distinct in function. Justification asks *why is this position warranted*; testing asks *under what conditions would this position be wrong*. A protocol that operates only in justification mode accumulates reasons-for but not conditions-against, and over time loses contact with what would have to change for the protocol itself to change. Popper's reformulation (§ 30 footnote 1959, Anker 9): *„W jaki sposób możemy najlepiej dokonać krytyki naszych teorii (hipotez, domysłów) zamiast brać je w obronę przed wątpliwościami?"* — How can we best criticise our theories instead of defending them against doubt. The protocol takes this as a working rule, not as a slogan.

**How to apply.**
- For methodological commitments captured in ADRs, the decision record should contain a *Falsifier* section alongside *Context*, *Decision*, *Consequences* — naming what would have to change for the decision to be revisited. Without this, the ADR is justification-only.
- For empirical claims in published outputs, the writing-protocol source-recheck is already a test-mode step. Falsification protocol generalises: every load-bearing claim should be paired with a sentence answering *this would be wrong if [...]*.
- For methodology revisions: a single failure-instance is not sufficient evidence for protocol-change (per Popper § 22: *single conflicting basic statement* ≠ *falsification*). A reproducible failure-mode pattern (≥ 2 instances, or 1 instance with constructive generalisation path) is required before a protocol is revised. This guards against ad-hoc protocol-churn under one-off pressure.

### 2.4 Instrument Validation and Test-Material Design

**Rule.** An empirical test of a methodological or analytical claim must apply falsification discipline to its own *instrument* and *material*, not only to the hypothesis. Four requirements:

- **(a) Pre-registered instrument validation.** The validation gate — the check that the judging procedure can discriminate at all — is specified in the pre-registration (reference-key source + flip set), independent of the hypotheses. Where the reference key can be built *by construction* (one base, N variants, each violating exactly one item of a finite forbidden list, built hypothesis-blind), the gate survives the refutation of the hypothesis: **the prediction table is not the reference key.** Where no independent key is possible, that limitation is declared in advance, with a substitute verification plan.
- **(b) Minimal pair for property toggles.** Where the tested property is a toggle (marked vs. unmarked, present vs. absent), the gate must contain a minimal pair — the same content with only the property switched. The pair *is* the instrument validation: it proves discrimination by the property rather than by co-varying content.
- **(c) Material difficulty as a design variable.** For tests on constructed material, how easy the material makes the clean result is a declared design parameter, varied across at least two tiers — or the conclusion is explicitly narrowed to the tested tier. A null finding on easy material says nothing about hard material.
- **(d) Pre-registered consequence matrix.** Where several pre-registered conditions jointly decide the verdict, the full matrix with explicit precedence is registered in advance, so that no conflicting clause-crossing is resolved under data knowledge.

**Why.** Each clause generalises a documented failure mode from the maintainer's test practice (July 2026). (a) The gap *instrument validation designed only at evaluation time, under data knowledge* occurred twice in one day, in independent runs — and, per this protocol's own OT-5, was acted on at the second instance, not the first. (b) Two successive runs of one test series returned VOID because the instrument could not be shown to discriminate the tested property from its carrier content; the first run whose gate was a minimal pair passed, retroactively explaining the VOIDs as instrument failures rather than untestability of the claim. (c) A test family returned a clean null on self-built material that carried explicit attribution markers; varying only the material difficulty surfaced the defect the easy tier had hidden. The deeper point: when the same actor states the hypotheses, builds the material, and evaluates, the bias lands invisibly in the material-construction step — the standard one-hand bias declaration named hypotheses, prompts, and evaluation, and missed the material as its own bias surface. (d) Two pre-registered clauses fired in opposite directions (test arm confirming, control arm voiding) with no precedence rule; the resolution thereby fell after data sight.

**How to apply.**
- OT-8, OT-9, and OT-10 below operationalise clauses (a)–(c); clause (d) folds into the pre-registration document itself.
- When constructing test material, treat your own expectations as a contamination source for difficulty calibration: name the difficulty axis (what makes the clean result easy) and place at least one cell per tier.
- Treat a passed gate as licensing verdicts about the hypothesis — and a failed or missing gate as capping the run at VOID, regardless of how the hypothesis cells look.

---

## 3. Operational Tests for AI-Assisted Work

The protocol's patterns translate to ten operational tests applicable to humanities-AI working contexts. They are usable individually; together they form a methodology self-audit pass.

| # | Test | Operative question | Failure-signal |
|---|---|---|---|
| OT-1 | Demarcation | What would falsify this load-bearing claim? | No answer available; claim treated as empirical without specifiable falsifier |
| OT-2 | Universal-claim reframing | Is the claim universal in form? If yes, has it been reframed as *tested-in-N-cases, falsifiable by Z*? | Universal form retained without scope-and-falsifier qualification |
| OT-3 | Auxiliary-hypothesis admissibility (per Popper § 20 Regel 1) | Does this added rule / protocol / patch increase what the methodology forbids? | No additional constraint introduced; addition is decoration or face-saving |
| OT-4 | Detection rule (per Popper § 20) | Has an ad-hoc save (in the methodology, the analysis, or the publication) been performed? If yes, has the whole system been re-tested, not only the patch? | Ad-hoc save accepted in isolation, downstream not re-examined |
| OT-5 | Reproducibility before methodology-revision (per Popper § 22) | Is the proposed protocol-revision grounded in a single failure-instance, or in a reproducible pattern? | One-off finding promoted to protocol change without second-instance confirmation |
| OT-6 | Test-mode reframing | For each load-bearing claim or decision, has the test-mode question (*how is this tested?*) been answered, not only the justification question (*how is this grounded?*)? | Justification given, no falsifier paired |
| OT-7 | Status-vocabulary audit | Are *stable / canonical / final*-labels paired with explicit falsifier specifications? | Labels carry implicit foundationalism (the *Pile-driver* failure mode) |
| OT-8 | Pre-registered instrument validation | Is the gate (reference-key source + flip set) specified before data sight, independent of the hypotheses? | Gate constructed under data knowledge; reference key derived from the prediction table |
| OT-9 | Material-difficulty declaration | Is the difficulty of constructed test material declared and varied (≥ 2 tiers) — or the conclusion narrowed to the tested tier? | Null finding generalised beyond its material tier; same-author material tuned, unnoticed, toward the expected outcome |
| OT-10 | Minimal-pair gate for property toggles | Does the gate contain the same content with only the tested property switched? | Gate cells vary content and property together; discrimination unproven |

The first seven tests trace directly to anchors and operational tests in the project's Popper-notes; the per-anchor mapping is preserved internally so that revisions to either side propagate via cross-reference rather than requiring re-derivation.

---

## 4. Current-Practice Table — Summary

Falsification protocol does not replace the existing five protocols; it sharpens what each already does and identifies the gaps. Three patterns from existing protocols are already Popper-aligned in their existing form and require no rewrite:

| Existing pattern | Protocol | Popper-anchor (already aligned) |
|---|---|---|
| *Search-Absence ≠ Proof-of-Absence* | source-protocol §2.3 | verification/falsification asymmetry (Popper § 6, verbatim) |
| *Lexicon Stability* | interpretive-frame-protocol §2.1 | methodological rule as irrevocable decision (Popper § 20 Regel 3, verbatim) |
| *Composition Drift* + *Descriptive Accuracy* | writing-protocol §2.1 / §2.2 | pile-driver image, § 30 (prior acceptance does not survive re-load) + psychological certainty ≠ justification |

Three patterns carry Popper-anchor *claims* but exhibit *fit-gaps* that this protocol names so they can be addressed:

| Existing pattern | Claimed anchor | Mismatch |
|---|---|---|
| *Discrediting-Frame Inoculation* | test-mode (Popper § 30, 1959 footnote) | Functionally a defense move (preemptive acknowledgment), not test-mode reframing |
| *Actant Self-Check* (all three audits) | implicit reproducibility | Single-coder by design; empirical evidence from the museum-exhibition-op-ed case that self-check alone is bias-susceptible |
| *Tool Protocol §Pre-Production Validation* | falsifier-set bipartition (Popper) | No explicit falsifier-set per tool; tests are present but the set of conditions that would identify the tool as broken is not enumerated |

The full gap-analysis covering the eight identified gaps that this protocol now closes is held internally in the project's audit notes (preserved for revision tracing).

---

## 5. Failure-Mode Gallery

Three documented failure-modes from this methodology's own short history serve as concrete tests of the protocol:

- **The *status: stable* mislabelling (2026-05-21).** A workspace draft schema file carried `status: stable` in its YAML frontmatter while its filename declared *_proposal* and the corresponding architecture-decision record was still in *Proposed* state. Treated as stable by downstream tools, the draft was correctable only by user-initiated catch. *Lift: Pattern 2.2 (OT-7 status-vocabulary audit).*

- **The interpretive-frame-protocol addition (2026-05-21).** A new protocol was added on the same day. Before integration, it was implicitly tested against the OT-3 question: does it add to what the methodology forbids? It does (frame-imposition is now a marked failure mode, lexicon-drift between stages is now disallowed). Had the addition not increased the forbidden set, it would have been decoration. *Lift: Pattern 2.2 (OT-3 auxiliary-hypothesis admissibility).*

- **The actant-self-check survival in the museum-exhibition op-ed (2026-05-17).** The actant self-check was performed on the op-ed pipeline as designed. Descriptive-accuracy errors and frame-imposition still passed through. The single-coder design exhibited the predicted OT-5 weakness: a one-off check by the same author cannot substitute for reproducible test. *Lift: Pattern 2.3 (OT-5 reproducibility before methodology-revision); also fed the addition of interpretive-frame-protocol.*

- **The null finding overturned by its own material (2026-07-18/19).** A two-operation authorship test came back clean — gate passed, full inter-judge agreement — on self-built material that carried explicit first-person attribution markers. The verification phase caught the confound: "self-interpreting material" had drifted, unnoticed, into "obviously attributable material", making the clean result easy. A follow-up run changed only the material difficulty (marker-free, gnomic register): the defect that never appeared on the easy tier appeared on the hard one (0/3 → 1/3, unanimous verdict). The null finding was material-dependent — demonstrated within the test family itself. *Lift: Pattern 2.4c (OT-9); second instance of the same-author-material ceiling class.*

- **A pre-registration gap meeting its own change threshold (2026-07-16 → 19).** The gap *instrument-validation design absent from the pre-registration* occurred twice in one day, in independent test runs. The first instance was parked per OT-5 (a single instance does not license protocol change); the second reached the threshold, and the gate became a mandatory pre-registration field — decided as its own act, not as a side effect of a running test. The first application under the new field built its reference key by construction and carried through: the gate stayed valid although the hypothesis under test was refuted. Three gate/analysis-plan patterns were subsequently ratified out of a three-run series whose first two attempts were VOID (the instrument could not be shown to discriminate) and whose third passed on a minimal-pair gate. *Lift: Pattern 2.4a/b (OT-8, OT-10) — the protocol applying its own reproducibility rule to its own revision.*

In all five cases the failure was caught and absorbed as methodology-evidence rather than as application-error. That absorption pathway — Failure → Methodology-Lift → Protocol-Addition — is itself the operative mechanism this protocol names.

---

## 6. What This Protocol Does **Not** Provide

- It does not specify *which* humanities-tradition the methodology should align with. Falsification protocol operates within whatever theoretical framework the analyst commits to; it tests the framework's claim-handling, not the framework's content.
- It does not displace the other five pipeline-stage protocols. Source / interpretive-frame / writing / actant-self-check / tool protocols each cover a distinct failure surface; falsification protocol tests the methodology containing them.
- It does not provide a procedure for resolving normative disagreement. When two analysts disagree on a normative claim, falsification protocol says nothing about which is right; it requires only that both claims be marked as normative rather than empirical and reasoned accordingly.
- It does not guarantee that absorbed failures will produce better protocols. The Failure → Methodology-Lift pathway is one mechanism among others; it can in principle generate over-specified protocols that forbid too much. The auxiliary-hypothesis test (OT-3) is the guard against that, but it is a guard, not a proof.

---

## 7. Cross-Refs

- [source protocol](source-protocol.md) — source intake; *Search-Absence* pattern shares A2.
- [interpretive-frame protocol](interpretive-frame-protocol.md) — analytical stage; *Lexicon Stability* shares A3 + § 20 Regel 3.
- [writing protocol](writing-protocol.md) — composition stage; *Composition Drift* shares A13.
- [actant self-check](actant-self-check.md) — voice positionality; mismatch flagged (single-coder vs OT-5).
- [tool protocol](tool-protocol.md) — infrastructure layer; mismatch flagged (no explicit falsifier-set per Popper § 21).
- [provenance protocol](provenance-protocol.md) — meta-level companion on the provenance axis.

---

*Versioning: working-draft. The protocol emerged as the meta-level Popper-falsification module of the methodology. Anchored in three verbatim Popper passages from Niklas 1977 (§§ 6 + 30), a cross-mapping against the other six protocols, and — since 0.2.0 — ten operational tests for AI-assisted humanities work. Pattern 2.4 (instrument validation and test-material design, with OT-8–OT-10 and two gallery entries) was added 2026-07-20, promoted from a documented test family in the maintainer's practice corpus; minor version bump per governance. Substantial structural re-articulation triggers a status update. Inline patch edits do not.*
