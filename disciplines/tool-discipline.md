# Tool Discipline

*Methodology module. Status: working-draft 2026-05-21. Audience: humanities scholar.*

---

## 1. Position

Tools mediate. Between the author and the artefact, between the source and the citation, between the draft and the publication, tools intervene — search engines, file readers, AI assistants, encoding pipelines, image renderers, OCR, web APIs. Each tool has its own assumptions, defaults, failure modes. None is a neutral conduit. A methodology that takes tools as transparent infrastructure inherits whatever distortions the tools introduce. A methodology that treats tools as objects of empirical validation gains a layer of corrective discipline that source discipline, writing discipline, and actant self-check cannot supply alone.

Tool discipline is *infrastructure-facing*: it does not check what the author says about the artefact (writing discipline) or what the author says as a positioned voice (actant self-check); it checks what the *tool* says about the artefact before either of those concerns arise.

Three patterns are robust enough across documented failures to be named separately. Together they constitute Tool Discipline.

---

## 2. The Three Patterns

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

Empirical case: a coding assistant's file-reader summarised an image artefact in a way that the author treated as direct view. The author's later text described the artefact as showing *"a chess player with a hat"*. The hat belonged to a different figure in the image; the chess player was bareheaded. The misdescription survived multiple drafts because the author continued to verify against the tool-mediated view rather than against the source image at native resolution. See also [[writing-discipline]] §2.2 for the descriptive-accuracy aspect.

**How to apply.**
- Identify which artefacts in the workflow are tool-mediated.
- For each, the empirical claims about the artefact must be verifiable independently of the tool — by viewing the source directly, by re-reading with a second tool that has different failure modes, or by extracting and inspecting the relevant bytes or pixels.
- When the artefact's verification requires the tool (e.g., the artefact is large enough that direct inspection is impractical), document the tool dependency explicitly so a later reader knows what the empirical claim is conditional on.

### 2.3 Pre-Production Tool Validation

**Rule.** Before a tool is used in a publication pipeline, validate it empirically with edge-case content — diacritics, special symbols, mixed scripts, long lines, embedded markup. A tool that handles standard ASCII English content reliably may fail silently on the content that matters.

**Why.** Tool defaults are optimised for the most common content their authors anticipated. Humanities-scholar content is often *not* that — multi-script, citation-heavy, character-rich, mark-up-bearing. Discovering a tool's failure mode by publishing a corrupted output is expensive; discovering it during a pre-production test is cheap. The cost asymmetry is the reason this pattern is a discipline rather than a habit.

**How to apply.**
- Define a *test content packet* containing the edge cases that matter for the work: representative diacritics for the relevant languages, special symbols used in citations, multi-line content with the relevant formatting, sample non-Latin script (Polish, Cyrillic, Greek, etc., per the actual corpus).
- Run the test packet through any new tool or new tool-chain configuration before integrating it.
- Compare output to source byte-for-byte where possible; visually where not.
- Document tool-specific findings in a runbook (in the companion runbook repository, per the README §3) so the next iteration of the same tool-chain does not require rediscovery.

---

## 3. Tool Discipline as an Upstream Layer

Tool discipline operates at a different layer than the other three Methodology modules. Source discipline checks what enters the workflow; writing discipline checks what the author says about it; actant self-check checks the author's positional voice. Tool discipline checks the infrastructure on which all three depend.

The relationship is *upstream*: tool-discipline failures invalidate the work of all three other disciplines. A source verified verbatim through a tool that silently re-encoded the text is not actually verified verbatim — what was checked was the tool's representation of the source. The same source-discipline pattern (Snippets ≠ Primary) reappears at the tool layer: *tool views ≠ artefacts*.

This is why tool discipline cannot be deferred to "engineering concerns". For humanities-scholar work where the artefact is the primary research object, infidelity at the tool layer is infidelity at the research layer.

---

## 4. Failure-Mode Gallery

Documented failures grounding the discipline:

- **UTF-8 corruption through PowerShell HTTP body** (museum-exhibition op-ed publication pipeline). German umlauts and the section sign reduced to replacement characters in the published op-ed. Root cause: ISO-8859-1 default in PowerShell's `Invoke-RestMethod` string-body handling. Lift to Pattern 2.1.
- **Read-tool emoji and position misrender** (same publication, composition stage). The file-reader's representation of an image artefact diverged from the source image; the author composed against the divergent view. Lift to Pattern 2.2.
- **AI-assistant content-approximation drift** (general pattern across multiple sessions). AI assistants reading and summarising files may report content that is plausibly but not actually present. Pattern 2.2 generalises here: assume the assistant's view is approximate; verify against the source for any load-bearing claim.

---

## 5. Operationalisation in the Workflow

Tool discipline runs as a separate workflow track, not as a final-stage check:

- **Workflow design:** identify every tool in the publication pipeline. Document its known failure modes.
- **Tool onboarding:** before adding a new tool to the pipeline, run the pre-production validation packet (Pattern 2.3).
- **Routine use:** when content passes through a tool, treat the tool's output as approximate until verified at the next boundary. For load-bearing content, verify explicitly.
- **Failure response:** when a tool failure is discovered post-publication, document it as a failure-mode entry; update the validation packet to catch the same class of failure earlier next time.

The runbook layer (the companion runbook repository) holds the specific tool fixes — encoding flags, configuration files, code workarounds. The methodology layer (this document) holds the discipline that produces those runbooks.

---

## 6. What This Discipline Does **Not** Provide

- It does not address whether a verified source is intellectually valid (see [[source-discipline]]).
- It does not address whether the author's claims about an artefact are accurate (see [[writing-discipline]]).
- It does not address whether the author's positional voice is well-calibrated (see [[actant-self-check]]).
- It does not solve general software engineering. Tool discipline is the minimum infrastructure-validation that humanities-scholar work needs to keep its source-, writing-, and actant-disciplines load-bearing. Engineers may have stronger requirements; this discipline is the floor, not the ceiling.

---

## 7. Cross-Refs

- [[source-discipline]] — source intake; tool-discipline failures invalidate source verification.
- [[writing-discipline]] — descriptive accuracy; tool-discipline failures upstream of descriptive errors.
- [[actant-self-check]] — positional voice; orthogonal layer.

---

*Versioning: working-draft. As the reference implementation accumulates more tool-failure incidents, additional patterns may emerge. Inline patch edits do not trigger a version bump; new patterns trigger a status update.*
