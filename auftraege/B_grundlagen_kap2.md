# Auftrag B — Grundlagen Kap. 2: Herleitungsgerüst prüfen und ergänzen (Copilot, 25.09.2026)

Ziel: Stichpunkt-Zuarbeit für die Grundlagen, die Thomas selbst ausformuliert. Masterniveau,
schrittweise hergeleitet, verständlich statt abgehoben. `kontext/ch2.tex` nicht bearbeiten.

## Teil B1 — Gegenprüfung der vorhandenen Herleitung (ch2, Abschnitt „Wärmeübertragung im Ladeluftkühler“)

Für jede nummerierte Gleichung (Luftwärmestrom, Wärmedurchgang kA, Stufengleichungen HT/LT,
LT-Spanne, Produktterme, Dynamik dT/dt = λ(T_stat − T), ε-NTU, Grenzfall C_r → 0, Druckverlust-
Proxy ṁ_rel):

- Stimmt die Algebra? Jeden Umformungsschritt nachrechnen (gern mit sympy), Fehler mit Zeile melden.
- Sind Annahmen vollständig genannt? Fehlende Annahme als Stichpunkt vorschlagen.
- Passt die zitierte Lehrbuchstelle zur Aussage (soweit online prüfbar)? Sonst als „nicht prüfbar“ markieren.
- Ist die Stufenreihenfolge (HT-Stufe zuerst, dann LT-Stufe) konsistent durchgehalten?

## Teil B2 — fehlende Grundlagenbausteine als Stichpunktgerüst

Je Baustein: 5–10 Stichpunkte, die zentrale(n) Gleichung(en) als LaTeX, 1–3 Lehrbuch-/Primäranker
mit Stelle, und ein Satz „Anschluss an diese Arbeit“.

1. **Zeitdiskretisierung**: kontinuierliches Modell → diskrete Form mit Abtastzeit (Euler vs. exakte
   ZOH-Diskretisierung eines PT1), Bedeutung für SINDYc in map-Form.
2. **Totzeit und Ratenbegrenzung eines Stellantriebs** im Modell (Padé vs. Verzögerungskette vs.
   verschobener Eingang), was davon in ein lineares QP passt.
3. **Lineares MPC als QP**: Prädiktionsgleichung, Kostenfunktion, Stellgrößenbeschränkung, weiche
   Ausgangsbeschränkung (Slack), offset-freie Regelung mit Störgrößenmodell (Stichwort
   Pannocchia/Rawlings, Maeder/Morari). Nur so tief, wie für Kap. 7 nötig.
4. **Stationäre Verstärkung (Gain) eines nichtlinearen Modells** am Arbeitspunkt: Definition über
   Ruhelage, Zusammenhang zur Linearisierung ∂T_stat/∂u_HP, warum sie für MPC entscheidend ist.
5. **Simulationsfehler vs. Einschritt-Prädiktionsfehler** (Freilauf vs. one-step), mit Ljung/Nelles-Anker.

## Rückgabe

`ergebnisse/B_grundlagen_kap2_<datum>.md`: B1 als Befundliste (Gleichung · Befund · Vorschlag),
B2 je Baustein als Stichpunktblock im Stil
`% COPILOT-STICHPUNKTE` + `\begin{itemize} … \end{itemize}` (LaTeX, direkt einfügbar), zuletzt
„Offen / nicht belegt“. Quellenregeln aus `CLAUDE.md` gelten.
