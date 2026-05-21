# Methodology-Development — Articulation-Pass v0

*Working-Draft. DE-first per DTrans (Translate-Last). Status: draft
2026-05-19. Source-of-Truth + Vor-README für Repo A. TBD-Marker sind
explizit gekennzeichnet und betreffen Strategic Open Questions
S1/S2/S3/S5, deren Resolution pending ist.*

---

## 1. Statement

**methodology-development** ist ein Meta-Projekt zur Entwicklung einer
**AI-agnostischen Methodologie** für **humanities-students und
humanities-scholars**, die **verantwortliches AI-Arbeiten mit
publizierbaren outcomes** ermöglicht. Es transzendiert einzelne
Disziplinen und konkrete AI-Tools; die Methodologie soll portabel sein
über die jeweils verfügbare AI-Generation.

Audience-Schärfung (early-career vs. etabliert vs. Mix) pending S1.

## 2. Motivation

Auslöser war kein theoretisches Bedürfnis, sondern eine empirische
Diagnose. Bei der Publikation eines analytischen Op-Eds (AX-006,
Body-Worlds-Wrocław, 2026-05-17) traten *descriptive-accuracy*-Fehler
auf, die post-publication manuell korrigiert werden mussten. Die
methodologische Re-Konstruktion ergab: die Disziplinen, die solche
Fehler verhindert hätten, existierten zwar fragmentiert in einzelnen
Projekt-Checklisten, aber nicht als kohärenter Workflow. Die Frage
*„haben wir einen konsistenten Workflow oder Stückwerk?"* musste mit
*Stückwerk* beantwortet werden.

Daraus emergierte das Reframing: **Methodologie ist nicht Side-Effect
der Projekt-Arbeit, sondern primäres Forschungsobjekt**. Konkrete
Projekte (Ideologiekritik, Studium, Rosenkranz, knowledge-
representation, aXIOM) sind ad-hoc Test-Cases, an denen sich die
Methodologie entwickelt und stresstesten lässt — nicht ihr Telos.

## 3. Was geliefert wird

Die Methodologie wird in **γ-shape** geliefert: zwei gekoppelte
Schichten.

- **β** — die abstrakte Methodologie, tool-portabel. Beschreibt, was
  eine humanities-scholar-AI-Arbeitsumgebung enthalten soll:
  Positionalität, Material-Boundaries, Source-Disziplin, Memory-
  Disziplin, Attribution-Hygiene. Sitz: **Repo A** (public,
  CC BY-SA 4.0, EN).

- **α** — eine konkrete Reference-Implementation, Claude-Code-
  spezifisch, aber architektonisch übertragbar: CLAUDE.md-Layering,
  auto-memory, workspace-Struktur, Skills, Hooks. Demonstriert, dass
  β implementierbar ist. Reference-Dokumentation in Repo A; das
  laufende α ist die Arbeitsumgebung selbst.

Project-internes Material, projekt-spezifische runbooks und research-
internal Notizen liegen in **Repo B** (private, DE), strukturell
getrennt von der publishable Schicht. Diese Two-Repo-Architektur macht
die Material-Boundary by construction sauber.

**Publikations-Strategie** ist *phased*: working-draft (Repo A +
Substack-Companion) ohne Peer-Review-Gate als initiale Form;
methodisch zitierbar von Tag 1. Eskalation zu Peer-Review (Methods-
Paper für β, Tools-Paper / Workshop für α) wenn ein Reifegrad
erreicht ist — Reifezeichen TBD (siehe §7).

## 4. Theoretische Grundlage *[TBD — S2]*

Die normative Grundlage von *„verantwortlich"* ist noch nicht
festgelegt. Kandidaten auf dem Tisch:

- **Frankfurter Schule / Kritische Theorie** — konsistent mit der
  ideologiekritischen Verortung der Op-Ed-Arbeit.
- **Diskurs-Ethik (Habermas)** — verfahrensorientiert; gut zu
  working-draft + Community-Feedback-Modus.
- **Care-Ethik** — relational; fit für die Reader-Audience-Beziehung.
- **Pragmatismus (Dewey, Peirce)** — Hypothese-Test-Revision-Cycle
  natürlich zu phased publication.
- **Bewusste Eklektik** — Methoden-Pluralismus statt single-tradition-
  Commitment.

Entscheidung pending. Rekursiv gekoppelt an die Backlog-Frage „welche
Methodologie für das Meta-Projekt selbst" (LEAN vs. Action Research
vs. TQM/PDCA vs. Pragmatist Inquiry vs. Reflective Practice). Beide
Fragen müssen vermutlich gemeinsam entschieden werden, damit
methodologische Konsistenz zwischen Norm und Norm-Entwicklung
gewahrt bleibt.

## 5. Position in existierender Literatur *[TBD — S3]*

Verortung zu prüfen in folgenden Feldern:

- **Digital Humanities** (Methoden-Reflexion, Tool-Kritik, Workflow-
  Dokumentation).
- **Critical Algorithm Studies** (AI als Untersuchungsgegenstand,
  nicht nur Werkzeug).
- **AI Ethics** (responsible-AI-Diskurs, Disclosure-Standards).
- **Reflective Practice / Action Research** (selbst-dokumentierende
  Methodik-Entwicklung).
- **Methods Papers in Humanities-Journals** (formaler Sitz im
  publishing-Ökosystem).

Pending: Literatur-Survey, ob bereits etablierte Standards / best
practices existieren, die das Meta-Projekt *extending* /
*critiquing* / *complementing* / *replacing* kann. Ohne diese
Verortung bleibt die Contribution-Behauptung unscharf.

## 6. Case-Studies und Skin-in-the-Game

Die fünf aktiven Projekte sind Test-Cases, in denen sich die
Methodologie bewährt oder Failure-Modes produziert:

- **Ideologiekritik** — Op-Ed-Pipeline + Multimodal-Artefakt-Analyse;
  AX-006 ist der erste empirische Failure-zu-Methodik-Lift (pre-
  publication-checklist als erstes β-Material).
- **Studium** — Bibliographie-Management + cross-disciplinary
  Methoden-Inventar.
- **Rosenkranz** — Übersetzungs-Workflow Deutsch → Polnisch mit
  Glossar-Disziplin.
- **knowledge-representation** — Retrieval-Tooling über Library-
  Korpus; Evaluations-Methodik.
- **aXIOM** — DFS-IP-Track, methodische Selbst-Beschreibung.

Beitrag *ad-hoc*: ein Artefakt liefert dann Methodologie-Material,
wenn es sich natürlich ergibt — nicht prophylaktisch pro Projekt.

**Skin-in-the-Game-Prinzip:** die Methodologie testet sich an realen
Publikations-Vorgängen. AX-006-Fehler sind kein Argument gegen,
sondern für sie — sie machen Lücken sichtbar, die corrected werden
können. Eine Methodologie, die nie im Live-Vorgang versagt, hat noch
nicht genug Last getragen.

## 7. Status und Reifezeichen *[TBD — S5]*

**Aktueller Status:** working-draft. Codifiziert in **ADR-0009**
(*Project-Identity + Two-Repo Methodology Architecture*, 2026-05-18,
Status Proposed). Layer-1 §Meta-Projekt und mehrere β-Kandidat-
Sektionen (Research-Disziplin, Writing-Disziplin, Aktanten-Selbst-
check, Tool-Fußnoten) sind in der Reference-Implementation eingebettet,
aber noch nicht zu Repo A extrahiert.

**Reifezeichen für Q3-Eskalation** (peer-review-ready) sind noch nicht
operationalisiert. Kandidaten:

- ≥ N Case-Studies, in denen die Methodologie *vor* dem Failure
  intervenierte (nicht nur retrospective Lift).
- Externe Lese-Tests durch ≥ M humanities-scholars mit substantieller
  Rückmeldung.
- β stabil über ≥ X Monate ohne strukturelle Re-Articulation.

Operationalisierung von N / M / X pending.

---

## Frozen Anchors

- **ADR-0009:** `D:\Claude\workspace\decisions\0009-project-identity-two-repo-methodology-architecture.md`
- **Session-1-State** (frozen pre-clarification Snapshot):
  `D:\Claude\workspace\methodology-development\2026-05-18-session-1-state.md`
- **State-Anchor Memory:**
  `~/.claude/projects/D--/memory/project_methodology_development.md`
- **Glossar (DE/PL/EN):**
  `D:\Claude\workspace\methodology-development\glossary-de-pl-en.md`

---

*Versionierung:* v0 = working-draft, lebend. Substantielle
strukturelle Änderungen (z.B. nach S2-Resolution) → v1.
