---
name: Addressee Map
status: draft
last_changed: 2026-07-05
derived_from:
  - protocols/source-protocol.md @ 0.1.0
  - protocols/interpretive-frame-protocol.md @ 0.1.0
  - protocols/writing-protocol.md @ 0.1.0
  - protocols/actant-self-check.md @ 0.1.0
staleness_rule: >
  If any protocol listed under derived_from bumps its version, this map is
  stale and must be re-judged by a human. The assignments below are
  judgements, not derivations — automation may flag this file stale, but
  must never rewrite an assignment.
---

# Addressee Map — who acts on each pattern: you, or your AI?

The protocols describe *what must hold* for responsible AI-assisted work. This
map answers the question the protocol texts leave open: **for each pattern, who
performs it — the human author, the AI assistant, or both together?**

It is a *sidecar*: the protocol files themselves are versioned and frozen; this
map layers the addressee information on top without editing them.

## The three tags

| Tag | Meaning |
|---|---|
| **[Human]** | A judgement or act only the author can perform. Delegating it to the AI defeats the pattern's purpose. |
| **[AI]** | A mechanical check the AI or tooling performs on its own; the human reviews exceptions only. *(Currently unused — kept for future bundles where a check may run fully mechanically.)* |
| **[Both]** | The AI carries the mechanical part (searching, comparing, enumerating, flagging); the author makes the final call. |

**Headline finding:** as of this version, **no pattern is fully delegable to
the AI.** Every pattern keeps the final call with the human; what varies is how
much of the mechanical work the AI can carry. If you paste the protocols into
an AI session, you are not handing the method over — you are equipping the AI
to carry its share of it.

## The map (pipeline protocols)

| Pattern | Tag | Division of labour |
|---|---|---|
| Source §2.1 — *Snippets ≠ Primary* | **[Both]** | AI retrieves the full text and compares the passage verbatim — but AI comparison alone yields only `agent-reported` status; before a source becomes load-bearing, the human cross-reads it personally (`deep-read`). |
| Source §2.2 — *Secondary ≠ Primary* | **[Both]** | AI proposes the source-level tag; the human confirms it — declaring the level (primary/secondary/tertiary) is a required field on *every* source tag, with extra scrutiny where amplification is plausible. |
| Source §2.3 — *Search-Absence ≠ Proof-of-Absence* | **[Both]** | AI must phrase negative results correctly ("not found in [tool] with [query] on [date]"); the human checks how absence is used in the argument. |
| Interpretive-Frame §2.1 — *Lexicon Stability* | **[Both]** | The mechanical target-language sweep is delegable and *should* run independently of authorial review (regex, pre-commit); every term-change decision and its stated reason is the human's. |
| Interpretive-Frame §2.2 — *Frame Plurality Check* | **[Both]** | AI enumerates two-to-three alternative readings; choosing the default reading is the analyst's interpretive judgement. |
| Writing §2.1 — *Composition Drift* | **[Both]** | AI can diff every quotation verbatim against the source; tracking composition windows and triggering the re-check is the author's discipline. |
| Writing §2.2 — *Descriptive Accuracy* | **[Human]** | Re-inspect the artefact directly, at native resolution. The AI's view *is* the tool-mediated approximation this pattern corrects — the direct look cannot be delegated to it. |
| Actant §2.1 — *Verb Audit* | **[Both]** | AI marks covertly asymmetric verb constructions mechanically; declaring the measure vs. neutralising the verb is the author's rhetorical decision. |
| Actant §2.2 — *Addressee Audit* | **[Both]** | AI maps the pronoun pattern (*we/they*); whether the coalition-building is intended is the author's call. |
| Actant §2.3 — *Discrediting-Frame Inoculation* | **[Both]** | AI *proposes* citation details (author, title, year) — the human verifies them against the source before use, since AI-proposed proper nouns are a documented fabrication risk; whether and how to cite the tradition is the author's voice decision. |

## Scope

This map covers the four pipeline protocols (the beginner set distilled into
the Paste-Card). The tool protocol and the three meta-protocols
(falsification, provenance, read-write boundary) will be added when their
delivery bundles exist; their patterns are meta-level and predominantly
**[Both]** with the same human-final rule.
