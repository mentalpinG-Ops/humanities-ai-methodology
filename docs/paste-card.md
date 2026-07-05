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

# Working with an AI on a real text — our session card

You know these moments: the AI cites a book nobody can find. A quote looks right but reads differently in the original. Three hours into writing, your draft says something the source never said. This card is the set of guardrails against exactly those moments. I paste it at the start of our session; we follow it together.

**How to read the arrows:** → **AI:** is your part (mechanical work — fetching, comparing, listing, flagging). → **Me:** is my part (reading, judging, deciding). Nothing on this card is yours alone to decide; the final call is always mine. *(One item is marked mine alone.)*

## Step 1 — Two minutes of setup

I tell you: which search tools we'll use, what language the final text is in, and that I'm keeping a small running note of naming decisions (which word we chose for a thing, and why). That note is our memory.

## Step 2 — While we gather sources

**1. The preview is not the source.** Search results and AI summaries show fragments — truncated, outdated, sometimes from ad copy rather than the original.
→ **AI:** fetch the full text and compare the exact wording; if they differ, the full text wins.
→ **Me:** I read it myself before we build anything on it. If the full text can't be reached, the fragment keeps its "unchecked" label — we never treat it as evidence, and if it must be mentioned, we say openly that it is unverified. *(Snippets ≠ Primary)*

**2. "Someone wrote about it" is not the thing itself.** A blog post about a study is not the study; a brochure quoting a newspaper is not the newspaper. Copies drift — sometimes deliberately, when promotional material polishes a quote until it says something better than the original did.
→ **AI:** for every source, say out loud what kind it is — the original, a description of it, or a description of a description — and name where the original should be found.
→ **Me:** if we can't reach the original, we say so in the text instead of quoting the copy as if it were the original. *(Secondary ≠ Primary)*

**3. "I found nothing" doesn't mean "it doesn't exist."** Search tools have gaps: paywalls, other languages, missing indexes, stale caches.
→ **AI:** when a search comes up empty, report it precisely — which tool, which exact search words, what date — and name what might have hidden it.
→ **Me:** before we claim something doesn't exist, we try at least two different tools; in the text I write "we could not find it", not "there is none". *(Search-Absence ≠ Proof-of-Absence)*

**Our trust labels.** Every source we use carries one, and it sticks until *I* change it by reading:
**read-it-myself** (safe to build on) · **summary-only** (I read only an abstract) · **AI-told-me** (you summarised it; I haven't read it — not safe to cite yet) · **preview-only** (a fragment — never cite). Ten AI summaries never add up to one read text.

## Step 3 — Before I start writing

**The gate:** anything still labelled *AI-told-me* or *preview-only* either gets read by me now — or it stays out of the argument.

**4. Watch our words for quiet shifts.** Early on we called the figure in the photo "a person throwing a lasso"; three drafts later it's "a cowboy". That switch smuggles in a whole interpretation — and nobody decided it.
→ **AI:** flag it whenever a name for the same thing changes between work stages, and before we finish, sweep the text for leftover foreign-language words (a mechanical check — run it even if I feel sure).
→ **Me:** every renaming needs a reason I can say out loud; no reason, we go back to the earlier plain word. Foreign terms appear only as marked quotes: my wording first, the original in italics in brackets. *(Lexicon Stability)*

**5. The first interpretation that comes to mind is not the only one.** A folded-hands emoji: prayer? thanks? a polite sign-off? Whichever reading feels obvious to me probably just matches my own background.
→ **AI:** before we fix a meaning, list two or three other plausible readings and note whether the text itself rules any of them out.
→ **Me:** I choose — and I write down that I chose it *against* the alternatives, so a reader (and future me) can see it was a decision, not a fact. *(Frame Plurality Check)*

## Step 4 — While I write

**6. My memory of the source drifts as I write.** After a couple of hours, I'm quoting my own draft, not the source — confidently and wrong.
→ **AI:** re-compare every direct quote in the draft against the source text, word for word, whenever I ask — and remind me if two hours have passed.
→ **Me:** every claim of the kind "the picture/text shows X" gets a little flag in the draft; the flag stays until I've looked at the original again. *(Composition Drift)*

## Step 5 — Before it goes out

**7. Look at the thing itself — this one is mine alone.** Whatever you tell me about an image or a document is itself a description, and descriptions of images are exactly where the famous mistakes happen (the hat that belonged to a different figure).
→ **Me:** I open the image at full size, put the original text next to my quote, check the actual emoji character — with my own eyes. This is the one step I cannot hand to you, because your view of the artefact is the thing being double-checked. *(Descriptive Accuracy — [Human])*

Then one last pass, three quick rounds: quotes vs. originals · "shows X" sentences vs. the artefacts · a fresh read of the final layout. And if the text speaks in my voice — an essay, an opinion piece, a public post — three more checks:

**8. Words that judge while pretending to describe.** "The museum *still hasn't* responded" sounds like a fact but carries a verdict — *by whose deadline?*
→ **AI:** flag every "fails to", "still hasn't", "refuses to", "ignores" and the like.
→ **Me:** for each one I either name the standard openly ("measured against X…") or switch to a neutral verb. Hidden verdicts stay out either way. *(Verb Audit)*

**9. Who is "we"?** Every "we must…" pulls the reader onto my team without asking; every "they" pushes a group away.
→ **AI:** map the we's and they's — who's included, who's talked about.
→ **Me:** if I didn't choose that team-building on purpose, I rewrite it neutrally — or state openly whom I'm speaking for. *(Addressee Audit)*

**10. Name the school of thought before someone weaponises it.** If my text uses ideas from a tradition that gets smeared in public debate (critical theory and its relatives), vague borrowing invites the smear.
→ **AI:** suggest the exact reference — author, title, year.
→ **Me:** I check every suggested name and year against the source before it goes in (invented references are a known AI failure), and I cite the tradition openly in the running text, by name — scholarship engaged is harder to smear than influence smuggled. *(Discrediting-Frame Inoculation)*

---

Every rule above was distilled from a documented, real mistake — the stories and the reasoning live in the four full protocols: source, interpretive-frame, writing, actant self-check.
Not covered here: checking your tools themselves (encoding, OCR, file readers) and the three advanced self-audit protocols — falsification, provenance, read-write boundary.
