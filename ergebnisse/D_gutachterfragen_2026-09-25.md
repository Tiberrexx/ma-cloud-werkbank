# Auftrag D — Gutachterfragen vorab recherchiert (Cloud-Sitzung, 25.09.2026)

Grundlage: `auftraege/D_gutachterfragen.md`, `kontext/ch2.tex`, `kontext/ch3.tex` (Kopie vom
25.09.2026). Je Frage: Antwortskizze (Stichpunkte), 2–5 Quellen, Hinweis auf die Kapitelstelle
(nur Hinweis, keine Änderung). Zum Schluss BibTeX und „Offen / nicht belegt“.

## Vorbemerkung

- Kein Volltext gelesen (Verlagsseiten, arXiv, doi.org gesperrt). **Keine Seiten- oder
  Abschnittsangabe ist geprüft**; „Stelle“ heißt deshalb durchgehend „lokal nachschlagen“, außer
  wo ein Kapitel im Treffer sichtbar war oder ch3 selbst eine Stelle nennt („laut ch3“).
- Status: `[nur Abstract]` nur, wo der Abstract wörtlich gelesen wurde (über GitHub-Spiegel des
  arXiv-Feeds oder eine Autoren-Datei auf GitHub); sonst `[nur bibliografisch]`.
- Herkunftskennung je Angabe: (T) Treffertitel/URL, (G) GitHub-Datei, (S) nur
  Suchzusammenfassung. „Bib“ = Key schon in `Masterarbeit.bib` (in ch2/ch3 zitiert);
  A/B/E = BibTeX-Entwurf in den Ergebnissen dieser Aufträge.
- Formulierungen „eigene Einordnung“ oder „eigene Herleitung“ sind nicht aus Quellen belegt.

---

## Frage 1 — \sindy{} und \edmd{} als reduzierte Modelle, Verwandtschaft zu POD-Galerkin

**Antwortskizze**

- POD-Galerkin: Projektion der Erhaltungsgleichungen (PDE) auf wenige Moden; intrusiv, braucht
  die Gleichungen. Trunkierung verliert die Rückwirkung der abgeschnittenen Moden (Instabilität,
  falsche Amplituden); fehlt die Mittelwertkorrektur (Shift-Mode, Noack u. a. 2003, S), wird die
  Transiente schlecht wiedergegeben.
- \sindy: nichtintrusiv, lernt die Dynamik direkt in gewählten Koordinaten aus Daten.
  Sparsifizierung wählt **Terme**, nicht **Moden**. Auf POD-Koordinaten mit
  Energieerhaltung als Nebenbedingung entspricht das einem datengetriebenen Galerkin-Modell.
- \edmd: Galerkin-Projektion des Koopman-Operators auf den Raum der Observablen (ch3 Z. 303–307;
  `williamsDataDrivenApproximation2015`, `bruntonModernKoopmanTheory2022`); Trunkierung zeigt
  sich als Scheineigenwerte und Closure-Problem (ch3 Z. 308–312; `bruntonModernKoopmanTheory2022`,
  S. 285–286 laut ch3 Z. 312). Beide Keys in Bib, [nur bibliografisch].
- Was bei Sparsifizierung verloren geht: viele kleine Terme mit gemeinsamer Wirkung;
  Gültigkeit außerhalb des Trainingsbereichs; Stabilität nur mit Nebenbedingung.
- Wo \sindyc{} in dieser Arbeit **kein** ROM im klassischen Sinn ist: Es gibt kein
  hochdimensionales Vollmodell; der Zustand ist eine gemessene Temperatur, die Termformen kommen
  aus einer Bilanz eines konzentrierten Modells. Näher an sensorbasierten Modellen
  (Loiseau, Noack, Brunton 2018) als an POD-Galerkin.
- Eigene Einordnung: \sindy{} mit Polynombibliothek auf POD-Koordinaten entspricht Operator
  Inference plus Sparsität; nicht belegt. Abgrenzung: Die Shift-Mode ist ein zusätzlicher Modus
  im Galerkin-Modell; der Offset des Störgrößenbeobachters ist kein Modellterm, sondern wird aus
  dem Residuum geschätzt. Gemeinsam ist nur, dass beide ein Niveau verschieben.

**Quellen**

| Quelle | Aussage (Herkunft) | Status | Stelle |
|---|---|---|---|
| `loiseauConstrainedSparseGalerkin2018` (Bib) | Bibliothek aus den Erhaltungsgleichungen, harte Gleichungsnebenbedingungen (ch3 Z. 444–447); Anwendung auf POD-Koordinaten mit energieerhaltenden quadratischen Termen (S, nicht aus ch3), im Original prüfen | [nur bibliografisch] (Key in Bib, Metadaten nicht neu geprüft) | lokal |
| Loiseau, J.-C.; Noack, B. R.; Brunton, S. L. (2018): Sparse reduced-order modelling: sensor-based dynamics to full-state estimation. J. Fluid Mech. 844, 459–490 (G, T) | \sindy{} im Merkmalsraum der Sensoren; lokale lineare Abbildung auf das Feld genauer als modale Entwicklung gleicher Ordnung (S) | [nur bibliografisch] | lokal |
| Noack, B. R.; Afanasiev, K.; Morzyński, M.; Tadmor, G.; Thiele, F. (2003): A hierarchy of low-dimensional models for the transient and post-transient cylinder wake. J. Fluid Mech. 497, 335–363 (G) | POD-Galerkin-Modell braucht eine Shift-Mode als Mittelwertkorrektur, sonst schlechte Transiente (S) | [nur bibliografisch] | lokal |
| Peherstorfer, B.; Willcox, K. (2016): Data-driven operator inference for nonintrusive projection-based model reduction. CMAME 306, 196–215 (G) | reduzierte Operatoren per Least Squares aus Trajektorien, konvergieren bei genug Daten gegen die intrusiv projizierten (S) | [nur bibliografisch] | lokal |
| Callaham, J. L.; Brunton, S. L.; Loiseau, J.-C. (2022): On the role of nonlinear correlations in reduced-order modelling. J. Fluid Mech. 938, A1 (T, G) | Rückwirkung abgeschnittener Moden als Funktion der behaltenen Moden (Mannigfaltigkeit) nachbilden (S) | [nur bibliografisch] | lokal |

Ergänzend: Rowley & Dawson 2017 (Annu. Rev. Fluid Mech. 49, 387–417, G): Übersicht POD-Galerkin,
balanced truncation, DMD, Koopman für Analyse und Regelung (S) `[nur bibliografisch]`; Benner,
Gugercin, Willcox 2015 (SIAM Review 57(4), 483–531, G) als Übersicht projektionsbasierter
Reduktion `[nur bibliografisch]`; Holmes, Lumley, Berkooz, Rowley 2012 (2. Aufl., Cambridge UP, G)
als Lehrbuch `[nur bibliografisch]`; Narayanan, Sicoli, Mehta 2026 (arXiv:2604.24646, G) koppeln ein
\sindyc-Modell mit einem Kalman-Filter und vergleichen mit DMDc `[nur Abstract]`.

**Ort in den Kapiteln:** ch3 nach Z. 238 (Koopman-Übersicht) oder im \sindy-Abschnitt nach
Z. 450; die Abgrenzung „kein ROM im klassischen Sinn“ in ch3 Z. 1155–1159.

---

## Frage 2 — Wie begründen andere Arbeiten die Wahl der Bibliothek?

**Antwortskizze**

- Generische Polynombibliotheken: Spaltenzahl wächst kombinatorisch, Kollinearität,
  schwache Extrapolation (ch3 Z. 106–122, 148–152).
- Physikalisch begründete Bibliothek: weniger Spalten, interpretierbar, dimensionstreu;
  robuster bei verrauschten, unvollständigen Messdaten (Reinbold u. a. 2021).
- Gegenposition aus der Motorenanwendung: Physikalisch motivierte Basisfunktionen sind nicht
  immer verfügbar; deshalb Bagging über Bibliotheken (Yahagi u. a. 2025, arXiv) oder
  Optimierung der Bibliothek auf die Langzeitprognose (Yonezawa u. a. 2025).
- Nächste Analogie zur Arbeit: Physik liefert die Termform, Daten die Koeffizienten, Sparsität
  wählt aus (Sheikh u. a. 2024, LPV-Batteriemodell; kein \sindy{} im engeren Sinn).
- Lücke: kein Beispiel aus Prozess-, Motor- oder Thermoanwendung mit Messdaten gefunden, das die
  Bibliothekswahl begründet (Yahagi 2025 nur Simulation); erst recht keine \sindy-Arbeit mit
  Messdaten und Bibliothek der Form Temperaturdifferenz × Betriebspunktfaktor für Wärmeübertrager
  oder Motorthermik (auch Auftrag A, A3.3).

**Quellen**

| Quelle | Aussage (Herkunft) | Status | Stelle |
|---|---|---|---|
| Reinbold, P. A. K.; Kageorge, L. M.; Schatz, M. F.; Grigoriev, R. O. (2021): Robust learning from noisy, incomplete, high-dimensional experimental data via physically constrained symbolic regression. Nat. Commun. 12, 3219 (G, T) | rein datengetriebene Verfahren bisher nur bei einfachen, rauscharmen Systemen erfolgreich; mit physikalischen Prinzipien quantitatives Modell aus Experimentdaten (S) | [nur bibliografisch] | lokal |
| Yahagi, S.; Yonezawa, A.; Seto, H.; Yonezawa, H.; Kajiwara, I. (2025): arXiv:2503.05154 (G), Titel v1/v2 „Sparse identification of nonlinear dynamics with high accuracy and reliability under noisy conditions for applications to industrial systems“; ab v3 anderer Titel (EMEC-SINDy, s. BibTeX) | \sindyc{} am Diesel-Luftpfad mit Library-Bagging, begründet mit „physically motivated basis functions are not always available“ (Abstract, laut arXiv-Feed auf GitHub in v1 bis v3 gleich, G); Simulation | [nur Abstract] | Abstract (v1–v3) |
| `yonezawaSparseIdentificationNonlinear2025` (Bib; vermutlich arXiv:2507.18220, G) | Bibliotheksentwurf als Hauptproblem; SINDy-LOM optimiert Basisfunktionen auf rekursive Langzeitprognose; klassisches \sindy{} sichert nur Einschrittgenauigkeit | [nur Abstract] | – |
| Sheikh, A. M. A.; Donkers, M. C. F.; Bergveld, H. J. (2024), J. Energy Storage 95, 112581 (A) | LPV-Batteriemodell, Termstruktur nach Ersatzschaltbild, Auswahl mit LASSO, verbesserte Versuchsplanung (S) | [nur bibliografisch] | lokal |
| `bakarjiDimensionallyConsistentLearning2022` (A) | Dimensionsanalyse als Nebenbedingung, eine Variante auf \sindy-Basis (S) | [nur bibliografisch] | lokal |

Ergänzend: Lathourakis & Cicirello 2024 (Nonlinear Dyn. 112(13), 11237–11264, G): Vorwissen als
„Biases“ in einem RK4-\sindy `[nur bibliografisch]`; Abdullah & Christofides 2023 (Autoren, Jahr
S): „Data-based modeling and control of nonlinear process systems using sparse identification: An
overview of recent results“ (T), PII S0098135423001175 (T); Übersicht Sparse-Identifikation und
MPC in der Prozesstechnik, Zeitschrift nur aus PII abgeleitet `[nur bibliografisch]`; Li,
Larrañaga, Brunton, Fasel 2026 (arXiv:2607.15077, Tutorial, G) `[nur bibliografisch]`. Der
IJCAS-Artikel „Sparse Identification and Nonlinear Model Predictive Control for Diesel Engine Air
Path System“ (DOI 10.1007/s12555-024-0452-9, T) `[nur bibliografisch]`. Zuordnung von IJCAS-DOI
und arXiv:2503.05154 zu den Bib-Keys `yahagiSparseIdentificationNonlinear` und
`yahagiSparseIdentificationNonlinear2025` offen; ch3 Z. 1094–1102 beschreibt unter
`yahagiSparseIdentificationNonlinear2025` \sindy{} mit NMPC für Ladedruck und AGR, passend zum
IJCAS-Titel.

**Suchweg:** 8 Websuchen (Bhadriraju/Kwon, Wärmeübertrager/Thermik mit Messdaten, Motorluftpfad
mit Prüfstandsdaten, Gebäudethermik, Batterie, „physics-informed library“, Titelsuche IJCAS) und
GitHub-Codesuche nach Titeln und arXiv-IDs. Zu Gebäudethermik nichts Belastbares; OASIS-P
(`bhadrirajuOASISPOperableAdaptive2021`, Bib) nur als Titeltreffer.

**Ort in den Kapiteln:** ch3 Z. 436–450 (Wahl der Bibliothek); Gegenposition Yahagi/Yonezawa in
ch3 Z. 985–996.

---

## Frage 3 — Identifikation aus Betriebsdaten unter Regelung (2018–2026)

**Antwortskizze**

- Allgemein: direkte Methode verzerrt, wenn das Störmodell nicht passt (ch3
  `eq.grundlagen.cl.bias`); das gilt für jedes in den Parametern lineare Modell, also auch
  \sindyc{} und \edmdc{} (ch3 Z. 840–843).
- Koopman-Seite: Bei bekanntem Regler werden Kreis- und Streckenmodell gemeinsam identifiziert
  (Dahdah & Forbes 2024, Bib; Abstract, G; ch3 Z. 752–754). Sollwert und exogene Vorsteuerung als
  Eingang liefern zunächst das Modell des geschlossenen Kreises; die Strecke und damit der
  Ventil-Gain folgen nur über den bekannten Regler, dessen Matrizen fest vorgegeben sind (S).
- Bias-Aussage (Reglerausgang als exogener Eingang korreliert mit dem Rauschen, Bias steigt;
  Sollwert oder Vorsteuerung als Eingang senken ihn, sofern diese Signale exogen sind): nur
  Suchzusammenfassung (S), nicht im Abstract; im Volltext prüfen.
- Übertrag auf die Arbeit: Der Serienregler ist ein PI-Regler mit Kennfeld-Vorsteuerung und
  Anti-Windup (ch2 Z. 1046–1059), an den Stellgrenzen also nichtlinear; ob die Voraussetzung
  dort trägt, lokal prüfen (indirekte Methode: linearer, exakt bekannter Regler, ch3 Z. 681).
  Die Vorsteuerung hängt von der Last ab (ch2 Z. 1054–1055); dann greift das Rangargument aus
  ch3 Z. 877–884, Stellgröße und Regressor werden kollinear, die Konfundierung bleibt.
- Neuer Befund (Wu 2026, Preprint): \edmdc{} kann das Verhalten im Regelkreis gut vorhersagen
  und trotzdem nicht identifizieren, wie ein **neuer** Stelleingriff wirkt. Kriterium ist ein
  „Interventionszertifikat“ (Schur-Komplement der Informationsmatrix); mit Dither wächst die
  Information quadratisch mit der Amplitude. Direkt die Frage nach dem Ventil-Gain aus
  geregelten Daten.
- Stationäre Sensitivität aus geregelten Daten: Bias abhängig von Closed-Loop-Sensitivität und
  Rausch-Signal-Verhältnis (Løvland u. a. 2025, Bib).
- Schema „Fit auf Open-Loop-Daten, geregelte Daten nur zur Validierung“ mit industriellen
  Messdaten: **nicht gefunden**. Nutzt die Arbeit dieses Schema, muss sie es selbst begründen,
  z. B. über die klassische Closed-Loop-Theorie (Forssell & Ljung 1999, Ljung 1999, Bib). ch3
  kündigt an, am Prüfstand zu prüfen, welche Eigenschaften (Niveau, Dynamik, Stellwirkung) sich
  aus Regelkreisdaten gegen die bekannte Wahrheit zurückgewinnen lassen (ch3 Z. 909–925). Das stützt das Schema
  indirekt, ist aber keine direkte Prüfung von „Fit auf Open-Loop-Daten, Validierung auf
  Closed-Loop-Daten“.
- Eine \sindy-spezifische Analyse des Closed-Loop-Bias wurde nicht gefunden.

**Quellen**

| Quelle | Aussage (Herkunft) | Status | Stelle |
|---|---|---|---|
| `dahdahClosedloopKoopmanOperator2024` (Bib; arXiv:2303.15318) | Kreis und Strecke gemeinsam bei bekanntem Regler (G, Abstract im GitHub-Spiegel Luvata/arxive); Bias-Aussage (S) | [nur Abstract] (Key in Bib), Bias-Aussage (S) | lokal |
| Wu, Y. (2026): Control-Channel Informativity for Koopman EDMDc under Behavior-Policy Data. arXiv:2605.17966 (G) | s. oben | [nur Abstract], Preprint | – |
| `lovlandClosedloopIdentificationChallenge2025` (Bib; arXiv:2509.01188, G) | Bias stationärer Sensitivitätsmodelle aus Closed-Loop-Daten in der Feedback-Optimierung; Divergenz, wenn eine Matrix aus Sensitivität und Rausch-Signal-Verhältnis negativ definit ist | [nur Abstract] | Theorem 1, Gl. (26) nur im Kommentar ch3 Z. 667, dort zur Aussage Grenzwert −K⁻¹ (Z. 668–671); \cite ohne Stellenangabe; Zuordnung zur Aussage dieser Zeile lokal prüfen |
| `forssellClosedloopIdenticationRevisited1999`, `ljungSystemIdentificationTheory1999` (Bib) | Konsistenzbedingungen der direkten Methode | [nur bibliografisch] (Key in Bib, Metadaten nicht neu geprüft) | Ljung 1999: Kap. 8 (Bias der LS-Schätzung), Abschn. 13.4 (Informativität unter Rückführung), laut ch3 Z. 822/871; Forssell & Ljung: lokal |
| `strasserOverviewKoopmanbasedControl2026` (Bib; arXiv:2509.02839, G) | Übersicht Koopman-Regelung von Fehlerschranken bis zu Closed-Loop-Garantien (Titelebene) | [nur bibliografisch] (Key in Bib, Metadaten nicht neu geprüft) | lokal |

Ergänzend (Autoren nicht gefunden): Kapitel „Control Reconfiguration of CPS via Online
Identification Using Sparse Regression (SINDYc)“, ML4CPS 2023, DOI 10.1007/978-3-031-47062-2_6
(T): Störsignal im Kreis, Online-\sindyc{} (S) `[nur bibliografisch]`. „Real-time adaptive
sparse-identification-based predictive control of nonlinear processes“, Chem. Eng. Res. Des.
(PII S0263876223004483, T): Online-Update in LMPC (S) `[nur bibliografisch]`. Grasev 2026
(arXiv:2604.01730, G): Koopman-MPC mit Störgrößenbeobachter am Turbofan, Simulationsdaten
`[nur Abstract]`.

**Suchweg:** 7 Websuchen („closed-loop identification“ SINDy feedback bias; Koopman EDMD
closed-loop data bias; Titelsuche Wu; SINDYc unter Regelung in Industrieanlagen; „routine
operating data“; open-loop fit / closed-loop validation; instrumental variables bias
feedback) und GitHub-Codesuche nach arXiv-IDs.

**Ort in den Kapiteln:** ch3 Z. 625–628: „zu erwarten“ durch Verweis auf ch3 Z. 633–637
(`bruntonSparseIdentificationNonlinear2016`, S. 713 laut ch3: Konditionierung unter Rückführung)
und Z. 840–843 (Bias-Gleichung gilt für \sindyc) stützen; eine \sindy-spezifische Bias-Analyse
fehlt weiterhin (s. Offen). ch3 Z. 749–754 (Koopman-Seite, Wu 2026 ergänzen); ch3 Z. 922–925
(Rückgewinnbarkeit aus Regelkreisdaten als indirekte Stütze des Schemas).

---

## Frage 4 — Offsetfreies MPC und Beobachter; Störgrößenbeobachter, Kalman-Filter, exponentielle Glättung

**Antwortskizze**

- Offsetfreies MPC: Ausgangsstörung als Integrator, erweitertes Modell, Beobachter schätzt
  Zustand und Störung, Zielwertberechnung verschiebt die Ruhelage. Bedingungen:
  Detektierbarkeit, Zahl der Störzustände gleich Zahl der Ausgänge
  (`muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003`,
  `maederLinearOffsetfreeModel2009`, Bib).
- Varianten: Störmodell mit Beobachter, Zustandsstörbeobachter, Geschwindigkeitsform; die
  Geschwindigkeitsform ist einem bestimmten Störmodell mit Beobachter äquivalent
  (Pannocchia, Gabiccini, Artoni 2015); einfacherer Aufbau mit Beobachter nur für den
  Prozesszustand (Tatjewski 2014).
- **Kalman ↔ exponentielle Glättung (eigene Herleitung, sympy-geprüft):** Störung als Random
  Walk $d^{\mathrm{off}}_k=d^{\mathrm{off}}_{k-1}+w_k$, Residuum
  $z_k=y_k-C\hat x_k=d^{\mathrm{off}}_k+v_k$ mit Varianzen $q$, $r$ (Notation wie B2.3; $y_k$
  steht für \Tout). Stationärer Kalman-Filter:
  $\hat d^{\mathrm{off}}_k=\hat d^{\mathrm{off}}_{k-1}+L\,(z_k-\hat d^{\mathrm{off}}_{k-1})=(1-L)\,\hat d^{\mathrm{off}}_{k-1}+L\,z_k$,
  also exponentielle Glättung mit $\alpha=L$. Die Verstärkung folgt aus $L^2/(1-L)=q/r$,
  $L=\bigl(\sqrt{q(q+4r)}-q\bigr)/(2r)$; $q/r\to0$ ergibt $L\to0$ (starke Glättung),
  $q/r\to\infty$ ergibt $L\to1$.
- Gilt exakt nur, wenn das Residuum wirklich $d^{\mathrm{off}}_k+v_k$ mit weißem $v_k$ ist:
  Ausgangsstörmodell, Prozessmodell als Parallelmodell, dessen Zustand der Beobachter nicht
  korrigiert ($Q_x=0$). Mit $Q_x>0$ oder mit einem Eingangsstörmodell korrigiert der Beobachter
  auch $\hat x$ ($L_x\neq0$), $L_d$ weicht von der Formel ab, und $Q_x$, $Q_d$, $R$ sind getrennte
  Stellschrauben (eigene Rechnung). Läuft das Modell ab dem gemessenen \Tout{}
  (Reihen-Parallel-Form), enthält das Residuum farbiges MA(1)-Rauschen, und die Störung geht nur
  skaliert ein (Modell erster Ordnung mit Eigenkoeffizient $a$:
  $z_k=(1-a)\,d^{\mathrm{off}}_{k-1}+w_k+v_k-a\,v_{k-1}$, eigene Rechnung); die exponentielle
  Glättung ist dann nur eine Näherung.
- Optimalität der exponentiellen Glättung für genau dieses Modell: Muth 1960 (S); Zustandsraum-
  Sicht: Harvey 1989 (Local-Level-Modell), Hyndman u. a. 2008. Vor Übernahme im Original prüfen.
- Abstimmung: Bias-Varianz-Zielkonflikt eines Kalman-Störbeobachters bei unvollständigem
  Störmodell (Li u. a. 2024, Preprint arXiv:2410.05061; laut Treffer 2026 in Automatica
  erschienen, PII S0005109826000907).
- Bezug Erstgutachter: Unter diesen Annahmen ist $q/r$ die einzige Stellschraube des
  Störgrößenbeobachters und entspricht direkt dem Glättungsfaktor.

**Quellen**

| Quelle | Aussage (Herkunft) | Status | Stelle |
|---|---|---|---|
| `muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003`, `maederLinearOffsetfreeModel2009` (Bib, ch2 Z. 1086–1088) | Bedingungen offsetfreier MPC: Detektierbarkeit, Zahl der Störzustände gleich Zahl der Ausgänge (Inhalt ungeprüft; ch2 Z. 1082–1088 nennt nur Störmodell als Zustand und Beobachter) | [nur bibliografisch] (Keys in Bib, Metadaten nicht neu geprüft) | lokal |
| Muth, J. F. (1960): Optimal properties of exponentially weighted forecasts. JASA 55(290), 299–306 (G) | exponentielle Glättung ist MSE-optimal für Random Walk plus Rauschen (S, aus einer Sekundär-PDF) | [nur bibliografisch] | lokal |
| Harvey, A. C. (1989): Forecasting, Structural Time Series Models and the Kalman Filter. Cambridge UP (G) | Local-Level-Modell und Kalman-Filter (Titelebene) | [nur bibliografisch] | lokal |
| Pannocchia, G.; Gabiccini, M.; Artoni, A. (2015): Offset-free MPC explained: novelties, subtleties, and applications. IFAC-PapersOnLine 48(23), 342–351 (G) | Geschwindigkeitsform äquivalent zu Störmodell mit Beobachter; Fehlannahmen, die Offsetfreiheit verhindern | [nur Abstract] (Autoren-Datei auf GitHub) | lokal |
| Tatjewski, P. (2014): Disturbance modeling and state estimation for offset-free predictive control with state-space process models. Int. J. Appl. Math. Comput. Sci. 24(2), 313–323 (T, G) | Beobachter nur für den Prozesszustand; weniger restriktive Bedingungen; auch Geschwindigkeitsform | [nur Abstract] (Seitenkopie auf GitHub) | lokal |

Ergänzend: Pannocchia 2015 „Offset-Free Tracking MPC: A Tutorial Review and Comparison of
Different Formulations“ (ECC 2015, Linz, 527–532, G): Vergleich der Formulierungen (Titelebene)
`[nur bibliografisch]`; Li, Shi, Lyu, Tang, Shi 2024 (arXiv:2410.05061, G; Zeitschriftenfassung
laut ScienceDirect-Treffer, T: PII S0005109826000907, Automatica 2026 aus PII abgeleitet)
`[nur Abstract]`: Kalman-Störbeobachter optimal bei bekanntem Störmodell, sonst
Bias-Varianz-Zielkonflikt; Hyndman, Koehler, Ord, Snyder 2008 (Springer, G): Glättung im
Zustandsraum `[nur bibliografisch]`; ein J.-Process-Control-Artikel 2026 zu offsetfreiem MPC mit
abstimmbarer Störschätzdynamik (PII S095915242600020X, Autoren unbekannt) `[nur bibliografisch]`.

**Ort in den Kapiteln:** ch2 Z. 1082–1088 (offsetfreie Erweiterung, bisher ein Satz; Baustein in
Auftrag B, B2.3); Methodik-Abschnitt `sec.methodik.mpc`.

---

## Frage 5 — Modellwahl für MPC jenseits der Vorhersagegüte

**Antwortskizze**

- Identifikation für die Regelung: Modellfehler müssen nicht klein, sondern für den Reglerentwurf
  passend sein; Modellbildung und Reglerentwurf sind iterativ (Skelton 1989, S). Schwerpunkt
  verschob sich zu regelungsorientierten Unsicherheitsmengen und Versuchsplanung (Gevers 2005, S;
  Hjalmarsson 2005, S).
- Verstärkung vor Einzelgenauigkeit: Richtung der Verstärkung (schwache Richtungen) beeinflusst
  die Regelgüte stärker als die Genauigkeit einzelner Elemente (Li & Lee 1996; Koung & MacGregor
  1994; Benchmark Wärmeübertrager bei Jacobsen & Skogestad 1994; alle S). Für die integrale
  Regelbarkeit gibt es Bedingungen an die identifizierte Verstärkung (Darby & Nikolaou 2009,
  Titelebene); ob daraus ein Vorzeichenkriterium folgt, im Original prüfen.
- Für die SISO-Strecke der Arbeit: Betrag und Vorzeichen des Ventil-Gains; bei trägen Strecken
  reagiert $K=b/(1-a)$ stark auf Fehler im Eigenkoeffizienten (Auftrag B, B2.4). Deshalb ist
  „kleinerer RMSE“ kein Beleg für „besserer Regler“.
- Anwendungsorientierte Versuchsplanung für MPC: Ebadat u. a. 2013 (Preprint, Inhalt ungeprüft).

**Quellen**

| Quelle | Aussage (Herkunft) | Status | Stelle |
|---|---|---|---|
| Skelton, R. E. (1989): Model error concepts in control design. Int. J. Control 49(5), 1725–1753 (G, T) | s. oben (S) | [nur bibliografisch] | lokal |
| Gevers, M. (2005): Identification for control: From the early achievements to the revival of experiment design. Eur. J. Control 11(4–5), 335–352 (G) | s. oben (S) | [nur bibliografisch] | lokal |
| Hjalmarsson, H. (2005): From experiment design to closed-loop control. Automatica 41(3), 393–438 (G) | Verbindung Identifikation–Regelung; Regler niedriger Komplexität aus statistischer Sicht (S) | [nur bibliografisch] | lokal |
| Li, W.; Lee, J. H. (1996, S): Control relevant identification of ill-conditioned systems: Estimation of gain directionality (T). Comput. Chem. Eng. 20, 1023–1042 (S) | Gain-Richtung wichtiger als Einzelelemente (S) | [nur bibliografisch] | lokal |
| Darby, M. L.; Nikolaou, M. (2009): Multivariable system identification for integral controllability. Automatica 45(10), 2194–2204 (G) | Identifikation mit Blick auf integrale Regelbarkeit (Titelebene) | [nur bibliografisch] | lokal |

Ergänzend: Koung, C. W.; MacGregor, J. F. (1994, S): Identification for robust multivariable
control: The design of experiments (T). Automatica 30(10), 1541–1554 (S); PII 0005109894900949 (T)
`[nur bibliografisch]`; Jacobsen & Skogestad 1994 „Identification of ill-conditioned plants – a
benchmark problem“ (DOI 10.1007/BFb0036269, T) `[nur bibliografisch]`; Van den Hof & Schrama 1995
„Identification and Control – Closed-loop Issues“ (Automatica 31(12), 1751–1770, S)
`[nur bibliografisch]`; Misra u. a. 2017 (Processes 5(3), 42, G) `[nur bibliografisch]`;
Ebadat u. a. 2013 (arXiv:1303.5199, G) `[nur bibliografisch]`;
`bomboisLeastCostlyIdentification2006`, `geversIdentificationInformationMatrix2009` (Bib)
`[nur bibliografisch]`.

**Ort in den Kapiteln:** ch3 Einordnung (Z. 1122ff.) als Begründung der Bewertungsgrößen
OL/CL/DoE/Gain; ch3 Z. 907–925 (Dreiteilung Niveau/Dynamik/Stellwirkung).

---

## Frage 6 — Fairer Vergleich datengetriebener Modellklassen

**Antwortskizze**

- Gleiche Daten, gleiche Information (gleiche Eingänge, gleiche Kenntnis künftiger Störgrößen),
  gleiches Bewertungsmaß (Freilauf und Horizontfehler, nicht nur Einschritt).
- Hyperparameter (Schwellwert, Bibliothek, Ordnung, Liftung) nur auf Auswahldaten; Testdaten
  unberührt. Sonst ist die Überanpassung der Auswahl oft ähnlich groß wie die
  Leistungsunterschiede zwischen Lernverfahren (Cawley & Talbot 2010, Abstract); der CV-Fehler
  des per CV abgestimmten Verfahrens ist verzerrt (Varma & Simon 2006, S).
- Gepaarter Vergleich auf denselben Testabschnitten; Fehler sind seriell korreliert, daher
  Test nach Diebold & Mariano 1995 oder Block-Bootstrap (Künsch 1989). Diebold 2015 (Inhalt
  ungeprüft): Der Test vergleicht Prognosen, nicht Modelle.
- Neuronale Netze einordnen: Feedforward- und Cascadeforward-Netze mit verzögerten Ein- und
  Ausgängen als Regressoren sind NARX-Modelle, LSTM-Netze ein Beispiel nichtlinearer
  Zustandsraummodelle (Ljung u. a. 2020, S). Die in ch3 ausgeschlossenen RNN/LSTM/NeuralODE sind
  damit keine NARX-Modelle (RNN, NeuralODE: eigene Einordnung). Nur der Vergleich mit einem
  NARX-Netz bliebe in der NARX-Familie (Bezug Zweitgutachter).
- Leitfaden und Benchmarks: Schoukens & Ljung 2019; Schoukens & Noël 2017; für \sindy-Solver
  Kaptanoglu u. a. 2023 (A).

**Quellen**

| Quelle | Aussage (Herkunft) | Status | Stelle |
|---|---|---|---|
| Schoukens, J.; Ljung, L. (2019): Nonlinear System Identification: A User-Oriented Road Map. IEEE Control Syst. Mag. 39(6), 28–99 (G) | Leitfaden von Versuchsplanung bis Validierung (S) | [nur bibliografisch] | lokal |
| Ljung, L.; Andersson, C.; Tiels, K.; Schön, T. B. (2020): Deep learning and system identification. IFAC-PapersOnLine 53(2), 1175–1181 (G) | Feedforward-/Cascadeforward-Netze sind NARX-Modelle; LSTM als Beispiel nichtlinearer Zustandsraummodelle (S) | [nur bibliografisch] | lokal |
| Cawley, G. C.; Talbot, N. L. C. (2010): On Over-fitting in Model Selection and Subsequent Selection Bias in Performance Evaluation. JMLR 11(70), 2079–2107 (G, T) | s. oben | [nur Abstract] (JMLR-Repo auf GitHub) | – |
| Varma, S.; Simon, R. (2006): Bias in error estimation when using cross-validation for model selection. BMC Bioinformatics 7, 91 (G) | CV-Fehler des per CV optimierten Verfahrens deutlich verzerrt (S) | [nur bibliografisch] | lokal |
| Diebold, F. X.; Mariano, R. S. (1995): Comparing Predictive Accuracy. J. Bus. Econ. Stat. 13(3), 253–263 (G, T) | Test gleicher Prognosegüte, beliebige Verlustfunktion, serielle Korrelation erlaubt (S) | [nur bibliografisch] | lokal |

Ergänzend: Diebold 2015 (JBES 33(1), G) `[nur bibliografisch]`; Schoukens & Noël 2017
(IFAC-PapersOnLine 50(1), 448–453, G) `[nur bibliografisch]`; Künsch 1989 und Efron & Tibshirani
1993 (BibTeX in E) `[nur bibliografisch]`; Narayanan u. a. 2026 (Frage 1) als
Beispiel eines Vergleichs innerhalb und außerhalb der Trainingsbedingungen `[nur Abstract]`.

**Ort in den Kapiteln:** ch3 Z. 1161–1174 (Ausschluss neuronaler Netze: ein NARX-Netz als
naheliegender, nicht aufgenommener Kandidat; für RNN/LSTM/NeuralODE trägt das NARX-Argument nicht);
ch3 Z. 520–526 (Modellauswahl); Methodik-Abschnitt `ssec.meth.gates`.

---

## BibTeX-Entwürfe D

Nur (T)/(G)-Felder im Eintrag, (S) als `% ungeprüft:` darüber. Schon in der Bib (keine neuen
Einträge): `loiseauConstrainedSparseGalerkin2018`, `dahdahClosedloopKoopmanOperator2024`,
`lovlandClosedloopIdentificationChallenge2025`, `strasserOverviewKoopmanbasedControl2026`,
`yahagiSparseIdentificationNonlinear2025`, `yahagiSparseIdentificationNonlinear` (ch3 Z. 986,
ohne Jahr, Inhalt ungeprüft), `yonezawaSparseIdentificationNonlinear2025`,
`yahagiGeneralizedBilinearKoopman2026`, `forssellClosedloopIdenticationRevisited1999`,
`ljungSystemIdentificationTheory1999`, `muskeDisturbanceModelingOffsetfree2002`,
`pannocchiaDisturbanceModelsOffsetfree2003`, `maederLinearOffsetfreeModel2009`,
`bomboisLeastCostlyIdentification2006`, `geversIdentificationInformationMatrix2009`,
`bhadrirajuOASISPOperableAdaptive2021`. In A: Sheikh, Bakarji, Kaptanoglu 2023. In E: Künsch,
Efron & Tibshirani, Quade, Billings.

```bibtex
@article{loiseauSparseReducedorderModelling2018,
  author    = {Loiseau, Jean-Christophe and Noack, Bernd R. and Brunton, Steven L.},
  title     = {Sparse reduced-order modelling: sensor-based dynamics to full-state estimation},
  journal   = {Journal of Fluid Mechanics},
  volume    = {844},
  pages     = {459--490},
  year      = {2018},
  doi       = {10.1017/jfm.2018.147}
}

@article{noackHierarchyLowdimensionalModels2003,
  author    = {Noack, Bernd R. and Afanasiev, Konstantin and Morzy{\'n}ski, Marek and Tadmor, Gilead and Thiele, Frank},
  title     = {A hierarchy of low-dimensional models for the transient and post-transient cylinder wake},
  journal   = {Journal of Fluid Mechanics},
  volume    = {497},
  pages     = {335--363},
  year      = {2003},
  doi       = {10.1017/S0022112003006694}
}

@article{rowleyModelReductionFlow2017,
  author    = {Rowley, Clarence W. and Dawson, Scott T. M.},
  title     = {Model Reduction for Flow Analysis and Control},
  journal   = {Annual Review of Fluid Mechanics},
  volume    = {49},
  pages     = {387--417},
  year      = {2017},
  doi       = {10.1146/annurev-fluid-010816-060042}
}

@article{peherstorferDatadrivenOperatorInference2016,
  author    = {Peherstorfer, Benjamin and Willcox, Karen},
  title     = {Data-driven operator inference for nonintrusive projection-based model reduction},
  journal   = {Computer Methods in Applied Mechanics and Engineering},
  volume    = {306},
  pages     = {196--215},
  year      = {2016},
  doi       = {10.1016/j.cma.2016.03.025}
}

% ungeprüft: doi = {10.1017/jfm.2021.994} (nur schwache GitHub-Quelle)
@article{callahamRoleNonlinearCorrelations2022,
  author    = {Callaham, Jared L. and Brunton, Steven L. and Loiseau, Jean-Christophe},
  title     = {On the role of nonlinear correlations in reduced-order modelling},
  journal   = {Journal of Fluid Mechanics},
  volume    = {938},
  pages     = {A1},
  year      = {2022}
}

@article{bennerSurveyProjectionbasedModel2015,
  author    = {Benner, Peter and Gugercin, Serkan and Willcox, Karen},
  title     = {A survey of projection-based model reduction methods for parametric dynamical systems},
  journal   = {SIAM Review},
  volume    = {57},
  number    = {4},
  pages     = {483--531},
  year      = {2015},
  doi       = {10.1137/130932715}
}

% Seitenzahl widersprüchlich (386/402), weggelassen
@book{holmesTurbulenceCoherentStructures2012,
  author    = {Holmes, Philip and Lumley, John L. and Berkooz, Gahl and Rowley, Clarence W.},
  title     = {Turbulence, Coherent Structures, Dynamical Systems and Symmetry},
  edition   = {2},
  series    = {Cambridge Monographs on Mechanics},
  publisher = {Cambridge University Press},
  address   = {Cambridge},
  year      = {2012},
  isbn      = {978-1-107-00825-0},
  doi       = {10.1017/CBO9780511919701}
}

@misc{narayananReducedorderDataAssimilation2026,
  author        = {Narayanan, Sriram and Sicoli, Daniele and Mehta, Piyush},
  title         = {Reduced-Order Data Assimilation for Thermospheric Density Using Physics-informed {SINDyc} Models},
  year          = {2026},
  eprint        = {2604.24646},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

@article{reinboldRobustLearningNoisy2021,
  author    = {Reinbold, Patrick A. K. and Kageorge, Logan M. and Schatz, Michael F. and Grigoriev, Roman O.},
  title     = {Robust learning from noisy, incomplete, high-dimensional experimental data via physically constrained symbolic regression},
  journal   = {Nature Communications},
  volume    = {12},
  pages     = {3219},
  year      = {2021},
  doi       = {10.1038/s41467-021-23479-0}
}

% Titel v1/v2; ab v3 (arXiv-Feed, GitHub ehijano/rss_fetch, rss_data/cs.SY/2025-10-20_cs.SY.xml, G):
% "Sparse Identification of Nonlinear Dynamics Enhanced by Ensemble Learning, Multi-Step Prediction
% Evaluation, Elite Strategy, and Classification Techniques for Applications to Industrial Systems" (EMEC-SINDy)
% NICHT importieren vor Abgleich mit yahagiSparseIdentificationNonlinear (ohne Jahr, ch3 Z. 986) und
% yahagiSparseIdentificationNonlinear2025 (ch3 Z. 987); evtl. schon in der Bib. Ist
% yahagiSparseIdentificationNonlinear = arXiv:2503.05154, diesen Eintrag streichen und den vorhandenen
% Key verwenden; sonst Suffix a nur als Platzhalter wegen Kollision mit yahagiSparseIdentificationNonlinear2025
@misc{yahagiSparseIdentificationNonlinear2025a,
  author        = {Yahagi, Shuichi and Yonezawa, Ansei and Seto, Hiroki and Yonezawa, Heisei and Kajiwara, Itsuro},
  title         = {Sparse identification of nonlinear dynamics with high accuracy and reliability under noisy conditions for applications to industrial systems},
  year          = {2025},
  eprint        = {2503.05154v1},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% ungeprüft: Vornamen (vermutlich Christos Lathourakis, Alice Cicirello)
@article{lathourakisPhysicsEnhancedSparse2024,
  author    = {Lathourakis and Cicirello},
  title     = {Physics enhanced sparse identification of dynamical systems with discontinuous nonlinearities},
  journal   = {Nonlinear Dynamics},
  volume    = {112},
  number    = {13},
  pages     = {11237--11264},
  year      = {2024},
  doi       = {10.1007/s11071-024-09652-2}
}

% ungeprüft: author = {Abdullah, Fahim and Christofides, Panagiotis D.};
%            journal = {Computers \& Chemical Engineering}; year = {2023} (aus PII abgeleitet); DOI nicht gesehen
@article{abdullahDatabasedModelingControl2023,
  title     = {Data-based modeling and control of nonlinear process systems using sparse identification: An overview of recent results},
  url       = {https://www.sciencedirect.com/science/article/abs/pii/S0098135423001175}
}

@misc{liIntroductionSparseIdentification2026,
  author        = {Li, Yao Cheng and Larra{\~n}aga, Ana and Brunton, Steven L. and Fasel, Urban},
  title         = {An Introduction to Sparse Identification of Nonlinear Dynamics for Engineering Applications},
  year          = {2026},
  eprint        = {2607.15077},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

@misc{wuControlchannelInformativityKoopman2026,
  author        = {Wu, Yue},
  title         = {Control-Channel Informativity for Koopman {EDMDc} under Behavior-Policy Data},
  year          = {2026},
  eprint        = {2605.17966},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% Titel v1 abweichend (vgl. Offen / nicht belegt, Titelvarianten)
@misc{grasevKoopmanbasedNonlinearIdentification2026,
  author        = {Grasev, David},
  title         = {Koopman-Based Nonlinear Identification and Model Predictive Control of a Turbofan Engine},
  year          = {2026},
  eprint        = {2604.01730},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

@article{muthOptimalPropertiesExponentially1960,
  author    = {Muth, John F.},
  title     = {Optimal properties of exponentially weighted forecasts},
  journal   = {Journal of the American Statistical Association},
  volume    = {55},
  number    = {290},
  pages     = {299--306},
  year      = {1960},
  doi       = {10.1080/01621459.1960.10482064}
}

% ISBN vermutlich Taschenbuchausgabe
@book{harveyForecastingStructuralTime1989,
  author    = {Harvey, Andrew C.},
  title     = {Forecasting, Structural Time Series Models and the Kalman Filter},
  publisher = {Cambridge University Press},
  year      = {1989},
  isbn      = {978-0521405737},
  doi       = {10.1017/CBO9781107049994}
}

% ungeprüft: doi = {10.1016/j.ifacol.2015.11.304}; Vornamen der Koautoren
@article{pannocchiaOffsetfreeMPCExplained2015,
  author    = {Pannocchia, G. and Gabiccini, M. and Artoni, A.},
  title     = {Offset-free {MPC} explained: novelties, subtleties, and applications},
  journal   = {IFAC-PapersOnLine},
  volume    = {48},
  number    = {23},
  pages     = {342--351},
  year      = {2015}
}

% ersetzt den schwächeren Entwurf aus Auftrag B (dort nur Titel und URL)
@inproceedings{pannocchiaOffsetfreeTrackingMPC2015,
  author    = {Pannocchia, Gabriele},
  title     = {Offset-Free Tracking {MPC}: A Tutorial Review and Comparison of Different Formulations},
  booktitle = {2015 European Control Conference (ECC)},
  address   = {Linz, Austria},
  publisher = {IEEE},
  pages     = {527--532},
  year      = {2015},
  isbn      = {978-3-9524269-3-7},
  doi       = {10.1109/ECC.2015.7330597}
}

@article{tatjewskiDisturbanceModelingState2014,
  author    = {Tatjewski, Piotr},
  title     = {Disturbance modeling and state estimation for offset-free predictive control with state-space process models},
  journal   = {International Journal of Applied Mathematics and Computer Science},
  volume    = {24},
  number    = {2},
  pages     = {313--323},
  year      = {2014},
  doi       = {10.2478/amcs-2014-0023}
}

% Zeitschriftenfassung (T): https://www.sciencedirect.com/science/article/abs/pii/S0005109826000907
% ungeprüft: journal = {Automatica}; year = {2026} (aus PII abgeleitet, laut Suchzusammenfassung Mai 2026);
%            volume, pages, doi fehlen
% vor Übernahme durch einen article-Eintrag liBiasvarianceTradeoffKalman2026 mit geprüften Metadaten
% ersetzen, Preprint nur als eprint
@misc{liBiasvarianceTradeoffKalman2024,
  author        = {Li, Shilei and Shi, Dawei and Lyu, Xiaoxu and Tang, Jiawei and Shi, Ling},
  title         = {Bias-Variance Trade-off in Kalman Filter-Based Disturbance Observers},
  year          = {2024},
  eprint        = {2410.05061},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% ungeprüft: Vornamen
@book{hyndmanForecastingExponentialSmoothing2008,
  author    = {Hyndman, R. J. and Koehler, A. B. and Ord, J. K. and Snyder, R. D.},
  title     = {Forecasting with Exponential Smoothing: The State Space Approach},
  publisher = {Springer},
  year      = {2008},
  doi       = {10.1007/978-3-540-71918-2}
}

@article{skeltonModelErrorConcepts1989,
  author    = {Skelton, R. E.},
  title     = {Model error concepts in control design},
  journal   = {International Journal of Control},
  volume    = {49},
  number    = {5},
  pages     = {1725--1753},
  year      = {1989},
  doi       = {10.1080/00207178908559735}
}

@article{geversIdentificationControlEarly2005,
  author    = {Gevers, Michel},
  title     = {Identification for control: From the early achievements to the revival of experiment design},
  journal   = {European Journal of Control},
  volume    = {11},
  number    = {4-5},
  pages     = {335--352},
  year      = {2005},
  doi       = {10.3166/ejc.11.335-352}
}

% ungeprüft: doi = {10.1016/j.automatica.2004.11.021}
@article{hjalmarssonExperimentDesignClosedloop2005,
  author    = {Hjalmarsson, H{\aa}kan},
  title     = {From experiment design to closed-loop control},
  journal   = {Automatica},
  volume    = {41},
  number    = {3},
  pages     = {393--438},
  year      = {2005}
}

% ungeprüft: author = {Li, W. and Lee, J. H.}; journal = {Computers \& Chemical Engineering};
%            volume = {20}; pages = {1023--1042}; year = {1996}
@article{liControlRelevantIdentification1996,
  title     = {Control relevant identification of ill-conditioned systems: Estimation of gain directionality},
  url       = {https://www.sciencedirect.com/science/article/pii/0098135495002146}
}

@article{darbyMultivariableSystemIdentification2009,
  author    = {Darby, M. L. and Nikolaou, M.},
  title     = {Multivariable system identification for integral controllability},
  journal   = {Automatica},
  volume    = {45},
  number    = {10},
  pages     = {2194--2204},
  year      = {2009}
}

% ungeprüft: author = {Jacobsen, E. W. and Skogestad, S.}; year = {1994}
@incollection{jacobsenIdentificationIllconditionedPlants1994,
  title     = {Identification of ill-conditioned plants -- A benchmark problem},
  doi       = {10.1007/BFb0036269}
}

@article{schoukensNonlinearSystemIdentification2019,
  author    = {Schoukens, Johan and Ljung, Lennart},
  title     = {Nonlinear System Identification: A User-Oriented Road Map},
  journal   = {IEEE Control Systems Magazine},
  volume    = {39},
  number    = {6},
  pages     = {28--99},
  year      = {2019},
  doi       = {10.1109/MCS.2019.2938121}
}

@article{ljungDeepLearningSystem2020,
  author    = {Ljung, Lennart and Andersson, Carl and Tiels, Koen and Sch{\"o}n, Thomas B.},
  title     = {Deep learning and system identification},
  journal   = {IFAC-PapersOnLine},
  volume    = {53},
  number    = {2},
  pages     = {1175--1181},
  year      = {2020},
  doi       = {10.1016/j.ifacol.2020.12.1329}
}

@article{schoukensThreeBenchmarksAddressing2017,
  author    = {Schoukens, Maarten and No{\"e}l, Jean Philippe},
  title     = {Three benchmarks addressing open challenges in nonlinear system identification},
  journal   = {IFAC-PapersOnLine},
  volume    = {50},
  number    = {1},
  pages     = {448--453},
  year      = {2017},
  doi       = {10.1016/j.ifacol.2017.08.071}
}

@article{cawleyOverfittingModelSelection2010,
  author    = {Cawley, Gavin C. and Talbot, Nicola L. C.},
  title     = {On Over-fitting in Model Selection and Subsequent Selection Bias in Performance Evaluation},
  journal   = {Journal of Machine Learning Research},
  volume    = {11},
  number    = {70},
  pages     = {2079--2107},
  year      = {2010},
  url       = {https://www.jmlr.org/papers/v11/cawley10a.html}
}

@article{varmaBiasErrorEstimation2006,
  author    = {Varma, Sudhir and Simon, Richard},
  title     = {Bias in error estimation when using cross-validation for model selection},
  journal   = {BMC Bioinformatics},
  volume    = {7},
  pages     = {91},
  year      = {2006},
  doi       = {10.1186/1471-2105-7-91}
}

@article{dieboldComparingPredictiveAccuracy1995,
  author    = {Diebold, Francis X. and Mariano, Roberto S.},
  title     = {Comparing Predictive Accuracy},
  journal   = {Journal of Business \& Economic Statistics},
  volume    = {13},
  number    = {3},
  pages     = {253--263},
  year      = {1995},
  doi       = {10.1080/07350015.1995.10524599}
}

% ungeprüft: pages = {1--9}
@article{dieboldComparingPredictiveAccuracy2015,
  author    = {Diebold, Francis X.},
  title     = {Comparing Predictive Accuracy, Twenty Years Later: A Personal Perspective on the Use and Abuse of {Diebold--Mariano} Tests},
  journal   = {Journal of Business \& Economic Statistics},
  volume    = {33},
  number    = {1},
  year      = {2015},
  doi       = {10.1080/07350015.2014.983236}
}
```

---

## Anhang: sympy-Prüfung Kalman-Filter ↔ exponentielle Glättung (Frage 4)

```python
# Stationärer Kalman-Filter für das Local-Level-Modell (Random Walk + Messrauschen)
#   d^off_k = d^off_{k-1} + w_k,  w ~ N(0, q)   (Ausgangsstörung als Random Walk, Notation wie B2.3)
#   z_k = y_k - C xhat_k = d^off_k + v_k,  v ~ N(0, r)   (z = Messung minus Modellvorhersage)
# Behauptung: Update dhat^off_k = dhat^off_{k-1} + L (z_k - dhat^off_{k-1}) ist exponentielle Glättung mit alpha = L.
import sympy as sp
q, r, P, L, d_prev, z = sp.symbols('q r P L d_prev z', positive=True)

# Riccati stationär: P_minus = P + q;  L = P_minus/(P_minus + r);  P = (1 - L) P_minus
P_minus = P + q
eqs = [sp.Eq(L, P_minus/(P_minus + r)), sp.Eq(P, (1 - L)*P_minus)]
sol = sp.solve(eqs, [P, L], dict=True)
sol = [s for s in sol if s[L].subs({q: 1, r: 1}).is_positive]
Ls = sp.simplify(sol[0][L])
print("stationäre Verstärkung L =", Ls)
print("Kontrolle L^2/(1-L) = q/r :", sp.simplify(Ls**2/(1 - Ls) - q/r) == 0)

# Update-Gleichung als exponentielle Glättung
upd = d_prev + L*(z - d_prev)
print("Update = (1-L) d_prev + L z :", sp.simplify(upd - ((1 - L)*d_prev + L*z)) == 0)
# Grenzfälle: q/r -> 0 ergibt L -> 0 (starke Glättung), q/r -> oo ergibt L -> 1
print("Grenzwert q->0:", sp.limit(Ls, q, 0), "  Grenzwert q->oo:", sp.limit(Ls, q, sp.oo))
```

Ausgabe: `L = (sqrt(q)*sqrt(q + 4*r) - q)/(2*r)`; Kontrolle `L^2/(1-L) = q/r`: True; Update als Glättung: True; Grenzwerte 0 (q→0) und 1 (q→∞).

---

## Offen / nicht belegt

- Kein Volltext gelesen; alle Stellen „lokal nachschlagen“ oder nur „laut ch3“. Inhaltsaussagen
  auf Abstract-Ebene, meist (S).
- DOIs nur (S) oder abgeleitet: Hjalmarsson 2005, Pannocchia u. a. 2015 (IFAC), Callaham u. a.
  2022 (schwache G-Quelle). Keine DOI gefunden: Koung & MacGregor 1994 (DOI aus PII ableitbar,
  ungeprüft), Li & Lee 1996, Van den Hof & Schrama 1995.
- Abdullah & Christofides 2023: Autoren, Zeitschrift, Jahr nur (S) bzw. aus PII; DOI nicht
  gesehen.
- Li u. a.: Automatica-Fassung 2026 nur als Treffer gesehen; Band, Seiten, DOI und Autorenliste
  der Zeitschriftenfassung ungeprüft.
- Dahdah & Forbes 2024: Aussage zu Reglerausgang/Sollwert als Eingang und Bias nur (S), nicht im
  Abstract; im Volltext prüfen. Ob der Serienregler (PI mit Anti-Windup, ch2 Z. 1046–1059) die
  Voraussetzung „bekannter Regler“ erfüllt, offen.
- Autoren fehlen: SINDYc-Kapitel ML4CPS 2023; adaptive SINDy-MPC (Chem. Eng. Res. Des.);
  J. Process Control 2026 zu offsetfreiem MPC (PII S095915242600020X); IECR 2022 „Modeling and
  Control of Nonlinear Processes Using Sparse Identification: Using Dropout to Handle Noisy Data“
  (DOI 10.1021/acs.iecr.2c02639, T).
- Muth-Aussage stammt aus der Zusammenfassung einer Sekundär-PDF; im Original prüfen.
- Äquivalenz Kalman-Filter ↔ exponentielle Glättung ist eigene Herleitung (sympy-geprüft, Skript
  im Anhang); Literaturstelle bei Harvey (Local-Level-Modell) oder
  Rawlings/Mayne/Diehl lokal nachschlagen. Die Einschränkungen ($Q_x>0$, Eingangsstörmodell,
  Reihen-Parallel-Form) sind nur eigene Rechnung, nicht im Skript.
- Eigene Einordnung (SINDy ≈ Operator Inference plus Sparsität) nicht belegt.
- Titelvarianten: Loiseau 2018 (modelling/modeling), Schoukens & Ljung (Road Map/Roadmap),
  Grasev 2026 (v1/v2), Yahagi arXiv:2503.05154 (v1/v2 vs. v3).
- Keys: Yahagi arXiv:2503.05154 evtl. Duplikat von `yahagiSparseIdentificationNonlinear` (Bib,
  ohne Jahr; ch3 Z. 995 nennt „EMEC“, Name ab v3, zitiert dort aber
  `bhadrirajuOASISPOperableAdaptive2021`); Zuordnung IJCAS-DOI und arXiv-IDs zu den Bib-Keys der
  Yahagi-/Yonezawa-Gruppe ungeprüft; Widerspruch zu A.md (Originalfassung Z. 332–333, bearbeitete
  Fassung Z. 413–414: 2503.05154 „vermutlich `yahagiSparseIdentificationNonlinear2025`“) klären.
- Lücken Frage 2: kein Beispiel aus Prozess-, Motor- oder Thermoanwendung mit Messdaten gefunden,
  das die Bibliothekswahl begründet; Yahagi 2025 nur Simulation, Reinbold 2021
  Strömungsexperiment, Sheikh 2024 Batterie, Datenart ungeprüft; erst recht keine Bibliothek der
  Form Temperaturdifferenz × Betriebspunktfaktor.
- Lücken Frage 3: kein Beleg für „Fit Open-Loop, Validierung Closed-Loop“ mit Industriedaten und
  keine \sindy-spezifische Closed-Loop-Bias-Analyse.
- Lücke Frage 6: keine Arbeit gefunden, die ARX, \sindy, \edmd und NN unter offengelegtem gleichem
  Protokoll vergleicht (gleiche Daten, Auswahl ohne Testdaten, gepaarter Test); die Skizze stützt
  sich nur auf Methodikquellen. Kandidat aus der eigenen Bib:
  `kaiserSparseIdentificationNonlinear2018` (ch3 Z. 603; SINDY-MPC gegen NN und lineare Modelle
  bei wenig Daten, S) [nur bibliografisch]; Vergleichsprotokoll lokal prüfen.
- OASIS-P (Bhadriraju/Kwon, Bib): Metadaten in dieser Sitzung nur als Titeltreffer gesehen.
