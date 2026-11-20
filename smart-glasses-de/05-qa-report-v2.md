# QA-Prüfbericht – Runde 2

Geprüft: `04-prototype/index.html` (überarbeitete Fassung) gegen `05-qa-report.md`, `02-strategy.md` und `03-copywriting.md`. Ich habe nur den Quelltext geprüft, die Seite wurde nicht im Browser gerendert.

## Status der Punkte aus Runde 1

| # | Punkt aus Runde 1 | Status | Nachweis |
|---|---|---|---|
| 🔴 1 | Preis-Hinweis widerspricht sich selbst, Zielpreis ≤ 499 € öffentlich sichtbar | ✅ Behoben | `p.price-note` ist entfernt. Im Dokument gibt es weder „499“ noch „€“ noch „Zielpreis“. |
| 🟡 1 | Interne Annotationen im Kundentext (Footer-Fußnote, * in Karte 02) | ✅ Behoben | Die Fußnote ist weg und der Footer enthält nur noch Demo- und Rechtshinweise. Aus Karte 02 sind der Zusatz zur Bauform und das * entfernt, der Text endet jetzt mit „Das Design ist alltagstauglich.“ Die Begründung steht als HTML-Kommentar im Quelltext (siehe 🟡 2 unten). |
| 🟡 2 | Primär-CTA suggeriert Verfügbarkeit | ✅ Behoben (Variante Fallback) | Das PLZ-Formular meldet jetzt: „In deiner Region gibt es noch keinen Partner-Optiker. Trag dich bei ‚Benachrichtige mich zum Start‘ ein …“. Der CTA-Text selbst ist unverändert und deckt sich mit der Copy. Eine kleine Restanmerkung steht unter 🟡 3. |
| 🟡 3 | E-Mail-Formular ohne Datenschutzhinweis, Impressum und Datenschutz fehlen | ✅ Behoben | Der `p.privacy-note` erklärt Double-Opt-in und Zweckbindung und verlinkt auf `#datenschutz`. Im Footer gibt es `nav` mit „Impressum“ und „Datenschutz“, beide Anker haben gültige Ziele (`#impressum`, `#datenschutz`). Die Platzhalter sind sichtbar als Platzhalter gekennzeichnet (siehe 🟡 1 unten). |
| 🟡 4 | Interner Arbeitstitel „Kernvorteile“ als h2 | ✅ Behoben | Die Überschrift lautet jetzt `<h2 id="benefits-title">Warum KLAR?</h2>`. |
| 🟡 5 | Schiefe Formulierung in Karte 04 | ✅ Behoben | Neuer Text: „Der Akku ist austauschbar, so hält deine Brille länger.“ |
| 🟡 6 | Slogan-Pill bricht mobil unschön um | ✅ Behoben | `@media (max-width: 759px) { .slogan { border-radius: 12px; } }` |

## 🔴 Muss behoben werden

Keine.

## 🟡 Sollte behoben werden

1. **Impressum und Datenschutzerklärung sind noch Platzhalter.** Betroffen sind `footer` → `p#impressum` und `p#datenschutz`.
   - Für die Demo ist das korrekt gekennzeichnet („Platzhalter – wird vor einem Live-Gang ergänzt“). Vor einer Veröffentlichung in DE sind beide Texte aber zwingend.
   - **Fix:** Die echten Texte vor dem Live-Gang einsetzen. Für die Demo besteht kein Handlungsbedarf.

2. **Interne Notiz im HTML-Quelltext.** Betroffen ist `article.card` 02 → `<!-- Intern: … Bauform rechtlich noch nicht bestätigt … -->`.
   - Die Notiz ist nicht sichtbar, aber über „Seitenquelltext anzeigen“ lesbar. Sie verrät eine offene rechtliche Prüfung. Für eine interne Demo ist das unkritisch, vor einer externen Weitergabe sollte sie raus.
   - **Fix:** Den Kommentar vor der Weitergabe entfernen und den Hinweis im Projekt-Tracking führen. Die überflüssige Leerzeile danach kann ebenfalls weg.

3. **Fallback der Optiker-Suche ist pauschal und verweist nur auf das andere Formular.** Betroffen ist das PLZ-Formular → `data-demo`.
   - Vor dem Pilotstart (Frühjahr 2027) ist die Meldung inhaltlich richtig. Es gibt aber kein E-Mail-Feld direkt im Fallback, und Nutzer müssen selbst zum zweiten Formular wechseln. Auf Mobilgeräten liegt es unterhalb, wird also nicht automatisch gesehen.
   - **Fix (optional):** Den Hinweis mit einem Anker oder Fokus auf `#email` verbinden. Ab dem Pilot braucht es eine echte PLZ-Logik.

4. **Copy-Dokument ist nicht mehr synchron mit dem Prototyp.** Betroffen ist `03-copywriting.md`.
   - Drei Stellen weichen jetzt bewusst und korrekt von der Copy ab: die h2 („Warum KLAR?“ statt „Kernvorteile“), Karte 02 (ohne Bauform-Zusatz) und Karte 04 (neue Akku-Formulierung). Inhaltlich ist der Prototyp so richtiger, aber die Quelle der Wahrheit stimmt nicht mehr.
   - **Fix:** Die Änderungen an den Copywriter zurückmelden und `03-copywriting.md` nachziehen.

## 🟢 Bestanden

- **HTML-Validität:** Alle Tags sind geschlossen und korrekt verschachtelt. Neu hinzugekommen sind `nav`, `privacy-note` und der HTML-Kommentar, alle sauber eingebettet. `lang="de"`, `charset` und `viewport` sind gesetzt. Die Überschriftenhierarchie h1 → h2 → h3 stimmt, ebenso die `aria-labelledby`-Bezüge.
- **Keine unfreigegebenen Angaben:** Es gibt keinen Zielpreis, kein \* und keine Bauform-Aussage „wie eine normale Korrekturbrille“. Alle öffentlich sichtbaren Aussagen (kamerafrei, Sehstärke über Optiker, EU-Datenhaltung, kein KI-Training, keine Gesichtserkennung, austauschbarer Akku) sind von der Strategie gedeckt.
- **Textübernahme:** Slogan, Headline, Subheadline, die Karten 01 und 03 sowie beide CTA-Texte stimmen wortgleich mit `03-copywriting.md` überein. Die Abweichungen in Karte 02 und 04 und bei der h2 sind gewollte QA-Fixes (siehe 🟡 4).
- **Zahlen:** Die 76 % (Bitkom 2026) sind korrekt und mit Quelle angegeben.
- **CTA:** Es gibt einen klaren primären CTA im Hero mit gültigem Anker `#cta` und zwei klar benannte Aktionen im CTA-Bereich. Der Fallback verhindert ein falsches Verfügbarkeitsversprechen.
- **Datenschutz/Vertrauen:** Der Double-Opt-in-Hinweis und der Link zur Datenschutzerklärung passen zum Kernversprechen „Speichert nichts“.
- **Mobile Layout:** Der Ansatz ist weiterhin mobile-first. Die Slogan-Pill ist mobil korrigiert, die Formulare umbrechen per `flex-wrap`, und `privacy-note` und `form-msg` nehmen per `width: 100%` jeweils die volle Breite ein. Kein horizontaler Overflow zu erwarten.
- **Links/Platzhalter:** Keine leeren `href`, alle Anker (`#cta`, `#impressum`, `#datenschutz`) haben Ziele, kein Lorem ipsum. Die Platzhalter sind explizit als Demo-Platzhalter markiert.
- **Formulare und Script:** Die `label`/`id`-Paare sind korrekt, `required`, `type="email"`, `pattern` und `inputmode` sind gesetzt. `preventDefault` verhindert das Absenden, und die Rückmeldung läuft über `aria-live`.
- **Demo-Kennzeichnung:** Banner, `<title>`, Formularhinweise und Footer kennzeichnen die Seite durchgängig als Prototyp.
- **Kontrast (geschätzt):** Die neue Warnfarbe `#8a5a00` auf `#fff4dc` bzw. `#f6f5f1` liegt bei ca. 5:1 und damit über 4,5:1.

## Fazit: Auslieferbar?

**Ja, als Demo-Prototyp auslieferbar.** Alle sieben Punkte aus Runde 1 (1× 🔴, 6× 🟡) sind behoben, und es sind keine neuen 🔴-Probleme entstanden. Offen sind nur kleinere 🟡-Punkte. Vor einer externen Weitergabe sollte der HTML-Kommentar entfernt werden. Vor einem öffentlichen Live-Gang braucht es das echte Impressum, die echte Datenschutzerklärung und eine echte PLZ-Logik. Außerdem sollte `03-copywriting.md` an den Prototyp angeglichen werden.
