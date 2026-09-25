# Cloud-Werkbank Masterarbeit

Privates Repo für autonome Cloud-Sitzungen (claude.ai/code). Enthält keine Messdaten, keine
Kennzahlen und keine Studienordner.

- `CLAUDE.md` — Regeln für die Cloud-Sitzung
- `auftraege/` — ein Auftrag je Datei (A Literaturlücken, B Grundlagen Kap. 2, D Gutachterfragen)
- `kontext/` — Kopien von ch2.tex/ch3.tex (Stand beim letzten Kopieren, nur lesen)
- `ergebnisse/` — Rückgaben der Cloud-Sitzungen, je auf Branch `cloud/<auftrag>`

## Start einer Cloud-Sitzung

Auf claude.ai/code dieses Repo wählen, Prompt:

> Arbeite `auftraege/A_literaturluecken.md` nach `CLAUDE.md` ab. Pushe das Ergebnis auf den Branch `cloud/A_literaturluecken`.

## Rückweg

Lokal `git fetch` + Branch auschecken; Copilot prüft das Ergebnis gegen Zotero/Originale und
übernimmt Geprüftes als Stichpunkte in `99_Verschriftlichung`. Vor jedem neuen Push `kontext/`
aus `99_Verschriftlichung` neu kopieren.
