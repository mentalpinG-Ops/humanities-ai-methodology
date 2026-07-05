---
name: Design Brief — Onboarding Page
status: draft
last_changed: 2026-07-05
audience: maintainer (visual-design pass)
---

# Design brief — onboarding page visual upgrade

`docs/index.html` ships as a functional, neutral-styled, standalone page. This
brief scopes the later visual-design pass (e.g. in a browser-based design
tool). The functional page is the source of truth for content and behaviour;
the design pass restyles, it does not rewrite.

## What the page is

A self-service front door for the methodology: a visitor with any AI setup
(free web chat → configured workspace → connected files → CLI agent) finds out
in under a minute which **integration level** fits them and walks away with a
working artefact (today: the Paste-Card).

## Non-negotiables (carry over unchanged)

1. **Content and copy are frozen inputs.** The ladder table, capability test
   questions and routing, the Paste-Card text, the worked example, the status/
   licence/contribute sections — no rewording during the design pass. Copy
   changes go through the content workflow, not the design tool.
2. **Self-contained single file.** No CDN fonts/scripts, no external images,
   no analytics/telemetry of any kind. Inline everything.
3. **Both colour schemes.** Light and dark, system-following, both readable.
4. **No horizontal page scroll**; wide tables scroll inside their own container.
5. **The capability test must remain fully client-side** and keyboard-usable;
   every routing path ends at a real target (Paste-Card or Automate preview) —
   never a dead end.
6. **Honesty markers stay visible:** the working-draft status note, the
   "illustrative, not authoritative" label on the AI-diagnostic prompt, and the
   post-MVP fallback lines on the deeper levels.

## Design intent (where the pass adds value)

- **The ladder as the hero visual.** Four ascending steps (Paste → Configure →
  Connect → Automate) with "activated capability" as the axis label; the
  current MVP highlights Paste as the built rung. A simple stepped/staircase
  composition beats an abstract diagram.
- **The Paste-Card as a tangible object.** Style it like a card — bounded, with
  a copy button — so "take this with you" is visually literal.
- **Division-of-labour cues.** The [Human]/[Both] tags deserve two small,
  consistent glyphs (e.g. a person, a person+spark) used identically in the
  ladder, the card, and the worked example.
- **Calm, academic tone.** Generous whitespace, restrained accent colour,
  serif-or-humanist headings acceptable; no startup-gradient aesthetics. The
  brand decision is deliberately open — stay neutral enough that a later
  identity pass can reskin via CSS variables only.
- **Typography for pasted text.** The Paste-Card and the diagnostic prompt are
  monospace blocks with visible boundaries; everything else is prose type.

## Acceptance for the design pass

- Rendered copy is byte-identical to the functional version (diff the text
  nodes, not the markup).
- Lighthouse-style basics hold: readable contrast in both schemes, focus
  states on all interactive elements, no layout shift on scheme toggle.
- File stays a single standalone HTML document.
