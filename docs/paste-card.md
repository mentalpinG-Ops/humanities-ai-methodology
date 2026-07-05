---
name: Paste-Card
status: draft
last_changed: 2026-07-05
class: derived-gloss   # human-judged compression; the pointer below is mechanical
derived_from:
  - protocols/source-protocol.md @ 0.1.0
  - protocols/interpretive-frame-protocol.md @ 0.1.0
  - protocols/writing-protocol.md @ 0.1.0
  - protocols/actant-self-check.md @ 0.1.0
staleness_rule: >
  If any protocol under derived_from bumps its version, this card is stale:
  a human re-glosses it against the changed text. Automation may flag
  staleness; it must never regenerate the card.
---

<!-- Everything below this line is the card users copy. -->

# AI Work-Session Card — a source-to-publication checklist for humanities work

Paste this at the start of an AI work session. It is a stage-gated checklist we walk through together. Tags: **[Both]** — you (the AI) do the mechanical part (search, compare, enumerate, flag); I (the author) make the final call. **[Human]** — only I can do it. No item on this card is fully delegable to you.

## Stage 1 — Before research

Declare the tool set (search engines, aggregators, AI search agents) and the verification plan. Fix the artefact's target language. Open an append-only coding-decision log (*coding* = assigning analytical labels to sources): term used, alternatives considered, reason.

## Stage 2 — During research: source intake

**1. Snippets ≠ Primary [Both].** Search snippets are pointers to sources, not attestations. Before a hit is cited or argued from, the full text is opened and the passage verified verbatim.
Apply: you retrieve and compare; on divergence, anchor on the full text. Your comparison alone yields only *agent-reported* status — I cross-read personally before anything becomes load-bearing. Unreachable full text → tag "pointer, unverified".

**2. Secondary ≠ Primary [Both].** A description of a primary source is not the primary source. Every source tag declares its level: primary / secondary / tertiary — always, not only on suspicion.
Apply: you propose the level and name the claimed primary; check it is independently accessible. Watch for *promoter amplification* — promotional material circulating an altered version of an original quote until repetition stabilises it; locate original language, venue, date. Unverifiable original → never used as primary attestation.

**3. Search-Absence ≠ Proof-of-Absence [Both].** A negative search result means "not found in [tool] with [query] on [date]" — never "does not exist".
Apply: you record tool, full query, date, hit count, and the possible reasons (indexing gap, operator mismatch, paywall, language corpus, cache staleness). Load-bearing absence claims need ≥ 2 independent tools; I hedge residual uncertainty as "not demonstrable in the available indices".

**Verification levels** — every source-based claim carries one: *deep-read* (full text read by me, passages verified — high trust) · *abstract* (summary only — medium) · *agent-reported* (your synthesis, not personally cross-read — low, provisional) · *aggregator-only* (snippet — not load-bearing). Levels persist: several agent-reported findings never merge into deep-read.

## Stage 3 — Before drafting: coding and analysis

Gate: every hit still *agent-reported* or *aggregator-only* is upgraded (deep-read) or dropped from load-bearing arguments.

**4. Lexicon Stability [Both].** The terms naming source items must not drift silently between stages — analytical (intake → coding → synthesis) or linguistic (source-language notes → target-language draft). A term change is a decision, not a translation.
Apply: prefer descriptive-actional names; defer typological labels until justified ("lasso-thrower" before "cowboy"). No articulable reason → roll back. Source-language terms survive only as marked quotes: target-language gloss primary, source term italicised in parentheses. You run a mechanical target-language sweep (regex over out-of-language diacritics) before publication — independently of my re-reading.

**5. Frame Plurality Check [Both].** Before a connotation or cultural-significance reading is assigned, two-to-three alternative readings are enumerated; the default is chosen consciously, not by first association.
Apply: you enumerate the alternatives and note which are excludable on source-internal grounds (context, genre, audience). I make the interpretive choice, mark it as *chosen against* the alternatives, and log them. My own cultural alignment with a reading demands extra scrutiny, not a skipped step.

## Stage 4 — While drafting

**6. Composition Drift [Both].** My memory of a source drifts over long composition windows (roughly two hours and beyond).
Apply: you diff every direct quotation verbatim against the source. I track the clock: after ~2 hours away from a source, claims resting on it are re-anchored against the source itself — never against a later draft state. Every "this artefact shows X" claim gets a re-check flag that persists until re-inspection.

## Stage 5 — Before publishing

**7. Descriptive Accuracy [Human].** Empirical claims about artefacts ("this image shows X", "this emoji is Z") are verified directly against the source — not from memory, not from a tool-rendered view.
Apply: I re-inspect the artefact myself — images at native resolution, text compared against a pasted verbatim original, emoji by Unicode codepoint. Your view of an artefact *is* the tool-mediated approximation this pattern corrects; the direct look cannot be delegated to you.

Then run the three-part re-check as its own step: quotations vs. original sources; "shows X" claims vs. the artefacts; a self-read of the freshly rendered final draft. For author-voiced texts only (essays, op-eds, public commentary, documentation with normative claims), add three audits:

**8. Verb Audit [Both].** Covertly asymmetric constructions — "fails to", "has not yet", "still hasn't", "refuses to" — smuggle my frame in as the implicit measure.
Apply: you flag *fail, not yet, still, refuse, neglect, omit, ignore* and equivalents. Per hit I either declare the measure ("by the standard of X …") or use a neutral verb — the smuggle stands in neither form.

**9. Addressee Audit [Both].** The pronoun pattern (*we/you* vs. *they/it*) positions the reader.
Apply: you map who *we/our/us* includes and whom *they/them* discusses. I judge whether that coalition is intended; if it is default, I neutralise it or declare it.

**10. Discrediting-Frame Inoculation [Both].** Texts drawing on critical-theoretical traditions (ideology critique, Frankfurt-School concepts, discourse analysis, post-colonial theory) cite the tradition preemptively by name — author, title, year — before a discrediting frame ("Cultural Marxism", "woke ideology") can be applied.
Apply: you propose exact citation details; I verify them against the source before use — AI-proposed names, titles and years are a known fabrication risk. I decide whether and how to cite, in the running text, without paraphrasing the tradition into anonymity.

---

The reasoning (*Why*) behind each rule and the documented failure cases grounding it live in the four full protocols: source, interpretive-frame, writing, actant self-check.
Not covered here: tool fidelity (tool protocol) and the three meta-protocols — falsification, provenance, read-write boundary — the advanced set.
