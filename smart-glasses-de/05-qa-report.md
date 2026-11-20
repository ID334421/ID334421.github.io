# QA-Prüfbericht

Geprüft: `04-prototype/index.html` gegen `02-strategy.md` und `03-copywriting.md` (nur Quelltextprüfung, kein Browser-Rendering).

## 🔴 Muss behoben werden

1. **Preis-Hinweis widerspricht sich selbst** – `section#cta` → `<p class="price-note">`
   - Aktuell: „Ein Preis wird erst nach der Kostenvalidierung genannt. Zielpreis ≤ 499 €* (noch nicht bestätigt).“ Der erste Satz sagt, es wird kein Preis genannt, der zweite nennt ihn.
   - In `03-copywriting.md` ist das als *Hinweis zum Preis* markiert, also eine interne Anweisung und kein Seitentext. Laut Copy-Vorgabe dürfen mit * markierte Angaben außerdem erst nach Freigabe veröffentlicht werden.
   - **Fix:** Den Absatz komplett entfernen. Alternativ, falls ein Preisbezug gewünscht ist: „Preis folgt in Kürze, melde dich an und erfahre ihn zuerst.“ (ohne Zahl).

## 🟡 Sollte behoben werden

1. **Interne Annotationen stehen im Kundentext** – `<footer>` → erstes `<p>`
   - „Annahme laut Strategiedokument, vor Veröffentlichung zu prüfen … (rechtliche Bestätigung ausstehend)“ ist eine interne Notiz. Für die Demo vertretbar, aber kein Endkundentext.
   - **Fix:** Als sichtbar internen Hinweis kennzeichnen (z. B. in den `.demo-banner`-Stil verschieben) oder in einen HTML-Kommentar umwandeln. Das * in Karte 02 (`article.card` „Deine Sehstärke…“) dann ebenfalls entfernen oder neutral auflösen.

2. **Primär-CTA suggeriert Verfügbarkeit** – Hero `<a class="btn">` und `cta-box` 1 (`form` PLZ)
   - „Jetzt Partner-Optiker in deiner Nähe finden“ verspricht, dass es Optiker gibt. Laut Strategie startet der Pilot erst ab Frühjahr 2027 mit 10–20 Optikern in 2–3 Großstädten, die meisten PLZ hätten also kein Ergebnis. Parallel heißt es im zweiten CTA „Benachrichtige mich zum Start“.
   - **Fix:** Für die Optiker-Suche einen Fallback-Zustand vorsehen („In deiner Region noch kein Partner, wir benachrichtigen dich“ + E-Mail-Feld) oder den CTA in der Vorstartphase umformulieren (z. B. „Prüfen, ob KLAR in deiner Stadt startet“). Mit dem Copywriter abstimmen.

3. **E-Mail-Formular ohne Datenschutzhinweis** – `cta-box` 2 → `<form>` mit `#email`
   - Bei einer Marke, deren Kernversprechen „Speichert nichts“ / Privacy-by-Design ist, fehlt ein Hinweis zur Datenverarbeitung (Double-Opt-in, Link zur Datenschutzerklärung). Für den Live-Gang in DE zudem rechtlich nötig, ebenso Impressum und Datenschutz im `<footer>`.
   - **Fix:** Unter dem Button einen Kurzsatz plus Link auf die Datenschutzerklärung einfügen, im Footer Platzhalter-Links „Impressum“ / „Datenschutz“ ergänzen (für die Demo deutlich als Platzhalter markieren, keine leeren `href`).

4. **Section-Überschrift ist ein interner Arbeitstitel** – `section.benefits` → `<h2 id="benefits-title">Kernvorteile</h2>`
   - „Kernvorteile“ ist die Gliederungsüberschrift aus dem Copy-Dokument, kein Kundentext.
   - **Fix:** Kundengerichtete Überschrift, z. B. „Warum KLAR?“ (mit Copywriter abstimmen).

5. **Unklare Formulierung in Karte 04** – `article.card` „Gebaut für Europa.“ → `<p>`
   - „…damit deine Brille länger hält als ein Akku“ ist inhaltlich schief (stammt so aus der Copy).
   - **Fix:** z. B. „Der Akku ist austauschbar, so hält deine Brille deutlich länger.“ Rückmeldung an den Copywriter.

6. **Slogan-Pill bricht mobil unschön um** – Hero → `<p class="slogan">` (`border-radius: 999px`, `display: inline-block`)
   - Der lange Slogan wird unter ~500 px zwei- bis dreizeilig, die Pill-Form wirkt dann als verzerrte Kapsel.
   - **Fix:** Per Media Query unter 760 px `border-radius: 12px` setzen oder den Slogan kürzen (z. B. nur „Sieht nichts. Speichert nichts.“).

## 🟢 Bestanden

- **HTML-Validität:** Alle Tags sind geschlossen, die Verschachtelung ist korrekt, `lang="de"`, `charset` und `viewport` sind gesetzt. Struktur `header` / `main` / `section` / `footer` ist semantisch sinnvoll, die Überschriftenhierarchie h1 → h2 → h3 stimmt.
- **Textübernahme:** Slogan, Headline, Subheadline, alle vier Vorteils-Karten und beide CTA-Texte stimmen wortgleich mit `03-copywriting.md` überein.
- **Positionierung:** Kamerafrei, Sehstärke über Optiker, EU-Datenhaltung, kein KI-Training, keine Gesichtserkennung und austauschbarer Akku entsprechen den drei Kern-Verkaufsargumenten der Strategie. Keine Funktion (Foto/Video, Biometrie) wird versprochen, auf die bewusst verzichtet wird.
- **Zahlen:** Bitkom 76 % korrekt übernommen und mit Quelle versehen.
- **Mobile Layout:** Mobile-first mit einspaltigen Grids, ab 760 px zwei Spalten (`.hero`, `.cards`, `.cta-grid`). `h1`/`h2` skalieren per `clamp()`, das SVG ist auf `width: 100%; max-width: 420px` begrenzt, die Formulare umbrechen per `flex-wrap` und `flex: 1 1 200px`. Kein horizontaler Overflow zu erwarten.
- **Formulare:** `label for`/`id` korrekt verknüpft, `required`, `type="email"`, PLZ-`pattern` und `inputmode="numeric"` gesetzt. Die Rückmeldung läuft über `aria-live`, und ein `preventDefault` verhindert echtes Absenden.
- **Demo-Kennzeichnung:** Banner, Formularhinweise und Footer machen klar, dass das ein Prototyp ohne Datenversand ist.
- **Links/Platzhalter:** Keine leeren `href`, kein Lorem ipsum. Der einzige Anker `#cta` hat ein gültiges Ziel.
- **Barrierefreiheit (Basis):** Das SVG hat `role="img"` und `aria-label`, die Kontraste der Textfarben liegen schätzungsweise über 4,5:1, und der Standard-Fokusrahmen bleibt erhalten.

## Fazit: Auslieferbar?

**Als interner Demo-Prototyp: ja, nach Behebung des einen 🔴-Punkts** (widersprüchlicher Preis-Hinweis im CTA-Bereich). Die 🟡-Punkte, vor allem CTA-Fallback, Datenschutzhinweis und die internen Annotationen, sollten vor einer Vorführung bei externen Stakeholdern bzw. zwingend vor einem öffentlichen Live-Gang erledigt sein.
