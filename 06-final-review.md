# Projekt-Abschlussbericht: KLAR – kamerafreie Display-Brille mit Sehstärke

## Executive Summary

Die Kette Recherche → Strategie → Copy → Prototyp → QA ist in sich schlüssig. Die Kernidee „kamerafrei als Antwort auf die Akzeptanz- und Regulierungsprobleme“ folgt direkt aus belegten Daten (Bitkom 2026, EDSA, HmbBfDI, HateAid). Der Prototyp setzt die Copy nach zwei QA-Runden sauber und ohne unfreigegebene Angaben um. **Die Schwächen liegen nicht in der Ausführung, sondern im Geschäftsmodell:** Preis, Herstellkosten, Marktgröße und Zeitplan sind Annahmen. Die Abgrenzung zum direkten Vorbild Even Realities ist dünn, und das Privacy-Versprechen blendet das Mikrofon aus. Empfehlung: vor weiterer Marketingarbeit die wirtschaftliche und rechtliche Machbarkeit validieren.

## Übersicht der Ergebnisse

| Phase | Ergebnis | Status |
|---|---|---|
| 01 Research | Markttrends, Wettbewerb, Zielgruppen, Barrieren, 15 Quellen | ✅ Solide, Lücken offen benannt (keine DE-Absatzzahlen) |
| 02 Strategie | Positionierung KLAR, 3 USPs, GTM in 4 Phasen | ⚠️ Logisch hergeleitet, wirtschaftlich unvalidiert |
| 03 Copywriting | Slogan, Website-Texte, 8 Pitch-Aussagen | ⚠️ Strategietreu, aber nicht mit dem Prototyp synchron |
| 04 Prototyp | Statische Landing Page, mobile-first, Demo-Formulare | ✅ Demo-reif |
| 05 QA (2 Runden) | 1× 🔴 + 6× 🟡 behoben, 4 kleine 🟡 offen | ✅ Auslieferbar als interne Demo |

## Stärken

- **Saubere Herleitung:** Die Positionierung stützt sich auf belegte Zahlen (76 % / 62 % / 82 % Bitkom; EDSA-Hochrisiko-Einstufung; Strafanzeigen gegen Händler). Die Zahlen sind korrekt in Strategie und Copy übernommen.
- **Ehrlicher Umgang mit Unsicherheit:** Research markiert Schätzungen (40 Mio. Brillenträger, TDDDG-Paragraf). Die Strategie führt offene Punkte explizit auf. Die Copy kennzeichnet Annahmen mit \* und hält sie von der Seite fern.
- **Klares Händler-Argument:** „Smart Glass ohne Strafanzeige-Risiko“ nutzt die aktuelle Unsicherheit im Optikerhandel geschickt als Türöffner.
- **Bewusster Verzicht** (keine Kamera, keine Biometrie) wird konsequent durchgezogen, auf keiner Stufe wird eine ausgeschlossene Funktion versprochen.
- **Wirksame QA:** Der widersprüchliche Preis-Hinweis, die Verfügbarkeitssuggestion und der fehlende Datenschutzhinweis wurden erkannt und behoben.

## Verbesserungsbedarf

**Belegt vs. angenommen – zentrale Kennzahlen**

| Belegt (mit Quelle) | Annahme / unverifiziert |
|---|---|
| Globale Auslieferungen, Meta-Anteil ~81–82 % | Zielpreis ≤ 499 € (keine Herstellkosten bekannt) |
| Bitkom-Akzeptanzwerte | 40 Mio. Brillenträger in DE |
| Meta-Preise DE (419–899 €) | Marktgröße DE (keine Daten) |
| Fielmann: ~200 von 1.300 Filialen | Pilot mit 10–20 Optikern, Zeitplan |
| Batterieverordnung ab 18.02.2027 | Zulässigkeit der unauffälligen Bauform |
| Even Realities Nr. 2 weltweit H1 2026 | Even-Preis DE, On-Device-KI machbar |

**Inhaltliche Brüche zwischen den Stufen**

1. **Mikrofon blendet das Privacy-Narrativ aus.** Research nennt § 201 StGB (Vertraulichkeit des gesprochenen Wortes) als Barriere. KLAR „übersetzt Gespräche“, verarbeitet also Sprache Dritter, teils auf EU-Servern. „Sieht nichts. Speichert nichts.“ ist damit angreifbar, und „Kein Rechtsrisiko für Händler“ ist eine absolute Aussage ohne rechtliche Prüfung.
2. **Abgrenzung zu Even Realities ist schwach.** Even ist das Beweisstück der Strategie und zugleich der direkte Konkurrent mit identischem Konzept und Westeuropa-Stärke. Die Gegenargumente (deutsche KI, EU-Hosting, Wechselakku) sind kopierbar, Evens Stand dazu ist nicht recherchiert.
3. **Zeitplan unrealistisch.** Phase 0 (Hardware, CE/RED, Wechselakku, App, Sprach-KI) soll bis Feb. 2027 abgeschlossen sein, also in unter drei Monaten, ohne dass ein Produkt oder Hardware-Know-how dokumentiert ist.
4. **Burggraben „Wechselakku“ unsicher.** Meta strebt laut Research eine Ausnahme für Wearables an. Kommt sie, entfällt der Vorteil.
5. **Leichte Zahlendrift:** Die IDC-Prognose +40,5 % (2027) bezieht sich auf XR-Stückzahlen inkl. Headsets, die Strategie nennt sie „Marktwachstum“. Research selbst nennt im Text 82 %, in der Tabelle „~70–80 %“ Meta-Anteil.
6. **Spannungen im Produktversprechen:** „Unabhängig vom Smartphone-Ökosystem“ vs. Benachrichtigungen (setzen Smartphone-Kopplung voraus). Fielmanns „Nischen“-Einschätzung wird genannt, fließt aber in keine Absatzplanung ein.
7. **B2B (Phase 3) kaum tragfähig:** Ohne Kamera fällt Remote-Support als Hauptanwendung weg, ROI-Daten fehlen. Das ist ehrlich benannt, aber eher eine Option als ein Plan.
8. **Dokumentenpflege:** `03-copywriting.md` weicht an drei Stellen vom Prototyp ab. Ein interner HTML-Kommentar verrät die offene Bauform-Prüfung. Impressum/Datenschutz sind Platzhalter.

## Empfohlene nächste Schritte (nach Priorität)

1. **Business Case validieren:** Herstellkosten und Machbarkeit einer Display-Brille mit Sehstärke zu ≤ 499 € prüfen (BOM, Partner-OEM). Ohne diese Zahl stehen Positionierung und Pitch auf Sand.
2. **Rechtsgutachten einholen:** Mikrofon/Übersetzung (§ 201 StGB, DSGVO), Bauform-Zulässigkeit, Haltbarkeit der Aussage „ohne Strafanzeige-Risiko“. Claims danach anpassen, z. B. „Filmt niemanden“ statt „Speichert nichts“.
3. **Even Realities tief analysieren:** DE-Preis, Vertrieb, Datenhaltung, Akku. Daraus eine belastbare Differenzierung ableiten, z. B. Optiker-Exklusivität oder Sehstärke-Service.
4. **Zeitplan neu aufsetzen:** Phase 0 realistisch terminieren, Wechselakku-Ausnahme für Wearables beobachten.
5. **Nachfrage testen:** Landing Page als Fake-Door-Test mit echter Anmeldung (nach Impressum/Datenschutz) und Optiker-Interviews in 2–3 Großstädten, um die fehlende DE-Marktgröße zu ersetzen.
6. **Hygiene:** `03-copywriting.md` synchronisieren, HTML-Kommentar entfernen, Zahlenbasis (Meta-Anteil, IDC-Bezug) vereinheitlichen.
7. **B2B zurückstellen**, bis B2C-Pilotdaten vorliegen.
