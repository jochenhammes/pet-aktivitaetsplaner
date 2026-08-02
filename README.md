# PET-Aktivitätsplaner

Eine kleine, clientseitige Web-App zur Berechnung der benötigten Radiotracer-Aktivität für ein Tagesprogramm in der nuklearmedizinischen Praxis. Alles läuft im Browser – keine Datenübertragung, kein Backend.

**Live:** https://jochenhammes.github.io/pet-aktivitaetsplaner/

## Was die App berechnet

Ausgehend von der für jeden Patienten benötigten Aktivität zum Injektionszeitpunkt wird zurückgerechnet, wie viel Gesamtaktivität zum Kalibrierzeitpunkt bestellt bzw. kalibriert werden muss, damit unter Berücksichtigung des radioaktiven Zerfalls und der einzelnen Entnahmen jeder Patient im Tagesprogramm exakt seine Solldosis erhält.

**Eingaben:**
- Nuklid (Halbwertszeit hinterlegt für F-18, Ga-68, C-11, N-13, O-15, Rb-82, Cu-64, Zr-89, Ga-67, Tc-99m, I-123, I-131, In-111, Lu-177, Y-90, Ra-223, sowie „Benutzerdefiniert")
- Kalibrierzeitpunkt (= Zeitpunkt der ersten Injektion)
- Abstand der Injektionen in Minuten
- Anzahl Patienten
- Aktivität pro Patient (MBq)
- Kosten pro MBq zum Kalibrierzeitpunkt (€)

**Ausgaben:**
- Injektionsplan als Tabelle: Uhrzeit, Zeitabstand zur Kalibrierung, Dosis, Restaktivität vor und nach jeder Injektion
- Zerfallsdiagramm der Bestandsaktivität über den Tagesverlauf
- Gesamtaktivität, Gesamtkosten, Ø Kosten pro Patient

## Hinweis

Die Berechnung geht von exakter Einhaltung des Zeitplans aus und plant ohne Sicherheitsreserve (Restaktivität nach dem letzten Patienten = 0). Für Verzögerungen im Praxisablauf empfiehlt sich ein eigener Aufschlag. Hinterlegte Halbwertszeiten sind gerundete Referenzwerte. Die App ersetzt keine Aktivitätsmessung vor Injektion – die tatsächlich applizierte Aktivität ist stets unmittelbar vor Injektion zu messen und zu dokumentieren.

## Lokale Nutzung

Einfach `index.html` im Browser öffnen – keine Installation, keine Abhängigkeiten.

## Deployment

Automatisches Deployment auf GitHub Pages via GitHub Actions bei jedem Push auf `main` (siehe `.github/workflows/deploy.yml`).
