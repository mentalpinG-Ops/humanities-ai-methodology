# Source-Disziplin

*β-Modul. Status: working-draft 2026-05-21. DE-first per DTrans (Translate-Last). Audience: humanities-scholar.*

---

## 1. Position

In AI-gestützter humanities-Forschung passiert der Großteil der Quellen-Begegnung über Such-Tools, die *Snippets*, *Abstracts*, *aggregierte Zusammenfassungen* oder *Such-Agent-Reports* liefern. Diese sind nicht Quellen — sie sind *Hinweise auf Quellen*. Eine Methodologie, die humanities-scholarly Standards einlösen soll, muss die Unterscheidung zwischen der durch Tool-Filterung produzierten Repräsentation und der Quelle selbst nicht als nachträgliches Gewissens-Korrektiv führen, sondern als arbeitswirksame Disziplin: erkennbar im Workflow, prüfbar im Output, Audit-fähig nach Publikation.

Drei Patterns sind empirisch wirksam genug, um eigenständig benannt zu werden. Sie bilden gemeinsam die Source-Disziplin.

---

## 2. Die drei Patterns

### 2.1 Snippets ≠ Primary

**Regel.** Such-Snippets — von Google, Consensus, Semantic Scholar, Perplexity, Claude-WebSearch, gleichartigen Tools — sind keine Primärquellen-Attestation. Bevor ein Snippet load-bearing wird (zitiert, in Argumente eingebaut, anderen vorgelegt), muss der Volltext geöffnet und die zitierte Passage verbatim verifiziert werden.

**Begründung.** Such-Snippets werden algorithmisch generiert aus indexierten Repräsentationen. Sie können:
- aus älteren / nicht-finalen Versionen stammen
- aus Marketing-Material oder Sekundär-Beschreibungen statt aus dem Original
- syntaktisch beschnitten sein, sodass die Aussagen-Polarität kippt
- aus Cache-Snapshots stammen, die seit der Index-Erstellung obsolet wurden

Diese Failure-Modes treten in allen Tool-Generationen auf. Eine AI-agnostische Methodologie kann sich nicht darauf verlassen, dass bessere Modelle das Problem lösen — die Snippet-Schicht selbst ist die Ungenauigkeits-Quelle.

**Operationalisierung.**
- Vor Verwendung: Volltext-Quelle aufrufen (Paywall, Repository, Wayback-Machine).
- Verbatim-Passage gegen Snippet abgleichen.
- Wenn divergent: Snippet verwerfen, Volltext-Version als Anker setzen.
- Wenn Volltext nicht erreichbar: Snippet als *„Hinweis, unverifizierbar"* tagen, nicht als Attestation behandeln.

### 2.2 Sekundärquelle ≠ Primärquelle

**Regel.** Eine Sekundärquelle (Beschreibung einer Primärquelle) ist nicht die Primärquelle. Beim Source-Tag muss die Ebene gekennzeichnet werden: Primär (das Original), Sekundär (eine Beschreibung), Tertiär (eine Beschreibung der Beschreibung).

**Begründung.** Eine besondere Fehler-Klasse ist *Promoter-Amplifikation*: Marketing-, Promotion- oder Vermittler-Material zirkuliert eine modifizierte Version eines Original-Verbatim und stabilisiert die Modifikation durch Wiederholung. Wer auf den zirkulierten Sekundär-Text zugreift und ihn als Original-Attestation behandelt, übernimmt die Modifikation unsichtbar.

Empirischer Fall: das Marketing einer Wander-Ausstellung in Polen attribuierte einer Vatikan-Tageszeitung den Satz *„wspaniały hymn" (großartiger Hymnus)*. Die Original-Tageszeitung schrieb *„hołd dla ciała" (Tribut an den Körper)*. *„Hymn"* ist die Promoter-Amplifikation; *„hołd"* ist der Originaltext. Wer den Promotion-Text als Quelle zitiert, ohne ihn als Sekundär zu markieren, gibt die Amplifikation als Original-Aussage weiter.

**Operationalisierung.**
- Source-Tag-Pflichtfeld: Ebene (Primär / Sekundär / Tertiär).
- Bei Sekundär: was ist die behauptete Primärquelle, ist sie unabhängig zugänglich?
- Bei Verdacht auf Promoter-Amplifikation: Original-Sprache, Original-Publikations-Organ, Original-Datum recherchieren.
- Wenn Original nicht prüfbar ist: nicht als Primär-Attestation verwenden; den Sekundär-Status im Output explizit nennen.

### 2.3 Search-Absence ≠ Beweis-für-Abwesenheit

**Regel.** Ein negatives Such-Ergebnis heißt nicht *„existiert nicht"*. Es heißt: *„in [Tool] mit [Query] [Datum] nicht gefunden"*. Diese Unterscheidung muss in Source-Tags wie in Argumentations-Strukturen sichtbar bleiben.

**Begründung.** Such-Tools haben Indexierungslücken, Operator-Mismatches, Paywall-Schranken, Sprach-Korpus-Beschränkungen, Versions-Caches, regionale Filter. Eine erfolglose Suche kann jeden dieser Faktoren reflektieren. Aus „nicht gefunden" *„existiert nicht"* zu schließen ist eine Inferenz-Sprung, der das Such-Tool von einem Hinweis-Geber zu einem Voll-Index promoviert — Status, den kein verfügbares Tool legitim einlöst.

**Operationalisierung.**
- Negativ-Ergebnis verbatim festhalten: Tool, Query (vollständig, inkl. Operatoren), Datum, Anzahl Treffer.
- Mögliche Gründe explizit machen: Indexierungslücke / Operator-Mismatch / Paywall / Sprach-Korpus / Cache-Staleness.
- Bei load-bearing Verwendung: ≥ 2 unabhängige Such-Tools, idealerweise mit unterschiedlichem Korpus.
- Bei verbleibender Unsicherheit: hedge-Sprache (*„in den verfügbaren Indices nicht nachweisbar"*, nicht *„existiert nicht"*).

---

## 3. Verbindung zu Verification-Levels

Jede source-tagged Behauptung trägt zusätzlich einen *Verification-Level*. Dies ist keine separate Disziplin, sondern die operative Konsequenz der drei Patterns:

| Level | Bedeutung | Quellen-Vertrauen |
|---|---|---|
| **deep-read** | Volltext gelesen, relevante Passagen verbatim verifiziert | hoch |
| **abstract** | Abstract / Zusammenfassung gelesen, Volltext nicht geöffnet | mittel |
| **agent-reported** | AI/Agent-Synthese aus Volltext, nicht selbst gegengelesen | niedrig (provisional) |
| **aggregator-only** | nur Snippet / Aggregator-Treffer, kein Volltext | nicht load-bearing |

Verification-Levels gelten **nicht nur** im Brief- oder Recherche-Stadium, sondern **auch bei späterer Synthese**: wenn ein Agent-Report später in eine Publikation eingeht, gilt weiter der `agent-reported`-Status, bis das Volltext-Gegenlesen erfolgt ist. Eine Synthese aus mehreren `agent-reported`-Befunden wird nicht durch Aggregation zu `deep-read`.

---

## 4. Fehler-Modus-Galerie

Failure-Modes, die diese Disziplin verhindert, lassen sich an drei dokumentierten Fällen demonstrieren:

- **Snippet-Cascade Failure-Mode** (PKA-ANSAS Case Study). Such-Snippet einer Verwaltungs-Sekundär-Quelle wurde als Primär-Attestation behandelt; nachgelagerte Synthese stabilisierte die Inkorrektheit über mehrere Bearbeitungs-Stufen. Methodologie-Lift: M03 Cascade-Risk-Audit (β-Kandidat, ADR-0012).

- **Promoter-Amplifikation LOR/hymn vs. hołd** (AX-006 Body-Worlds Wrocław). Marketing-Sekundär-Text als Original-Vatikan-Attestation behandelt. Methodologie-Lift: Pattern 2.2.

- **Agent-Report-Synthesis-Drift** (knowledge-representation bi-methodology-Track). Aggregierte Agent-Suchen wurden ohne per-Source-Verification-Level synthetisiert; Synthese-Stadium muss Verification-Level erneut prüfen. Methodologie-Lift: Pattern 3 + eigene Memory-Regel `research-synthesis-verification`.

Jeder Fall zeigt: Source-Disziplin ist nicht prophylaktisch oberflächlich, sondern adressiert dokumentierte Failure-Modes mit empirischer Last.

---

## 5. Operationalisierung im Workflow

Source-Disziplin ist nicht nur Source-Tag-Sammlung. Sie ist eine Workflow-Position:

- **Vor Recherche-Beginn:** Tool-Set ausweisen (Search-Engines, Aggregatoren, AI-Search-Agents), Verifikations-Plan deklarieren.
- **Während Recherche:** jeden Treffer per Pattern 2.1 / 2.2 / 2.3 klassifizieren; Verification-Level taggen.
- **Vor Synthese:** alle als `agent-reported` oder `aggregator-only` getaggten Treffer either upgraden (deep-read) oder aus load-bearing Argumenten entfernen.
- **Vor Publikation:** Pre-Publication-Re-Check gegen Original-Source, nicht gegen spätere Composition-Stage (siehe `writing-discipline.md` §Composition-Drift).
- **Nach Publikation:** Audit-Trail erhalten — welche Source-Tags wurden in welcher Stufe gesetzt, welche Verification-Levels waren load-bearing.

---

## 6. Was diese Disziplin **nicht** leistet

- Sie macht keine Aussage über die *intellektuelle Qualität* einer Primärquelle. Eine verbatim verifizierte Quelle kann trotzdem falsch, voreingenommen oder methodologisch problematisch sein. Source-Disziplin garantiert nur, dass die Quelle ist, was sie zu sein scheint — nicht, dass sie taugt.

- Sie ersetzt nicht **Schreib-Disziplin** (Descriptive-Accuracy beim Beschreiben von Artefakten, Composition-Drift während längerer Texte). Source-Disziplin schützt den Quellen-Eingang, Schreib-Disziplin den Text-Ausgang. Beide nötig.

- Sie ersetzt nicht **Aktanten-Selbstcheck** (Positionalität der eigenen Subject-Position). Source-Disziplin macht *Quellen* prüfbar, nicht den eigenen *Lese-Akt*.

---

## 7. Cross-Refs

- [[writing-discipline]] — Schreib-Disziplin: Descriptive-Accuracy + Composition-Drift, beobachtungs-Treue im Text-Ausgang
- [[actant-self-check]] — Aktanten-Selbstcheck: Positionalität des Analyse-Akts (Verb-Audit, Addressee-Audit, CMF-Inoculation)
- [[tool-discipline]] — Tool-Disziplin: empirische Tool-Validation als Methodologie-Erweiterung
- α-Reference: Memory `feedback_research_synthesis_verification` (Verification-Level-Rule, Operationalisierung in Claude-Code-Umgebung)

---

*Versionierung: working-draft. Substantielle strukturelle Re-Articulation (z.B. nach Empirie-Lift durch weitere Case-Studies oder Reader-Feedback) → Status-Update. Patch-Edits inline, kein Versionsbump.*
