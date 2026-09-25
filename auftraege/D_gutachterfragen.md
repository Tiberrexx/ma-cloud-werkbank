# Auftrag D — Gutachterfragen vorab recherchieren (Copilot, 25.09.2026)

Hintergrund: Erstgutachter promovierte zu closed-loop Strömungsregelung mit reduzierten Modellen
(POD/Galerkin) und Kalman-Beobachtern, danach Industrie (Antriebsstrang). Zweitgutachter mit
NARX-/closed-loop-Bezug. Zu erwartende Fragen sollen mit Literatur beantwortbar sein.

Je Frage: kurze Antwortskizze in Stichpunkten, 2–5 belegte Quellen (Stelle angeben), und welche
Stelle in `kontext/ch3.tex` bzw. `kontext/ch2.tex` die Antwort aufnehmen könnte (nur Hinweis, keine Änderung).

1. **Einordnung SINDy/EDMD als reduzierte Modelle**: Verwandtschaft zu POD-Galerkin, was geht bei
   Trunkierung/Sparsifizierung verloren, wo ist SINDy kein ROM im klassischen Sinn?
2. **Wie begründen andere Arbeiten die Wahl der Bibliothek?** Physikalisch motiviert vs. generisch,
   Beispiele aus Prozess-/Motor-/Thermoanwendungen mit Messdaten.
3. **Identifikation aus Betriebsdaten unter Regelung**: Was sagen neuere Arbeiten (2018–2026) zu
   SINDy/Koopman/EDMD im geschlossenen Kreis? Gibt es Arbeiten, die Open-Loop-Prüfstandsdaten für
   den Fit und Closed-Loop-Daten nur zur Validierung nutzen?
4. **Offset-freier MPC und Beobachter**: Standardreferenzen, Zusammenhang Störgrößenbeobachter ↔
   Kalman-Filter ↔ exponentielle Glättung (EMA als stationärer Kalman-Filter für Random-Walk-Störung).
5. **Modellwahl für MPC jenseits der Vorhersagegüte**: Arbeiten, die zeigen, dass bessere RMSE
   nicht bessere Regelung heißt (Identification for Control, „Kriterium = Verwendungszweck“),
   Gain-Genauigkeit als Kriterium.
6. **Fairer Vergleich datengetriebener Modellklassen**: Wie werden ARX/SINDy/EDMD/NN in der
   Literatur fair verglichen (gleiche Daten, Hyperparameterwahl ohne Validierungsdaten, gepaarter
   Bootstrap)?

## Rückgabe

`ergebnisse/D_gutachterfragen_<datum>.md`, je Frage ein Abschnitt, zuletzt „Offen / nicht belegt“.
Quellenregeln aus `CLAUDE.md` gelten.
