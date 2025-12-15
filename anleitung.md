# 📖 Anleitung: Phils PF2e AI Translator

Willkommen beim ultimativen Übersetzungs-Tool für Foundry VTT (Pathfinder 2e). Dieses Modul hilft dir, Journal-Einträge schnell und konsistent mithilfe von KI (Gemini, ChatGPT, Claude etc.) zu übersetzen.

## 1. Erste Schritte

1.  **Installation**: Stelle sicher, dass das Modul in Foundry aktiviert ist.
2.  **Einstellungen**:
    * Navigiere zu `Einstellungen` > `Modul-Einstellungen` > `Phils PF2e AI Translator`.
    * **AI Provider**: Wähle deinen KI-Anbieter (z. B. Google Gemini).
    * **Game System**: Wähle "Pathfinder 2e" (wichtig für den Regel-Kontext).
    * **Max Prompt-Länge**: Standard ist 100.000 Zeichen. *Hinweis: Erhöhe diesen Wert nur, wenn du ein kostenpflichtiges Abo beim KI-Anbieter hast.*

## 2. Übersetzung (Schritt-für-Schritt)

### A. Journal auswählen
Öffne den "AI Translation Assistant" über den Button im Journal-Browser und ziehe ein Journal (oder eine Seite) in das Fenster.


### B. Konfiguration & Prompt erstellen
Im Konfigurationsfenster:
1.  **Seiten wählen**: Markiere die Seiten, die übersetzt werden sollen.
    * *Tipp:* Nimm nicht zu viele Seiten auf einmal, sonst wird die Anfrage an die KI zu lang.
2.  **Starten**: Klicke auf `Übersetzung starten`.
3.  **Zwischenablage**: Das Modul hat nun einen speziell formatierten Text in deine Zwischenablage kopiert.
    * Dieser beginnt mit `[ANFANG_DER_ANFRAGE]` und endet mit `[ENDE_DER_ANFRAGE]`.
    * *Warnung:* Sollte der Text zu lang für die KI sein, erhältst du eine Warnmeldung.

### C. KI füttern
1.  Öffne deinen KI-Chat (z. B. Gemini oder ChatGPT). Der Tab sollte sich meist automatisch öffnen.
2.  Klicke in das Textfeld und drücke `STRG+V` (Einfügen).
3.  Sende die Nachricht ab.

4. ### 4. Antwort verarbeiten
Die KI antwortet mit **zwei separaten Blöcken**. Füge diese **nacheinander** ein:

1.  **Block 1 (Übersetzung):**
    *   Kopiere den **ersten JSON-Code-Block** (unter "BLOCK 1").
    *   Füge ihn in das Textfeld des Moduls ein.
    *   Klicke auf **"Aktualisieren"**.
    *   *Das Journal wird nun aktualisiert.*

2.  **Block 2 (Glossar):**
    *   Nach dem ersten Schritt öffnet sich (falls nötig) automatisch ein **neues Fenster** ("Glossar aktualisieren" oder "Glossar JSON").
    *   Kopiere nun den **zweiten JSON-Code-Block** aus der KI-Antwort (unter "BLOCK 2").
    *   Füge ihn in dieses neue Fenster ein und bestätige.
    *   *Dein 'AI Glossary' wird nun mit den neuen Begriffen erweitert.*

---

---

## 3. Die Fenster im Detail

### 📋 Das Resultat-Fenster ("Result")
Hier landest du immer, nachdem du die Antwort der KI kopiert hast.
*   **Eingabefeld**: Hier fügst du die Antwort (STRG+V) ein.
*   **Button "Journal aktualisieren"**: Wendet die Änderungen an.
*   **Button "Überspringen"**: Falls die KI Unsinn geredet hat und du diese Seite auslassen willst.

### 📚 Das Glossar-Fenster ("Update Glossary")
Dieses Fenster erscheint automatisch, wenn die KI neue Begriffe gefunden hat, die noch nicht in deinem Glossar stehen.
*   **Liste**: Zeigt dir die neuen Begriffe (z.B. `Fireball = Feuerball`).
*   **"Zum Glossar hinzufügen"**: Speichert die Begriffe dauerhaft. Ab jetzt weiß die KI bei *jeder* zukünftigen Übersetzung, wie diese Begriffe heißen.

### ⚖️ Das Konflikt-Fenster ("Glossar Konflikte")
*Erscheint vor allem beim Grammatik-Check.*
Dieses Fenster ist deine Sicherheits-Zentrale. Es geht auf, wenn die KI versucht, einen Begriff zu ändern, der eigentlich durch dein Glossar geschützt ist.
*   **Original**: Zeigt den Begriff, wie er im Glossar steht (z.B. "Langschwert").
*   **Neu (KI)**: Zeigt, was die KI daraus machen wollte (z.B. "Langes Schwert"). Beachte das es manchmal schwer sein kann vorher von nachher zu      unterscheiden. 
*   **Entscheidung**:
    *   🔘 **Wiederherstellen**: Der Begriff aus dem Glossar wird erzwungen. (Sicherste Option).
    *   🔘 **Neu behalten**: Du erlaubst der KI, den Begriff in diesem speziellen Fall zu ändern (z.B. bei Grammatik-Anpassungen).
*   **"Alle neuen übernehmen"**: Akzeptiert alle Änderungen der KI mit einem Klick.

---

## 4. Features & Funktionen

### 📚 KI-Glossar (Für konsistente Begriffe)
Damit die KI weiß, dass "Mage Hand" nicht "Magierhand", sondern "Magische Hand" heißt, nutzt das Modul ein Glossar.
* **Funktionsweise**: Das Modul sucht nach einem Journal namens **"AI Glossary"** (oder "AI Glossar"). Existiert es, wird der Inhalt automatisch jeder Anfrage beigefügt.
* **Erstellung**: Nimm ein Journal mit vielen Namen/Orten, setze den Haken bei "Nur Glossar (Namen) generieren" und lass die KI eine Liste für dich erstellen.

### 📝 Grammatik-Check
* Wähle im Menü `Grammatik-Check` statt `Übersetzung`.
* Die KI prüft den Text auf Fehler und Logik (z. B. korrigiert sie "Schattenwandeln Zwilling" zu "Schattenzwilling").
* *Sicherheit:* Begriffe aus dem Glossar werden dabei geschützt, damit die KI sie nicht "verschlimmbessert".

### 🔄 Auto-Batch (Workflow-Automatisierung)
Das Modul denkt mit!
*   **Automatische Weiterschaltung**: Nachdem du einen Batch (Standard: 10 Seiten, einstellbar in den Settings) bearbeitet hast, öffnet sich automatisch das nächste Fenster.
*   **Intelligente Auswahl**:
    *   Im **Übersetzungs-Modus**: Wählt die nächsten 10 *unübersetzten* Seiten.
    *   Im **Grammatik-Modus**: Wählt die nächsten 10 Seiten, die noch *nicht geprüft* wurden.

### ✅ Status-Symbole
In der Seitenliste siehst du den Status jeder Seite:
*   ✅ **Grüner Haken**: Diese Seite wurde bereits **übersetzt**.
*   **Blaues "AB" mit Haken**: Diese Seite wurde bereits **grammatikalisch geprüft**.

---

## 5. Fehlerbehebung (Troubleshooting)

### Die KI "halluziniert" (Häufigster Fehler)
Die KI kann manchmal den Kontext verlieren oder Unsinn schreiben. Das lässt sich technisch nie zu 100 % verhindern.
* **Lösung**: Wenn die KI offensichtlich Fehler macht ("spinnt"), versuche nicht, sie im selben Chat zu korrigieren. Das verschwendet meist nur deine Tokens (Nutzungslimit).
* **Besser**: Starte einen **neuen Chat** und füge den Prompt erneut ein.

### Fehler: "Incomplete AI Response"
Die KI hat mitten im Satz aufgehört, weil die maximale Antwortlänge erreicht wurde.
* **Lösung A**: Schreibe der KI "Weiter" oder "Continue". Kopiere danach **beide** Teile der Antwort zusammen in das Tool.
* **Lösung B**: Wähle beim nächsten Mal weniger Seiten aus ("Batch Size" in den Einstellungen reduzieren).

### Fehler: "JSON invalid"
Die KI hat keinen gültigen Programm-Code geliefert oder Text außerhalb der Code-Blöcke geschrieben.
* **Lösung**: Überprüfe die Antwort. Versuche, nur den Teil zwischen ` ```json ` und ` ``` ` manuell zu kopieren und einzufügen. Hilft das nicht -> Neuer Chat.

### Fehler: "ID Verification Failed"
Die KI hat halluziniert und versucht, die internen IDs der Journal-Seiten zu ändern oder zu löschen. Das Modul blockiert dies zum Schutz deiner Daten.
* **Lösung**: Versuche es erneut ("Regenerate" bei der KI). Wenn das Problem bestehen bleibt, wähle weniger Seiten aus oder starte einen neuen Chat.

### Fehler: "Glossary JSON in Translation" / "Invalid Glossary JSON"
Du hast versehentlich den falschen Modus benutzt oder das falsche JSON eingefügt.
* **Lösung**:
    * Wenn du **"Nur Glossar generieren"** wolltest -> Stelle sicher, dass du das Glossar-JSON kopiert hast.
    * Wenn du **übersetzen** wolltest -> Stelle sicher, dass du NICHT das Glossar-JSON kopiert hast (manchmal gibt die KI beides aus).


---

## 6. Profi-Tipps
* **Custom Instructions**: Du kannst im Übersetzungs-Fenster eigene Anweisungen geben (z. B. "Nutze das informelle 'Du' statt 'Sie'" oder "Schreibe im Piraten-Slang").
* **Konflikt-Lösung**: Wenn die KI einen Begriff anders übersetzt, als er im Glossar steht, fragt dich das Modul, ob du den alten Begriff behalten oder den neuen übernehmen möchtest.