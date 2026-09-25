# Auftrag E — Mehrwert und Ideensammlung aus Gutachtersicht (Cloud-Sitzung, 25.09.2026)

Grundlage: `auftraege/E_mehrwert_ideen.md` (auf main), `kontext/ch2.tex`, `kontext/ch3.tex`
(Kopie vom 25.09.2026), Ergebnisse der Aufträge A, B und D dieser Sitzung (Branches
`cloud/A_literaturluecken`, `cloud/B_grundlagen_kap2`, `cloud/D_gutachterfragen`).
Nur Stichpunkte. Keine Zahlen zu Modellgüte; Aufwände sind grobe Arbeitszeitschätzungen.

## Vorbemerkung

- Quellenlage wie in A: nur Websuche, kein Volltext. Status aller neuen Quellen
  `[nur bibliografisch]`; Herkunftskennung (T) Treffertitel/URL, (G) GitHub-Datei, (S) nur
  Suchzusammenfassung. Keys aus A, B, D sind dort mit BibTeX-Entwurf hinterlegt; hier nur
  genannt.
- Zeilenangaben: `ch2` = `kontext/ch2.tex`, `ch3` = `kontext/ch3.tex`.
- Leitplanken aus `CLAUDE.md` gelten: SINDYc mit physikalisch motivierter Bibliothek, keine
  Greybox; linearer QP-MPC; Kühlwassertemperaturen sind Störgrößen; Stellglied nur HP-Ventil.

---

## Teil E1 — Lektorat aus Gutachtersicht

### Befunde je Kriterium

**1 Erfüllung der Aufgabenstellung**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 1.1 | ch3 Z. 1122–1147 | Forschungsfrage steht nur in den Copilot-Stichpunkten (Z. 1185–1190), nicht im Fließtext der Einordnung | Frage und Anforderungen (lineares QP, Ventil-Gain, OL/CL/DoE) am Anfang von „Einordnung und Abgrenzung“ nennen |
| 1.2 | ch2 Z. 1080–1082 | QP-Anforderung ist die harte Randbedingung der Modellwahl, im Kapitel aber nur als Halbsatz und unvollständig (Affinität im Zustand fehlt, Auftrag B) | Bedingung als eigenen Stichpunkt; in ch3 als Auswahlkriterium der Modellklassen aufgreifen |
| 1.3 | ch3 Z. 339–366 | Bilineares \edmdc{} wird ausführlich motiviert und dann wegen des QP verworfen; der Leser weiß nicht, ob es in der Arbeit vorkommt | Einen Satz: nur als Ausblick oder als Vergleich ohne MPC |
| 1.4 | ch3 Z. 155–195 | ARX als Baseline gut begründet; die Rolle von NARX (Merkel) bleibt auf einen Absatz beschränkt | Einen Satz ergänzen, warum kein polynomiales NARX mit Simulationsfehler-Selektion (Piroddi & Spinelli 2003) als zweite Baseline |

**2 Umfang der Ergebnisse (hier: Vollständigkeit der Grundlagen)**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 2.1 | ch2 Z. 1083–1088 | Beobachter bzw. Kalman-Filter nur in einem Satz; Erstgutachter hat dazu promoviert | Kurzer Baustein: Störmodell, Beobachtergleichung, Wahl der Kovarianzen, Bezug EMA (Auftrag D, Frage 4) |
| 2.2 | ch2 Z. 1111–1113 | Offene Notiz „Störgrößenprädiktion erwähnen“ | Gemessene Störgrößen ($\TLT$, Last) im Horizont: konstant fortschreiben oder Prognose (Auftrag B, B2.3) |
| 2.3 | ch2 gesamt | Diskretisierung, Totzeit, stationäre Verstärkung, Simulations- vs. Einschrittfehler fehlen als Grundlagen | Bausteine B2.1–B2.5 aus Auftrag B |
| 2.4 | ch3 Z. 390–431 | SINDy-Solver nur STLSQ und LASSO; SR3, Nebenbedingungen (Gleichung, Ungleichung) fehlen, obwohl physikalische Vorzeichen für die Arbeit naheliegen | Einen Absatz mit Zheng u. a. 2019, Champion u. a. 2020, Kaptanoglu u. a. 2022 (Auftrag A) |
| 2.5 | ch3 gesamt | Bezug zu reduzierten Modellen (POD-Galerkin) fehlt; Erstgutachter wird danach fragen | Absatz nach Auftrag D, Frage 1 |
| 2.6 | ch3 Z. 463–486 | SINDy-MPC-Literatur fehlt: `kaiserSparseIdentificationNonlinear2018` steht nur in den Grenzen (Z. 603) | Kaiser u. a. 2018 als SINDy-MPC-Referenz nennen, mit Abgrenzung: dort nichtlineares MPC (laut Autoren-Code), hier QP |

**3 Korrektheit**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 3.1 | ch3 Z. 36–38, 41 | „werden sie zu vollwertigen Grey-Box-Modellen“ und „bewegt sich im Black-Box- und Grey-Box-Bereich“ widersprechen der Leitplanke „SINDYc mit physikalisch motivierter Bibliothek, keine Greybox“ | Einordnen als datengetrieben mit physikalisch motivierter Termauswahl; Physik liefert Termformen, keine Koeffizienten |
| 3.2 | ch3 Z. 323–325 | Korda & Mezić 2018 „eDMDc-Modelle für nichtlineare MPC … asymptotisch konsistent“: Die Arbeit baut lineare Prädiktoren für ein lineares MPC nichtlinearer Systeme; die Konvergenzaussage gegen den Koopman-Operator ist am Original zu prüfen | Satz am Original prüfen; „für nichtlineare MPC“ vermutlich „für lineares MPC nichtlinearer Systeme“ |
| 3.3 | ch3 Z. 201–205 | „ändert nichts an den Limitierungen der linearen Modellklasse“: SINDy ist linear in den Parametern, nicht in der Modellklasse | „linear in den Parametern“ schreiben |
| 3.4 | ch3 Z. 426–430 vs. Z. 496–498 | LASSO-Zielfunktion einmal mit $\lVert\cdot\rVert_2^2$, in der Bildunterschrift mit $\lVert\cdot\rVert_2$ | Vereinheitlichen (quadriert) |
| 3.5 | ch2 Z. 543–546 vs. Z. 738–741 | $C_{\min}=C_L$ „über den ganzen Hub“ als Annahme, zugleich Hypothese eines Wechsels auf die Wasserseite bei kleinem Hub | Gültigkeitsbereich der Grenzfallformel eingrenzen (Auftrag B) |
| 3.6 | ch3 Z. 625–628 | „eine analoge Sensitivität ist für SINDy zu erwarten“; Z. 633–637 belegt genau das mit Brunton u. a. 2016, S. 713 | „zu erwarten“ streichen, Beleg nach vorn ziehen |
| 3.7 | ch3 Z. 1144–1146 | „ein aus einem Modell gewonnenes Modell [kann] die Güte seiner Quelle nicht übertreffen“: als allgemeine Aussage zu stark; reduzierte Modelle aus Simulation sind im Fach des Erstgutachters Standard | Begrenzen: Für die Frage der Übertragbarkeit auf die reale Strecke reicht Simulation nicht, weil Modellfehler der Quelle erhalten bleiben |

**4 Methodik (Entwurfsentscheidungen hinterfragt, systematisch geprüft)**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 4.1 | ch3 Z. 869–873 | Modussprung als „natürliches Instrument“ mit Ljung Abschn. 13.4 (Umschalten zwischen Reglergesetzen). Im Dieselbetrieb steht das Ventil fest offen (ch2 Z. 288–289), das ist Sättigung, kein zweites Reglergesetz | Begründung umstellen: Sprung der Stellgröße beim Umschalten als exogene Anregung; prüfen, ob gleichzeitig Last oder Kühlwasser springen (Konfundierung) |
| 4.2 | ch3 Z. 899–905 | Regler schneller als Modelltakt, „vergleichbar einem Aliasing der Rückführung“: unbelegt und ohne Zahlen zum Verhältnis Reglertakt (500 ms, ch2 Z. 275) zu Modelltakt | Verhältnis nennen; Beleg oder als eigene Überlegung kennzeichnen |
| 4.3 | ch3 Z. 126–141 | Skalierung ohne Zentrierung als „üblich“ gesetzt, unbelegt. Zentrierung verändert bei Polynombibliotheken die Sparsamkeit (Auftrag A, A3.2), bei Differenzbibliotheken nicht | Entscheidung mit Bezug auf die eigene Bibliothek begründen; PySINDy-Doku als Beleg für Basisabhängigkeit (Auftrag A) |
| 4.4 | ch3 Z. 520–526 | Schwellwertwahl: Informationskriterien nur als Nachprüfung; offen, wie Schwellwert und Bibliothek ohne Verbrauch der Testdaten gewählt werden | Aufteilung Training / Auswahl / Test explizit; Stability Selection oder Ensemble-Inklusionshäufigkeit (Meinshausen & Bühlmann 2010, Fasel u. a. 2022) |
| 4.5 | ch3 Z. 1018–1029 | Leerbefund mit Suchumfang ist vorbildlich (Kriterium 4); Stand 02.09.2026 | Mit Auftrag A (A3.3–A3.5) aktualisieren; Akan u. a. 2024 als nächstliegende Arbeit prüfen |
| 4.6 | ch3 Z. 877–884 | Vorsteuerung $\valveCA\approx f(\text{Last})$: Rangargument mit Proctor u. a. 2018 (Zustandsrückführung) belegt; für Störgrößenaufschaltung passt die Quelle nur mittelbar | Als Kollinearität zweier Regressoren formulieren; Konfundierungsmaß (Bestimmtheitsmaß $\valveCA$ gegen Last) ist schon geplant |

**5 Durchdringung**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 5.1 | ch2 Z. 309–465 und Z. 467–1003 | Zwei parallele Herleitungsstränge (Grundherleitung und Stichpunkte ch2-08) mit Doppelungen: `eq.grundlagen.basic.stufen` ↔ `eq.Tout.stat`, `eq.grundlagen.basic.dynamik` ↔ `eq.energiebilanz.dyn` | Ein Strang: Bilanz → Stufen → Zielwert (konvexe Kombination, Auftrag B G1) → Relaxation → Bibliotheksfamilien |
| 5.2 | ch2 Z. 848–859 | Gute Stelle: Einzustandsbilanz liefert $N/(1+N)$, nicht $1-e^{-\mathrm{NTU}}$; daraus Hammerstein-Trennung. Steht mitten in einer Liste | Als Begründung der Modellstruktur hervorheben; das ist Durchdringung, die Gutachter honorieren |
| 5.3 | ch3 Z. 806–843 | Biasgleichung gilt für jedes in den Parametern lineare Modell, also auch \sindyc{} und \edmdc{}; stark. Bezug zur Schwellwertauswahl (Z. 841–843) knapp | Einen Satz: Verzerrte Koeffizienten können unter den Schwellwert fallen, also ändert Rückführung die Struktur, nicht nur die Werte |
| 5.4 | ch3 Z. 590–611 | Grenzen generisch (Rauschen, Bibliothek, Extrapolation, Stabilität) | Je Grenze ein Satz, welche für die Ladeluftstrecke dominiert (Closed-Loop-Konfundierung, Extrapolation in $\TLT$) |
| 5.5 | ch3 Z. 308–312 | Closure-Problem bei Mitführen von $\mathbf x$ und Liftung genannt, ohne Bezug zur eigenen \edmdc-Bibliothek | Einen Satz, wie die eigene Liftung das Problem behandelt |

**6 Selbstständigkeit und Kreativität**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 6.1 | ch2 Z. 392, 920 | Eigene Algebra ist gekennzeichnet; gut | Beibehalten; konvexe Kombination (Auftrag B G1) als weitere eigene Herleitung |
| 6.2 | ch3 Einordnung | Deutung von \sindyc{} mit Produkten „Betriebspunktgröße × Temperaturdifferenz“ als LPV-Modell mit exogenem Scheduling ist nach Auftrag A (A3.4) in der Literatur nicht ausdrücklich zu finden | Als eigenen methodischen Beitrag formulieren (E2) |
| 6.3 | ch3 Einordnung | Verschiebungsinvarianz der Differenzbibliothek ist nach Auftrag A (A3.1) nicht als Literaturbefund zu finden | Als eigenes Argument führen, mit kleinem Test belegen (E3, Idee 2) |
| 6.4 | ch3 Z. 1024–1027 | Leerbefund „keine SINDy-/Koopman-Arbeit prüft Residuen auf Autokorrelation …“ | Residuentests selbst durchführen macht daraus einen Beitrag (E3, Idee 5) |

**7 Qualität der Ausarbeitung**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 7.1 | ch3 Z. 760–776 | Rohentwurf mit Tippfehlern („In meisten Industriellen Systeme …“, „Direkte Motehode“, „Indirkete Methdoe“), inhaltlich doppelt zu Z. 617–755 | Entfernen oder in den Abschnitt davor einarbeiten |
| 7.2 | ch3 Z. 218–220 | Satz doppelt, Tippfehler „unendlichdimsensionalen“ | Ersten Satz streichen |
| 7.3 | ch3 Z. 625 | `textbf{…}` ohne Backslash, erscheint als Text | `\textbf` |
| 7.4 | ch3 Z. 506, 552; ch2 Z. 296 | „Esemble“, „Identifiaktion“; Label `closed_loop_identifkation` | Korrigieren (Label nur mit allen `\ref` gemeinsam) |
| 7.5 | ch3 Z. 948, 995; ch2 Z. 1039 | Umgangssprache/Denglisch („LT Cooling Water Temperatur“), unklarer Begriff „EMEC-nahe Ansätze“, Floskel „zudem“ | Fachbegriffe nach Formelzeichenliste ($\TLT$), Begriff erklären oder streichen |
| 7.6 | ch2 Z. 184–185 u. a. | „Bündel“ für HT/LT (Vorgabe: Stufe) | Auftrag B, Befund T1 |
| 7.7 | ch2 Z. 438, 1068; ch3 | $\lambda$ dreifach belegt (Rate, MPC-Gewicht, Schwellwert) | Auftrag B, Befund T2 |

### Verteidigungsfragen (H = Henning, M = Merkel)

Antwortskizzen als Stichpunkte; Belege mit Key (Bib = schon in der Bib, A/B/D = BibTeX-Entwurf in
diesem Auftrag). Keine Volltextprüfung.

1. **(H) Ist Ihr \sindyc-Modell ein reduziertes Modell im Sinne von POD-Galerkin?**
   - Nein im engeren Sinn: keine Projektion einer PDE auf Moden, sondern ein konzentriertes
     Modell mit einem Temperaturzustand.
   - Eigene Deutung (nicht belegt): Die Termformen entsprechen einer Projektion der
     Energiebilanz auf eine einzige räumliche Mode (Mitteltemperatur); Sparsifizierung ersetzt
     die Trunkierung.
   - Brücke in der Literatur: `loiseauConstrainedSparseGalerkin2018` (Bib); weitere Belege
     Auftrag D, Frage 1.
2. **(H) Wie schätzt Ihr Beobachter die Störung, und warum reicht ein Integrator-Störmodell?**
   - Offsetfreies MPC: Ausgangsstörung als Random Walk, Beobachter/Kalman-Filter schätzt
     Zustand und Störung; Zielwertberechnung verschiebt die Ruhelage.
   - Bedingung: Detektierbarkeit, Zahl der Störzustände = Zahl der Ausgänge.
   - `muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003`,
     `maederLinearOffsetfreeModel2009` (Bib); Pannocchia 2015 (B). Bezug EMA: Auftrag D, Frage 4.
3. **(M) Ist \sindyc{} in Map-Form nicht einfach ein polynomiales NARX mit Subset-Auswahl?**
   - Ja, strukturell (ch3 Z. 201–205). Unterschiede: Bibliothek aus der Wärmeübertrager-Physik
     statt generischer Polynome; Auswahl über Schwellwert statt Fehlerreduktionsverhältnis;
     Schätzung auf Einschrittfehler.
   - `billingsNonlinearSystemIdentification2013` (E), `piroddiIdentificationAlgorithmPolynomial2003` (A),
     `aguirreBirdsEyeView2019` (A).
4. **(M) Warum sind Ihre Koeffizienten aus geregelten Daten nicht verzerrt?**
   - Sind sie bei der direkten Methode im Allgemeinen (ch3 Gl. `eq.grundlagen.cl.bias`); daher
     Fit auf DoE-/Prüfstandsdaten mit Anregung, geregelte Daten zur Validierung, Prüfung gegen
     die bekannte Wahrheit am Prüfstand (ch3 Z. 922–925).
   - `forssellClosedloopIdenticationRevisited1999`, `ljungSystemIdentificationTheory1999`,
     `dahdahClosedloopKoopmanOperator2024` (Bib).
5. **(M) Warum Einschritt-Kleinste-Quadrate statt Simulationsfehler-Minimierung?**
   - Einschritt-LS ist konvex und schnell; Simulationsfehler passt bei Ausgangsrauschen besser.
     Bewertung deshalb im Freilauf und über den Horizont (Auftrag B, B2.5; E3 Idee 3).
   - `farinaIterativeAlgorithmSimulation2010` (A), `somalwarLearningImperfectModels2025` (A),
     `ribeiroParallelTrainingConsidered2018` (B).
6. **(H/M) Ist Ihr Modell überhaupt QP-tauglich?**
   - Bedingung ist Affinität in Zustand und Stellgröße bei gegebenem exogenen Verlauf
     (Auftrag B, B1); Produkte mit gemessenen Betriebsgrößen sind LPV mit exogenem Scheduling.
   - Bilineares \edmdc{} verliert den QP (ch3 Z. 363–366).
   - `rawlingsModelPredictiveControl20202020` (Bib), `cisnerosEfficientNonlinearModel2016` (A).
7. **(H) Wie sichern Sie Stabilität von Modell und Regelkreis?**
   - Modell: Eigenkoeffizient bzw. Eigenwerte über dem Betriebsbereich im Einheitskreis
     (E3 Idee 7). Regelkreis: Standardbedingungen des MPC (Endkosten, Horizont),
     Störgrößenbeobachter.
   - `rawlingsModelPredictiveControl20202020` (Bib); für nichtlineare SINDy-Modelle
     Stabilitätsförderung `kaptanogluPromotingGlobalStability2021` (A), für affine Modelle nicht nötig.
8. **(M) Wie wählen Sie Schwellwert und Bibliothek, ohne die Testdaten zu verbrauchen?**
   - Trennung Training / Auswahl / Test; Inklusionshäufigkeit über Ensembles oder Stability
     Selection; Informationskriterium nur als Nachprüfung (ch3 Z. 520–524).
   - `faselEnsembleSINDyRobustSparse2022`, `manganModelSelectionDynamical2017` (Bib),
     `meinshausenStabilitySelection2010` (A); Auftrag D, Frage 6.
9. **(H) Ist die Ventilverstärkung das richtige Kriterium, und wie genau muss sie sein?**
   - Identifikation für die Regelung: Kriterium nach Verwendungszweck (Auftrag D, Frage 5).
     Verstärkung bestimmt Zielwertberechnung und Kreisverstärkung; bei trägen Strecken reagiert
     $K=b/(1-a)$ stark auf Fehler im Eigenkoeffizienten (Auftrag B, B2.4).
   - `skogestadMultivariableFeedbackControl2005` (B); Belege aus Auftrag D, Frage 5.
10. **(H) Wie übertragen Sie das Modell auf andere Motoren und auf Verschmutzung im Feld?**
    - Termstruktur aus der Physik übertragbar, Koeffizienten nicht; Bänder der 51/60DF-Flotte
      anders (ch2 Z. 125–126). Nachführung als Ausblick.
    - `quadeSparseIdentificationNonlinear2018` (E), `bhadrirajuOASISPOperableAdaptive2021` (Bib).


---

## Teil E2 — Beitrag der Arbeit schärfen

### Beitragsformulierungen

Formulierungsvorschläge; jeweils nur verwenden, wenn die Ergebnisse der Arbeit sie tragen.
Die Lücke ist jeweils der Stand der Suche dieser Sitzung (kein Nachweis der Nichtexistenz).

1. **Physikalisch motivierte Bibliothek, QP-taugliche Struktur.** „Diese Arbeit zeigt, wie
   Termformen aus der Wärmeübertrager-Bilanz (Temperaturdifferenz × Betriebspunktfaktor) ein
   \sindyc-Modell ergeben, das affin in Zustand und Ventilfunktion bleibt und damit ohne
   Linearisierung in einen linearen QP-MPC passt.“
   - Lücke: keine SINDy-Arbeit mit Wärmeübertrager-Termformen in der Bibliothek gefunden
     (Auftrag A, A3.3); SINDy nicht ausdrücklich als LPV gedeutet (A3.4); SINDy-MPC in der
     Literatur nichtlinear optimiert (Kaiser u. a. 2018 laut Autoren-Code; Yahagi u. a. 2025 NMPC,
     ch3 Z. 1094–1102).
   - Beleg für die Nähe: Cisneros u. a. 2016 (quasi-LPV-MPC), Sheikh u. a. 2024 (sparse LPV mit
     physikalisch motivierter Basis, Batterie), beide Auftrag A.
2. **Messdaten eines Großgasmotors statt Simulation.** „Diese Arbeit identifiziert die
   Ladelufttemperatur am Motoreintritt aus Prüfstands- und Felddaten eines mittelschnelllaufenden
   Dual-Fuel-Motors.“
   - Lücke: ch3 Z. 1018–1029 und 1138–1147; Auftrag A (A3.5): außerhalb der Yahagi-/Yonezawa-Gruppe
     keine SINDy-/Koopman-Arbeit an Motorluftpfad oder Ladeluftkühler mit Messdaten gefunden;
     E2-Tabelle unten.
3. **Bewertung nach Verwendungszweck.** „Diese Arbeit bewertet datengetriebene Modelle nicht nur
   am Vorhersagefehler, sondern an Ventil-Verstärkung, offener und geschlossener Kette und
   DoE-Validierung, also an dem, was der Regler braucht.“
   - Lücke: ch3 Z. 1024–1027 (keine gefundene SINDy-/Koopman-Arbeit prüft Residuen);
     Identifikation für Regelung als Kriterium (Auftrag D, Frage 5).
4. **Closed-Loop-Daten gegen bekannte Wahrheit.** „Diese Arbeit prüft am Prüfstand, welche der
   drei Modelleigenschaften (Niveau, Dynamik, Stellwirkung) sich aus geregelten Betriebsdaten
   zurückgewinnen lassen.“
   - Lücke: Closed-Loop-Bias für \edmdc{} bei Dahdah u. a. 2024 (ch3 Z. 626–627, 752–754);
     für \sindyc{} keine eigene Standardquelle gefunden (Recherche E2, Offen).
5. **Invarianz als Entwurfsregel (nur mit Idee 2 aus E3).** „Diese Arbeit zeigt, dass eine
   Bibliothek aus Temperaturdifferenzen die Prognose gegenüber dem Temperaturniveau
   verschiebungsinvariant macht, eine Bibliothek mit freiem Absolutterm nicht.“
   - Lücke: Auftrag A (A3.1), nicht gefunden; Auftrag B (G1) liefert die Algebra.

### Nächste Verwandte (2019–2026, dazu ältere Kernarbeiten)

Kennung: Bib = Key schon in `Masterarbeit.bib` (in ch2/ch3 zitiert); A/B/E = BibTeX-Entwurf in
Auftrag A, B oder hier. Inhalte auf Abstract-Ebene, meist (S).

| Arbeit | Was sie macht | Was sie nicht macht | Abgrenzung dieser Arbeit |
|---|---|---|---|
| Vagapov u. a. 2022 (Bib) | Hammerstein-Modell eines Ladeluftkühlers, Prüfstand und Fahrzeug (ch3 Z. 1058–1068) | kein Regler, keine sparse Termauswahl | datengetriebene Termauswahl, Regler |
| Vagapov 2024, Diss. (Bib) | prädiktive Ladelufttemperaturregelung im Fahrzeug über Pumpe und Ventil (ch3 Z. 1069–1081) | vollständige Kaskade nicht echtzeitfähig; Pkw, kein Großmotor | Großmotor, lineares QP, Ventil als einzige Stellgröße |
| Beran u. a. 2021 (Bib; DOI 10.1007/s41104-021-00087-0, T) | Regelstrategie für Ladeluftkühlkonzept mit ML-Steuermodellen (ch3 Z. 976–982) | keine interpretierbaren Terme | explizite Terme mit physikalischer Form |
| Rupprecht 2016 (Bib) | physikalisches Kühlkreismodell eines Großmotors, Ventilregelung (ch3 Z. 1044–1056) | $\TLT$ konstant; keine datengetriebene Struktur | $\TLT$ als gemessene Störgröße |
| Yahagi u. a. 2025 (Bib; ein IJCAS-Artikel mit DOI 10.1007/s12555-024-0452-9 (T) wurde gefunden, Zuordnung zum Bib-Key ungeprüft) | SINDy für Ladedruck/AGR, NMPC am Simulationsmodell | keine Messdaten, keine Temperatur | Messdaten, Temperaturstrecke, QP |
| Yahagi u. a. 2026 (Bib; vermutlich arXiv:2602.15422, T, Zuordnung ungeprüft) | bilineares Koopman aus E/A-Daten, Motorprüfstand unter PID | noch kein Regler (laut ch3 Z. 1103–1111) | Regler, linear statt bilinear |
| Yonezawa u. a. 2025 (Bib; vermutlich arXiv:2507.18220, T, Zuordnung ungeprüft) | SINDy mit Bibliotheksoptimierung, rekursive Langzeitprognose, Diesel-Luftpfad | Temperatur nicht Regelgröße; Datenherkunft unklar | thermische Strecke, Messdaten |
| Kaiser u. a. 2018 (Bib) | SINDYc im MPC, wenig Daten | nichtlineares MPC (SQP) laut Autoren-Code; Benchmark-Systeme | QP-taugliche Struktur, reale Anlage |
| Zinage u. a. 2022 (Bib; arXiv:2204.10421, T) | EDMD für Turbinendrehzahl und Turbinenaustrittstemperatur aus Motormessdaten, besser als NARX (G) | kein Regler | Regler, Ladeluft statt Turbine |
| Akan u. a. 2024 (A) | \sindyc{} lernt die Abweichung zu einem physikalischen Modell eines Wärmeübertrager-Netzes (S) | kein eigenständiges \sindyc-Modell, Bibliothek unbekannt | eigenständiges Modell mit Wärmeübertrager-Termen |
| Kaleli 2020 (E; nur PII) | MPC eines Ottomotor-Kühlsystems, lokal lineare Modelle, Echtzeittest am Prüfstand (S) | Regelgröße Kühlmittel-, nicht Ladelufttemperatur; keine Bibliothek | Ladeluft, sparse Bibliothek |
| Zhang u. a. 2022 (E; arXiv:2202.12803, T) | lineare/LPV-MPC des Diesel-Luftpfads, Modell aus transienten GT-Power-Daten; Wandtemperatur-Dynamik beeinflusst die Güte (G) | nur Simulation, Regelgröße Druck/AGR | Messdaten, Temperatur |
| Vega-Zambrano u. a. 2025 (E; DOI 10.1016/j.ijpharm.2025.125322, G) | Vergleich DMDc, MOESP, \sindyc{} für MPC einer Granulieranlage (S) | kein thermisches System; Datenherkunft unklar | gleiche Modellfamilien, thermische Strecke |
| Valábek u. a. 2025 (E; arXiv:2511.04437, T) | Deep-Koopman-EMPC einer Pasteurisieranlage mit Plattenwärmeübertrager, Laborstand (S) | Black-Box-Lifting, keine physikalische Bibliothek | physikalisch motivierte Terme |
| Miyashita u. a. 2022 (E; DOI 10.23919/SICE56594.2022.9905828, G) | Koopman-MPC mit STL-Spezifikation für Warmwassertemperatur (T) | Datenherkunft unklar; kein Motor | Motor, Messdaten |
| Ou u. a. 2024 (E; nur PII) | SINDy-Modell reduzierter Ordnung und MPC der Wafertemperatur (S) | Halbleiterprozess; Datenherkunft widersprüchlich | Motor, Ventilstrecke |

- Einordnung: Die nächste Arbeit zur Strecke ist Vagapov 2024 (Fahrzeug); die nächste zur
  Methode unter realen Daten ist Yahagi u. a. 2026 (Motorprüfstand, ohne Regler). Keine der
  gefundenen Arbeiten verbindet beides mit einem linearen QP.
- Nicht gefunden: Journal- oder Konferenzarbeit 2019–2026 zu datengetriebener
  Ladelufttemperaturregelung am Groß- oder Schiffsmotor (Treffer fast nur US-Patente; CIMAC
  mit den verfügbaren Werkzeugen nicht durchsuchbar). Suchweg: 39 Anfragen, siehe Anhang E.


---

## Teil E3 — Ideen mit Mehrwert, priorisiert

Sortiert nach Nutzen je Aufwand. Harte Grenzen eingehalten: keine neuen Prüfstandsmessungen,
Stellglied nur HP-Ventil, Kühlwassertemperaturen nur als Störgrößen, MPC bleibt lineares QP,
umsetzbar bis 19.10.2026 (große Ideen unten als Ausblick). „Messdaten“ heißt: vorhandene Daten
der Arbeit nötig. Aufwand S ≤ 4 h, M 4–12 h, L > 12 h (grobe Schätzung).

### Top 5

| Rang | Idee | Kriterium | Aufwand | Messdaten | Literaturanker | Risiko |
|---|---|---|---|---|---|---|
| 1 | **QP-Tauglichkeitstabelle:** je Modellklasse und Variante prüfen, ob die Prädiktion affin in Zustand und Ventilfunktion ist (Terme Zustand×Zustand, Ventil×Zustand, exogenes Scheduling) | 4, 5, 3 | S, 1–2 h | nein | Auftrag B (B1, sympy-Beispiel; B2.3); `rawlingsModelPredictiveControl20202020`; Cisneros u. a. 2016 (A) | Keins; deckt ggf. auf, dass eine Variante nicht QP-tauglich ist, dann als Grenze benennen |
| 2 | **Verschiebungsinvarianz-Test:** alle Temperatureingänge und den Anfangswert um denselben Betrag verschieben (oder °C gegen K tauschen) und prüfen, ob sich die Prognose um genau diesen Betrag verschiebt; für ARX, \sindyc{} (Differenz- vs. Absolutbibliothek), \edmdc | 6, 4, 5 | S, 2–3 h | ja (vorhanden) | Eigenes Argument (A3.1: in der Literatur nicht gefunden); Auftrag B G1 | Modelle mit freiem Absolutterm bestehen den Test nicht; das ist dann ein Ergebnis, kein Fehlschlag |
| 3 | **Persistenzreferenz und Fehler über dem Horizont:** Einschritt- und Freilauffehler immer gegen $\hat y_{k+1}=y_k$ stellen; Fehlerkurve $e(h)$ für $h=1\dots N$ (MPC-Horizont) je Modell | 4, 3 | S, 2–4 h | ja | Auftrag B (B2.5); `ljungSystemIdentificationTheory1999`; Somalwar u. a. 2025 (A); Nelles 2020 (B) | Rangfolge der Modelle kann sich gegenüber Einschrittmaßen ändern; genau das ist die Aussage |
| 4 | **Residuentests:** Autokorrelation der Freilauf-Residuen, Kreuzkorrelation Residuum–$\valveCA$ und Residuum–Last mit Konfidenzband | 4, 6 | S, 3–4 h | ja | `ljungSystemIdentificationTheory1999` (Kapitel Modellvalidierung, lokal); Billings & Voon 1986 (s. Anker unten); ch3 Z. 1024–1027 (Leerbefund) | Tests fallen durch (farbiges Rauschen, Rückführung); dann als Grenze berichten und mit Closed-Loop-Bias verknüpfen |
| 5 | **Konditionierung und Koeffizientenstreuung:** Konditionszahl und VIF je Bibliothek; Streuung der Koeffizienten über Block-Bootstrap oder Ensemble-Inklusionshäufigkeit | 4, 5, 3 | M, 4–8 h | ja | Belsley u. a. 1980, Künsch 1989 (s. Anker unten); `faselEnsembleSINDyRobustSparse2022`; Meinshausen & Bühlmann 2010 (A) | Rechenzeit; große Streuung zeigt Nicht-Identifizierbarkeit einzelner Terme; ehrlich benennen |

### Weitere Ideen

| Rang | Idee | Kategorie | Kriterium | Aufwand | Messdaten | Literaturanker | Risiko |
|---|---|---|---|---|---|---|---|
| 6 | **Modussprung prüfen:** um jeden Umschaltzeitpunkt Diesel/Gas die Sprunghöhe von $\valveCA$ gegen gleichzeitige Last- und $\TLT$-Änderung stellen; Instrument nur, wenn der Stellgrößensprung nicht mit Störungen zusammenfällt | Absicherung | 4 | S–M, 3–5 h | ja | `ljungSystemIdentificationTheory1999` (Abschn. 13.4); E1 Befund 4.1 | Sprünge fallen mit Laständerungen zusammen; dann Instrument abschwächen |
| 7 | **Stabilität über dem Betriebsbereich:** Eigenwert bzw. Eigenkoeffizient $a(\mrel)$ für alle im Datensatz vorkommenden Betriebspunkte in $(0,1)$? | Analyse | 3 | S, 1–2 h | ja | `khalilNonlinearSystems2002` (B); Auftrag B (B2.1) | Instabile Bereiche am Rand; Gültigkeitsbereich einschränken |
| 8 | **Weiche Schranke exakt machen:** linearen Slack-Term $\mu_1 s$ ergänzen, zeigen, dass die Untergrenze nur bei Unzulässigkeit verletzt wird | Absicherung | 3, 4 | S, 1–2 h | nein (Simulation) | Kerrigan & Maciejowski 2000 (B) | Gewichtswahl; gering |
| 9 | **Einfache physikalische Referenz:** $\varepsilon$-NTU-Zielwert mit 2–3 Parametern plus Relaxation als zusätzliche Vergleichslinie neben ARX | Analyse | 3, 4 | M, 4–8 h | ja | `vagapovDynamicModelTemperature2022` (Hammerstein); `suiMeanValueFirst2022`; Auftrag B G1 | Referenz kann \sindyc{} erreichen; dann Aussage „Bibliothek trifft die Physik“ |
| 10 | **Gain-Empfindlichkeit im simulierten Kreis:** MPC mit skaliertem Modell-Gain gegen dieselbe Strecke laufen lassen; zeigt, wie viel Gain-Fehler der Regler verträgt | Analyse | 4, 5 | M, 6–10 h | nein (Simulation mit vorhandenem Modell) | `skogestadMultivariableFeedbackControl2005` (B); Yousefi u. a. 2015 (B, nur S) | Streckenmodell ist selbst identifiziert; als Simulationsaussage kennzeichnen |
| 11 | **Rechenzeit des QP je Takt** gegen den Reglertakt $500\,$ms | Absicherung | 1, 4 | S, 1–2 h | nein | `rawlingsModelPredictiveControl20202020` | Keins |
| 12 | **Hyperparameterwahl ohne Testdaten dokumentieren:** Trennung Training / Auswahl / Test als Schema; Schwellwert und Bibliothek nur auf Auswahldaten | Absicherung | 4 | S, 1–2 h | nein | Auftrag D (Frage 6) | Keins |
| 13 | Abbildung: **Ersatzschaltbild** (ch2 Z. 905–907) mit $C_{\mathrm{eff}}$, $1/(kA)$, Ventilpfeil, HT-Stufe als vorgeschaltetem Block | Abbildung | 7, 5 | S, 2 h | nein | ch2 Z. 877–884 | Keins |
| 14 | Abbildung: **Zielwert als gewichtete Mischung** von $\Tin$, $\THT$, $\TLT$ (Balken oder Dreieck, Gewichte aus Auftrag B G1) über dem Ventilhub | Abbildung | 5, 7 | S, 2 h | nein (qualitativ) | Auftrag B G1 | Keine Zahlen erfinden: qualitativ zeichnen |
| 15 | Abbildung: **Prüfmatrix** Modell × {Niveau, Dynamik, Stellwirkung} × {OL, CL, DoE, Gain} als Ampel | Abbildung | 7, 4 | S, 2 h | ja (Ergebnisse) | ch3 Z. 907–925 (Dreiteilung) | Keins |
| 16 | Abbildung: **Blockschaltbild geschlossener Kreis** mit Konfundierungspfad Last → Vorsteuerung → Ventil und Last → Strecke | Abbildung | 7, 5 | S, 2 h | nein | ch3 Z. 650–651 (Kommentar), Z. 877–884 | Keins |
| 17 | Diskussion: **Übertragbarkeit** auf die Feldbaureihe 51/60DF (anderes Band, ch2 Z. 125–126): Struktur übertragbar, Koeffizienten nicht | Diskussion | 5 | S, 1–2 h | nein | `rupprechtAnalysisSimulationOptimisation2016`; Auftrag A (PG 51/60DF) | Keins |
| 18 | Diskussion: **Online-Nachführung** bei Verschmutzung und Drift (ch3 Z. 458–460 schließt sie aus) als Ausblick | Diskussion | 6 | S, 1 h | nein | `bhadrirajuOASISPOperableAdaptive2021`; Quade u. a. 2018 (s. Anker unten) | Keins |
| 19 | Diskussion: **Beobachter ↔ Kalman ↔ exponentielle Glättung** (Henning) | Diskussion | 5 | S, 2 h | nein | Auftrag D (Frage 4) | Keins |
| 20 | Diskussion: **Reduzierte Modelle** (POD-Galerkin) gegen \sindyc{} (Henning) | Diskussion | 5 | S, 2 h | nein | Auftrag D (Frage 1) | Keins |

### Große Ideen (nur Ausblick, bis 19.10. nicht umsetzbar)

- Adaptive bzw. online nachgeführte \sindyc-Modelle im Feldbetrieb.
- Mehrgrößenregelung mit LP-Ventil als zweiter Stellgröße (heute ausgeschlossen: Stellglied nur HP).
- Nichtlineares MPC auf bilinearem \edmdc{} (ch3 Z. 339–366) mit Vergleich zum QP.
- Versuchsplanung für geregelte Feldanlagen (kostenminimales Experiment,
  `bomboisLeastCostlyIdentification2006`).
- Ökonomisches MPC mit Derating-Grenze (ch2 Z. 39–41) als Zielgröße.

### Methodenanker für E3

| Zweck (Idee) | Quelle | DOI / ISBN (Herkunft) | Nutzen |
|---|---|---|---|
| Konditionsdiagnostik (5) | Belsley, D. A.; Kuh, E.; Welsch, R. E. (1980): Regression Diagnostics: Identifying Influential Data and Sources of Collinearity. Wiley (G) | ISBN 9780471058564 (G); DOI 10.1002/0471725153 nur in einer Bib (G), vermutlich Neuausgabe | Konditionsindizes und Varianzzerlegung zeigen, welche Bibliotheksterme sich gegenseitig ersetzen; VIF zeigt das nicht |
| Bootstrap (5) | Efron, B.; Tibshirani, R. J. (1993): An Introduction to the Bootstrap. Chapman & Hall (G) | ISBN 0412042312 (G) | Grundlage Bootstrap |
| Block-Bootstrap für Zeitreihen (5) | Künsch, H. R. (1989): The Jackknife and the Bootstrap for General Stationary Observations. Ann. Stat. 17(3), 1217–1241 (G) | 10.1214/aos/1176347265 (G) | Blöcke erhalten die Autokorrelation geregelter Messreihen; Konfidenzintervalle nicht künstlich eng |
| Praktische Identifizierbarkeit (5) | Raue, A. u. a. (2009): Structural and practical identifiability analysis of partially observed dynamical models by exploiting the profile likelihood. Bioinformatics 25(15), 1923–1929 (G) | 10.1093/bioinformatics/btp358 (G) | flaches Profil = praktisch nicht identifizierbarer Koeffizient, z. B. Ventilterm bei schwacher Anregung |
| Globale Sensitivität (optional) | Saltelli, A. u. a.: Global Sensitivity Analysis. The Primer. Wiley (G); Jahr 2007 oder 2008 uneinheitlich (G) | ISBN 9780470059975 (G); DOI 10.1002/9780470725184 (G) | Sobol-Indizes: welche Eingänge ($\TLT$, $\mrel$, $\valveCA$) die Streuung der Vorhersage tragen |
| Residuentests (4) | Billings, S. A.; Voon, W. S. F. (1986): Correlation based model validity tests for non-linear models. Int. J. Control 44(1), 235–244 (T/G) | 10.1080/00207178608933593 (T) | Korrelationstests höherer Ordnung finden ausgelassene nichtlineare Terme |
| Residuentests (4) | Billings, S. A. (2013): Nonlinear System Identification: NARMAX Methods in the Time, Frequency, and Spatio-Temporal Domains. Wiley (G); Kap. 5 „Model Validation“ (T) | 10.1002/9781118535561 (G) | Lehrbuchanker; zugleich NARMAX-Bezug für Merkel |
| Online-Nachführung (18) | Quade, M.; Abel, M.; Kutz, J. N.; Brunton, S. L. (2018): Sparse identification of nonlinear dynamics for rapid model recovery. Chaos 28(6), 063116 (G) | 10.1063/1.5027470 (G); arXiv:1803.00894 (G) | SINDy-Koeffizienten nach abrupter Änderung mit wenig Daten neu schätzbar |

### BibTeX-Entwürfe E

Nur (T)/(G)-Felder im Eintrag, (S) als `% ungeprüft:` darüber. Status aller Einträge
[nur bibliografisch]. `zinageDataDrivenModeling2022` ist schon in der Bib (ch3 Z. 1000).

```bibtex
% ungeprüft: doi = {10.1002/0471725153} (eine GitHub-Bib; vermutlich Neuausgabe 2005)
@book{belsleyRegressionDiagnosticsIdentifying1980,
  author    = {Belsley, David A. and Kuh, Edwin and Welsch, Roy E.},
  title     = {Regression Diagnostics: Identifying Influential Data and Sources of Collinearity},
  series    = {Wiley Series in Probability and Statistics},
  publisher = {Wiley},
  year      = {1980},
  isbn      = {9780471058564}
}

@book{efronIntroductionBootstrap1993,
  author    = {Efron, Bradley and Tibshirani, Robert J.},
  title     = {An Introduction to the Bootstrap},
  series    = {Monographs on Statistics and Applied Probability},
  number    = {57},
  publisher = {Chapman \& Hall},
  address   = {New York},
  year      = {1993},
  isbn      = {0412042312}
}

@article{kunschJackknifeBootstrapGeneral1989,
  author    = {K{\"u}nsch, Hans R.},
  title     = {The Jackknife and the Bootstrap for General Stationary Observations},
  journal   = {The Annals of Statistics},
  volume    = {17},
  number    = {3},
  pages     = {1217--1241},
  year      = {1989},
  doi       = {10.1214/aos/1176347265}
}

@article{raueStructuralPracticalIdentifiability2009,
  author    = {Raue, Andreas and Kreutz, Clemens and Maiwald, Thomas and Bachmann, Julie and Schilling, Marcel and Klingm{\"u}ller, Ursula and Timmer, Jens},
  title     = {Structural and practical identifiability analysis of partially observed dynamical models by exploiting the profile likelihood},
  journal   = {Bioinformatics},
  volume    = {25},
  number    = {15},
  pages     = {1923--1929},
  year      = {2009},
  doi       = {10.1093/bioinformatics/btp358}
}

% Jahr uneinheitlich: 2008 (eine Bib) oder 2007 (zwei Bibs); Key hängt am Jahr
@book{saltelliGlobalSensitivityAnalysis2008,
  author    = {Saltelli, Andrea and Ratto, Marco and Andres, Terry and Campolongo, Francesca and Cariboni, Jessica and Gatelli, Debora and Saisana, Michaela and Tarantola, Stefano},
  title     = {Global Sensitivity Analysis. The Primer},
  publisher = {John Wiley \& Sons, Ltd},
  isbn      = {9780470059975},
  doi       = {10.1002/9780470725184}
}

@article{billingsCorrelationBasedModel1986,
  author    = {Billings, S. A. and Voon, W. S. F.},
  title     = {Correlation based model validity tests for non-linear models},
  journal   = {International Journal of Control},
  volume    = {44},
  number    = {1},
  pages     = {235--244},
  year      = {1986},
  doi       = {10.1080/00207178608933593}
}

@book{billingsNonlinearSystemIdentification2013,
  author    = {Billings, Stephen A.},
  title     = {Nonlinear System Identification: {NARMAX} Methods in the Time, Frequency, and Spatio-Temporal Domains},
  publisher = {John Wiley \& Sons},
  year      = {2013},
  doi       = {10.1002/9781118535561}
}

@article{quadeSparseIdentificationNonlinear2018,
  author        = {Quade, Markus and Abel, Markus and Kutz, J. Nathan and Brunton, Steven L.},
  title         = {Sparse identification of nonlinear dynamics for rapid model recovery},
  journal       = {Chaos: An Interdisciplinary Journal of Nonlinear Science},
  volume        = {28},
  number        = {6},
  pages         = {063116},
  year          = {2018},
  doi           = {10.1063/1.5027470},
  eprint        = {1803.00894},
  archivePrefix = {arXiv}
}

@misc{valabekDeepKoopmanEconomic2025,
  author        = {Val{\'a}bek, Patrik and Horv{\'a}thov{\'a}, Michaela and Klau{\v{c}}o, Martin},
  title         = {Deep Koopman Economic Model Predictive Control of a Pasteurisation Unit},
  year          = {2025},
  eprint        = {2511.04437},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% ungeprüft: Artikelnummer 125322 (nur aus DOI abgeleitet)
@article{vegazambranoDatadrivenModelPredictive2025,
  author    = {Vega-Zambrano, Consuelo and Diangelakis, Nikolaos A. and Charitopoulos, Vassilis M.},
  title     = {Data-driven model predictive control for continuous pharmaceutical manufacturing},
  journal   = {International Journal of Pharmaceutics},
  volume    = {672},
  year      = {2025},
  doi       = {10.1016/j.ijpharm.2025.125322}
}

@inproceedings{miyashitaKoopmanModelPredictiveControl2022,
  author        = {Miyashita, Ryo and Susuki, Yoshihiko and Ishigame, Atsushi},
  title         = {Koopman-Model Predictive Control with Signal Temporal Logic Specifications for Temperature Regulation of a Warm-Water Supply System},
  booktitle     = {2022 61st Annual Conference of the Society of Instrument and Control Engineers (SICE)},
  publisher     = {IEEE},
  pages         = {1113--1118},
  year          = {2022},
  doi           = {10.23919/SICE56594.2022.9905828},
  eprint        = {2207.04184},
  archivePrefix = {arXiv}
}

% ungeprüft: author (Kaleli, Vorname/Koautoren unbekannt); journal = {Control Engineering Practice};
%            volume = {100}; pages = {104424}; year = {2020}
@article{kaleliDevelopmentPredictiveBased2020,
  title     = {Development of the predictive based control of an autonomous engine cooling system for variable engine operating conditions in SI engines: design, modeling and real-time application},
  url       = {https://www.sciencedirect.com/science/article/abs/pii/S0967066120300770}
}

% ungeprüft: weitere Autoren
@misc{zhangDevelopmentModelPredictive2022,
  author        = {Zhang, Jiadi and others},
  title         = {Development of a Model Predictive Airpath Controller for a Diesel Engine on a High-Fidelity Engine Model with Transient Thermal Dynamics},
  year          = {2022},
  eprint        = {2202.12803},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% ungeprüft: author = {Ou, F. and Abdullah, F. and Wang, H. and others}; journal = {Chemical Engineering
%            Research and Design}; volume = {202}; pages = {1--11}; year = {2024}
@article{ouSparseIdentificationModeling2024,
  title     = {Sparse identification modeling and predictive control of wafer temperature in an atomic layer etching reactor},
  url       = {https://www.sciencedirect.com/science/article/abs/pii/S0263876223008201}
}

% ungeprüft: author = {Beran, ... and Gärtner, ... and Koch, ...} (nur Nachnamen, S)
% Abgleich mit vorhandenem Key beranModelbasedApproachControl2021
@article{beranModelbasedApproachControl2021,
  title     = {A model-based approach for a control strategy of a charge air cooling concept in an ejector refrigeration cycle},
  journal   = {Automotive and Engine Technology},
  doi       = {10.1007/s41104-021-00087-0}
}
```


---

## Offen / nicht belegt

- Keine Quelle im Volltext gelesen; alle Inhaltsangaben der Verwandten und Anker auf
  Abstract-Ebene, meist (S). Metadaten-Lücken: Kaleli 2020 (Autoren, DOI), Ou 2024 (Autoren,
  DOI, Datenherkunft), Zhang 2022 (Koautoren), Castiglione 2020 (Autoren nur S), IFAC-Fassung
  Zinage 2022.
- Widersprüchlich: Jahr Belsley (1980 gegen Neuausgabe 2005) und zugehörige DOI; Jahr Saltelli
  (2007/2008); Efron-DOI der Neuauflage nicht übernommen.
- Zuordnung ungeprüft: arXiv:2602.15422, 2503.05154, 2507.18220 zu den Bib-Keys der
  Yahagi-/Yonezawa-Gruppe; IJCAS-DOI zu `yahagiSparseIdentificationNonlinear2025`.
- Vega-Zambrano u. a. 2025: Aussagen „\sindyc{} auf Validierungsdaten am schlechtesten“ und
  „\sindyc{} mit linearer Bibliothek und Schwellwert null entspricht DMDc“ nur (S).
- E1 Befund 3.2 (Korda & Mezić) und 4.1 (Modussprung): am Original bzw. an den Daten prüfen.
- Closed-Loop-Bias speziell für \sindyc: keine eigene Standardquelle gefunden.
- Nicht durchsuchbar: CIMAC-Kongressbeiträge; Patente (US 8099222, US 9394858, nur Titel)
  bewusst nicht als Beleg verwendet.
- Ältere Arbeiten außerhalb des Zeitfensters, nur Titel (T): „Modeling and control of a
  single-phase marine cooling system“ (Control Eng. Pract., PII S0967066113001524); „Model Based
  Control of Intake Air Temperature and Humidity on the Test Bench“ (Energy Procedia,
  PII S1876610217336494).
- Aufwandsschätzungen in E3 sind grob und ohne Kenntnis des Codes der Arbeit.

---

## Anhang E: Suchweg zu E2 (39 Anfragen, Rechercheagent)

intake manifold temperature model predictive control engine coolant valve; charge air temperature
control low temperature cooling circuit engine; intercooler outlet temperature control model
predictive coolant flow diesel engine; marine engine charge air cooler temperature control; gas
engine charge air temperature knock control cooling water model-based; engine thermal management
model predictive control coolant valve experimental validation charge air; „charge air“
temperature controller water-cooled charge air cooler nonlinear heat exchanger actuating
variable; intake air temperature control indirect charge air cooler coolant pump MPC vehicle;
SINDYc model predictive control experimental data process plant; Koopman model predictive
control experimental validation thermal system heat exchanger; data-driven model intake manifold
temperature prediction engine neural network test bench; scavenge air temperature control marine
two-stroke engine cooling water valve controller; Koopman operator model predictive control
diesel engine air path experimental; dynamic mode decomposition with control engine thermal model
predictive control; Titelsuche Zinage; „Sparse identification and nonlinear model predictive
control for diesel engine air path“; marine engine cooling system model predictive control low
temperature freshwater three-way valve; control-oriented model charge air cooler outlet
temperature engine validation measurements 2023; charge air temperature control strategy
dual-fuel engine gas mode medium speed; intercooler coolant temperature control heavy-duty engine
MPC fuel consumption experimental; Titelsuchen Valábek, Vega-Zambrano; sparse identification
SINDy heat exchanger experimental data temperature control; charge air temperature predictive
control engine cooling system coolant flow; water-cooled charge air cooler transient intake
temperature control strategy engine test bench; Koopman OR SINDy engine coolant temperature
thermal management; sparse identification closed-loop data industrial process feedback SINDy;
Titelsuchen Kaleli, Ou; CIMAC charge air temperature control gas engine cooling water HT LT
stage; marine diesel engine operational data data-driven model scavenge air temperature charge
air cooler performance monitoring; SAE 2021-01-0225 authors; Titelsuche Castiglione; SINDy
system identification closed-loop data feedback correlation bias input excitation; Koopman MPC
power plant field operating data linear MPC temperature; Billings Voon 1986 doi; Kaleli 2020
local linear models dyno; Ladelufttemperatur Regelung Großmotor Ladeluftkühler
Niedertemperaturkreis MTZ (nur link.springer.com); Titelsuche Beran u. a. 2021.
