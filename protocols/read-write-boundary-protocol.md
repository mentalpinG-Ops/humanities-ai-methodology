---
name: Read-Write Boundary Protocol
version: 0.1.0
status: draft
last_changed: 2026-06-29
---

# Read-Write Boundary Protocol

*Methodology module. Audience: humanities scholar.*

---

## 1. Position

In AI-assisted scholarly work, the durable artefacts of a project — decision records, continuity notes, glossaries, review verdicts, status fields, bibliographies — are written and rewritten by two kinds of agent: the researcher, exercising judgement, and an automated step (a script, a linter, an assistant) deriving facts. When the two write into the same artefact without a declared boundary, two opposite failures follow. Either the automated step overwrites something only the researcher was entitled to decide (a judgement, an attestation, a rationale), or the researcher maintains by hand something a machine could derive — and it silently drifts out of date.

The other protocols in this repository do not address this. Provenance protocol tracks *where an idea came from*; it does not say *which fields of an artefact a human must author versus a machine may compute*. Tool protocol tracks whether a tool faithfully read or wrote a file; it does not say whether the tool was *entitled* to write that field at all. Falsification protocol tests whether a claim could be wrong; it does not test whether a still-displayed claim has quietly outlived the premises it was decided under.

The Read-Write Boundary protocol fills that gap. It is a *meta-level* protocol on a third audit axis: where falsification asks *"could this be wrong?"* (validity) and provenance asks *"where did this come from?"* (origin), this protocol asks *"who or what may write this field, and when must a stale decision be forced back to a human?"* (authority and currency). Its purpose is twofold:

1. **A field-level write-contract.** Every field of a durable artefact is assigned to one of four classes that fix who may write it. The contract makes explicit what is usually only an implicit habit, so that automation can be trusted with the derivable parts without ever silently rewriting the judged parts.
2. **Currency through invalidation, not vigilance.** A judgement recorded under a set of premises must not keep counting as valid after those premises change. The protocol makes the standing of a judgement depend on its premises mechanically — by *invalidating* (forcing re-decision) rather than by the researcher remembering to re-check.

The protocol does not mechanise the judgements themselves. It governs *who may write each field and when a judgement expires* — not *what the judgement should be*.

---

## 2. The Three Patterns

### 2.1 The Four Field-Classes

**Rule.** Every field of a durable project artefact is assigned to exactly one of four write-classes, and the assignment fixes what an automated step may do to it:

- **COMPUTED** — derivable from other state. An automated step derives it and *overwrites it on every run* (e.g. a "last-checked" flag, an aggregated verdict, a cross-reference resolution, a count).
- **MECHANICAL** — bookkeeping that changes only when derived output changes (a version bump, a superseded-by pointer, an updated-at timestamp). An automated step may write it, but only on a real change; a human may refine it before it is finalised.
- **HUMAN** — a judgement, an attestation, a rationale, a decision. An automated step *must never author or alter it*. It may, where the rule below permits, *void* it — but it never writes its content.
- **EXTERNAL** — outside the automation's trust boundary entirely: a person's identity, a signature, the act of sending, publishing, or committing. The automation may prepare the thing to be signed or sent; it never holds the key and never performs the act.

**Why.** Most artefact drift and most over-reach come from an *unstated* field-class. When the class is left implicit, an assistant "helpfully" edits a rationale (over-reach into HUMAN), or a researcher hand-maintains a value a script could derive (under-automation of COMPUTED), and neither error is visible until it has propagated. Naming the class per field converts a vague "be careful here" into a checkable contract: each field has exactly one writer-of-record and one rule for automation. The four classes are exhaustive for the artefacts a scholarly project actually keeps; a field that seems to belong to two classes is usually two fields that should be separated.

**How to apply.**
- When designing any new durable artefact type (a record format, a header convention, a review schema), classify each field COMPUTED / MECHANICAL / HUMAN / EXTERNAL *before* it is first used. Write the classification into the artefact's own spec or governance note.
- For existing artefacts, classify on first edit. The fastest diagnostic question per field: *"If I deleted this value, could a script regenerate it correctly from other state?"* Yes → COMPUTED (or MECHANICAL if it only changes on a real edit). No, it took a judgement → HUMAN. It is an identity/signature/send → EXTERNAL.
- Treat a field that "needs a human to confirm what the script proposed" as MECHANICAL (machine drafts, human finalises) — not as a blurred HUMAN/COMPUTED hybrid.

### 2.2 Invalidate, Never Author

**Rule.** An automated step may compute facts and may **invalidate** a human judgement — marking it stale and forcing a re-decision — but it must **never author or alter** the content of a HUMAN-class field. When it invalidates, it flags the judgement and leaves the original value in place for the audit record; it does not delete, rewrite, or guess a replacement. A judgement that has been invalidated no longer counts as current until a human redecides.

**Why.** This is the single safety property that lets automation be trusted near judgement at all. If a script could rewrite a rationale or flip an attestation, no recorded judgement would be reliable — the researcher could never be sure a displayed decision was theirs. If, instead, the script's only powers over a judgement are *compute-adjacent-facts* and *force-me-to-look-again*, then automation strengthens the record instead of corrupting it: it can catch that a decision's premises moved and *make the researcher re-decide*, without ever putting words in the researcher's mouth. Keeping the stale value visible (flagged, not erased) preserves the audit trail — the history of what was decided, and that it was superseded, is itself evidence.

**Why a premise-change must invalidate.** A judgement is made under premises — the inputs, sources, or prior decisions it depended on. When those change, the judgement's standing is in question, but the working text still *displays* the old conclusion. Without invalidation, the stale conclusion is inherited silently across the change and misleads everyone downstream (including the researcher, days later). Binding a judgement's currency to its premises — so that a premise-change flips it to "re-decide" — is what converts "I should remember to re-check this" into a property of the artefact.

**How to apply.**
- Record, with each recorded judgement, the premises it was decided under — by *naming* them (the sources, the prior decisions, the inputs), not merely by date. "Decided given X and Y" is checkable; "decided on the 14th" is not.
- At natural checkpoints (session start, review, milestone), test whether any named premise has moved. If it has, mark the judgement stale and re-decide; do not carry it forward unread.
- When automation does the checking, restrict it to two moves: compute whether a premise changed, and set a *stale* flag. It must not edit the judgement's text. The re-decision is the human's.
- Keep the superseded judgement in the record, flagged, not deleted. Erasing it loses the audit trail the next pattern and the provenance protocol both rely on.

### 2.3 A Hand-Maintained Derived Field Is a Drift Bug

**Rule.** A field that is mechanically derivable from other state (a COMPUTED field) must not be maintained by hand. If a value can be computed, computing it by vigilance — remembering to update it each time its inputs change — is treated as a defect to be removed, not as a normal working practice. Where a derivation is not yet automated, the field is flagged as owed-an-automation, and the manual upkeep is named as interim, not endorsed.

**Why.** Hand-maintained derived fields are the most common and least visible source of drift. A count that says "seven" after an eighth item was added; a "version 1.0" stamp left on an artefact whose schema moved to 2.0; a cross-reference that was supposed to be updated everywhere a decision was amended but was updated in only one place. Each is a value that *looks* authoritative and *is* wrong, because a human was relied upon to propagate a change a machine could have propagated. The drift is invisible precisely because the field still displays a plausible value. Naming hand-maintained derivation as a *bug* — rather than as diligence — is what licenses removing it: the goal is to derive the field, or, until then, to mark it as provisional and owed.

A second, subtler case: the *enumeration* and the *audit-clause*. When a process is described both by a hand-written list ("update files A, B, C") and by a rule that defines the true scope ("update every file that cites the amended decision"), the rule is authoritative and the list is a seed. Treating the hand-written enumeration as complete is the same drift bug at the level of a procedure: the derived set, not the enumerated one, is the standard.

**How to apply.**
- For each COMPUTED field, prefer a derivation (a script, a lint, a query) over manual upkeep. The derivation need not be elaborate — a check that recomputes the value and compares is enough.
- Where no derivation exists yet, mark the field as owed-an-automation and its current value as provisional, so a reader knows it is a known drift risk rather than a guaranteed fact.
- When a change has derived consequences across multiple files (an amended decision, a renamed term, an added module), propagate by the *rule* ("everywhere this is cited"), not by a remembered list. Verify the propagation by recomputing the set, not by recalling it.
- Resist the inverse temptation to over-automate: only fields that are genuinely derivable are COMPUTED. A judgement is not made COMPUTED by wishing it were cheaper (see §6).

---

## 3. Operationalisation in the Workflow

The protocol integrates into existing workflows rather than requiring separate tooling:

- **When designing a new durable artefact type:** classify every field (§2.1) in the artefact's spec before first use. This is the cheapest moment; retrofitting classification after drift has appeared is more expensive.
- **At session-start (read-time invalidation):** for the judgements you are about to rely on (a continuity note's next-step, a prior decision, a review verdict), check their named premises (§2.2). If a premise moved, re-decide before building on it; do not inherit the stale conclusion.
- **During the session:** as you record a judgement, name its premises. As automation derives facts, confine it to COMPUTED/MECHANICAL fields; never let it author a HUMAN field.
- **At session-end (write-time invalidation):** for every artefact this session touched, ensure each HUMAN judgement is either refreshed or explicitly flagged stale. A touched-but-not-updated judgement is a drift bug, not a tidy default — catching it at write-time, while the change is fresh, is far cheaper than discovering it as staleness at the next read.
- **At milestones and amendments:** when a decision is amended or an item added, propagate the derived consequences by rule and recompute the affected set; do not trust a remembered enumeration (§2.3).

The protocol requires no separate file *if* the artefact's existing spec or governance note can carry the field-class table and the premise-naming convention. For artefacts without such a note, a minimal classification block at the artefact's head serves the purpose.

---

## 4. Failure-Mode Gallery

Three failure modes the protocol guards against, drawn from observed patterns in AI-assisted scholarly work. Each is described generically; all are recoverable only with the protocol's before-the-fact discipline.

- **The stale continuity note.** A project keeps a short "where I left off / what's next / what's blocking" note at the head of its task file. One working session shifts the project's active front but updates only the body of the task file, not the head note. At the next session the head note confidently points at the *previous* front; the researcher follows it and loses time before noticing the newer work. The note was a judgement (the next-step) whose premise (which front is live) had moved, inherited silently across the change. *Lift: Pattern 2.2 (name the premise; invalidate on change) + 2.1 (the next-step is HUMAN, the staleness-flag is COMPUTED).*

- **The drifted version stamp.** A set of artefacts each declares the schema version it conforms to. The schema is revised; the artefacts are not re-stamped, because re-stamping was a manual step nobody owned. Months later every artefact displays a version it no longer matches, and a reader trusts the stamp. The declared-version field was COMPUTED (derivable from the schema-conformance check) but maintained by hand. *Lift: Pattern 2.3 (a derivable field maintained by vigilance is a drift bug).*

- **The un-propagated amendment.** A decision record is amended by a later one. The amendment is noted in the new record, but the several other documents that cited the old decision are not updated — because the update depended on someone remembering each citation site. A reader of one of those documents acts on the superseded decision. The propagation should have followed the rule "everywhere this decision is cited," recomputed, not recalled. *Lift: Pattern 2.3 (enumeration is a seed; the audit-rule is the standard).*

In all three, the failure is invisible from within because the stale field still displays a plausible value. The protocol's value is that it makes the staleness a *flagged* state rather than a silent one.

---

## 5. Relation to Other Protocols

Read-Write Boundary is a *meta-level* protocol, operating across the whole methodology's artefacts rather than at a single pipeline stage. It is the third meta axis alongside falsification and provenance: falsification audits *validity* (could this be wrong?), provenance audits *origin* (where did this come from?), and this protocol audits *authority and currency* (who may write this, and has it outlived its premises?).

- **Provenance protocol** records *who introduced* an idea. This protocol records *who may write* a field and *when a recorded decision expires*. Provenance is about genealogy; read-write boundary is about write-authority and currency. The two share the conviction that durable markers beat reconstructed memory, on different axes.
- **Writing protocol** guards *composition drift* — a final text drifting from its source during a long composition. This protocol generalises that intuition from the op-ed to every durable judgement: a recorded decision drifting from its premises. Composition drift is the special case at the writing stage; premise-staleness is the general case across all artefacts.
- **Falsification protocol** tests whether a claim *could* be wrong. This protocol tests whether a recorded judgement has *outlived the premises it was decided under* — a currency question, not a validity question. A judgement can be valid and stale at once.
- **Tool protocol** is infrastructure-upstream: it ensures a tool read and wrote faithfully. This protocol sits above it: granted faithful tools, it governs *which fields a tool is entitled to write*.
- **Actant self-check** audits the researcher's *voice* in author-voiced text. This protocol audits the *write-authority* over an artefact's fields — distinct: voice is about how the researcher writes, authority is about what an automated step may write instead.

---

## 6. What This Protocol Does **Not** Provide

- It does not mechanise interpretive judgement. Term choices, readings, analytical decisions, and rationales remain HUMAN-class and are never computed, never hash-bound, never auto-generated. The protocol governs *who writes a field and when a decision expires*, not *what the decision should be*. Applying derivation or invalidation machinery to interpretive content is a category error this protocol explicitly forbids.
- It does not specify a build. The field-class contract and the invalidation discipline are stated as a working practice; whether any of it is enforced by code (a validator, a content-hash binding, an automated re-resolution pass) is a separate, deferred engineering decision. The protocol is usable in full by hand.
- It does not adjudicate which class a contested field belongs to. Where reasonable people would classify a field differently, the protocol requires the classification to be *declared and justified*, not that it be resolved a particular way.
- It does not replace the provenance or falsification audits. Currency-of-judgement is a third axis, complementary to origin and validity, not a substitute for either.

---

## 7. Cross-Refs

- [provenance protocol](provenance-protocol.md) — meta-level companion (origin axis; this protocol is authority/currency axis).
- [falsification protocol](falsification-protocol.md) — meta-level companion (validity axis).
- [writing protocol](writing-protocol.md) — composition drift is the writing-stage special case of premise-staleness.
- [tool protocol](tool-protocol.md) — infrastructure upstream of write-authority.
- [actant self-check](actant-self-check.md) — voice-positionality (distinct from write-authority).

---

*Versioning: working-draft. The protocol was promoted 2026-06-29 from documented practice: a recurrent class of artefact-drift in which a recorded judgement (a continuity note, a version stamp, an amended decision) outlived the premises it was decided under, or an automated step over-reached into a field only a human should write. Per the auxiliary-hypothesis admissibility test (falsification-protocol §3 OT-3), the addition increases the methodology's forbidden set by three items — automation authoring a human judgement, a mechanically-derivable field maintained by vigilance, and a recorded judgement inherited unchanged across a premise-change. Substantial structural re-articulation triggers a status update; inline patch edits do not.*
