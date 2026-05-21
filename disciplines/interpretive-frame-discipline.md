# Interpretive-Frame Discipline

*β module. Status: working-draft 2026-05-21. Audience: humanities scholar. Repo language EN per ADR-0014.*

---

## 1. Position

Once a source has been verified (see [[source-discipline]]) and before it enters the composition stage (see [[writing-discipline]]), there is an analytical step in which the source is *coded*: categorised, labelled, brought under interpretive concepts. The same image is named *cowboy* or *lasso-thrower*; the same emoji is named *prayer gesture* or *folded-hands gesture* or simply transcribed as a glyph. These naming choices are not innocent. They commit the analysis to a frame, and the frame then propagates through every downstream step — coding tables, semiotic readings, citations in the published text. By the time a reader sees the analysis, the frame has the appearance of description rather than choice.

Interpretive-frame discipline addresses the analytical step itself. It is orthogonal to writing discipline: where writing discipline asks *does the final text match the source*, interpretive-frame discipline asks *did the coding step impose a frame the source did not require*. The two failure modes are distinct and need distinct correctives.

A separate finding underwrites this distinction: descriptive errors in a published text fall into at least two classes. The first class is composition drift — the text says something about an artefact that the artefact does not show, because the author lost source-contact during a long composition window. The second class is frame imposition — the analysis carries a categorical or connotative frame that was selected upstream in the coding step, never made explicit, and never tested against alternatives. Class one is cheaper to fix (re-inspect the source, rewrite the sentence); class two is more expensive (the frame may be load-bearing for the entire reading). A methodology that catches only class one leaves the more expensive class undiagnosed.

---

## 2. The Two Patterns

### 2.1 Lexicon Stability Across Analytical Stages

**Rule.** When analysis moves between stages (intake → coding → categorisation → synthesis), the descriptive lexicon used to refer to source items must not drift silently from descriptive-actional terms to culturally-typological terms. A move from *what the figure is doing* to *what cultural category the figure belongs to* is a decision, not a translation, and requires an explicit marker with reasoning.

**Why.** Each analytical stage tends to consolidate its preferred vocabulary. Early stages are often closer to direct description (the body is throwing a lasso; the figure is at a chess board). Later stages, working over coding tables and aggregated patterns, tend to substitute typological labels (cowboy, chess player) that read more naturally in prose. The substitution is rarely flagged because it feels like ordinary stylistic compression. But the substitution carries the analysis from observation-grounded language into culture-loaded language. By the time the typological label reaches the published text, the descriptive grounding has been forgotten and the typology appears self-evident.

The cost is asymmetric. If the typology turns out to be defensible, the inter-stage shift cost nothing. If the typology turns out to be loaded, contestable, or out of register with the analytic claim being made, the shift has corrupted the analysis at a point that is hard to locate retrospectively, because no single stage performed the substitution — it was distributed across stages.

**How to apply.**
- Maintain an explicit lexicon for each analytical stage. When the lexicon changes between stages, document the change with a brief reason.
- When a later stage uses a different term for the same source item, treat the term-change as a decision that needs justification. *"We move from 'lasso-thrower' (Stage 1) to 'cowboy' (Stage 2) because [reason]."*
- If no reason can be articulated, the term-change is unjustified drift. Roll back to the earlier-stage term.
- Be particularly cautious about descriptive-to-typological moves: *what the figure does* → *what category the figure embodies*. The typological move is high-yield rhetorically and high-risk analytically.

### 2.2 Frame Plurality Check at the Coding Step

**Rule.** When the coding step assigns a connotation, interpretation, or cultural-significance reading to a source element, at least two or three alternative readings must be enumerated and considered before a default is selected. The choice of default must be made consciously, not by salience-of-first-association.

**Why.** Connotation coding is interpretively load-bearing in qualitative discourse analysis, semiotic reading, and frame analysis. It is also where the analyst's own cultural background tends to assert itself silently. A symbol that has multiple plausible cultural readings (a folded-hands gesture readable as *prayer*, *thanks*, *acknowledgment*, *namaste*, *high-five-completion*) will tend to be coded according to the first reading that comes to mind, which is the reading most native to the analyst's own frame. The competing readings are not weighed and rejected; they are simply not noticed.

The result is a frame default that is invisible from the analyst's position and that the analysis presents as the cultural reading rather than as one of several. Readers from outside the analyst's frame may experience the reading as parochial without being able to locate why. This is a different failure than wrong description (which is class-one). The descriptive content is correct (the gesture is the gesture); the connotative reading is partial without admitting that it is partial.

**How to apply.**
- For any connotation code in the analysis, enumerate two to three plausible alternative readings.
- For each alternative, note briefly whether it can be excluded on source-internal grounds (the surrounding text, the genre, the audience) or whether the choice between readings is interpretive.
- Where the choice is interpretive, mark the default reading as *chosen against* the alternatives, not as *the* reading. Cite the alternatives in a footnote, an annex, or a coding-decision log.
- When the analyst's cultural background is closely aligned with one of the candidate readings, treat that alignment as a reason for extra scrutiny, not as a reason to skip the enumeration step.

---

## 3. Operationalisation in the Workflow

The discipline lives in the analytical phase between source intake and composition:

- **At the start of the analytical stage:** establish a working lexicon. Source items get descriptive-actional names where possible; typological names are deferred until justified.
- **At each transition between analytical stages:** check the lexicon. If terms changed, flag the change and articulate the reason.
- **At each connotation-coding step:** enumerate alternatives before fixing a default.
- **Maintain a coding-decision log.** A short append-only file in the analytical workspace, recording per-decision the lemma used, the alternatives considered, and the reasoning. The log is not for publication; it exists so the analyst can re-examine the frame retrospectively when downstream readings depend on it.

The discipline does not require formal protocols. It requires that the analyst can answer, for any item in the published reading, the question *"why this term and not another?"* without retrospectively constructing the reason. If the reason was not formed at the coding moment, the lexicon may have drifted.

---

## 4. Failure-Mode Gallery

Two documented cases from a single op-ed publication (AX-006, Body-Worlds exhibition advertisement, May 2026):

- **Lexicon-drift from "lasso-thrower" to "cowboy".** Early-stage analysis (a methodological synthesis grounded in the exhibition catalogue's own pose-vocabulary) labelled a plastinated figure with raised arm a *lasso-thrower* — descriptive-actional, drawn from the catalogue. Mid-stage analysis (discourse analysis tables, semiotic coding) substituted *cowboy* — culturally-typological, Western-genre-loaded. The published op-ed inherited *cowboy*. The substitution was never flagged with a reason. *Lift: Pattern 2.1.*

- **Default-frame imposition on the 🙏 emoji.** Mid-stage semiotic coding assigned the emoji the connotation *religiously-respectful gesture* (*religiös-respektvolle Geste*). Alternative readings (a thank-you gesture; a culturally-ambiguous folded-hands gesture; a marketing-tonal politeness marker; the South-Asian *namaste* reading; the East-Asian *please/thank-you* reading) were not enumerated. The op-ed and its accompanying paratexts inherited *prayer-emoji* as a fixed label, which the published version then carried into a reading partly about religious framing. The connotative reading was not wrong; it was partial without being marked as partial. *Lift: Pattern 2.2.*

Both errors are upstream of writing discipline: they were already present in the analytical step that produced the coding tables. Re-inspecting the source against the published text — the writing-discipline corrective — would not have caught them, because the source was correctly described in descriptive terms. What was missing was an audit of the frame the coding step had silently imposed.

---

## 5. Hierarchy of Findings

Class-one errors (composition drift, descriptive-accuracy slips) are correctable in place: re-inspect, re-write. The cost is the time of a re-read pass. Class-two errors (lexicon drift, frame imposition) may propagate through the entire reading: the typological label or the connotative default may be load-bearing for the analytical argument. Correcting them retrospectively can require re-doing portions of the analysis. The methodology should treat class-two findings as more expensive and prioritise their detection.

Practical implication: when a publication review surfaces *both* a class-one and a class-two finding, audit the class-two case before fixing the class-one case. The class-one fix is often a one-line edit; the class-two finding may change which one-line edits are needed elsewhere.

---

## 6. What This Discipline Does **Not** Provide

- It does not address source intake — the source must already have been verified (see [[source-discipline]]).
- It does not address composition-stage drift between source and text — that is covered by [[writing-discipline]]. Interpretive-frame discipline operates earlier, on the coding step itself.
- It does not address authorial positionality at the level of voice and addressee — that is the scope of [[actant-self-check]]. The two are related (frame defaults are positionality-adjacent) but distinct: actant self-check audits *who is asserting*, interpretive-frame discipline audits *what categories the assertion is made in*.
- It does not address tool-infrastructure fidelity — that is the scope of [[tool-discipline]].
- It does not provide a procedure for resolving frame plurality. Where the coding step finds two or three plausible alternative readings and the source cannot adjudicate between them, the discipline requires the alternatives to be enumerated, not to be resolved. Resolution is an interpretive judgment that the analyst makes and defends; the discipline ensures the judgment is made consciously rather than by default.

---

## 7. Cross-Refs

- [[source-discipline]] — source intake; the upstream stage.
- [[writing-discipline]] — composition stage; the downstream stage. Together with this discipline forms the source → analysis → text chain.
- [[actant-self-check]] — voice positionality; orthogonal but frame-adjacent.
- [[tool-discipline]] — infrastructure layer; complementary.
- α reference: AX-006 case material in the reference implementation; the cascade audit (`artefacts/AX-006/2026-05-21-ax-006-cascade-audit.md`) is the worked example that triggered the lift of this discipline from the writing-discipline scope.

---

*Versioning: working-draft. The discipline is the most recent of the five β modules (added 2026-05-21 after the AX-006 cascade audit distinguished class-one and class-two failure modes). Substantial structural re-articulation triggers a status update. Inline patch edits do not trigger a version bump.*
