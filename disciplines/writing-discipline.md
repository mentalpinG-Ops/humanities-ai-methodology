# Writing Discipline

*β module. Status: working-draft 2026-05-21. Audience: humanities scholar.*

---

## 1. Position

Once a source has been verified (see [[source-discipline]]), the work is not done. Between source intake and publication sits the *composition stage* — drafting, revising, illustrating, citing — and this stage is itself an error surface that source discipline does not cover. The author's memory of the source drifts over long composition windows; tools that mediate the author's view of the source (file readers, image-display systems, OCR, AI assistants) silently misrender; the original artefact begins to recede behind the author's developing argument about it. Writing discipline addresses the gap between the source as verified and the text as published.

Two patterns are empirically robust enough to be named separately. Together they constitute Writing Discipline.

---

## 2. The Two Patterns

### 2.1 Composition Drift

**Rule.** Initial source readings drift during long composition windows (two to three hours and beyond). Memory of what the source said becomes unreliable. A pre-publication re-check must compare claims against the *original source*, not against a later state of the composition.

**Why.** Compositional momentum is a known feature of writing: as the argument develops, the source recedes into the author's representation of it. Phrases get internalised, re-cited from memory, revised against the developing argument rather than against the source. By the time of publication, the cited material may resemble the source approximately but no longer match it verbatim. The drift is invisible from inside the composition because the author's internal reference is the most-recent composition state, not the source itself.

**How to apply.**
- Before publication, open the original source again.
- Re-verify every direct quotation verbatim against the source.
- Re-verify every empirical claim (the artefact shows X, the text says Y) against the source, not against the composition.
- Track composition windows: re-check is mandatory after roughly two hours since the source was last consulted; recommended even for shorter intervals.

### 2.2 Descriptive Accuracy

**Rule.** Empirical claims about artefacts (this image shows X, this text says Y, this emoji is Z) must be verified directly against the source, not from memory and not from a tool-output approximation. Tool-mediated views of an artefact can misrender what is actually there.

**Why.** Mediation introduces approximation. File readers may report emoji positions inaccurately, mis-align indentation, or substitute Unicode confusables. Image-display tools may compress, crop, or transcode in ways that change what an author then sees. OCR may misread similar characters. AI assistants summarising a file may report what they expect to be there alongside what is actually there. The author working with the mediated view forms an "obvious" but false impression of what the artefact contains. The error then enters the publication as a confidently-asserted empirical claim.

Empirical case: a published op-ed described an exhibit photograph as showing *"a chess player with a hat"*. The hat was on a different figure (a cowboy plastinate); the chess player was bareheaded. The author had composed against a tool-mediated memory of the image, not against a direct re-inspection. A second incident from the same publication misidentified a 🙏-emoji's referent under the same drift dynamic. Both errors required post-publication manual correction.

**How to apply.**
- For any claim of the form *"the artefact shows X"*, re-inspect the source directly.
- For text claims, copy-paste the original verbatim into the draft to compare against the citation as written.
- For images, view the source at native resolution, not as a thumbnail or tool summary.
- For emojis and special characters, paste the original Unicode codepoint, not a description.
- When the author depends on a tool to mediate the artefact (e.g., a coding assistant reading a file), assume the tool view is approximate and verify the specific claim independently.

---

## 3. Pre-Publication Re-Check Protocol

Composition Drift and Descriptive Accuracy share an operational consequence: a pre-publication re-check pass must exist as a distinct workflow stage, not as a vague "final read".

The re-check has three concrete components:

| Component | What is verified | Against what |
|---|---|---|
| **Source re-check** | every direct quotation, every cited claim | the original source, not the composition |
| **Artefact re-check** | every empirical "this shows X" claim | the source artefact, not a tool-rendered view |
| **Composition self-read** | the published-version text | a freshly-rendered final draft, ideally in a different format than the composition tool |

The third component (composition self-read) catches errors of formatting, structure, and rendering that are invisible in the composition tool but visible in the published format.

---

## 4. Failure-Mode Gallery

The discipline is grounded in documented errors, not prophylaxis. Two cases from the same op-ed publication:

- **Chess-player misattribution.** Op-ed described a photograph as showing "a chess player with a hat". The hat belonged to a different figure (a cowboy plastinate). The error survived multiple drafts because every revision was checked against the prior draft, not against the original image. Lift: Pattern 2.2.

- **🙏-emoji misidentification.** The op-ed treated an emoji as a prayer gesture; closer inspection showed the gesture was different. Same drift mechanism: composition built on an early impression, not re-verified against the source. Lift: Pattern 2.2.

Both errors required manual post-publication correction. Both were preventable by a pre-publication artefact re-check; neither was prevented by source discipline alone, because the sources had been correctly cited — the failure was in the author's descriptive claim about them.

---

## 5. Operationalisation in the Workflow

Writing discipline is a workflow stage, not a final-read habit:

- **During composition:** tag every "this artefact shows X" claim with a re-check flag. The flag persists until the artefact has been re-inspected.
- **At ~2-hour intervals:** pause; note compositional drift risk; refresh source-anchored claims if the composition has moved far from the last source consultation.
- **Before publication:** execute the three-component re-check (source / artefact / composition self-read) as a distinct step, not folded into general proof-reading.
- **After publication:** if errors are caught post-publication, lift them as failure-mode entries (per this gallery) rather than treating them as one-off mistakes. Failures yield methodology material when systematised.

---

## 6. What This Discipline Does **Not** Provide

- It does not address source intake — the source must already have been verified (see [[source-discipline]]).
- It does not address authorial positionality — the question of *who is asserting what about whom* (see [[actant-self-check]]).
- It does not address tool-infrastructure failures at the system level — that is the scope of [[tool-discipline]]. Writing discipline expects tool mediation to be present and treats verification against the source as the corrective; tool discipline addresses the tools themselves.
- It does not guarantee that what the author *means* to assert is well-formed; it guarantees only that *what the author asserts about the artefact* matches the artefact.

---

## 7. Cross-Refs

- [[source-discipline]] — source intake; verification before composition.
- [[actant-self-check]] — positionality of the asserting voice; orthogonal layer.
- [[tool-discipline]] — tool fidelity at the infrastructure layer; complementary.

---

*Versioning: working-draft. Substantial structural re-articulation (e.g., after additional case-study evidence or reader feedback) triggers a status update. Inline patch edits do not trigger a version bump.*
