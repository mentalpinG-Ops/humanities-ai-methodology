---
status: historical
last_changed: 2026-06-29
---

# 0002 — Add the Read-Write Boundary protocol (eighth module)

**Date:** 2026-06-29
**Status:** historical (a frozen account of the decision as taken; the protocol enters at `status: draft` and matures via the normal pipeline)

## Context

The methodology's protocols cover source intake, interpretive coding, composition, author voice, tool fidelity, claim-validity (falsification), and human-vs-AI origin (provenance). A recurrent class of failure in AI-assisted scholarly work fell outside all of them: the *drift of a durable artefact's own fields*. Three observed patterns recurred —

1. a recorded judgement (a continuity note's next-step, a review verdict) kept being displayed as current after the premises it was decided under had changed;
2. a mechanically-derivable field (a version stamp, a count, a cross-reference) maintained by hand silently fell out of date when its inputs moved;
3. an automated step over-reached into a field only a person should author (a rationale, an attestation).

None of the existing protocols name *who may write each field of an artefact* or *when a recorded judgement expires*. Provenance tracks origin, falsification tracks validity, tool tracks read/write fidelity — but not write-authority or currency.

## Decision

Add an eighth protocol, **Read-Write Boundary** (`protocols/read-write-boundary-protocol.md`), as a third meta-level axis alongside falsification (validity) and provenance (origin). It contributes three patterns:

- **The Four Field-Classes** — every durable-artefact field is COMPUTED / MECHANICAL / HUMAN / EXTERNAL, fixing who may write it.
- **Invalidate, Never Author** — an automated step may compute facts and may *invalidate* a human judgement (force re-decision, keep the old value for audit) but never authors or alters one.
- **A Hand-Maintained Derived Field Is a Drift Bug** — a mechanically-derivable field maintained by vigilance is a defect, not diligence; propagate derived consequences by rule, not by a remembered enumeration.

Consequential updates: a row in `METHODOLOGY_SPEC.md` §1 and the §2 layering (three meta axes, not two); the `README.md` §7 list and orthogonality paragraph; the `CLAUDE.md` module count (seven → eight); this record; and a `CHANGELOG.md` entry. The protocol enters at `status: draft`.

The protocol explicitly **does not** mechanise interpretive judgement: term choices, readings, and rationales remain human-authored and are never computed or auto-invalidated. It governs write-authority and currency, not the content of any judgement.

## Consequences

- The methodology now has a third audit axis. Where falsification asks *"could this be wrong?"* and provenance asks *"where did this come from?"*, read-write boundary asks *"who may write this field, and has it outlived its premises?"*.
- The protocol passes the admissibility test (falsification-protocol §3 OT-3): it enlarges the methodology's forbidden set by three items — automation authoring a human judgement, a derivable field maintained by hand, and a recorded judgement inherited unchanged across a premise-change.
- The empirical anchor and any machinery for automated enforcement live in the maintainer's private working context, not here; this repository carries the generalised, de-identified protocol only.

## Falsifier

This addition would be revisited if external read-tests showed the four-class contract being consistently misapplied to interpretive content (the category error the protocol forbids), or if the authority/currency axis proved to collapse into provenance or falsification rather than standing as a distinct concern. No such evidence existed at the time of the decision.
