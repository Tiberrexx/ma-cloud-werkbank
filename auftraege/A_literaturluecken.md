# Auftrag A — Literaturlücken schließen (Copilot, 25.09.2026)

Ziel: Für offene Quellen und Negativbefunde der Arbeit geprüfte Belege finden. Ergebnis ist eine
Kandidatenliste, keine Kapiteländerung.

## Teil A1 — fehlende Keys in Kap. 2 und 3 (`kontext/ch2.tex`, `kontext/ch3.tex`)

Je Punkt: vollständige Bibliografie + DOI/ISBN, genaue Stelle (Seite/Gleichung), ob die im Kapitel
behauptete Aussage dort wirklich steht, BibTeX-Entwurf.

1. Tschöke/Pucher 2018, S. 68, Gl. 41 „Rekuperationsgrad“ (ch2, Kennzahlen Ladeluftkühler).
2. Holmgren 2005, Gl. 3.26 (Druckfehler Plus statt Minus behauptet) — Titel ermitteln.
3. Llamas 2019, S. 18: Luftmassenstrom am Großmotor nicht gemessen.
4. Heywood, Internal Combustion Engine Fundamentals, S. 54, Gl. 2.27a (Liefergrad) — Auflage klären.
5. Beleg für `Δp ∝ ṁ²/ρ` bzw. `ṁ ∝ sqrt(Δp·p/T)` an Wärmeübertragern/Ladeluftkühlern
   (Lehrbuch oder Motorliteratur; ch2 „Beleg nachschlagen“).
6. ch3 `\anno`: Hansen 1989 (Erstquelle dual-Youla), Chiuso 2007 (Erstdefinition PBSID),
   Schrama 1993 (Erstquelle Zwei-Stufen-Verfahren).
7. Weitere Stellen mit „Key fehlt“ in ch2 (per Suche) mit aufnehmen.

## Teil A2 — Quellen der SINDYc-Methodenleiter mit Status [nZ]/[?]

Prüfen, ob es sie gibt, genaue Bibliografie, und ob die zugeschriebene Aussage stimmt:

- Bakarji, Callaham, Brunton, Kutz 2022, Nat. Comput. Sci. 2:834–844 (Buckingham-Pi/Dimensionsanalyse mit SINDy)
- Schaeffer & McCalla 2017, Phys. Rev. E (Integralform SINDy); Messenger & Bortz 2021 Weak SINDy ODE, MMS 19(3)
- Zhang & Schaeffer 2019, MMS 17(3) (Konvergenz STLSQ); Rudy u. a. 2017, Sci. Adv. (STRidge)
- Zheng u. a. 2019, IEEE Access (SR3); Kaptanoglu u. a. 2023, Nonlinear Dyn. (Solver-Benchmark)
- Hastie, Tibshirani, Tibshirani 2020, Stat. Sci. „Best subset, forward stepwise or lasso?“
- Piroddi & Spinelli 2003, Int. J. Control; Farina & Piroddi 2010 (Simulationsfehler-Minimierung NARX)
- Champion u. a. 2020, IEEE Access (SINDy mit Ungleichungsnebenbedingungen)
- Machado & Jones 2024, ACC, SINDy-SI (Nebeninformation Positivität/Monotonie)
- Kaptanoglu u. a. 2021, Phys. Rev. Fluids (Trapping, Stabilität)
- Tulleken 1993, Automatica (Grey-Box mit Vorzeichen stationärer Verstärkungen)
- Aguirre, Barroso, Saldanha, Mendes 2004, IEE Proc. CTA; Aguirre „Bird's Eye View“ arXiv 1907.06803 Abschn. 7.1/7.2
- Cisneros, Voss, Werner 2016, CDC (MPC mit quasi-LPV-Form)
- Schaeffer, Tran, Ward 2018, SIAM J. Appl. Math. (Monom- vs. Legendre-Basis, Sparsamkeit)
- Meinshausen & Bühlmann 2010, JRSS B; Hirsh, Barajas-Solano, Kutz 2022, R. Soc. Open Sci.
- Sheikh u. a. 2024 (LPV mit physikalisch motivierten Basisfunktionen + Lasso)
- Somalwar u. a. 2025, arXiv:2504.01766 (Mehrschritt-Kriterium)

## Teil A3 — Negativbefunde absichern

Gezielt suchen, ob es Arbeiten gibt zu (Ergebnis „gefunden: …“ oder „nicht gefunden, Suchweg: …“):

1. SINDy/SINDYc, bei dem ein **frei geschätzter Eigenterm** (x(k+1) mit freiem Koeffizienten auf x(k))
   die **Verschiebungsinvarianz** gegenüber Temperaturniveaus bricht; bzw. Bibliotheken nur aus
   Temperaturdifferenzen für Invarianz.
2. **Sparsamkeit ist basisabhängig** (Monom vs. verschoben vs. orthogonal) im SINDy-Kontext.
3. SINDy mit **ε-NTU-/Wärmeübertrager-Spalten** in der Bibliothek.
4. SINDy ausdrücklich als **LPV-Identifikation** gedeutet.
5. SINDYc/EDMDc an **Ladeluftkühlern, Motor-Luftpfaden oder Wärmeübertragern** mit Messdaten (2020–2026).

## Rückgabe

`ergebnisse/A_literaturluecken_<datum>.md`: Tabelle je Teil (Quelle · Bibliografie · DOI · Status ·
geprüfte Aussage ja/nein/teilweise · Stelle), darunter BibTeX-Block, zuletzt „Offen / nicht belegt“.
