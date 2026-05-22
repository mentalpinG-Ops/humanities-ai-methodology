# Source Discipline

*β module. Status: working-draft 2026-05-21. Audience: humanities scholar.*

---

## 1. Position

In AI-assisted humanities research, most source encounters happen through tools that return *snippets*, *abstracts*, *aggregated summaries*, or *search-agent reports*. These are not sources. They are *pointers to sources*. A methodology that aims to meet humanities-scholarly standards cannot treat the distinction between the tool-filtered representation and the source itself as an after-the-fact conscience correction. It must operate as a working discipline — visible in the workflow, checkable in the output, auditable after publication.

Three patterns are robust enough across documented failure modes to be named separately. Together they constitute the Source Discipline.

---

## 2. The Three Patterns

### 2.1 Snippets ≠ Primary

**Rule.** Search snippets — from Google, Consensus, Semantic Scholar, Perplexity, an AI assistant's web-search tool, or any equivalent — are not primary-source attestations. Before a snippet becomes load-bearing (cited, used in an argument, presented to others), the full text must be opened and the quoted passage verified verbatim.

**Why.** Snippets are algorithmically generated from indexed representations. They can:
- come from older or non-final versions
- come from marketing material or secondary descriptions rather than the original
- be syntactically truncated in ways that flip the polarity of the claim
- come from cache snapshots that are stale relative to the live source

These failure modes recur across tool generations. An AI-agnostic methodology cannot rely on better models to fix the problem — the snippet layer itself is the source of imprecision.

**How to apply.**
- Before use, retrieve the full text (publisher, paywall, repository, Wayback Machine).
- Compare the verbatim passage against the snippet.
- If they diverge, discard the snippet and anchor on the full text.
- If the full text is unreachable, tag the snippet as *"pointer, unverified"* — do not treat as attestation.

### 2.2 Secondary ≠ Primary

**Rule.** A secondary source (a description of a primary source) is not the primary source. Every source tag must declare the level: primary (the original), secondary (a description), tertiary (a description of a description).

**Why.** A specific failure class is *promoter amplification*: marketing, promotional, or intermediary material circulates a modified version of an original verbatim quote and stabilises the modification through repetition. A scholar who consumes the circulated secondary text and treats it as original attestation absorbs the modification invisibly — and, by citation, passes it on to others.

Empirical case: marketing material for a travelling exhibition in Poland attributed to a Vatican daily the phrase *"wspaniały hymn" (great hymn)*. The original daily had written *"hołd dla ciała" (tribute to the body)*. *"Hymn"* is the promoter amplification; *"hołd"* is the original. A scholar who cites the promotional text as primary, without flagging it as secondary, propagates the amplification as if it were the original claim.

**How to apply.**
- Make the source level (primary / secondary / tertiary) a required field of the source tag.
- For secondary sources: what is the claimed primary, and is it independently accessible?
- When promoter amplification is plausible: locate original language, original publication venue, original date.
- If the original cannot be verified, do not use the text as primary attestation; mark the secondary status explicitly in the output.

### 2.3 Search-Absence ≠ Proof-of-Absence

**Rule.** A negative search result does not mean *"does not exist"*. It means *"not found in [tool] with [query] on [date]"*. This distinction must remain visible in source tags and in argument structures alike.

**Why.** Search tools have indexing gaps, operator mismatches, paywall barriers, language-corpus limits, version caches, and regional filters. An unsuccessful search may reflect any of these. Inferring *"does not exist"* from *"not found"* promotes the search tool from a pointer-giver to a complete index — a status no available tool legitimately fulfils.

**How to apply.**
- Record the negative result verbatim: tool, full query (operators included), date, hit count.
- Make the possible reasons explicit: indexing gap / operator mismatch / paywall / language corpus / cache staleness.
- For load-bearing use, run ≥ 2 independent search tools, ideally with different corpora.
- For residual uncertainty, hedge: *"not demonstrable in the available indices"* rather than *"does not exist"*.

---

## 3. Verification Levels

Every source-tagged claim carries an additional *verification level*. This is not a separate discipline but the operational consequence of the three patterns:

| Level | Meaning | Source trust |
|---|---|---|
| **deep-read** | full text read; relevant passages verified verbatim | high |
| **abstract** | abstract or summary read; full text not opened | medium |
| **agent-reported** | AI/agent synthesis from the full text; not personally cross-read | low (provisional) |
| **aggregator-only** | snippet or aggregator hit only; no full text | not load-bearing |

Verification levels apply **not only** at the brief or research stage but **also at later synthesis stages**. When an agent report enters a publication later, its `agent-reported` status remains until full-text cross-reading occurs. A synthesis of multiple `agent-reported` findings does not aggregate into `deep-read`.

---

## 4. Failure-Mode Gallery

The discipline is grounded in documented failure modes, not prophylactic abstraction. Three cases:

- **Snippet-cascade failure** (administrative-document forensic-analysis case study). A search snippet from an administrative secondary source was treated as primary attestation; downstream synthesis stabilised the inaccuracy through several editorial stages. Methodology lift: an explicit cascade-risk audit step (separately codified).

- **Promoter amplification *hymn* vs. *hołd*** (Body-Worlds Wrocław travelling exhibition). Promotional secondary text treated as original Vatican attestation. Direct lift to Pattern 2.2.

- **Agent-report synthesis drift** (knowledge-representation lab). Aggregated agent searches were synthesised without per-source verification level; the synthesis stage must re-check verification level, not assume it carries through. Methodology lift: Pattern 3 plus a dedicated verification-level rule.

Each case shows: source discipline addresses dated, observable failure modes — not generic best practice.

---

## 5. Operationalisation in the Workflow

Source discipline is not a source-tag collection alone. It is a workflow position:

- **Before research starts:** declare the tool set (search engines, aggregators, AI search agents) and the verification plan.
- **During research:** classify every hit per Pattern 2.1 / 2.2 / 2.3; tag the verification level.
- **Before synthesis:** every hit tagged `agent-reported` or `aggregator-only` must either be upgraded (deep-read) or removed from load-bearing arguments.
- **Before publication:** pre-publication re-check against the original source, not against a later composition stage (see `writing-discipline.md` §Composition Drift).
- **After publication:** preserve the audit trail — which source tags were set at which stage, which verification levels were load-bearing.

---

## 6. What This Discipline Does **Not** Provide

- It makes no claim about the *intellectual quality* of a primary source. A verbatim-verified source can still be wrong, biased, or methodologically problematic. Source discipline guarantees only that the source is what it appears to be — not that it is fit for purpose.

- It does not replace **writing discipline** (descriptive accuracy when describing artefacts, composition drift in longer texts). Source discipline protects the source intake; writing discipline protects the text output. Both are required.

- It does not replace **actant self-check** (the analyst's own positionality in the reading act). Source discipline makes *sources* checkable, not the *reading act* itself.

---

## 7. Cross-Refs

- [[writing-discipline]] — descriptive accuracy plus composition drift; observation fidelity at text output.
- [[actant-self-check]] — verb audit, addressee audit, CMF inoculation; positionality of the analytical act.
- [[tool-discipline]] — empirical tool validation as a methodology extension.

---

*Versioning: working-draft. Substantial structural re-articulation (e.g., after additional case-study evidence or reader feedback) triggers a status update. Inline patch edits do not trigger a version bump.*
