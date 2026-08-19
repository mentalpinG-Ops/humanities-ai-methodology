---
name: Tool Protocol
version: 0.2.1
status: draft
last_changed: 2026-08-19
---

# Tool Protocol

*Methodology module. Audience: humanities scholar.*

---

## 1. Position

Tools mediate. Between the author and the artefact, between the source and the citation, between the draft and the publication, tools intervene — search engines, file readers, AI assistants, encoding pipelines, image renderers, OCR, web APIs. Each tool has its own assumptions, defaults, failure modes. None is a neutral conduit. A methodology that takes tools as transparent infrastructure inherits whatever distortions the tools introduce. A methodology that treats tools as objects of empirical validation gains a layer of corrective protocol that source protocol, writing protocol, and actant self-check cannot supply alone.

Tool protocol is *infrastructure-facing*: it does not check what the author says about the artefact (writing protocol) or what the author says as a positioned voice (actant self-check); it checks what the *tool* says about the artefact before either of those concerns arise.

Four patterns are robust enough across documented failures — and one documented averted-failure decision — to be named separately. Together they constitute Tool Protocol.

---

## 2. The Four Patterns

### 2.1 Encoding Fidelity

**Rule.** Verify that text passing through a tool chain preserves its encoding. UTF-8 content — special characters, diacritics, non-Latin scripts, symbols such as `§` and `→` — must survive the full chain from source through processing to publication. Default encodings cannot be trusted to handle this; explicit declarations are required at every transport boundary.

**Why.** Many tools default to legacy single-byte encodings (Latin-1, ISO-8859-1, Windows-1252) for backward compatibility. Content passed through these defaults silently mojibakes: German *ü* becomes `Ã¼` or `�`; Polish *ę* becomes `Ä™`; the section sign *§* becomes `Â§` or `�`. The corruption is invisible at the source tool and at the destination tool individually, because each sees its own default-encoded view. The corruption becomes visible only when the content reaches a reader whose tool has a different default — at which point the content is published and the audit trail of where the corruption entered is gone.

Empirical case: an op-ed publication pipeline routed text through a PowerShell HTTP-API call that defaulted to ISO-8859-1 string-body encoding. UTF-8 content (German umlauts, the section sign) was silently corrupted to replacement characters in the published output. Recovery required reissuing the publication with explicit `charset=utf-8` declarations and byte-array body construction.

**How to apply.**
- At every transport boundary (file read/write, HTTP request/response, API call, terminal output, copy-paste), declare encoding explicitly.
- For HTTP / API: send `Content-Type: ...; charset=utf-8` headers explicitly; send body as UTF-8-encoded bytes, not as a string that may be re-encoded by the client.
- For file I/O: use UTF-8 read and write functions explicitly, not the platform default.
- Test the chain end-to-end with content that contains diacritics, non-Latin script, and special symbols *before* using it in a real publication.

### 2.2 Read Fidelity

**Rule.** When a tool mediates the author's view of an artefact (file readers, image display, OCR, AI assistants that summarise file content), assume the tool view is approximate. Verify specific empirical claims against the artefact directly, not against the tool view.

**Why.** File readers may misrender Unicode, mis-align indentation, drop trailing whitespace, normalise line endings, substitute visually-similar characters, or summarise binary data in ways that omit detail. Image-display tools may compress, transcode, crop, or scale. OCR may misread similar characters (*1* vs. *l*, *O* vs. *0*). AI assistants summarising a file may report what they expect to be there alongside what is actually there. The author working with the tool view forms confident empirical impressions that are wrong in ways the tool does not signal.

Empirical case: a coding assistant's file-reader summarised an image artefact in a way that the author treated as direct view. The author's later text described the artefact as showing *"a chess player with a hat"*. The hat belonged to a different figure in the image; the chess player was bareheaded. The misdescription survived multiple drafts because the author continued to verify against the tool-mediated view rather than against the source image at native resolution. See also [writing protocol](writing-protocol.md) §2.2 for the descriptive-accuracy aspect.

**How to apply.**
- Identify which artefacts in the workflow are tool-mediated.
- For each, the empirical claims about the artefact must be verifiable independently of the tool — by viewing the source directly, by re-reading with a second tool that has different failure modes, or by extracting and inspecting the relevant bytes or pixels.
- When the artefact's verification requires the tool (e.g., the artefact is large enough that direct inspection is impractical), document the tool dependency explicitly so a later reader knows what the empirical claim is conditional on.

### 2.3 Pre-Production Tool Validation

**Rule.** Before a tool is used in a publication pipeline, validate it empirically with edge-case content — diacritics, special symbols, mixed scripts, long lines, embedded markup. A tool that handles standard ASCII English content reliably may fail silently on the content that matters.

**Why.** Tool defaults are optimised for the most common content their authors anticipated. Humanities-scholar content is often *not* that — multi-script, citation-heavy, character-rich, mark-up-bearing. Discovering a tool's failure mode by publishing a corrupted output is expensive; discovering it during a pre-production test is cheap. The cost asymmetry is the reason this pattern is a protocol rather than a habit.

**How to apply.**
- Define a *test content packet* containing the edge cases that matter for the work: representative diacritics for the relevant languages, special symbols used in citations, multi-line content with the relevant formatting, sample non-Latin script (Polish, Cyrillic, Greek, etc., per the actual corpus).
- Run the test packet through any new tool or new tool-chain configuration before integrating it.
- Compare output to source byte-for-byte where possible; visually where not.
- Document tool-specific findings in the project's own working materials (outside this repository) so the next iteration of the same tool-chain does not require rediscovery.

### 2.4 Declare vs. Enforce for Encoded Analytical Rules

**Rule.** When a tool encodes analytical rules — an operations register, a conflict table, a screening heuristic — the rules' evidence status governs how hard the tool may act on them. An *untested* encoded rule may be **declared**: marked, recommended, planned around. Only a rule that has passed a material test may be **enforced**: used to block, reject, or overrule — and a passed test licenses enforcement per operationalisation, not per rule-family. The evidence status travels *in the tool's output*, not in source-code comments: code strips metadata, and a stripped status re-enters downstream work looking like fact.

**Why.** Enforcement is a structural promise. A hard gate built on an untested hypothesis asserts a certainty the evidence does not cover — frame-imposition through code, the failure class [interpretive-frame protocol](interpretive-frame-protocol.md) names at the coding step, recurring at the infrastructure layer. Declaration, by contrast, keeps the hypothesis falsifiable: every marked recommendation is a falsification candidate that continued use can refute. "Conservative defaults" are not exempt; the operative test is mechanical — *does it block, or does it mark?* A default that in practice blocks counts as enforcement.

Empirical case (July 2026, maintainer's practice corpus): an operations register for artefact analysis (24 operations with conflict and interoperability relations) was built into a planning tool while the register itself was almost entirely untested — a single rule carried practice evidence. An adversarial review of the build plans converged, from both use cases examined, on the same verdict: build nothing that hardens the untested register into a gate. The tool was built declaring — it marks exposed operations and carries the register's evidence status in its output. A subsequent test family delivered the first positive behavioural evidence that the marking approach reaches the executing agent's behaviour: explicit source-marking where an unmitigated run had silently adopted the source's self-interpretation.

**The shared evidence field — the hinge between testing and use.** The register carries one evidence field per rule (e.g. *reading-derived / practice-void / practice-attested*). The test regime **writes** it (after a test, one cell at a time); the tool **reads** it (at each application, all cells at once). A passed test thereby becomes a tool licence: *practice-attested* lifts a rule from "marks only" to "may enforce". The asymmetry is the load-bearing part: **applying is not testing.** A clean tool run does not attest the register — no pre-registration, no control, no instrument validation — it only produces test material. "The tool ran cleanly, so the register holds" is precisely the overclaim the shared field exists to block.

**How to apply.**
- For every encoded analytical rule, record an evidence status; emit it in the tool's output wherever the rule shapes a recommendation.
- Ask the mechanical question per rule: does the tool *mark* on its basis, or *block*? Blocking requires a passed material test of that rule, in that operationalisation.
- Let only the test regime write the evidence field, and only after a test; let the tool read it. Never lift a status because application "went well".
- Treat tool runs as producers of test material and route that material into the test regime, rather than counting clean runs as confirmation.

---

## 3. Tool Protocol as an Upstream Layer

Tool protocol operates at a different layer than the other three Methodology modules. Source protocol checks what enters the workflow; writing protocol checks what the author says about it; actant self-check checks the author's positional voice. Tool protocol checks the infrastructure on which all three depend.

The relationship is *upstream*: tool-protocol failures invalidate the work of all three other protocols. A source verified verbatim through a tool that silently re-encoded the text is not actually verified verbatim — what was checked was the tool's representation of the source. The same source-protocol pattern (Snippets ≠ Primary) reappears at the tool layer: *tool views ≠ artefacts*.

This is why tool protocol cannot be deferred to "engineering concerns". For humanities-scholar work where the artefact is the primary research object, infidelity at the tool layer is infidelity at the research layer.

---

## 4. Failure-Mode Gallery

Documented failures grounding the protocol:

- **UTF-8 corruption through PowerShell HTTP body** (museum-exhibition op-ed publication pipeline). German umlauts and the section sign reduced to replacement characters in the published op-ed. Root cause: ISO-8859-1 default in PowerShell's `Invoke-RestMethod` string-body handling. Lift to Pattern 2.1.
- **Read-tool emoji and position misrender** (same publication, composition stage). The file-reader's representation of an image artefact diverged from the source image; the author composed against the divergent view. Lift to Pattern 2.2.
- **AI-assistant content-approximation drift** (general pattern across multiple sessions). AI assistants reading and summarising files may report content that is plausibly but not actually present. Pattern 2.2 generalises here: assume the assistant's view is approximate; verify against the source for any load-bearing claim.

---

## 5. Operationalisation in the Workflow

Tool protocol runs as a separate workflow track, not as a final-stage check:

- **Workflow design:** identify every tool in the publication pipeline. Document its known failure modes.
- **Tool onboarding:** before adding a new tool to the pipeline, run the pre-production validation packet (Pattern 2.3).
- **Routine use:** when content passes through a tool, treat the tool's output as approximate until verified at the next boundary. For load-bearing content, verify explicitly.
- **Failure response:** when a tool failure is discovered post-publication, document it as a failure-mode entry; update the validation packet to catch the same class of failure earlier next time.

Implementation-specific tool fixes — encoding flags, configuration files, code workarounds — live in project-level working materials outside this repository. The methodology layer (this document) holds the protocol that guides their creation; it does not itself hold instance-specific configurations.

---

## 6. What This Protocol Does **Not** Provide

- It does not address whether a verified source is intellectually valid (see [source protocol](source-protocol.md)).
- It does not address whether the author's claims about an artefact are accurate (see [writing protocol](writing-protocol.md)).
- It does not address whether the author's positional voice is well-calibrated (see [actant self-check](actant-self-check.md)).
- It does not solve general software engineering. Tool protocol is the minimum infrastructure-validation that humanities-scholar work needs to keep its source-, writing-, and actant-protocols load-bearing. Engineers may have stronger requirements; this protocol is the floor, not the ceiling.

---

## 7. Cross-Refs

- [source protocol](source-protocol.md) — source intake; tool-protocol failures invalidate source verification.
- [writing protocol](writing-protocol.md) — descriptive accuracy; tool-protocol failures upstream of descriptive errors.
- [actant self-check](actant-self-check.md) — positional voice; orthogonal layer.

---

*Versioning: working-draft. As the canonical practice accumulates more tool-failure incidents, additional patterns may emerge. Pattern 2.4 (declare vs. enforce) was added 2026-07-20, promoted from a documented tool-governance decision in the maintainer's practice corpus; minor version bump per governance. Inline patch edits do not trigger a version bump; new patterns trigger a status update.*
