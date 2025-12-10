# Exegese der funktionalen Systemarchitektur des Phil's PF2e AI Translator

**Vorbemerkung:**
Dieses Dokument dient der dezidierten Erläuterung der operativen Mechanismen der vorliegenden Softwarelösung. Es richtet sich an ein Auditorium, welches die Präzision der deutschen Sprache zu schätzen weiß und sich nicht mit profanen Anglizismen oder technokratischem Jargon zufriedengeben möchte.

---

## I. Präambel: Die Rolle des menschlichen Intermediärs

In Ermangelung einer direkten, kostenintensiven Schnittstelle (API) zu den großen Sprachmodellen unserer Zeit, bedient sich dieses Modul eines bewährten, wenngleich archaisch anmutenden Verfahrens: der Nutzung des menschlichen Anwenders als biologische Middleware.

Der Nutzer fungiert hierbei als *Transmissionsriemen* zwischen dem lokalen Foundry VTT System und der externen künstlichen Intelligenz. Dieser Prozess, obgleich er manuelle Arbeitsschritte erfordert, garantiert die vollständige Kostenfreiheit der Übersetzungstätigkeit und demokratisiert somit den Zugang zu fortschrittlicher Technologie.

## II. Die Wahrung der terminologischen Konsistenz

Das fundamentale Problem maschineller Übersetzung im Kontext komplexer Regelwerke (wie Pathfinder 2e) ist die Tendenz der Algorithmen zur unerwünschten Kreativität. Ein „Fireball“ darf unter keinen Umständen als „Feuerkugel“ oder „Brandgeschoss“ übersetzt werden, so poetisch dies auch klingen mag.

Um dies zu verhindern, implementiert das Modul ein rigoroses Verfahren der **kontextuellen Injektion**:

1.  **Konsultation der Primärquellen:** Das Modul analysiert die offiziellen deutschen Übersetzungsdaten (`lang-de-pf2e`). Es „weiß“ somit a priori, wie spezifische Termini zu übertragen sind.
2.  **Das Glossar als Gesetz:** Über ein dediziertes Journal („AI Glossary“) kann der Anwender eigene terminologische Festlegungen treffen. Diese überschreiben jegliche Standardalgorithmen und besitzen dogmatischen Charakter.

## III. Der Grammatik-Check: Ein Verfahren zur Wahrung der Integrität

Besonderes Augenmerk verdient die Funktionalität der grammatikalischen Revision. Hierbei stehen wir vor einem dialektischen Dilemma: Wir wünschen eine Verbesserung des Satzbaus (Syntax) und des Stils, verbieten jedoch kategorisch die Alteration feststehender Regelbegriffe (Semantik).

Die Lösung liegt in einem Verfahren, welches ich als **„Indexierte Tokenisierung“** bezeichnen möchte:

1.  **Identifikation und Isolation:** Relevante Termini (z.B. „Machtangriff“) werden vor der Übermittlung an die KI identifiziert.
2.  **Substitution:** Sie werden durch abstrakte Platzhalter ersetzt (z.B. `[[#1:Machtangriff]]`). Dies signalisiert der KI unmissverständlich: *„Dieser Textbaustein ist sakrosankt. Er darf syntaktisch eingebettet, jedoch nicht intrinsisch modifiziert werden.“*
3.  **Verifikation:** Nach Rückerhalt des Textes prüft das Modul, ob die Integrität dieser Platzhalter gewahrt wurde. Sollte die KI – in einem Anfall von künstlicher Hybris – versuchen, aus dem „Machtangriff“ einen „Kraftschlag“ zu formen, interveniert das System mit einer sofortigen Fehlermeldung (Konflikt-Dialog).

## IV. Sicherheitsarchitektur und Redundanz

Da das Vertrauen in stochastische Sprachmodelle stets begrenzt sein sollte, operiert das Modul nach dem Prinzip der maximalen Risikominimierung.

*   **Präventive Duplikation:** Vor jeder Schreiboperation wird eine vollständige Kopie (Backup) des betroffenen Journals angelegt.
*   **Strukturelle Validierung:** Das System verifiziert, ob die interne Datenstruktur (IDs, Verlinkungen) der Rückgabe kongruent mit dem Original ist. Eine „Halluzination“ von nicht existenten Verweisen wird rigoros sanktioniert und der Import verweigert.

## V. Konklusion

Der *Phil's PF2e AI Translator* ist somit nicht bloß ein Werkzeug, sondern ein orchestraler Dirigent, der die Kakophonie generativer KI in die harmonische Symphonie eines perfekt übersetzten Regelwerkes zwingt – stets unter der strengen Aufsicht des menschlichen Intellekts.

*Hochachtungsvoll,*
*Die Systemarchitektur*
