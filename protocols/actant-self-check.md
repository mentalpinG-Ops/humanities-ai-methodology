---
name: Actant Self-Check
version: 0.1.0
status: draft
last_changed: 2026-06-17
---

# Actant Self-Check

*Methodology module. Audience: humanities scholar.*

---

## 1. Position

When a humanities scholar writes a text with positional voice — an op-ed, an essay, a critical commentary, a public-repository document, a thread — the writing acts on the reader: it includes, excludes, asks, normates, demands. The author is an *actant* in the text, not just an observer of the artefact under analysis. The actant self-check is a protocol of bringing the author's own positional acts into view before publication, so that they can be revised deliberately rather than smuggled in.

The protocol is *scoped*: it applies to author-voiced texts. It does not apply to purely descriptive-operational outputs — code edits, repository listings, memory writes, audit logs. These have no positional voice in the relevant sense; subjecting them to actant self-check is a mis-scoped over-application.

Three audits, executed before publication.

---

## 2. The Three Audits

### 2.1 Verb Audit

**Rule.** Mark covertly asymmetric verb constructions — *"fails to"*, *"has not yet"*, *"still hasn't"*, *"refuses to"*, *"neglects to"*. These constructions presuppose a normative measure that the subject does not meet, with the author's own frame as the implicit measure.

**Why.** Asymmetric verbs do work in the background. *"The institution fails to address X"* asserts both that the institution has not addressed X and that X is an obligation the institution holds — but only the first is empirical; the second is the author's normative claim, presented as if it were given. A reader who shares the author's frame absorbs both as facts; a reader who does not absorbs only the first and reads the second as overreach. The author rarely notices the smuggle because the frame feels natural from inside.

**How to apply.**
- Search the draft for *fail*, *not yet*, *still*, *refuse*, *neglect*, *omit*, *ignore* and equivalents.
- For each occurrence, check whether the normative measure is declared or implied.
- If implied, either declare it (*"by the standard of X, the institution has not addressed Y"*) or replace the verb with a non-asymmetric one (*"the institution has not addressed Y"*).
- The choice between declaration and neutralisation is rhetorical, but the smuggle is not acceptable in either case.

### 2.2 Addressee Audit

**Rule.** Identify who the text addresses (the *we / you* of the author's voice) and who the text discusses as a third-person object (*they / them / it*). The inclusion-exclusion pattern in pronouns frames the reader's position relative to the discussed subject.

**Why.** Pronouns are positional. A text that says *"we must reconsider how they have treated this issue"* places the reader inside the author's coalition (*we*) and the discussed group outside it (*they*) — a positioning the reader may or may not have consented to. A text that says *"the issue raises questions about how it has been treated"* is positionally neutral. Neither phrasing is wrong, but the first commits the reader rhetorically; the second does not. Authors regularly choose the first without registering the choice.

**How to apply.**
- Map the text's pronouns: where does *we / our / us* appear, and who is included?
- Where does *they / them / their* appear, and who is the discussed group?
- Is the inclusion-exclusion pattern intentional, or default?
- If default and the author has not consciously consented to it, revise to neutral phrasing or declare the coalition explicitly.

### 2.3 Discrediting-Frame Inoculation

**Rule.** When the text engages with critical-theoretical material — ideology critique, Frankfurt-School concepts, discourse analysis, post-colonial theory — preemptively cite the established academic tradition by name (verbatim author, title, year) before the discrediting framing that targets that tradition can be applied.

**Why.** Critical-theoretical work is the target of established discrediting frames in popular and right-wing-political discourse: *"Cultural Marxism"*, *"woke ideology"*, *"Critical Race Theory as conspiracy"*. The frame's effect is to delegitimise the author by labelling the tradition as a foreign-import threat rather than as an academic field. The defence is empirical: cite the tradition openly, by name, with bibliographic specificity. The discrediting frame relies on the author *smuggling* critical theory in without naming it; explicit citation removes the smuggle and forces critics either to engage the academic tradition or to discredit visible scholarship by name (a harder rhetorical move).

This pattern is named *Discrediting-Frame Inoculation* because the dynamic generalises beyond Cultural-Marxism specifically: any tradition that is the target of a discrediting frame benefits from the same defence — preemptive named citation rather than tacit invocation.

**How to apply.**
- Identify which critical traditions the text draws on.
- Cite them by name in the text, not only in footnotes: *"following Adorno (1951)"*, *"per the DISS framework on neo-right discourse"*, *"in the Frankfurt-School sense of culture industry"*.
- Use verbatim titles and dates where load-bearing; do not paraphrase the tradition's contribution into anonymity.
- The citation is rhetorical as well as bibliographic: it announces that the tradition is here and that the author engages it as scholarship.

---

## 3. When Actant Self-Check Applies

Scoping is part of the protocol:

| Text type | Actant self-check | Why |
|---|---|---|
| **Op-eds, essays, public commentary** | required | author-voiced, positional, reader-affecting |
| **Public-repo documentation with normative claims** | required | the documentation positions readers and users |
| **Threads, social-media posts on substantive topics** | required | author-voiced even if short |
| **Methodology documents (like this one)** | required | normative claims about how to work |
| **Code edits, repo listings, log entries** | not applicable | no positional voice |
| **Memory writes, audit notes** | not applicable | descriptive-operational |
| **Private notes** | optional | depends on whether they will later be lifted into public material |

The boundary is positional voice. A text that asserts how things should be read, who should act, or what counts as legitimate is in scope. A text that records what happened is not.

---

## 4. Failure-Mode Gallery

The protocol was lifted from concrete patterns in published material:

- **Verb-audit deferred.** Op-ed contained constructions like *"the exhibit has not yet been recognised as ..."* — a deferred-recognition framing that smuggled the author's normative measure as a temporal claim. Recognised post-publication; lift to methodology yielded Pattern 2.1.
- **Addressee-coalition smuggle** (op-ed drafts, pre-revision). Inclusive *we* references did not match the actual readership of the publication venue. Caught in pre-publication revision, but only because reader feedback flagged it; the author had not registered the choice. Lift to Pattern 2.2.
- **Discrediting-Frame exposure** (op-ed, anticipatory). The text engaged Critical Theory without explicit citation; the discrediting frame could plausibly have been applied. Preemptive citation protocol added before publication as a prophylactic; lift to Pattern 2.3 as a generalised pattern.

The protocol is the methodology lift from these cases. It is not a stylistic preference.

---

## 5. Operationalisation in the Workflow

Actant self-check is a discrete pre-publication stage:

- **During composition:** tag passages with positional voice (*we*, *they*, asymmetric verbs, tradition references) as they appear. The tags persist into revision.
- **At revision time:** run the three audits in sequence — verb audit, addressee audit, inoculation audit.
- **Document the choices:** where positional choices are deliberate, note them (in a checklist file, an audit log, or a draft footnote). The next reader of the methodology should be able to see that the choices were made, not assumed.
- **After publication:** if positional issues surface in reader feedback, lift them as failure-mode entries.

---

## 6. What This Protocol Does **Not** Provide

- It does not address whether the *claims* in the text are correct (see [source protocol](source-protocol.md) for source intake; [writing protocol](writing-protocol.md) for descriptive accuracy).
- It does not police the author's politics or normative commitments. The audits make the commitments *visible* and *declarable*, not different.
- It does not apply to purely descriptive-operational outputs (per §3 scoping). Applying it there is a mis-scoped over-application.
- It does not provide a guarantee against being misread; it provides a guarantee against being unfairly misread on grounds the author could have anticipated.

---

## 7. Cross-Refs

- [source protocol](source-protocol.md) — source intake; orthogonal layer.
- [writing protocol](writing-protocol.md) — descriptive accuracy; orthogonal layer.
- [tool protocol](tool-protocol.md) — tool fidelity; unrelated layer.

---

*Versioning: working-draft. The Discrediting-Frame Inoculation pattern is currently named generically rather than tied to a single discrediting frame; future case-study evidence may justify naming additional inoculation sub-patterns. Substantial structural re-articulation triggers a status update. Inline patch edits do not.*
