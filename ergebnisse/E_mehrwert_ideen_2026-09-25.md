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
| 1.4 | ch3 Z. 155–195 (ARX), Z. 197–205 (NARX) | ARX als Baseline gut begründet; die Rolle von NARX (Merkel) bleibt auf einen Absatz beschränkt | Einen Satz ergänzen, warum kein polynomiales NARX mit Simulationsfehler-Selektion (Piroddi & Spinelli 2003) als zweite Baseline |

**2 Umfang der Ergebnisse (hier: Vollständigkeit der Grundlagen)**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 2.1 | ch2 Z. 1083–1088 | Beobachter bzw. Kalman-Filter nur in einem Satz; Erstgutachter hat dazu promoviert | Kurzer Baustein: Störmodell, Beobachtergleichung, Wahl der Kovarianzen, Bezug EMA (Auftrag D, Frage 4) |
| 2.2 | ch2 Z. 1111–1113 | Offene Notiz „Störgrößenprädiktion erwähnen“ | Gemessene Störgrößen ($\TLT$, Last) im Horizont: konstant fortschreiben oder Prognose (Auftrag B, B2.3) |
| 2.3 | ch2 Z. 1089–1091, 866–874, 262–268, 796–802 | Diskretisierung nur als Halbsatz (Z. 1089–1091); Totzeit nur physikalisch (Z. 866–874, 262–268); stationäre Verstärkung nur für die ε-NTU-Statik (Gl. `eq.grundlagen.gain.epsntu`, Z. 796–802); Einschritt- vs. Simulationsfehler fehlt. Als Bausteine für das diskrete Modell fehlen sie | Bausteine B2.1–B2.5 aus Auftrag B |
| 2.4 | ch3 Z. 390–431, 444–447 | SINDy-Solver: STLSQ, LASSO, Elastic Net (Z. 421–430); SR3 und Ungleichungsnebenbedingungen (z. B. Vorzeichen) fehlen, obwohl physikalische Vorzeichen für die Arbeit naheliegen; Gleichungsnebenbedingungen nur als Empfehlung nach Loiseau (Z. 444–447, laut Z. 447 aufgegriffen), ohne zugehöriges Schätzverfahren | Einen Absatz mit Zheng u. a. 2019, Champion u. a. 2020, Kaptanoglu u. a. 2022 (Auftrag A) |
| 2.5 | ch3 Z. 303–307, 444–447 | Bezug zu reduzierten Modellen (POD-Galerkin) fehlt: Galerkin nur für EDMD (Z. 303–307), Loiseau nur als Bibliotheksempfehlung (Z. 444–447); Erstgutachter wird danach fragen | Absatz nach Auftrag D, Frage 1 |
| 2.6 | ch3 Z. 463–486 | SINDy-MPC-Literatur fehlt: `kaiserSparseIdentificationNonlinear2018` steht nur in den Grenzen (Z. 603) | Kaiser u. a. 2018 als SINDy-MPC-Referenz nennen, mit Abgrenzung: dort nichtlineares MPC (laut Autoren-Code), hier QP |

**3 Korrektheit**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 3.1 | ch3 Z. 36–38, 41 | „werden sie zu vollwertigen Grey-Box-Modellen“ und „bewegt sich im Black-Box- und Grey-Box-Bereich“ widersprechen der Leitplanke „SINDYc mit physikalisch motivierter Bibliothek, keine Greybox“ | Einordnen als datengetrieben mit physikalisch motivierter Termauswahl; Physik liefert Termformen, keine Koeffizienten |
| 3.2 | ch3 Z. 323–325 | Korda & Mezić 2018 „eDMDc-Modelle für nichtlineare MPC … asymptotisch konsistent“: Die Arbeit baut lineare Prädiktoren für ein lineares MPC nichtlinearer Systeme; die Konvergenzaussage gegen den Koopman-Operator ist am Original zu prüfen | Satz am Original prüfen; „für nichtlineare MPC“ vermutlich „für lineares MPC nichtlinearer Systeme“ |
| 3.3 | ch3 Z. 201–205 | „ändert nichts an den Limitierungen der linearen Modellklasse“: SINDy ist linear in den Parametern, nicht in der Modellklasse | Satz ersetzen: \sindy{} ist nur in den Parametern linear, in den Regressoren nichtlinear; die Linearitätsgrenzen von ARX (Z. 187–195) entfallen. Übertragen werden die Grenzen der Kleinste-Quadrate-Schätzung (Z. 178–183: Gleichungsfehler, Anregung, Closed-Loop-Bias, Abschnitt `closed_loop_identifkation`) |
| 3.4 | ch2 Z. 543–546 vs. Z. 738–741 | $C_{\min}=C_L$ „über den ganzen Hub“ als Annahme, zugleich Hypothese eines Wechsels auf die Wasserseite bei kleinem Hub | Gültigkeitsbereich der Grenzfallformel eingrenzen (Auftrag B) |
| 3.5 | ch3 Z. 1141–1146 | „ein aus einem Modell gewonnenes Modell [kann] die Güte seiner Quelle nicht übertreffen“: als allgemeine Aussage zu stark; reduzierte Modelle aus Simulation sind im Fach des Erstgutachters Standard. Z. 1141–1144 nennt Yahagi u. a. 2026 als Ausnahme mit Messdaten; Zinage u. a. 2022 (ch3 Z. 1000, Motormessdaten laut E2-Tabelle) fehlt dort | Begrenzen: Für die Frage der Übertragbarkeit auf die reale Strecke reicht Simulation nicht, weil Modellfehler der Quelle erhalten bleiben; Zinage u. a. 2022 als zweite Ausnahme nennen (vgl. E2 Beitrag 2) |
| 3.6 | ch3 Z. 822–823, 838–840, 891–893 | Kreuzterm im geschlossenen Kreis nicht unbedingt ≠ 0: Bei weißem Gleichungsfehler und Verzögerung im Kreis gilt $\bar{\mathrm E}\{\varphi v\}=0$, direkte LS dann konsistent (vgl. Z. 827–829). Sättigung beseitigt nur den rückführungsbedingten Anteil; bei farbigem $v$ bleibt der Anteil über verzögerte Ausgänge (Z. 819–822) | Z. 822–823: „… von null verschieden, sofern $v$ farbig ist oder der Kreis keine Verzögerung enthält.“ Z. 838–840 und 891–893: „Sättigung beseitigt den rückführungsbedingten Anteil des Kreuzterms; der Anteil aus farbigem $v$ über verzögerte Ausgänge bleibt.“ |

**4 Methodik (Entwurfsentscheidungen hinterfragt, systematisch geprüft)**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 4.1 | ch3 Z. 869–873 | Modussprung als „natürliches Instrument“ mit Ljung Abschn. 13.4 (Umschalten zwischen Reglergesetzen). Ljung-Argument formal haltbar: Der feste Stellwert im Dieselbetrieb (ch2 Z. 288–289, eigene Betriebsart, keine Reglersättigung) entspricht dem Regler $F=0$; Umschalten PI ↔ $F=0$ macht die Daten gemeinsam informativ (Abschn. 13.4 am Original prüfen) | Einschränkungen benennen: gleiches Strecken- und Störmodell in Diesel- und Gasbetrieb nötig; prüfen, ob Last, $\Tin$ oder $\TLT$ beim Umschalten mitspringen (Idee 6); nahe 100 % Hub ist ε nahe eins und die Ventilwirkung klein (ch2 Z. 781–786) |
| 4.2 | ch3 Z. 899–905 | Regler schneller als Modelltakt, „vergleichbar einem Aliasing der Rückführung“: unbelegt und ohne Zahlen zum Verhältnis Reglertakt (500 ms, ch2 Z. 275) zu Modelltakt | Verhältnis nennen; Beleg oder als eigene Überlegung kennzeichnen |
| 4.3 | ch3 Z. 126–141 | Skalierung ohne Zentrierung als „üblich“ gesetzt, unbelegt. Spaltenzentrierung von Θ (Z. 130–137) ändert bei vorhandener, nicht bestrafter Konstante nur das Absolutglied (Frisch-Waugh-Lovell), unabhängig von der Bibliothek; bei STLSQ kann sie nur über das Abschneiden der Konstante wirken. Sparsamkeitsverlust entsteht erst beim Verschieben der Variablen vor dem Bilden der Terme (A3.2): bei Polynomen und bei Produkten $\mrel\,\Delta T$, wenn $\mrel$ zentriert wird ($\mrel\,\Delta T=(\mrel-\mu)\,\Delta T+\mu\,\Delta T$) oder die Temperaturen einzeln zentriert werden; reine Differenzen bleiben nur bei gemeinsamer Verschiebung aller Temperaturen sparsam (A3.1) | Entscheidung mit Bezug auf die eigene Produktbibliothek (ch2 Z. 404–413) begründen; PySINDy-Doku als Beleg für Basisabhängigkeit (Auftrag A) |
| 4.4 | ch3 Z. 520–526 | Schwellwertwahl: Informationskriterien nur als Nachprüfung; offen, wie Schwellwert und Bibliothek ohne Verbrauch der Testdaten gewählt werden | Aufteilung Training / Auswahl / Test explizit; Stability Selection oder Ensemble-Inklusionshäufigkeit (Meinshausen & Bühlmann 2010, Fasel u. a. 2022) |
| 4.5 | ch3 Z. 1018–1029 | Leerbefund mit Suchumfang ist vorbildlich (Kriterium 4); Stand 02.09.2026 | Mit Auftrag A (A3.3–A3.5) aktualisieren; Akan u. a. 2024 als nächstliegende Arbeit prüfen |
| 4.6 | ch3 Z. 877–884 | Vorsteuerung $\valveCA\approx f(\text{Last})$: Rangargument mit Proctor u. a. 2018 (Zustandsrückführung) belegt; für Störgrößenaufschaltung passt die Quelle nur mittelbar | Als Kollinearität zweier Regressoren formulieren; Konfundierungsmaß (Bestimmtheitsmaß $\valveCA$ gegen Last) ist schon geplant |

**5 Durchdringung**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 5.1 | ch2 Z. 309–465 und Z. 467–1003 | Zwei parallele Herleitungsstränge (Grundherleitung und Stichpunkte ch2-08) mit Doppelungen: `eq.grundlagen.basic.stufen` ↔ unnummerierte Zweistufenform Z. 573–577 (und Z. 551–556); `eq.grundlagen.basic.dynamik` ↔ unnummerierte Relaxation Z. 854–856. `eq.energiebilanz.dyn` ist laut Z. 888–896 eine eigene Einzustandsform, keine Doppelung | Ein Strang: Bilanz → Stufen → Zielwert (konvexe Kombination, Auftrag B G1) → Relaxation → Bibliotheksfamilien; `eq.energiebilanz.dyn` beim Zusammenführen als Begründung der Hammerstein-Trennung (Z. 848–859) behalten |
| 5.2 | ch2 Z. 848–859 | Gute Stelle: Einzustandsbilanz liefert $N/(1+N)$, nicht $1-e^{-\mathrm{NTU}}$; daraus Hammerstein-Trennung. Steht mitten in einer Liste | Als Begründung der Modellstruktur hervorheben; das ist Durchdringung, die Gutachter honorieren |
| 5.3 | ch3 Z. 806–843 | Biasgleichung gilt für jedes in den Parametern lineare Modell, also auch \sindyc{} und \edmdc{}; stark, mit Korrektur 3.6. Bezug zur Schwellwertauswahl (Z. 841–843) knapp und ohne Beleg | Aussage steht bereits (ch3 Z. 841–843), ist aber nicht belegt. Statt eines weiteren Satzes im Ergebnisteil zeigen: Inklusionshäufigkeit der Terme über Ensembles, Prüfstands- gegen Regelkreisdaten (E3 Idee 5) |
| 5.4 | ch3 Z. 590–611 | Grenzen generisch (Rauschen, Bibliothek, Extrapolation, Stabilität) | Je Grenze ein Satz, welche für die Ladeluftstrecke dominiert (Closed-Loop-Konfundierung, Extrapolation in $\TLT$) |
| 5.5 | ch3 Z. 308–312 | Closure-Problem bei Mitführen von $\mathbf x$ und Liftung genannt, ohne Bezug zur eigenen \edmdc-Bibliothek | Einen Satz, wie die eigene Liftung das Problem behandelt |
| 5.6 | ch3 Z. 625–628 | „eine analoge Sensitivität ist für SINDy zu erwarten“; Z. 633–637 belegt genau das mit Brunton u. a. 2016, S. 713 | „zu erwarten“ streichen, Beleg nach vorn ziehen |

**6 Selbstständigkeit und Kreativität**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 6.1 | ch2 Z. 392, 920 | Eigene Algebra ist gekennzeichnet; gut | Beibehalten; konvexe Kombination (Auftrag B G1) als weitere eigene Herleitung |
| 6.2 | ch3 Z. 1026–1028 | Deutung von \sindyc{} mit Produkten „Betriebspunktgröße × Temperaturdifferenz“ als quasi-LPV-Modell ($\Tin$, $\TLT$, $\mrel$ gehen schwach mit dem Hub mit, ch2 Z. 517–519, 775–780) ist nach Auftrag A (A3.4) in der Literatur nicht ausdrücklich zu finden | Als eigenen methodischen Beitrag formulieren (E2); Annahme eingefrorener oder ventilunabhängig prognostizierter Scheduling-Größen benennen |
| 6.3 | ch2 Z. 392–396 (Differenzen); in ch3 fehlt die Aussage | Verschiebungsinvarianz der Differenzbibliothek ist nach Auftrag A (A3.1) nicht als Literaturbefund zu finden | Als eigenes Argument und Modelleigenschaft führen (exakt nur mit festgehaltenem $\mrel$ oder $q_{\mathrm{rel}}$), mit kleinem Test belegen (E3, Idee 2) |
| 6.4 | ch3 Z. 1024–1027 | Leerbefund „keine SINDy-/Koopman-Arbeit prüft Residuen auf Autokorrelation …“ | Residuentests selbst durchführen macht daraus einen Beitrag (E3, Idee 4) |

**7 Qualität der Ausarbeitung**

| Nr. | Stelle | Befund | Vorschlag |
|---|---|---|---|
| 7.1 | ch3 Z. 761–777 | Rohentwurf mit Tippfehlern (Z. 764–772: „In meisten Industriellen Systeme …“, „Direkte Motehode“, „Indirkete Methdoe“), inhaltlich doppelt zu Z. 617–755; Z. 775–777 leiten Gl. `eq.grundlagen.cl.strecke` ein | Z. 761–774 (auskommentierte Überschrift und Rohentwurf) entfernen; in Z. 775 nur den Satzrest „Messdaten.“ streichen; Z. 775–777 als Überleitung zu `eq.grundlagen.cl.strecke` behalten |
| 7.2 | ch3 Z. 218–222 | Satzfragment in Z. 218 doppelt zu Z. 220–222, Tippfehler „unendlichdimsensionalen“ | Fragment „Der Koopman-Operator wirkt linear auf einen unendlichdimsensionalen Raum“ (Z. 218, zweiter Teil) streichen; „DMD ist eng mit dem Koopman-Operator verbunden.“ behalten |
| 7.3 | ch3 Z. 625, 506, 552, 618 (Label), 426–430 vs. 496–498; ch2 Z. 296 | Satz-, Tipp- und Notationsfehler: `textbf{…}` ohne Backslash (Z. 625), erscheint als Text; „Esemble“ (Z. 506 Überschrift; Z. 552 nur Dateiname), „Identifiaktion“ (ch2 Z. 296), Label `closed_loop_identifkation`; LASSO-Zielfunktion in Z. 427 mit $\lVert\cdot\rVert_2^2$, in der Bildunterschrift (Z. 496–498) mit $\lVert\cdot\rVert_2$ (formal Square-Root-LASSO, anderer Schätzer) und mit $\boldsymbol\Theta^{\top}\boldsymbol\xi_k$, dimensionsfalsch nach Gl. `eq.sindy.def` | `\textbf`; Z. 506 korrigieren, Z. 552 optional und nur zusammen mit Umbenennung der Bilddatei; Label nur mit allen `\ref` gemeinsam; Bildunterschrift: $\min_{\boldsymbol\xi_k}\lVert\dot{\mathbf x}_k-\boldsymbol\Theta(\mathbf X,\mathbf U,\mathbf D)\boldsymbol\xi_k\rVert_2^2+\lambda\lVert\boldsymbol\xi_k\rVert_1$ (ohne Transponierung, passend zu Gl. `eq.sindy.def`; quadriert wie Z. 427) |
| 7.4 | ch3 Z. 948, 995; ch2 Z. 1039 | Umgangssprache/Denglisch („LT Cooling Water Temperatur“), unklarer Begriff „EMEC-nahe Ansätze“, Floskel „zudem“ | Fachbegriffe nach Formelzeichenliste ($\TLT$), Begriff erklären oder streichen |
| 7.5 | ch2 Z. 184–185 u. a. | „Bündel“ für HT/LT (Vorgabe: Stufe) | Auftrag B, Befund T1 |
| 7.6 | ch2 Z. 438, 1068; ch3 Z. 423, 428, 498 | $\lambda$ dreifach belegt (Rate, MPC-Gewicht, Schwellwert) | Auftrag B, Befund T2 |

### Verteidigungsfragen (H = Henning, M = Merkel)

Antwortskizzen als Stichpunkte; Belege mit Key (Bib = schon in der Bib; A/B = BibTeX-Entwurf in
Auftrag A bzw. B; E = BibTeX-Entwurf hier). Keine Volltextprüfung.

1. **(H) Ist Ihr \sindyc-Modell ein reduziertes Modell im Sinne von POD-Galerkin?**
   - Nein im engeren Sinn: keine Projektion einer PDE auf Moden, sondern ein konzentriertes
     Modell mit einem Temperaturzustand.
   - Eigene Deutung (nicht belegt): Ein-Moden-Galerkin mit konstanter Ansatzfunktion ergibt
     eine Mitteltemperatur; $\Tout$ als Zustand setzt Mitteltemperatur = Austrittstemperatur
     voraus (Rührkessel-Annahme, Advektionsterm sonst mit Randtemperatur).
   - Die Trunkierung entspricht der Wahl eines einzigen Zustands; die Regression ersetzt die
     Projektion (Berechnung der Koeffizienten), nicht die Trunkierung
     (`loiseauConstrainedSparseGalerkin2018`, laut Abstract, S).
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
     statt generischer Polynome; Auswahl über Schwellwert statt Fehlerreduktionsverhältnis.
     Gemeinsam: Schätzung auf dem Einschrittfehler wie beim klassischen NARX (OLS/ERR);
     Unterschied nur zu Simulationsfehler-NARX (Piroddi & Spinelli 2003).
   - `billingsNonlinearSystemIdentification2013` (E), `piroddiIdentificationAlgorithmPolynomial2003` (A),
     `aguirreBirdsEyeView2019` (A).
4. **(M) Warum sind Ihre Koeffizienten aus geregelten Daten nicht verzerrt?**
   - Direkte Methode konsistent, wenn das Störmodell stimmt (weißer Gleichungsfehler), der Kreis
     eine Verzögerung enthält und die Daten informativ sind (Ljung 1999, Kap. 13; Forssell &
     Ljung 1999; Stelle am Original prüfen); sonst verzerrt (ch3 Gl. `eq.grundlagen.cl.bias`;
     E1 Befund 3.6).
   - Gegenmittel: Schätzung auf Daten mit vom Regler unabhängiger Anregung, geregelte Daten zur
     Validierung (Schema aus Auftrag D, Frage 3); welche Eigenschaften sich aus Regelkreisdaten
     zurückgewinnen lassen, wird gegen die am Prüfstand bekannte Wahrheit geprüft
     (ch3 Z. 922–924).
   - Datenrollen (Schätzung, Auswahl, Bewertung) aus Kap. 4/5 der Arbeit übernehmen; laut
     Bewertungsschema dienen DoE-Daten der Validierung.
   - `forssellClosedloopIdenticationRevisited1999`, `ljungSystemIdentificationTheory1999`,
     `dahdahClosedloopKoopmanOperator2024` (Bib).
5. **(M) Warum Einschritt-Kleinste-Quadrate statt Simulationsfehler-Minimierung?**
   - Einschritt-LS ist konvex und schnell; Simulationsfehler passt bei Ausgangsrauschen besser.
     Bewertung deshalb im Freilauf und über den Horizont (Auftrag B, B2.5; E3 Idee 3).
   - `farinaIterativeAlgorithmSimulation2010` (A), `somalwarLearningImperfectModels2025` (A),
     `ribeiroParallelTrainingConsidered2018` (B).
6. **(H/M) Ist Ihr Modell überhaupt QP-tauglich?**
   - Affin in Zustand und $g(\valveCA)$ bei gegebenem Verlauf der Betriebsgrößen (Auftrag B, B1);
     QP nur mit linearem $g$ oder $v=g(\valveCA)$ als Entscheidungsvariable ($g$ monoton,
     Schranken in $v$ übertragen, Stellschritt-Strafe auf $\Delta v$), sonst Linearisierung von $g$.
   - Produkte mit gemessenen Betriebsgrößen: quasi-LPV ($\Tin$, $\TLT$, $\mrel$ gehen schwach mit
     dem Hub mit, ch2 Z. 517–519, 775–780). QP-tauglich unter der Annahme, dass diese Größen über
     den Horizont eingefroren oder unabhängig vom Ventil prognostiziert werden; der Fehler dieser
     Annahme gehört in die Modellbewertung.
   - Bilineares \edmdc{} verliert den QP (ch3 Z. 363–366).
   - `rawlingsModelPredictiveControl20202020` (Bib), `cisnerosEfficientNonlinearModel2016` (A).
7. **(H) Wie sichern Sie Stabilität von Modell und Regelkreis?**
   - Modell: skalar $\lvert a(\mrel)\rvert<1$ für alle Betriebspunkte reicht; $a\in(0,1)$
     zusätzlich als Plausibilität, schließt Oszillation aus (E3 Idee 7). Mehrzustandsmodelle mit
     variabler Matrix: gemeinsame Lyapunov-Funktion oder langsame Parameteränderung nötig.
   - Regelkreis: Gl. `eq.grundlagen.mpc` hat keine Endkosten; Stabilität über Horizontlänge und
     Simulation begründen oder Endkosten ergänzen.
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
   \sindyc-Modell ergeben, das affin in Zustand und in $g(\valveCA)$ bleibt und unter
   angebbaren Bedingungen in einen linearen QP-MPC passt.“
   - Bedingung: QP-tauglich, wenn $g$ linear ist oder im QP $v=g(\valveCA)$ als
     Entscheidungsvariable dient ($g$ monoton, Schranken in $v$ übertragen, Stellschritt-Strafe
     auf $\Delta v$); bei Totzone/S-Form sonst Linearisierung von $g$ um den Arbeitspunkt.
   - Annahme: Betriebsgrößen der Produktterme ($\Tin$, $\TLT$, $\mrel$) gehen schwach mit dem
     Hub mit (quasi-LPV, ch2 Z. 517–519, 775–780); über den Horizont eingefroren oder
     ventilunabhängig prognostiziert, Fehler dieser Annahme in der Modellbewertung.
   - Lücke: keine SINDy-Arbeit mit Wärmeübertrager-Termformen in der Bibliothek gefunden
     (Auftrag A, A3.3); SINDy nicht ausdrücklich als (quasi-)LPV gedeutet (A3.4); SINDy-MPC in der
     Literatur nichtlinear optimiert (Kaiser u. a. 2018 laut Autoren-Code; Yahagi u. a. 2025 NMPC,
     ch3 Z. 1094–1102).
   - Beleg für die Nähe: Cisneros u. a. 2016 (quasi-LPV-MPC), Sheikh u. a. 2024 (sparse LPV mit
     physikalisch motivierter Basis, Batterie), beide Auftrag A.
2. **Messdaten eines Großgasmotors statt Simulation.** „Diese Arbeit identifiziert die
   Ladelufttemperatur am Motoreintritt aus Prüfstands- und Felddaten eines mittelschnelllaufenden
   Dual-Fuel-Motors.“
   - Lücke: an Ladeluftkühler bzw. Ladelufttemperatur keine SINDy-/Koopman-Arbeit mit Messdaten
     gefunden; am Motorluftpfad mit Messdaten außerhalb der Yahagi-/Yonezawa-Gruppe nur Zinage
     u. a. 2022 (EDMD, Turboladerturbine, ohne Regler). ch3 Z. 1018–1029, 1138–1147; Auftrag A
     (A3.5); E2-Tabelle unten.
3. **Bewertung nach Verwendungszweck.** „Diese Arbeit bewertet datengetriebene Modelle nicht nur
   am Vorhersagefehler, sondern an Ventil-Verstärkung, offener und geschlossener Kette und
   DoE-Validierung, also an dem, was der Regler braucht.“
   - Lücke: Identifikation für die Regelung ist allgemein etabliert (Auftrag D, Frage 5); eine
     SINDy-/Koopman-Arbeit mit Stellverstärkung, OL/CL und DoE als Bewertungsgrößen nicht gezielt
     gesucht (s. Offen).
   - Residuen-Leerbefund ch3 Z. 1024–1027 nur nennen, wenn der Beitrag um Residuentests erweitert
     wird („… und prüft die Residuen auf Autokorrelation und Kreuzkorrelation mit $\valveCA$“,
     Bedingungen s. E3 Idee 4).
4. **Closed-Loop-Daten gegen bekannte Wahrheit.** „Diese Arbeit prüft am Prüfstand, welche der
   drei Modelleigenschaften (Niveau, Dynamik, Stellwirkung) sich aus geregelten Betriebsdaten
   zurückgewinnen lassen.“
   - Lücke: Closed-Loop-Bias für \edmdc{} bei Dahdah u. a. 2024 (ch3 Z. 626–627, 752–754);
     für \sindyc{} keine eigene Standardquelle gefunden (Recherche E2, Offen).
5. **Invarianz als Entwurfsregel (nur mit Idee 2 aus E3).** „Die Differenzbibliothek dieser
   Arbeit erzwingt Verschiebungsinvarianz der Prognose, solange die Betriebspunktfaktoren nicht
   von der Temperatur abhängen.“
   - Gilt mit $q_{\mathrm{rel}}$ oder mit im Test festgehaltenem $\mrel$; mit $\mrel$ aus
     verschobenem $\Tin$ nicht exakt ($\mrel$ enthält $T_{\mathrm{col,in,K}}$, ch2 Z. 686–691).
   - Modelle mit Absoluttemperatur-Termen erfüllen sie nur, wenn sich die stationären
     Temperaturverstärkungen zu 1 summieren (Auftrag B, G1).
   - Als Modelleigenschaft und Annahme formulieren, nicht als Befund; die reale Strecke ist wegen
     Dichte und Stoffwerten nicht exakt invariant (ch2 Z. 664–680 Dichte, Z. 967–969 Stoffwertterm).
   - Lücke: Auftrag A (A3.1), nicht gefunden; Auftrag B (G1) liefert die Algebra.

### Nächste Verwandte (2019–2026, dazu ältere Kernarbeiten)

Kennung: Bib = Key schon in `Masterarbeit.bib` (in ch2/ch3 zitiert); A/B/E = BibTeX-Entwurf in
Auftrag A, B oder hier; Kandidat = kein BibTeX-Entwurf, s. Offen. Inhalte aus
Suchzusammenfassungen (S) oder GitHub-Dateien (G), kein Volltext; Abstract nur, wo (G) ihn
wörtlich wiedergibt; „laut Abstract … (S)“ heißt: Abstractinhalt nur über die
Suchzusammenfassung.

| Arbeit | Was sie macht | Was sie nicht macht | Abgrenzung dieser Arbeit |
|---|---|---|---|
| Vagapov u. a. 2022 (Bib) | Hammerstein-Modell eines Ladeluftkühlers, Prüfstand und Fahrzeug (ch3 Z. 1058–1068) | kein Regler, keine sparse Termauswahl | datengetriebene Termauswahl, Regler |
| Vagapov 2024, Diss. (Bib) | prädiktive Ladelufttemperaturregelung im Fahrzeug über Pumpe und Ventil (ch3 Z. 1069–1081) | vollständige Kaskade nicht echtzeitfähig; Nutzfahrzeug (Titel der Diss., T), kein Großmotor | Großmotor, lineares QP, Ventil als einzige Stellgröße |
| Beran u. a. 2021 (Bib; DOI 10.1007/s41104-021-00087-0, T) | Regelstrategie für Ladeluftkühlkonzept mit ML-Steuermodellen (ch3 Z. 976–982) | keine interpretierbaren Terme | explizite Terme mit physikalischer Form |
| Rupprecht 2016 (Bib) | physikalisches Kühlkreismodell eines Großmotors, Ventilregelung (ch3 Z. 1044–1056) | $\TLT$ konstant; keine datengetriebene Struktur | $\TLT$ als gemessene Störgröße |
| Yahagi u. a. 2025 (Bib; ein IJCAS-Artikel mit DOI 10.1007/s12555-024-0452-9 (T) wurde gefunden, Zuordnung zum Bib-Key ungeprüft) | SINDy für Ladedruck/AGR, NMPC am Simulationsmodell | keine Messdaten, keine Temperatur | Messdaten, Temperaturstrecke, QP |
| Yahagi u. a. 2026 (Bib; vermutlich arXiv:2602.15422, T, Zuordnung ungeprüft) | bilineares Koopman aus E/A-Daten, Motorprüfstand unter PID | noch kein Regler (laut ch3 Z. 1103–1111) | Regler, linear statt bilinear |
| Yonezawa u. a. 2025 (Bib; vermutlich arXiv:2507.18220, T, Zuordnung ungeprüft) | SINDy mit Bibliotheksoptimierung, rekursive Langzeitprognose, Diesel-Luftpfad | Temperatur nicht Regelgröße; Datenherkunft unklar | thermische Strecke, Messdaten |
| Kaiser u. a. 2018 (Bib) | SINDYc im MPC, wenig Daten | nichtlineares MPC (SQP) laut Autoren-Code; Benchmark-Systeme | QP-taugliche Struktur, reale Anlage |
| Zinage u. a. 2022 (Bib; arXiv:2204.10421, T) | EDMD für Turbinendrehzahl und Turbinenaustrittstemperatur aus Motormessdaten; laut Abstract besser als NARX (G); für die Austrittstemperatur bei hoher Turbinendrehzahl NARX besser (S) | kein Regler | Regler, Ladeluft statt Turbine |
| Akan u. a. 2024 (A) | \sindyc{} lernt die Abweichung zu einem physikalischen Modell eines Wärmeübertrager-Netzes (S) | kein eigenständiges \sindyc-Modell, Bibliothek unbekannt | eigenständiges Modell mit Wärmeübertrager-Termen |
| Kaleli 2020 (Kandidat; nur PII) | MPC eines Ottomotor-Kühlsystems, lokal lineare Modelle, Echtzeittest am Prüfstand (S) | Regelgröße Kühlmittel-, nicht Ladelufttemperatur; keine Bibliothek | Ladeluft, sparse Bibliothek |
| Zhang u. a. 2022 (E; arXiv:2202.12803, T) | lineare/LPV-MPC des Diesel-Luftpfads, Modell aus transienten GT-Power-Daten; transiente thermische Motordynamik beeinflusst die Saugrohrdruck-Antwort, MPC laut Abstract robust gegen Fehler in deren Modellierung (S) | nur Simulation, Regelgröße Druck/AGR | Messdaten, Temperatur |
| Vega-Zambrano u. a. 2025 (E; DOI 10.1016/j.ijpharm.2025.125322, G) | Vergleich DMDc, MOESP, \sindyc{} für MPC einer Granulieranlage (S) | kein thermisches System; Datenherkunft unklar | gleiche Modellfamilien, thermische Strecke |
| Valábek u. a. 2025 (E; arXiv:2511.04437, T) | Deep-Koopman-EMPC einer Pasteurisieranlage mit Plattenwärmeübertrager, Laborstand (S) | Black-Box-Lifting, keine physikalische Bibliothek | physikalisch motivierte Terme |
| Miyashita u. a. 2022 (E; DOI 10.23919/SICE56594.2022.9905828, G) | Koopman-MPC mit STL-Spezifikation für Warmwassertemperatur (T) | Datenherkunft unklar; kein Motor | Motor, Messdaten |
| Ou u. a. 2024 (Kandidat; nur PII) | SINDy-Modell reduzierter Ordnung und MPC der Wafertemperatur (S) | Halbleiterprozess; Daten laut Abstract aus CFD-Modell (Ansys Fluent), Messdaten nicht erwähnt (S) | Motor, Ventilstrecke |

- Einordnung: Die nächste Arbeit zur Strecke ist Vagapov 2024 (Nutzfahrzeug); die nächste zur
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
| 1 | **QP-Tauglichkeitstabelle:** je Modellklasse und Variante prüfen, ob die Prädiktion affin in Zustand und $g(\valveCA)$ ist (Spalten: Terme Zustand×Zustand, Ventil×Zustand, $g(\valveCA)$ linear oder monoton invertierbar, Scheduling-Größen eingefroren oder ventilunabhängig prognostiziert, quasi-LPV) | 4, 5, 3 | S, 1–2 h | nein | Auftrag B (B1, sympy-Beispiel; B2.3); `rawlingsModelPredictiveControl20202020`; Cisneros u. a. 2016 (A) | Keins; deckt ggf. auf, dass eine Variante nicht QP-tauglich ist, dann als Grenze benennen |
| 2 | **Verschiebungsinvarianz-Test:** alle Temperatureingänge und den Anfangswert um denselben Betrag verschieben (oder °C gegen K tauschen), $\mrel$ dabei festhalten, und prüfen, ob sich die Prognose um genau diesen Betrag verschiebt; für ARX, \sindyc{} (Differenz- vs. Absolutbibliothek), \edmdc | 6, 4, 5 | S, 2–3 h | ja (vorhanden) | Eigenes Argument (A3.1: in der Literatur nicht gefunden); Auftrag B G1 | Absolutterm-Modelle bestehen nur bei Verstärkungssumme 1; Abweichung davon berichten |
| 3 | **Persistenzreferenz und Fehler über dem Horizont:** Einschritt- und Freilauffehler immer gegen $\hat y_{k+1}=y_k$ stellen; Fehlerkurve $e(h)$ für $h=1\dots N$ (MPC-Horizont) je Modell | 4, 3 | S, 2–4 h | ja | Auftrag B (B2.5); `ljungSystemIdentificationTheory1999`; Somalwar u. a. 2025 (A); Nelles 2020 (B) | Rangfolge der Modelle kann sich gegenüber Einschrittmaßen ändern; genau das ist die Aussage |
| 4 | **Residuentests:** Weißheitstest auf Einschritt-Residuen bzw. Residuen eines Modells mit Störmodell; Kreuzkorrelationstest Residuum–$\valveCA$ und Residuum–Last auf DoE-/ungeregelten Abschnitten oder nur bei weißen Residuen, mit Konfidenzband | 4, 6 | S, 3–4 h | ja | `ljungSystemIdentificationTheory1999` (Kapitel Modellvalidierung, lokal); Billings & Voon 1986 (s. Anker unten); ch3 Z. 1024–1027 (Leerbefund) | Unter Rückführung und farbiger Störung ist ein Ausschlag auch beim wahren Modell zu erwarten; kein Nachweis eines Modellfehlers oder Closed-Loop-Bias |
| 5 | **Konditionierung und Koeffizientenstreuung:** Konditionszahl und VIF je Bibliothek; Streuung der Koeffizienten über Block-Bootstrap oder Ensemble-Inklusionshäufigkeit | 4, 5, 3 | M, 4–8 h | ja | Belsley u. a. 1980, Künsch 1989 (s. Anker unten); `faselEnsembleSINDyRobustSparse2022`; Meinshausen & Bühlmann 2010 (A) | Rechenzeit; große Streuung zeigt Nicht-Identifizierbarkeit einzelner Terme; ehrlich benennen |

### Weitere Ideen

| Rang | Idee | Kategorie | Kriterium | Aufwand | Messdaten | Literaturanker | Risiko |
|---|---|---|---|---|---|---|---|
| 6 | **Modussprung prüfen:** um jeden Umschaltzeitpunkt Diesel/Gas die Sprunghöhe von $\valveCA$ gegen gleichzeitige Last- und $\TLT$-Änderung stellen; Instrument nur, wenn der Stellgrößensprung nicht mit Störungen zusammenfällt | Absicherung | 4 | S–M, 3–5 h | ja | `ljungSystemIdentificationTheory1999` (Abschn. 13.4); E1 Befund 4.1 | Sprünge fallen mit Laständerungen zusammen; dann Instrument abschwächen |
| 7 | **Stabilität über dem Betriebsbereich:** Eigenwert bzw. Eigenkoeffizient $a(\mrel)$ für alle im Datensatz vorkommenden Betriebspunkte in $(0,1)$? (Plausibilität, Stabilität schon bei $\lvert a\rvert<1$; eingefrorene Eigenwerte bei mehreren Zuständen nicht hinreichend) | Analyse | 3 | S, 1–2 h | ja | `khalilNonlinearSystems2002` (B); Auftrag B (B2.1) | Instabile Bereiche am Rand; Gültigkeitsbereich einschränken |
| 8 | **Weiche Schranke exakt machen:** linearen Slack-Term $\mu_1 s$ ergänzen, zeigen, dass die Untergrenze nur bei Unzulässigkeit verletzt wird | Absicherung | 3, 4 | S, 1–2 h | nein (Simulation) | Kerrigan & Maciejowski 2000 (B) | Gewichtswahl; gering |
| 9 | **Einfache physikalische Referenz:** $\varepsilon$-NTU-Zielwert mit 2–3 Parametern plus Relaxation als zusätzliche Vergleichslinie neben ARX | Analyse | 3, 4 | M, 4–8 h | ja | `vagapovDynamicModelTemperature2022` (Hammerstein); `suiMeanValueFirst2022`; Auftrag B G1 | Referenz kann \sindyc{} erreichen; dann Aussage „Bibliothek trifft die Physik“ |
| 10 | **Gain-Empfindlichkeit im simulierten Kreis:** MPC mit skaliertem Modell-Gain gegen dieselbe Strecke laufen lassen; zeigt, wie viel Gain-Fehler der Regler verträgt | Analyse | 4, 5 | M, 6–10 h | nein (Simulation mit vorhandenem Modell) | `skogestadMultivariableFeedbackControl2005` (B); Yousefi u. a. 2015 (B, nur S) | Streckenmodell ist selbst identifiziert; als Simulationsaussage kennzeichnen |
| 11 | **Rechenzeit des QP je Takt** gegen den MPC-Takt aus Abschnitt `sec.methodik.mpc` (zum Vergleich Serienregler $500\,$ms, ch2 Z. 275) | Absicherung | 1, 4 | S, 1–2 h | nein | `rawlingsModelPredictiveControl20202020` | Keins |
| 12 | **Hyperparameterwahl ohne Testdaten dokumentieren:** Trennung Training / Auswahl / Test als Schema; Schwellwert und Bibliothek nur auf Auswahldaten | Absicherung | 4 | S, 1–2 h | nein | Cawley & Talbot 2010, Varma & Simon 2006 (D, Frage 6) | Keins |
| 13 | Abbildung: **Ersatzschaltbild** (ch2 Z. 905–907) zu Gl. `eq.energiebilanz.dyn`: $C_{\mathrm{eff}}$ als Kapazität am Knoten $\Tout$, Leitwert $\dot m_L c_{p,L}$ von Quelle $\Tin$, Leitwert $U_{\mathrm{eff}}A$ (nicht $kA$ der Statik, ch2 Z. 830–831; Ventilpfeil auf den wasserseitigen Anteil) zu Quelle $\TLT$, HT-Stufe als vorgeschalteter Block | Abbildung | 7, 5 | S, 2 h | nein | ch2 Z. 877–884 | Keins |
| 14 | Abbildung: **Zielwert als gewichtete Mischung** von $\Tin$, $\THT$, $\TLT$ (Balken oder Dreieck, Gewichte aus Auftrag B G1) über dem Ventilhub | Abbildung | 5, 7 | S, 2 h | nein (qualitativ) | Auftrag B G1 | Keine Zahlen erfinden: qualitativ zeichnen |
| 15 | Abbildung: **Prüfmatrix** Modell × {Niveau, Dynamik, Stellwirkung} × {OL, CL, DoE, Gain} als Ampel | Abbildung | 7, 4 | S, 2 h | ja (Ergebnisse) | ch3 Z. 907–925 (Dreiteilung) | Keins |
| 16 | Abbildung: **Blockschaltbild geschlossener Kreis** mit Konfundierungspfad Last → Vorsteuerung → Ventil und Last → Strecke | Abbildung | 7, 5 | S, 2 h | nein | ch3 Z. 650–651 (Kommentar), Z. 877–884 | Keins |
| 17 | Diskussion: **Übertragbarkeit** auf die Feldbaureihe 51/60DF (anderes Band, ch2 Z. 125–126): Struktur übertragbar, Koeffizienten nicht | Diskussion | 5 | S, 1–2 h | nein | `rupprechtAnalysisSimulationOptimisation2016`; Auftrag A (PG 51/60DF) | Keins |
| 18 | Diskussion: **Online-Nachführung** bei Verschmutzung und Drift (ch3 Z. 458–460 schließt sie aus) als Ausblick | Diskussion | 6 | S, 1 h | nein | `bhadrirajuOASISPOperableAdaptive2021`; Quade u. a. 2018 (s. Anker unten) | Keins |
| 19 | Diskussion: **Beobachter ↔ Kalman ↔ exponentielle Glättung** (Henning) | Diskussion | 5 | S, 2 h | nein | `muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003` (Bib); Auftrag D (Frage 4) | Keins |
| 20 | Diskussion: **Reduzierte Modelle** (POD-Galerkin) gegen \sindyc{} (Henning) | Diskussion | 5 | S, 2 h | nein | `loiseauConstrainedSparseGalerkin2018` (Bib), `loiseauSparseReducedorderModelling2018` (D); Auftrag D (Frage 1) | Keins |

### Große Ideen (nur Ausblick, bis 19.10. nicht umsetzbar)

- Adaptive bzw. online nachgeführte \sindyc-Modelle im Feldbetrieb
  (`bhadrirajuOASISPOperableAdaptive2021` (Bib), Quade u. a. 2018 (E)).
- Mehrgrößenregelung mit LP-Ventil als zweiter Stellgröße (heute ausgeschlossen: Stellglied nur HP;
  `skogestadMultivariableFeedbackControl2005` (B)).
- Nichtlineares MPC auf bilinearem \edmdc{} (ch3 Z. 339–366) mit Vergleich zum QP
  (`kelmanBilinearModelPredictive2011` (Bib, ch3 Z. 366)).
- Versuchsplanung für geregelte Feldanlagen (kostenminimales Experiment,
  `bomboisLeastCostlyIdentification2006` (Bib)).
- Ökonomisches MPC mit Derating-Grenze (ch2 Z. 39–41) als Zielgröße (kein Literaturanker
  gefunden, s. Offen).

### Methodenanker für E3

| Zweck (Idee) | Quelle | DOI / ISBN (Herkunft) | Status | Nutzen |
|---|---|---|---|---|
| Konditionsdiagnostik (5) | Belsley, D. A.; Kuh, E.; Welsch, R. E. (1980): Regression Diagnostics: Identifying Influential Data and Sources of Collinearity. Wiley (G) | ISBN 9780471058564 (G); DOI 10.1002/0471725153 nur in einer Bib (G), vermutlich Neuausgabe | [nur bibliografisch] | Konditionsindizes und Varianzzerlegung zeigen, welche Bibliotheksterme sich gegenseitig ersetzen; VIF zeigt das nicht (eigene Einschätzung) |
| Bootstrap (5) | Efron, B.; Tibshirani, R. J. (1993): An Introduction to the Bootstrap. Chapman & Hall (G) | ISBN 0412042312 (G) | [nur bibliografisch] | Grundlage Bootstrap (eigene Einschätzung) |
| Block-Bootstrap für Zeitreihen (5) | Künsch, H. R. (1989): The Jackknife and the Bootstrap for General Stationary Observations. Ann. Stat. 17(3), 1217–1241 (G) | 10.1214/aos/1176347265 (G) | [nur bibliografisch] | Blöcke erhalten die Autokorrelation geregelter Messreihen; Konfidenzintervalle nicht künstlich eng (eigene Einschätzung) |
| Strukturelle und praktische Identifizierbarkeit (5) | Raue, A. u. a. (2009): Structural and practical identifiability analysis of partially observed dynamical models by exploiting the profile likelihood. Bioinformatics 25(15), 1923–1929 (G) | 10.1093/bioinformatics/btp358 (G) | [nur bibliografisch] | Profil-Likelihood je Koeffizient: Profil flach = strukturell nicht identifizierbar (z. B. exakt linear abhängige Bibliotheksterme); Profil mit Minimum, das die Konfidenzschwelle in einer oder beiden Richtungen nicht überschreitet = praktisch nicht identifizierbar (z. B. Ventilterm bei schwacher Anregung) (S; Begriffe am Original prüfen) |
| Globale Sensitivität (optional) | Saltelli, A. u. a.: Global Sensitivity Analysis. The Primer. Wiley (G); Jahr 2007 oder 2008 uneinheitlich (G) | ISBN 9780470059975 (G); DOI 10.1002/9780470725184 (G) | [nur bibliografisch] | Sobol-Indizes: Anteil von $\TLT$, $\mrel$, $\valveCA$ an der Streuung der Vorhersage; nur mit unabhängig angesetzten Eingangsverteilungen (Szenario) oder mit Varianten für abhängige Eingänge; auf geregelten Betriebsdaten wegen Konfundierung (ch3 Z. 877–889) nicht direkt interpretierbar (eigene Einschätzung) |
| Residuentests (4) | Billings, S. A.; Voon, W. S. F. (1986): Correlation based model validity tests for non-linear models. Int. J. Control 44(1), 235–244 (T/G) | 10.1080/00207178608933593 (T) | [nur bibliografisch] | Korrelationstests höherer Ordnung finden ausgelassene nichtlineare Terme (S) |
| Residuentests (4) | Billings, S. A. (2013): Nonlinear System Identification: NARMAX Methods in the Time, Frequency, and Spatio-Temporal Domains. Wiley (G); Kap. 5 „Model Validation“ (T) | 10.1002/9781118535561 (G) | [nur bibliografisch] | Lehrbuchanker; zugleich NARMAX-Bezug für Merkel (eigene Einschätzung) |
| Online-Nachführung (18) | Quade, M.; Abel, M.; Kutz, J. N.; Brunton, S. L. (2018): Sparse identification of nonlinear dynamics for rapid model recovery. Chaos 28(6), 063116 (G) | 10.1063/1.5027470 (G); arXiv:1803.00894 (G) | [nur bibliografisch] | SINDy-Koeffizienten nach abrupter Änderung mit wenig Daten neu schätzbar (S) |

### BibTeX-Entwürfe E

Nur (T)/(G)-Felder im Eintrag, (S) als `% ungeprüft:` darüber. Status aller Einträge
[nur bibliografisch]. `zinageDataDrivenModeling2022` (ch3 Z. 1000) und
`beranModelbasedApproachControl2021` (ch3 Z. 976) sind schon in der Bib. Kaleli 2020 und Ou 2024
ohne Eintrag (Autoren und Jahr nur S), als Kandidaten unter „Offen / nicht belegt“.

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

% ungeprüft: Key-Jahr 2008. Jahr uneinheitlich: 2008 (eine Bib) oder 2007 (zwei Bibs; Erscheinen
%            Dez. 2007 laut Suchzusammenfassung, S); Key erst in Zotero (Better BibTeX) nach
%            Festlegen des Jahres vergeben
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

% ungeprüft: author = {Val{\'a}bek, Patrik and Horv{\'a}thov{\'a}, Michaela and Klau{\v{c}}o, Martin} (S);
%            Nachname im Key damit ebenfalls nur (S)
@misc{valabekDeepKoopmanEconomic2025,
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

% ungeprüft: author = {Zhang, Jiadi and Amini, Mohammad Reza and Kolmanovsky, Ilya and Tsutsumi, Munechika and Nakada, Hayato} (S)
% arXiv-PDF-Kopf: 2022 American Control Conference (ACC), June 8-10, 2022, Atlanta, GA, USA (T); DOI und Seiten der ACC-Fassung nicht gefunden
@misc{zhangDevelopmentModelPredictive2022,
  author        = {Zhang, Jiadi and others},
  title         = {Development of a Model Predictive Airpath Controller for a Diesel Engine on a High-Fidelity Engine Model with Transient Thermal Dynamics},
  year          = {2022},
  eprint        = {2202.12803},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% beranModelbasedApproachControl2021 ist schon in der Bib (ch3 Z. 976); nur DOI 10.1007/s41104-021-00087-0 (T) gegen Zotero abgleichen.
% ungeprüft: journal = {Automotive and Engine Technology} (ohne Herkunftskennung); Autoren nur Nachnamen Beran, Gärtner, Koch (S)
% ungeprüft: title = {A model-based approach for a control strategy of a charge air cooling concept in an ejector refrigeration cycle} (ohne Herkunftskennung)
```

---

## Anhang E: Suchweg zu E2 (39 Anfragen, Copilot)

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

---

## Offen / nicht belegt

- Keine Quelle im Volltext gelesen; Inhaltsangaben der Verwandten und Anker aus
  Suchzusammenfassungen (S) oder GitHub-Dateien (G), Nutzen-Spalte der Anker teils eigene
  Einschätzung. Metadaten-Lücken: Kaleli 2020 (Autoren, DOI), Ou 2024 (Autoren, DOI,
  Datenherkunft nur S), Zhang 2022 (Koautoren nur S; DOI und Seiten der ACC-2022-Fassung),
  Valábek 2025 (Autoren nur S), Castiglione 2020 (Autoren nur S), IFAC-Fassung Zinage 2022.
- Kandidaten ohne BibTeX-Entwurf (Autoren und Jahr nur S, daher kein Key):
  - Kaleli 2020: „Development of the predictive based control of an autonomous engine cooling
    system for variable engine operating conditions in SI engines: design, modeling and real-time
    application“ (T), https://www.sciencedirect.com/science/article/abs/pii/S0967066120300770;
    Control Eng. Pract. 100, 104424 (2020) nur (S); Autoren und DOI offen.
  - Ou u. a. 2024: „Sparse identification modeling and predictive control of wafer temperature in
    an atomic layer etching reactor“ (T),
    https://www.sciencedirect.com/science/article/abs/pii/S0263876223008201; nur (S): Ou, F.;
    Abdullah, F.; Wang, H.; Tom, M.; Orkoulas, G.; Christofides, P. D.; Chem. Eng. Res. Des. 202,
    1–11 (2024); DOI 10.1016/j.cherd.2023.12.024.
- Beran u. a. 2021: DOI 10.1007/s41104-021-00087-0 (T) mit vorhandenem Bib-Eintrag
  `beranModelbasedApproachControl2021` abgleichen.
- Vagapov 2024 (Diss., Bib): Titel „Modellierung, Identifikation und modellbasierte Regelung des
  Niedertemperaturkühlkreislaufs eines Nutzfahrzeuges“ (T),
  https://repo.uni-hannover.de/handle/123456789/18098; Grundlage für „Nutzfahrzeug“ in der
  Verwandtentabelle, mit dem Bib-Eintrag abgleichen.
- Widersprüchlich: Jahr Belsley (1980 gegen Neuausgabe 2005) und zugehörige DOI; Jahr Saltelli
  (2007/2008), Key erst nach Festlegen des Jahres in Zotero vergeben; Efron-DOI der Neuauflage
  nicht übernommen.
- Zuordnung ungeprüft: arXiv:2602.15422, 2503.05154, 2507.18220 zu den Bib-Keys der
  Yahagi-/Yonezawa-Gruppe; IJCAS-DOI zu `yahagiSparseIdentificationNonlinear2025`.
- Vega-Zambrano u. a. 2025: Aussagen „\sindyc{} auf Validierungsdaten am schlechtesten“ und
  „\sindyc{} mit linearer Bibliothek und Schwellwert null entspricht DMDc“ nur (S).
- E1 Befund 3.2 (Korda & Mezić), 3.6 (Konsistenzbedingungen der direkten Methode, Ljung 1999
  Kap. 13, Forssell & Ljung 1999) und 4.1 (Ljung Abschn. 13.4, Modussprung): am Original bzw. an
  den Daten prüfen.
- Raue u. a. 2009: Unterscheidung strukturell/praktisch nicht identifizierbar nur (S), am Original
  prüfen.
- Closed-Loop-Bias speziell für \sindyc: keine eigene Standardquelle gefunden.
- E2 Beitrag 3: SINDy-/Koopman-Arbeit mit Stellverstärkung, OL/CL und DoE als Bewertungsgrößen
  nicht gezielt gesucht.
- E3 Große Ideen: für ökonomisches MPC mit Derating-Grenze kein Literaturanker gefunden.
- Nicht durchsuchbar: CIMAC-Kongressbeiträge; Patente (US 8099222, US 9394858, nur Titel)
  bewusst nicht als Beleg verwendet.
- Ältere Arbeiten außerhalb des Zeitfensters, nur Titel (T): „Modeling and control of a
  single-phase marine cooling system“ (Control Eng. Pract., PII S0967066113001524); „Model Based
  Control of Intake Air Temperature and Humidity on the Test Bench“ (Energy Procedia,
  PII S1876610217336494).
- Aufwandsschätzungen in E3 sind grob und ohne Kenntnis des Codes der Arbeit.
