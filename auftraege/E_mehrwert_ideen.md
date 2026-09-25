# Auftrag E — Mehrwert und Ideensammlung aus Gutachtersicht (Copilot, 25.09.2026)

Ziel: Autonom herausarbeiten, wo die Arbeit noch Punkte holen kann, und daraus eine priorisierte
Ideenliste machen, die Thomas lokal (mit Messdaten) umsetzen oder verschriftlichen kann.
Nur Stichpunkte, keine Fließtexte. `kontext/` nicht bearbeiten.

## Bewertungskriterien der Hochschule (BHT)

1 Erfüllung der Aufgabenstellung · 2 Umfang der Ergebnisse · 3 Korrektheit · 4 Methodik (jede
Entwurfsentscheidung kritisch hinterfragt, Ergebnisse systematisch geprüft) · 5 Durchdringung ·
6 Selbstständigkeit und Kreativität (eigene Ergebnisse, sinnvolle Erweiterung der Fragestellung) ·
7 Qualität der Ausarbeitung. Ehrlich benannte Grenzen werten nicht ab. Eine umgesetzte Variante
schlägt zehn beschriebene. Größte Hebel: Methodik, Selbstständigkeit, Korrektheit.

Gutachter: Henning (closed-loop-Identifikation, reduzierte Modelle POD/Galerkin, Kalman-Beobachter,
Industrie Antriebsstrang), Merkel (NARX, closed-loop-Identifikation).

## Teil E1 — Lektorat aus Gutachtersicht (ch2, ch3)

- Je Kriterium 3–6 konkrete Befunde mit Zeilenbezug: Was fehlt, was ist unklar, wo ist eine
  Behauptung unbelegt, wo ist die Herleitung sprunghaft, wo fehlt die Brücke zur eigenen Arbeit?
- Welche Fragen würde Henning bzw. Merkel in der Verteidigung zu diesen Kapiteln stellen?
  (10 Fragen, je mit Stichpunkt-Antwortskizze und Beleg.)

## Teil E2 — Beitrag der Arbeit schärfen

- Aus ch2/ch3 ableiten: Was ist neu gegenüber der zitierten Literatur? 3–5 Beitragsformulierungen
  als Stichpunkte („Diese Arbeit zeigt …“), je mit der Literaturlücke, die sie schließt (Beleg).
- Nächste Verwandte in der Literatur (2019–2026) finden, die dem Thema am nächsten kommen
  (datengetriebene Modelle für Ladeluft-/Kühler-/Luftpfadtemperatur, SINDYc/Koopman für MPC an
  Motoren oder Prozessanlagen mit Messdaten). Je Arbeit: was sie macht, was sie nicht macht, wie
  sich diese Arbeit abgrenzt.

## Teil E3 — Ideen mit Mehrwert, priorisiert

Ideen sammeln, die mit wenig Aufwand viel Note bringen. Je Idee: Kurzbeschreibung · welches
Kriterium sie hebt · Aufwand (S/M/L, grob in Stunden) · ob Messdaten nötig sind · Literaturanker ·
Risiko. Kategorien:

- kleine zusätzliche Analysen (z. B. Sensitivität, Identifizierbarkeitsmaß, Konditionszahl, Unsicherheit
  der Koeffizienten, Vergleich mit einfacher physikalischer Referenz),
- Abbildungen, die eine Kernaussage schneller verständlich machen (Idee skizzieren, nicht zeichnen),
- Diskussions- und Ausblickspunkte mit Literaturbezug (Übertragbarkeit, Online-Nachführung, Feldbetrieb),
- methodische Absicherungen, nach denen ein Gutachter fragen würde.

Harte Grenzen: keine weiteren Prüfstandsmessungen möglich; Stellglied nur das HP-Ventil;
Kühlwassertemperaturen sind Störgrößen, nie Stellgrößen; MPC muss ein lineares QP bleiben;
Abgabe 19.10.2026, also nur Ideen, die bis dahin umsetzbar sind (große Ideen separat als Ausblick).
Keine Zahlen zu Modellgüte erfinden.

## Rückgabe

`ergebnisse/E_mehrwert_ideen_<datum>.md`: E1 Befundliste + Verteidigungsfragen, E2 Beitrag +
Verwandtentabelle, E3 Ideentabelle sortiert nach Nutzen/Aufwand mit Top 5 oben, zuletzt
„Offen / nicht belegt“. Quellenregeln aus `CLAUDE.md` gelten.
