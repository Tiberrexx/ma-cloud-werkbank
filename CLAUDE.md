# Cloud-Werkbank Masterarbeit Thomas Welzel — Arbeitsregeln

Masterarbeit (BHT Berlin, Abgabe 19.10.2026): datengetriebene Modelle (SINDYc, EDMDc, ARX als
Baseline) der Ladelufttemperatur eines Großgasmotors (49/60DF, zweistufiger Ladeluftkühler mit
HT- und LT-Stufe) für einen modellprädiktiven Regler (MPC). Gutachter: Prof. Henning
(closed-loop-Identifikation, reduzierte Modelle, Beobachter) und Prof. Merkel.

Diese Sitzung arbeitet autonom einen Auftrag aus `auftraege/` ab. Das Ergebnis prüft Copilot
lokal gegen Zotero und die Originale, bevor irgendetwas in die Arbeit übernommen wird.

## Ablauf

1. Auftrag in `auftraege/` lesen. `kontext/ch2.tex` (Grundlagen) und `kontext/ch3.tex` (Stand
   der Technik) als Bezug lesen. Diese Dateien sind Kopien und werden **nicht bearbeitet**.
2. Ergebnis als **eine** Markdown-Datei nach `ergebnisse/<auftragsname>_<JJJJ-MM-TT>.md`.
3. Auf einem eigenen Branch `cloud/<auftragsname>` committen und pushen. Keinen Merge auf main.
4. Am Ende der Ergebnisdatei: Abschnitt „Offen / nicht belegt“ mit allem, was nicht geprüft
   werden konnte.

## Quellenregeln (streng)

- **Nichts erfinden.** Jede Quelle nur, wenn sie im Web tatsächlich gefunden wurde: Autoren,
  Jahr, Titel, Zeitschrift/Verlag, **DOI oder stabile URL**.
- Status je Quelle angeben: `[Volltext gelesen]` (mit Seite/Abschnitt/Gleichung),
  `[nur Abstract]`, `[nur bibliografisch]`. Aussagen aus Abstracts nie als Volltextbeleg ausgeben.
- Wörtliche Zitate höchstens einen kurzen Satz, mit Seitenangabe. Sonst eigene Paraphrase.
- Keine Blogs, keine KI-generierten Übersichten, keine Wikipedia als Beleg. Lehrbücher, Journals,
  Konferenzbeiträge, arXiv (als Preprint gekennzeichnet).
- BibTeX-Einträge nur mit geprüften Metadaten; Key im Stil `nachnameTitelwoerterJahr`
  (Better-BibTeX, z. B. `bruntonDiscoveringGoverningEquations2016`).

## Schreibregeln

- **Nur Stichpunkte, keine ausformulierten Thesis-Absätze.** Thomas schreibt den Fließtext selbst.
- Deutsch, sachlich, keine KI-Floskeln („zudem“, „darüber hinaus“, „spielt eine zentrale Rolle“,
  Aufzählungen in Dreiergruppen aus Gewohnheit, Gedankenstrich-Ketten).
- Das Werkzeug heißt in allen Dateien **„Copilot“**.
- Formelzeichen wie in der Arbeit:
  - `T_eng,in` Ladelufttemperatur am Motoreintritt (nach dem Kühler, Regelgröße)
  - `T_col,in` Ladelufttemperatur am Kühlereintritt
  - `T_LTCW`, `T_HTCW` Eintrittstemperaturen Niedertemperatur- bzw. Hochtemperatur-Kühlwasser
  - `u_HP` Stellung des HP-Ladeluftkühler-Ventils, `Δp_HP` Druckverlust über den HP-Kühler
  - `ṁ_rel` relativer Luftmassenstrom-Proxy
  - HT/LT bezeichnen die **Stufe** des Kühlers, nicht „Bündel“ (in ch2.tex steht noch „Bündel“,
    das nicht übernehmen).
- LaTeX-Makros aus den Kapiteln (`\Tin`, `\Tout`, `\TLT`, `\THT`, `\valveCA`, `\mrel`, `\sindyc`,
  `\edmdc`) in Formelvorschlägen verwenden.

## Inhaltliche Leitplanken

- Arbeit ist **SINDYc mit physikalisch motivierter Bibliothek**, keine Greybox. Physik liefert nur
  die Termformen (Temperaturdifferenz × Betriebspunktfaktor), die Koeffizienten kommen aus Daten.
- Modelle müssen für einen **linearen QP-MPC** taugen (Stellgröße muss beim QP-Lösen linear bzw.
  mit bekanntem Koeffizienten eingehen).
- Bewertung in der Arbeit: offene Kette (OL), geschlossene Kette (CL), DoE-Validierung, Ventil-Gain.
  Keine eigenen Zahlen zu diesen Größen erfinden oder schätzen; diese Werkbank hat keine Messdaten.
- Keine Aussagen über Firmeninterna (Everllence) über das hinaus, was in `kontext/` steht.
