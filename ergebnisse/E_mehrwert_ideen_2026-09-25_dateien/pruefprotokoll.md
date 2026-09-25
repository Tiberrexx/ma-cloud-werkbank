# Prüfprotokoll der Zusammenführung (Auftrag E, 25.09.2026)

Je Abschnitt: jeder Originalpunkt aus L1 (Commit 653ece4) und L2 (Commit d8ee6a1) mit Prüfung der Zeilen in `kontext/ch2.tex` bzw. `kontext/ch3.tex`, Urteil zum Inhalt und Verwendung im zusammengeführten Ergebnis. Geprüft ohne Internet; Quellenaussagen nicht neu geprüft.

- zeilen: bestätigt / korrigiert / nicht auffindbar / keine Zeilenangabe
- urteil: korrekt / teilweise (im Ergebnis berichtigt) / falsch / nicht prüfbar
- verwendet: Hauptbefund / weiterer Befund / zusammengelegt / übernommen / verworfen

## Zuordnung der E1-Befunde

63 eindeutige Befunde aus 82 Originalbefunden; drei L1-Befunde gingen in E1.2/E1.3 auf.

| ID | Kriterium | Titel | Mitglieder |
|---|---|---|---|
| U01 | K1 | ch2 Z. 1061–1091, 1111–1113: MPC-Problem ohne Störgrößenfolge über den Horizont (L1+L2) | L2-K1-1, L1-2.2 |
| U02 | K1 | ch2 Z. 1080–1082: „linear in der Stellgröße“ reicht als QP-Bedingung nicht (L1+L2) | L2-K1-2, L1-1.2 |
| U03 | K1 | ch2 Z. 266–268 gegen Z. 1064–1074: Ratenbegrenzung und Signaldefinition von \valveCA fehlen im QP (L2) | L2-K1-3 |
| U04 | K1 | ch2 Z. 117–120, 1071–1072: Obergrenze (Derating) fehlt als Beschränkung im MPC (L2) | L2-K1-4 |
| U05 | K1 | ch3 Z. 1122–1159: Einordnung nennt Forschungsfrage und Kern der Arbeit (QP, Ventil-Gain, CL, DoE) nicht (L1+L2) | L2-K1-5, L1-1.1 |
| U06 | K1 | ch3 Z. 1188 gegen ch2 Z. 211–212: „LT-Ventil“ in der Forschungsfrage mehrdeutig (L2) | L2-K1-6 |
| U07 | K1 | ch3 Z. 339–366: Rolle des bilinearen \edmdc in der Arbeit offen (L1) | L1-1.3 |
| U08 | K2 | ch2 Z. 1082–1088: Beobachter bzw. Kalman-Filter nur als Halbsatz (L1+L2) | L2-K2-1, L1-2.1 |
| U09 | K2 | ch3 Z. 1024–1026 gegen Z. 1–616: Modellvalidierung (Residuentests, Einschritt-, k-Schritt-, Simulationsfehler) als Grundlage nicht eingeführt (L2) | L2-K2-2 |
| U10 | K2 | ch3 Z. 155–205: NARX/NARMAX-Absatz zu dünn, FROLS und Abgrenzung zu Polynom-NARX mit Termauswahl fehlen, „lineare Modellklasse“ unscharf (L1+L2) | L2-K2-3, L1-1.4, L1-3.3 |
| U11 | K2 | ch3 Z. 463–486, 600–610 und ch2 Z. 1093–1094: SINDy-MPC-Referenz `kaiserSparseIdentificationNonlinear2018` an falscher Stelle (L1+L2) | L2-K2-4, L1-2.6 |
| U12 | K2 | ch3 Z. 52–122: Kovarianz der LS-Schätzung fehlt (L2) | L2-K2-5 |
| U13 | K2 | ch3 (Z. 241–262, 303–307): Bezug zu reduzierten Modellen und POD-Galerkin fehlt (L1+L2) | L2-K2-6, L1-2.5 |
| U14 | K2 | ch2 gesamt: Grundlagenbausteine Diskretisierung, Totzeit, stationäre Verstärkung, Simulations- gegen Einschrittfehler fehlen (L1) | L1-2.3 |
| U15 | K2 | ch3 Z. 390–431: SINDy-Solver nur STLSQ und LASSO, SR3 und Nebenbedingungen fehlen (L1) | L1-2.4 |
| U16 | K3 | ch2 Z. 112–114 gegen Z. 237–239: Sollwertlage 52 °C widersprüchlich (L2) | L2-K3-1 |
| U17 | K3 | ch2 Z. 89–95, 112–114: Taupunkt-Argument hängt am Ladedruck (L2) | L2-K3-2 |
| U18 | K3 | ch3 Z. 360–366 gegen ch2 Z. 929–934: Bilinearität und „Verlust des QP“ falsch begründet (L2) | L2-K3-3 |
| U19 | K3 | ch2 Z. 1048–1056, ch3 Z. 786–787: Vorzeichen des PI-Reglers (L2) | L2-K3-4 |
| U20 | K3 | ch3 Z. 529–548: „diskrete map-Form“ ist keine eigene Form (L2) | L2-K3-5 |
| U21 | K3 | ch3 Z. 143–147: „numerische Ableitung geht gegen null“ falsch (L2) | L2-K3-6 |
| U22 | K3 | ch2 Z. 742, 279–281 gegen Z. 1037–1038: Ventilkennlinie widersprüchlich beschrieben (L2) | L2-K3-7a |
| U23 | K3 | ch3 Z. 1149–1152: „keine behandelt die Ladelufttemperatur“ zu weit gefasst (L2) | L2-K3-7b |
| U24 | K3 | ch3 Z. 1141–1142: „Messdaten fast immer aus Simulationen“ zu weit gefasst (L2) | L2-K3-7c |
| U25 | K3 | ch3 Z. 819–823: Kreuzterm im geschlossenen Kreis nicht allgemein ungleich null (L2) | L2-K3-7d |
| U26 | K3 | ch3 Z. 838–840: Sättigung beseitigt den Kreuzterm nur im Stellteil des Regressors (L2) | L2-K3-7e |
| U27 | K3 | ch3 Z. 323–325: Korda/Mezić 2018 überzeichnet, siehe E1.3 (L2) | L2-K3-7f |
| U28 | K3 | ch2 Z. 796–802: Gain-Gleichung nutzt nur die einstufige Ersatzform, siehe E1.2 (L2) | L2-K3-7g |
| U29 | K3 | ch2 Z. 543–546 gegen Z. 733–741: Annahme C_W ≫ C_L (C_min = C_L über den ganzen Hub) gilt bei kleinem Hub nicht, zwei Wirkwege des Ventils (L1+L2) | L2-K5-2, L1-3.5 |
| U30 | K3 | ch3 Z. 625–628: „analoge Sensitivität für SINDy zu erwarten“, obwohl Z. 633–637 sie belegt (L1) | L1-3.6 |
| U31 | K4 | ch3 Z. 27–41: Grey-Box-Einordnung widerspricht der eigenen Linie (L1+L2) | L2-K4-1, L1-3.1 |
| U32 | K4 | ch3 Z. 654–721: CL-Verfahren aufgezählt ohne Festlegung, Zielkonflikt HO-ARX gegen Informativität (L2) | L2-K4-2 |
| U33 | K4 | ch3 Z. 877–889 gegen ch2 Z. 271–274: Konfundierung zu eng als Bestimmtheitsmaß gegen die Last gefasst (L2) | L2-K4-3 |
| U34 | K4 | ch2 Z. 217–219, 517–519, 799–801: \TLT nicht rein exogen, Ventil-Gain als partielle Größe definieren (L2) | L2-K4-4 |
| U35 | K4 | ch2 Z. 604–619, 848–857 gegen ch3 Z. 573–575: nichtlineare Parameter (Exponent, NTU) mit STLSQ auf fester Bibliothek nicht schätzbar (L2) | L2-K4-5 |
| U36 | K4 | ch3 Z. 869–873: Modussprung als „natürliches Instrument“ nicht abgesichert (L1+L2) | L2-K4-6, L1-4.1 |
| U37 | K4 | ch3 Z. 126–141: Skalierung ohne Zentrierung als „üblich“ unbelegt (L1) | L1-4.3 |
| U38 | K4 | ch3 Z. 520–526: Wahl von Schwellwert und Bibliothek ohne Verbrauch der Testdaten offen (L1) | L1-4.4 |
| U39 | K4 | ch3 Z. 1018–1029: Leerbefund mit Suchumfang vorbildlich, Stand aktualisieren (L1) | L1-4.5 |
| U40 | K5 | ch2 Z. 848–859: Konsistenzgrenze N/(1+N) gegen 1−e^{−N} als Begründung der Modellstruktur und als Modellreduktion herausstellen (L1+L2) | L2-K5-1, L1-5.2 |
| U41 | K5 | ch2 Z. 434–448, 929–934: „Rate trägt nur den schwachen Rest“ unbelegt, Ventil nur im Zielwert ist Modellentscheidung (L2) | L2-K5-3 |
| U42 | K5 | ch2 Z. 1082–1088 mit ch3 Z. 909–921: offsetfreie Regelung korrigiert das Niveau, nicht den Gain (L2) | L2-K5-4 |
| U43 | K5 | ch3 Z. 275–281, 314–341: Form des Ventil-Gains je Modellklasse (L2) | L2-K5-5 |
| U44 | K5 | ch2 Z. 437–438, 854–871: gleiche Zeitkonstante für Ventil- und Störkanal (L2) | L2-K5-6 |
| U45 | K5 | ch3 Z. 806–843: Rückführungsbias ändert über den Schwellwert die Modellstruktur (L1) | L1-5.3 |
| U46 | K5 | ch3 Z. 590–611: Grenzen generisch, dominierende Grenze für die Ladeluftstrecke fehlt (L1) | L1-5.4 |
| U47 | K5 | ch3 Z. 308–312: Closure-Problem ohne Bezug zur eigenen \edmdc-Bibliothek (L1) | L1-5.5 |
| U48 | K6 | ch3 Z. 877–925: eigene Übertragungen (Vorsteuerung als Rangproblem, Reglertakt gegen Modelltakt, Dreiteilung) unmarkiert bzw. nur mittelbar belegt (L1+L2) | L2-K6-1, L1-4.2, L1-4.6 |
| U49 | K6 | ch3 Z. 434–450 gegen ch2 Z. 398–425: eigene Bibliotheksherleitung erscheint als Übernahme von `loiseauConstrainedSparseGalerkin2018` (L2) | L2-K6-2 |
| U50 | K6 | ch3 Z. 1122–1174, 1196–1197: keine Beitragsliste (L2) | L2-K6-3 |
| U51 | K6 | ch2 und ch3: „Copilot:“-Überschriften im gesetzten Text (L2) | L2-K6-4 |
| U52 | K6 | ch2 Z. 271–274: Serienkennfeld als Obergrenze des stationären Ventil-Gains ungenutzt (L2) | L2-K6-5 |
| U53 | K6 | ch2 Z. 407–425, 611–613, 781–782: erwartete Vorzeichen als Prüfkriterium oder Nebenbedingung ungenutzt (L2) | L2-K6-6 |
| U54 | K6 | ch2 Z. 392, 920: eigene Algebra gekennzeichnet, konvexe Kombination als weitere eigene Herleitung (L1) | L1-6.1 |
| U55 | K6 | ch3 Einordnung: LPV-Deutung von \sindyc mit exogenem Scheduling als eigener Beitrag (L1) | L1-6.2 |
| U56 | K6 | ch3 Einordnung: Verschiebungsinvarianz der Differenzbibliothek als eigenes Argument (L1) | L1-6.3 |
| U57 | K6 | ch3 Z. 1024–1027: Residuentests selbst durchführen macht den Leerbefund zum Beitrag (L1) | L1-6.4 |
| U58 | K7 | ch3 Z. 218–220, 506, 552, 625, 757–776 und ch2 Z. 296: sichtbare Entwurfsreste und Tippfehler (L1+L2) | L2-K7-1, L1-7.1, L1-7.2, L1-7.3, L1-7.4 |
| U59 | K7 | ch2 Z. 184–185: „Bündel“ für HT/LT statt Stufe (L1+L2) | L2-K7-2, L1-7.6 |
| U60 | K7 | ch2 und ch3: Symbole mehrfach belegt (λ, N, K, e u. a.) (L1+L2) | L2-K7-3, L1-7.7 |
| U61 | K7 | ch2 und ch3: tote Labels und Arbeitsnotizen im Satz (L2) | L2-K7-4 |
| U62 | K7 | ch2 Z. 309–465 gegen Z. 467–1003: zwei parallele Herleitungsketten (L1+L2) | L2-K7-5, L1-5.1 |
| U63 | K7 | ch3 Z. 948, 964, 989, 995 und ch2 Z. 1039: Sprache, Denglisch, unerklärte Begriffe (L1+L2) | L2-K7-6, L1-7.5 |
| – | E1.2/E1.3 | E1.3, Zeile „ch3 Z. 323–325 / `kordaLinearPredictorsNonlinear2018` / nicht gestützt“ | L1-3.2 |
| – | E1.2/E1.3 | E1.2, Zeile „ch3 421–430, 495–500 (STLSQ, LASSO, Bildunterschrift) / fehlerhaft“ (Norm ungequadratet) | L1-3.4 |
| – | E1.2/E1.3 | E1.3, Zeile „ch3 Z. 1144–1147 / eigenes Argument / teilweise“ | L1-3.7 |

## E1.1 K1 und K2

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L2-K1-2 | bestätigt | korrekt | Hauptbefund | U02, K1 Rang 1. Satz ch2 Z. 1080-1082 wörtlich geprüft; Gegenbeispiel und Bedingung (b) mit λ(\mrel,\valveCA) aus Z. 437-438 per Zahlentest bestätigt (d2x2/du0^2 = -2θb^2, gemischte Ableitung ungleich 0, LPV mit exogenem Scheduling affin). Ergänzt: Grenze der virtuellen Stellgröße v = g(u) bei Ratenschranke und Δu-Strafe (eigene Algebra). |
| L1-1.2 | bestätigt | korrekt | zusammengelegt | In U02. Verweis 'Auftrag B' aufgelöst: B1-Tabellenzeile MPC-Satz (sympy-Gegenbeispiel) und B2.3 (Affinität im Zustand, Prädiktorform); Vorschlag 'in ch3 als Auswahlkriterium' übernommen, Ort ch3 Z. 570-588. |
| L2-K1-1 | korrigiert | korrekt | Hauptbefund | U01, K1 Rang 2. ch2 hat nur 1112 Zeilen, Notiz steht in Z. 1111 (nicht 1111-1113). Nebenpunkt präzisiert: Diskretisierung ist in Z. 1088-1090 als Halbsatz genannt, nur Liftung und Zustandsraumrealisierung fehlen. ch3 Z. 1202-1204 bestätigt. |
| L1-2.2 | korrigiert | korrekt | zusammengelegt | In U01. Zeile 1111-1113 auf 1111 korrigiert. Verweis Auftrag B, B2.3 aufgelöst (gemessene Störgrößen im Horizont konstant fortschreiben oder Prognose). |
| L2-K1-3 | bestätigt | korrekt | Hauptbefund | U03, K1 Rang 3. Z. 255, 263-268, 277-281 und 1071 geprüft. Präzisiert: Δu_k = 0 für k >= N_u ist implizit durch die Entscheidungsvariablen, nur nicht ausgeschrieben; Umkehrspanne wirkt bei fester Rate wie Totzeit, ist aber nicht LTI. Transporttotzeit Rohrstrecke (Z. 263-265) ergänzt mit Auftrag B, B2.2. |
| L2-K1-4 | bestätigt | korrekt | Hauptbefund | U04, K1 Rang 4. Z. 117-120, 39-41, 1071-1072 bestätigt. Ergänzt: y_max-Wahl offen (Derating-Beginn 55 °C unter Bandkante 60 °C, Z. 108-109); nach oben wirkt heute nur der Folgeterm; exakte Schlupfstrafe nach Kerrigan & Maciejowski 2000 als Idee S2/D7. |
| L2-K1-5 | bestätigt | korrekt | Hauptbefund | U05, K1 Rang 5. Fließtext Z. 1126-1159 nennt nur 'prädiktive Regelung' (Z. 1127), kein QP, CL, Gain, DoE. Anker Yahagi Z. 1106-1107 und Rupprecht Z. 1052-1053 bestätigt, auf Z. 1051-1055 erweitert (getrennte Prüfung Temperatur/Stellsignal steht dort selbst). |
| L1-1.1 | korrigiert | korrekt | zusammengelegt | In U05. Bereich 1122-1147 auf Einordnungs-Fließtext Z. 1126-1174 erweitert; Forschungsfrage Z. 1185-1190 im Copilot-Zusatzblock Z. 1176-1213 bestätigt. |
| L2-K1-6 | bestätigt | korrekt | Hauptbefund | U06, K1 Rang 6. ch3 Z. 1188 'LT-Ventil', ch2 Z. 211-212 (LT-Kreis-Vorlaufventil) bestätigt. Ergänzt: baugleiches LP-Ventil (Z. 253-254) als weitere Lesart; \valveCA stellt den Durchsatz durch die LT-Stufe des HP-Kühlers (Z. 249-258); T_eng,in statt \Tout in Z. 1187. |
| L1-1.3 | bestätigt | korrekt | weiterer Befund | U07, unter K1 'Weitere Befunde' (7. Punkt, Limit 6). Präzisiert: Text verwirft die bilineare Form nicht ausdrücklich, er nennt sie 'einschlägig' (Z. 359-362) und den Preis (Z. 363-366). Querverweis auf K3 (L2-K3-3), weil die Spanne aus Störgrößen besteht. |
| L2-K2-1 | bestätigt | korrekt | Hauptbefund | U08, K2 Rang 1. Rangbedingung für Ausgangsstörung (det = 1-a) und Eingangsstörung (det = c·b, also Gain ungleich 0) nachgerechnet. 'Kalman' kommt in ch2/ch3 nicht vor; ch3 Z. 919-922 verweist auf sec.methodik.mpc. Zuschreibung der Rangbedingung zu Pannocchia 2003/Maeder 2009 nicht am Original geprüft. |
| L1-2.1 | korrigiert | korrekt | zusammengelegt | In U08. Z. 1083-1088 auf 1082-1088 (Satzbeginn). Verweis Auftrag D, Frage 4 aufgelöst: stationärer KF für Random Walk plus Rauschen = exponentielle Glättung mit α = L, L^2/(1-L) = q/r, nachgerechnet; Abgrenzung zur EMA-Bibliotheksspalte ch3 Z. 440-441 ergänzt. |
| L2-K2-2 | bestätigt | korrekt | Hauptbefund | U09, K2 Rang 2. ch3 Z. 1024-1026 Leerbefund, ch2 Z. 491 'Transientenfehler' und Z. 999 'Nutzen im Freilauf' ohne Definition bestätigt (grep: keine Einschritt-/Simulationsfehler-Begriffe). Quellen aus verifiziert.json (Ljung & Box 1978, Billings & Voon 1986, Billings & Zhu 1994, Douma 2008) ergänzt. |
| L1-2.3 | keine Zeilenangabe | teilweise | Hauptbefund | U14, K2 Rang 3. 'ch2 gesamt' auf Stellen präzisiert: Diskretisierung als Halbsatz vorhanden (ch2 Z. 1088-1090), Totzeit physikalisch vorhanden (Z. 263-265, 866-874), Stellverstärkung physikalisch vorhanden (Z. 775-802); es fehlen deren diskrete/QP-Darstellung und eine modellklassenübergreifende Gain-Definition. Nur Simulations- vs. Einschrittfehler fehlt ganz. B2.1, B2.2, B2.4 Kernformeln nachgerechnet. |
| L2-K2-5 | bestätigt | korrekt | Hauptbefund | U12, K2 Rang 4. Keine Kovarianzformel in ch3 Z. 52-122, VIF Z. 114 ohne Beleg. Präzisiert per Zahlentest: VIF-Bezug gilt ohne Konstantspalte mit unzentriertem R_j^2, mit Konstantspalte zentriert; bei Skalierung ohne Zentrierung (Z. 134-137) weichen beide stark ab. 'Unterschätzt' auf positiv autokorrelierte Residuen/Regressoren eingeschränkt; Bias bei verzögerten Ausgängen ergänzt. |
| L2-K2-3 | bestätigt | korrekt | Hauptbefund | U10, K2 Rang 5. Z. 197-205 nennt nur aranDieselEngineAirpath2020 (NFIR). 'direkter Vorläufer' als unbelegte ideengeschichtliche Aussage abgeschwächt auf 'gleiche LS-Struktur'. Chen, Billings, Luo 1989: laut verifiziert.json aussage_check teilweise (ERR-Auswahl im Abstract nicht gesehen), so vermerkt. |
| L1-1.4 | korrigiert | korrekt | zusammengelegt | In U10. Stelle 155-195 ist der ARX-Teil; NARX-Absatz steht in Z. 197-205. Piroddi & Spinelli 2003 in verifiziert.json bestätigt. Positiver Teil ('ARX gut begründet', Z. 187-195) als 'Stärke:' unter K2 Weitere Befunde. |
| L1-3.3 | bestätigt | korrekt | zusammengelegt | In U10 (Unterpunkt Z. 203-205). Geschärft: Bezieht sich 'oben' auf Z. 187-195, ist der Satz sachlich falsch; gemeint sind vermutlich die LS-Grenzen Z. 106-152. |
| L2-K2-4 | bestätigt | teilweise | Hauptbefund | U11, K2 Rang 6. Kaiser nur Z. 603 bestätigt (grep), Z. 608-610 ohne Beleg bestätigt. Korrigiert: 'Abschnitt existiert nicht mehr' gilt nur für einen eigenen MPC-Abschnitt (Kommentar ch3 Z. 1008-1009); verstreute MPC-Stellen gibt es in sec.sot.application (Z. 1003-1007, 1069-1081, 1094-1102). Metadaten Kaiser 2018 aus verifiziert.json (bestätigt, DOI gesehen). |
| L1-2.6 | bestätigt | korrekt | zusammengelegt | In U11. Z. 463-486 ohne Kaiser, Z. 603 bestätigt. NMPC-Abgrenzung stammt nur aus Autoren-Code (Auftrag B, B2.1), als 'am Original prüfen' markiert. |
| L2-K2-6 | bestätigt | korrekt | weiterer Befund | U13 unter K2 'Weitere Befunde' (Limit 6 Hauptbefunde; geringeres Gewicht für Kap. 5-7, Abdeckung auch in E1.4). DMD Z. 247-255 ohne SVD-Trunkierung, 'Galerkin' nur Z. 305, 'POD' in ch3 nicht vorhanden (grep). |
| L1-2.5 | keine Zeilenangabe | korrekt | zusammengelegt | In U13. 'ch3 gesamt' durch L2-Zeilen ersetzt. Verweis Auftrag D, Frage 1 aufgelöst (POD-Galerkin intrusiv, SINDy wählt Terme statt Moden, kein ROM im klassischen Sinn); Belege aus verifiziert.json (Noack 2003, Rowley & Dawson 2017, Peherstorfer & Willcox 2016, Benner u. a. 2015). |
| L1-2.4 | bestätigt | teilweise | weiterer Befund | U15 unter K2 'Weitere Befunde'. Solver Z. 420-431 bestätigt, Elastic Net Z. 429-430 genannt. Korrigiert: Gleichungsnebenbedingungen sind über Loiseau (Z. 445-447) genannt; nur SR3 und Ungleichungen fehlen. Quellenvorschlag nach Auftrag A korrigiert: Champion 2020 belegt nur Gleichungen, Ungleichungen über Kaptanoglu 2022; Zheng-Jahr offen. Keine dieser drei Quellen in verifiziert.json. |

## E1.1 K3

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L2-K3-1 | bestätigt | korrekt | weiterer Befund | U16. ch2 Z. 114 („oberer Teil“), Z. 237–238 (52 °C), Z. 108–109 (Band 50–60 °C), Z. 39–41 (Derating ab 55 °C) geprüft. „Unteres Fünftel“ präzisiert zu 20 % der Bandbreite, 2 K über der Untergrenze. Z. 105 und die Möglichkeit, dass der variable Serien-Sollwert gemeint ist (Z. 230–236), ergänzt. |
| L2-K3-2 | bestätigt | korrekt | weiterer Befund | U17. Magnus nachgerechnet: 3 bar abs 51,49 °C, 4 bar abs 57,44 °C, 3 bar Überdruck 57,51 °C. Ergänzt: Taupunkt gilt am HP-Kühler nach der zweiten Verdichtung (ch2 Z. 157–160); die PG-Kondensatmenge (Z. 89–92) spricht für Kondensat im Auslegungsfall. Für die Magnus-Koeffizienten gibt es keine gegengeprüfte Quelle. |
| L2-K3-3 | bestätigt | korrekt | Hauptbefund | U18. ch3 Z. 343–347 und 360–366 sowie ch2 Z. 929–934 geprüft; Horizontalgebra nachgerechnet. Präzisiert: Die Bilanzform (ch2 Z. 877–884, 929–930) und λ(mrel, u) (Z. 437–438) enthalten das Produkt u·Tout. ch3 stützt die zustandsbilineare Form auf das Störgrößenargument. Reiner Eingangsterm fehlt ohne konstante Observable (aus E1.2). Bezug zu U07 (K1) hergestellt. |
| L2-K3-4 | korrigiert | korrekt | Hauptbefund | U19. ch2 Z. 1048–1055 und ch3 Z. 786–787 bestätigt; Streckenvorzeichen ch2 Z. 288–291, 781. Folgestelle präzisiert von ch3 666–671 auf 668–671. Zahlentest: P-Regler ergibt LS-Steigung genau −1/K_c > 0 (Illustrationswerte). Folgerung abgeschwächt, weil beim PI-Regler −1/C gegen null geht (Idee A13). E1.2-Punkt Z. 1056–1057 gegen 273–274 aufgenommen. |
| L2-K3-5 | bestätigt | korrekt | Hauptbefund | U20, gemeinsamer Hauptpunkt mit U21. Die Aussage steht in ch3 Z. 543–547. Zahlentest bestätigt: Map-Form und Vorwärtsdifferenz liefern dasselbe Ξ. Ergänzt: Der genannte Nachteil (Δt-Abhängigkeit) trifft beide Formen gleich. |
| L2-K3-6 | bestätigt | korrekt | Hauptbefund | U21, zusammen mit U20 in einem Hauptpunkt. ch3 Z. 143–146 geprüft. Rauschanteil √2σ/Δt nachgerechnet. Die Folgerung „passt sich dem Rauschen an“ bleibt richtig, falsch ist nur der Mechanismus. |
| L2-K3-7a | bestätigt | korrekt | weiterer Befund | U22. ch2 Z. 279–281, 742 und 1037–1038 geprüft. Ergänzt: Z. 253 („linearer Kennlinie“), Uneinheitlichkeit linear/nahezu linear, Z. 736–737 (S-Form ist Messbefund) und die Abgrenzung zur Kennlinie des Stellkanals (Z. 278–279). |
| L2-K3-7b | bestätigt | korrekt | weiterer Befund | U23. Die Leeraussage steht in ch3 Z. 1152, der Vagapov-2024-Stichpunkt in Z. 1069–1081. Z. 1126–1128 ist schon richtig eingeschränkt und dient als Vorlage. |
| L2-K3-7c | bestätigt | korrekt | weiterer Befund | U24. ch3 Z. 1141–1144; sec.sot.application umfasst Z. 946–1121. Belegt mit Rupprecht (Z. 1049–1050), Vagapov 2022 (Z. 1060), Vagapov 2024 (Z. 1074) und Sui (Z. 1086). Zinage 2022 als zweite Ausnahme aus E1.3 ergänzt; laut verifiziert.json stützt der Abstract das (Motormessdaten). |
| L2-K3-7d | bestätigt | korrekt | Hauptbefund | U25, gemeinsamer Hauptpunkt mit U26. ch3 Z. 822–823 gegen Z. 827–832 geprüft. Zahlentest: CL mit weißem v unverzerrt, mit farbigem v verzerrt. Anker Shardt & Huang 2011 [nur Abstract] ergänzt. |
| L2-K3-7e | bestätigt | korrekt | Hauptbefund | U26, zusammen mit U25 in einem Hauptpunkt. ch3 Z. 838–840 geprüft. Zahlentest mit fast durchgehend gesättigter Stellgröße: Bei farbigem v bleibt die Verzerrung, der Ventilkoeffizient wird unzuverlässig. Bezug zu Idee B2 (Schalter unterbricht nur Pfad A). |
| L2-K3-7f | bestätigt | korrekt | weiterer Befund | U27, als Verweis auf E1.3 geführt und nicht gedoppelt. Korda & Mezić 2018 (J. Nonlinear Sci.) ist in verifiziert.json bestätigt [nur Abstract]. Die Einschränkung auf autonome Systeme stand nicht im Abstract-Auszug, das ist vermerkt. |
| L2-K3-7g | bestätigt | korrekt | Hauptbefund | U28, Überschrift mit dem E1.2-Bereich ch2 Z. 775–802. Die zweistufige Gleichung wurde per finiter Differenz bestätigt, w3 = (1−ε_HT)(1−ε_LT). Ergänzt: ch2 Z. 806–811 enthält den partiellen Term bereits richtig, Gleichung und Stichpunkt passen nicht zusammen. |
| L2-K5-2 | bestätigt | korrekt | zusammengelegt | U29. ch2 Z. 543–546, 733–741, 785–786 geprüft. ε ≈ C_W/C_L bei C_W ≪ C_L per Zahlentest bestätigt, mit der Bedingung eines großen wasserseitigen NTU. Den Satz „versagt zuerst im Flankenbereich“ qualitativ umformuliert. |
| L1-3.5 | bestätigt | korrekt | zusammengelegt | U29. Auftrag B, B1 (Annahmen, Kapazitätsstrom bei kleinem Hub) nachgesehen und den Kern übernommen. Präzisiert: C_r → 0 verlangt C_W ≫ C_L, C_min = C_L reicht nicht (Gegenstrom, NTU = 2, C_r = 0,5: 0,77 statt 0,86). Die Annahme steht auch in Z. 611–613 und 764–765. |
| L1-3.6 | bestätigt | korrekt | weiterer Befund | U30. ch3 Z. 626–628 und 633–637 geprüft. Präzisiert: Brunton 2016 beschreibt Kondition und Unterscheidbarkeit, Dahdah 2024 eine Verzerrung, „analog“ verwischt beides. Die Seitenangabe S. 713 ist nicht am Original geprüft. Hinweis auf textbf in Z. 625 (K7). |

## E1.1 K4 und K5

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L2-K4-1 | bestätigt | korrekt | zusammengelegt | Mit L1-3.1 zum Hauptbefund K4 ch3 Z. 27–41 (Grey-Box) zusammengelegt. Z. 36–38, 41, 453–457, 1155–1159 und ch2 Z. 420–422 geprüft. Präzisiert: ch3 nutzt zwei Grey-Box-Definitionen; nach der weiten Definition Z. 27–30 fiele die Arbeit formal darunter, der Widerspruch liegt also zwischen beiden Definitionen und Z. 1155–1159. Ljung-Begriff semi-physikalisch nur als zu prüfender Kandidat. |
| L1-3.1 | bestätigt | korrekt | zusammengelegt | Mit L2-K4-1 zusammengelegt; von K3 nach K4 umgeordnet (methodische Einordnung). Z. 36–38 und 41 stimmen wörtlich. |
| L2-K4-2 | bestätigt | korrekt | Hauptbefund | Hauptbefund K4, Rang 1. Z. 654–721, 674–676, 678–683, 696–700 und ch2 Z. 237, 270–279 geprüft. HO-ARX-Singularität per Zahlentest bestätigt (ARX(2,2,1) singulär, (1,1,1), (2,1,1), (1,2,1) nicht). Präzisiert: mit einem Takt Verzug im Kreis erst ab n_a ≥ 3; Vorsteuerung, Adaption, Sättigung und Taktunterschied brechen die exakte Abhängigkeit. Präzisiert: Seriensollwert in Felddaten evtl. mit Ansauglufttemperatur mitgeführt (ch2 Z. 234–236), dann Instrumentvorbehalt wie beim Modussprung. Van den Hof & Schrama 1993 und Chiuso 2007 aus verifiziert.json für die Anno-Notizen Z. 692, 702 ergänzt. |
| L2-K4-3 | bestätigt | korrekt | Hauptbefund | Hauptbefund K4, Rang 4. ch3 Z. 877–889 und ch2 Z. 271–274 geprüft. R² = 1 − 1/VIF stimmt. Präzisiert: Z. 883–884 gilt nur bei exakter Abhängigkeit; bei Beinahe-Kollinearität sinkt die Varianz mit der Datenmenge. Nicht mit L1-4.6 zusammengelegt (Quellenpassung Proctor gesondert). |
| L2-K4-4 | bestätigt | teilweise | Hauptbefund | Hauptbefund K4, Rang 3. Z. 217–219, 517–519, 796–802 bestätigt. Korrigiert: Die Mitbewegung von \Tin über den LP-Kühlerregler (Z. 157–160, 253–261) ist in ch2 nicht beschrieben; Beleg ist Z. 777–780, der Mechanismus bleibt offen. Die Festhaltebedingung steht schon in Z. 781 und im Copilot-Stichpunkt Z. 806–814; offen ist nur, welche Größe die Bewertungsgröße ist. Ergänzt: DoE-Sekante enthält die Mitbewegung, Modell-Gain nicht. |
| L2-K4-5 | bestätigt | teilweise | Hauptbefund | Hauptbefund K4, Rang 5. ch2 Z. 604–619 (Fitgröße Z. 617–619), 848–857, 994–995 und ch3 Z. 573–575 geprüft; Befund korrekt. Vorschlag 'Raster \mrel^p als mehrere Bibliotheksspalten' verworfen: Zahlentest zeigt Korrelation nahe eins, STLSQ verteilt willkürlich; ersetzt durch äußere 1-D-Suche mit je einer Spalte. |
| L2-K4-6 | bestätigt | korrekt | zusammengelegt | Mit L1-4.1 zum Hauptbefund K4 ch3 Z. 869–873 (Modussprung) zusammengelegt. ch2 Z. 958–961 und ch3 Z. 647–649, 874–875, 891–897 geprüft. Ljung Abschn. 13.4 selbst nicht am Original geprüft. |
| L1-4.1 | bestätigt | korrekt | zusammengelegt | Mit L2-K4-6 zusammengelegt. ch2 Z. 288–289 und 268–270 bestätigt. Präzisiert: Formal ist u = 100 % ein konstantes Gesetz; nach ch3 Z. 891–897 liefert dieser Abschnitt nur den stationären Anteil, Information über den Stellkanal trägt nur der Übergangssprung. |
| L1-4.3 | bestätigt | teilweise | weiterer Befund | Weiterer Befund K4; Kernstelle Z. 134–137. 'üblich' unbelegt: korrekt. Einschränkung 'bei Differenzbibliotheken nicht' gilt nur für Spalten linear in den Rohsignalen; bei Produkten \mrel·ΔT ändert Zentrierung des Faktors vor der Produktbildung die Sparsamkeit (Zahlentest). Spaltenweise Zentrierung mit Konstantspalte ändert nur die Konstante. Neben E1.2-Befund (σ_j = 0 betrifft Skalierung) gestellt. PySINDy-Doku nur als Hinweis, nicht als Beleg. |
| L1-4.4 | bestätigt | teilweise | weiterer Befund | Weiterer Befund K4 (L1 nannte Z. 520–526, der Satz beginnt in Z. 519). Die Wahlregel verweist auf ssec.meth.gates, das nicht in kontext/ liegt, daher nur teilweise prüfbar. Ergänzt: Inklusionswahrscheinlichkeiten aus Ensemble-SINDy stehen schon in Z. 512–514. Meinshausen & Bühlmann 2010 und Cawley & Talbot 2010 in verifiziert.json bestätigt. |
| L1-4.5 | bestätigt | korrekt | weiterer Befund | Als 'Stärke:' unter weitere Befunde K4. Stand 02.09.2026 und Suchbegriffe Z. 1021–1024 bestätigt. Aktualisierung nach Auftrag A (A3.3–A3.5); Akan u. a. 2024 nur aus Auftrag A, nicht in verifiziert.json. |
| L2-K5-1 | bestätigt | korrekt | zusammengelegt | Mit L1-5.2 zum Hauptbefund K5 ch2 Z. 848–859 zusammengelegt. Zellformel ε_n = 1 − (1 + N/n)^{−n} mit beiden Grenzfällen nachgerechnet. Präzisiert: Projektion auf konstante Ansatzfunktion braucht eine Schließung (T̄ = \Tout gibt N/(1+N), Mittelwert gibt 2N/(2+N)); der zweite Pol (Kaltseite, Z. 860–863) gehört zur Speicherzusammenfassung, nicht zur Zellzahl; U_eff A ≠ kA (Z. 830–831). |
| L1-5.2 | bestätigt | korrekt | zusammengelegt | Mit L2-K5-1 zusammengelegt. Präzisiert: 'Hammerstein' gilt nur bei fester Rate (Z. 857–859 sagt das selbst); λ(ṁ_L, \valveCA) in Z. 855 widerspricht der QP-Bedingung. |
| L2-K5-3 | bestätigt | korrekt | Hauptbefund | Hauptbefund K5, Rang 1. Elastizitäten 1 − ε und ε per finiter Differenz bestätigt. Ergänzt: Widerspruch innerhalb ch2 zwischen Z. 447–448, 897–898, 985–990 und Z. 932–934, 994–995; Z. 855 setzt λ mit \valveCA. |
| L2-K5-4 | korrigiert | teilweise | Hauptbefund | Hauptbefund K5, Rang 3. ch2 Z. 1082–1088 und ch3 Z. 909–921 bestätigt; ch2 Z. 722 nennt Verschmutzung nur als Grenze des Druckverlust-Proxys, kA-Wirkung korrigiert auf Gl. eq.k.zusammensetzung (Z. 752–757). Präzisiert per Zahlentest: stationär keine Abweichung bei Gain-Fehler, solange der Kreis stabil ist; der Gain-Fehler wirkt auf Übergang und Stabilität, bei falschem Vorzeichen Divergenz. |
| L2-K5-5 | bestätigt | korrekt | Hauptbefund | Hauptbefund K5, Rang 2. ch3 Z. 275–281, 314–331 und ch2 Z. 781–786 geprüft; konstanter Gain bei linearem Eingang auch mit nichtlinearer Zustandsliftung bestätigt. Präzisiert: Gain-Form hängt an der Eingangsparametrierung (ARX/\edmdc mit v = \valveCA·Spanne sind ebenfalls spannenproportional); Folge für die Ablation BT5. |
| L2-K5-6 | bestätigt | korrekt | Hauptbefund | Hauptbefund K5, Rang 5. Z. 437–438, 854–871 geprüft. Ergänzt aus ch2 selbst: zweiter Pol auf der Kaltseite (Z. 860–863); Z. 866–871 addiert Luftverweilzeit und Rohrstrecke zu einer Totzeit, kanalbezogen gehören sie zu verschiedenen Eingängen. Filterpol und Totzeit nur fest gewählt linear im Parameter. |
| L1-5.3 | bestätigt | teilweise | weiterer Befund | Weiterer Befund K5; Kern steht schon in Z. 841–843 ('trifft zusätzlich die Termauswahl'). Ergänzt: beide Richtungen (Term fällt weg, Scheinterm bleibt) und Verschiebung der übrigen Koeffizienten nach dem Entfernen. Nicht mit den K3-Befunden zu Z. 819–823 und 838–840 zusammengelegt. |
| L1-5.4 | bestätigt | korrekt | weiterer Befund | Weiterer Befund K5. Liste Z. 595–611 bestätigt; ergänzt, dass die Rückführung dort fehlt, weil Z. 151–152 sie abtrennt. Fehlende Belege zu Z. 603 und 608–610 verweisen auf K2. Streckenbezogene Gewichtung nur als zu prüfende Einschätzung, keine Datenaussage. |
| L1-5.5 | bestätigt | korrekt | weiterer Befund | Weiterer Befund K5. Z. 308–312 und Z. 369–383 geprüft; ch3 legt die eigene Liftung nicht fest. Ergänzt als eigene Überlegung: Delay-Liftung ist in den Verschiebungszeilen exakt geschlossen (Grenzfall ARX, Z. 328–331), Monome von \Tout erzeugen das Closure-Problem, Störgrößen im Lift sind nie geschlossen. |

## E1.1 K6 und K7

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L2-K6-1 | bestätigt | korrekt | Hauptbefund | U48. ch3 Z. 877–925 geprüft: vier eigene Übertragungen, Belege fehlen für Z. 891–897, 899–905, 909–925. Präzisiert: Bei konstantem Ventil werden in der Produktbibliothek g(u)·ΔT und ΔT kollinear (eigene Algebra, Zahlentest). Konfundierungsmaß nur gegen die Last: Verweis auf K4. |
| L1-4.2 | bestätigt | korrekt | zusammengelegt | In U48. Z. 899–905 unbelegt, 500 ms in ch2 Z. 275 bestätigt. Der Modelltakt steht nicht in kontext/. Präzisiert: gemeint ist der fehlende Verzug im Kreis im Modelltakt (Kreuzterm, K3). Anker Shardt & Huang 2011 [nur Abstract]. |
| L1-4.6 | bestätigt | korrekt | zusammengelegt | In U48. Proctor 2018 steht in ch3 Z. 749–751 für u = h(x). Die Übertragung auf die Vorsteuerung ist eigene Überlegung. ch3 Z. 636–640 belegt den Rangverlust schon mit proctorDynamicModeDecomposition2016 S. 153. Das Kennfeld hat zwei Eingänge (ch2 Z. 271–273), dazu K4. |
| L2-K6-2 | bestätigt | korrekt | Hauptbefund | U49. ch3 Z. 444–447 bestätigt. Solverliste Z. 420–431 ohne Nebenbedingungen. Eigene Herleitung ch2 Z. 386–425 und 909–934 ergänzt. Vorschlag: Nebenbedingungen einlösen über A18 (Gleichung) und Vorzeichen (Ungleichung). |
| L2-K6-3 | bestätigt | korrekt | Hauptbefund | U50. ch3 Z. 1196–1197 steht im Copilot-Block. Die Einordnung Z. 1122–1174 hat keine Beitragsliste. Die Eigenleistungen sind mit Zeilen belegt (ch2 Z. 790–793 bestätigt). BT1–BT6 nach fester Zuordnung. |
| L2-K6-4 | bestätigt | korrekt | Hauptbefund | U51. Alle elf \textbf{Copilot: …} stehen außerhalb von Kommentaren, per grep bestätigt. Präzisiert: Die Kennzeichnungen ‚eigene Algebra/Reduktion/Umformung‘ (ch2 Z. 392, 553, 611, 825, 920) stehen innerhalb dieser Blöcke. |
| L2-K6-5 | bestätigt | korrekt | Hauptbefund | U52. Algebra per Zahlentest bestätigt (Produkt = ε_LT bei festem r). Präzisiert: Voraussetzung sind ein fester Sollwert und feste Zusatzeingänge (ch2 Z. 259–261). Abgeleitet nach r ist das Produkt 1, das Kennfeld über r − TLT invertiert also nur näherungsweise. Die Obergrenze ≤ 1//∂K/∂x/ gilt in beiden Fällen. |
| L2-K6-6 | korrigiert | korrekt | Hauptbefund | U53. In Z. 407–425 selbst stehen keine Vorzeichen. Ergänzt: Z. 439, 446, 841–842 (λ) und 764–766 (b<1), dazu 288–289. Präzisiert (eigene Algebra): Das Koeffizientenvorzeichen −a_2 ist fest, nur das Vorzeichen der Wirkung hängt von ΔT ab. Nach Einsetzen der LT-Spanne bleiben beide Spalten negativ. Die Vorzeichen zuerst als Prüfung nutzen, weil eine harte Schranke die Umkehr des CL-Gains verdeckt. |
| L1-6.1 | bestätigt | korrekt | weiterer Befund | U54 als ‚Stärke:‘. ch2 Z. 392 und 920 bestätigt, weitere Marker in Z. 434, 553, 611, 651, 825. Kern von Auftrag B, G1 (konvexe Kombination) nachgerechnet. ch2 Z. 555–556 sagt das schon in Worten. Hinweis: Die Marker stehen in Copilot-Blöcken (U51). |
| L1-6.2 | korrigiert | korrekt | weiterer Befund | U55. Die Angabe ‚ch3 Einordnung‘ enthält keinen solchen Text. Es gibt nur den Leerbefund ch3 Z. 1026–1028, die Deutung fehlt in Z. 1122–1174. Kern aus A3.4 übernommen. Präzisiert: Die Deutung gilt nur, wenn \valveCA nicht mit \Tout multipliziert wird. Der Begriff LPV und quasi-LPV ist mit Z. 1027 abzugleichen. Anschluss an BT1. |
| L1-6.3 | korrigiert | korrekt | weiterer Befund | U56. In ch2/ch3 gibt es keinen Textort (grep ‚invarian/verschieb‘). Als Anker gesetzt: ch2 Z. 392–394 und 935–937. Kern aus A3.1 übernommen. Präzisiert per Zahlentest: Der lineare \Tout-Term aus Z. 935–937 bricht die Invarianz, die Konstante nicht. Hängt an A18 und BT6. |
| L1-6.4 | bestätigt | korrekt | weiterer Befund | U57. Leerbefund in ch3 Z. 1024–1026 bestätigt. Der Ideenverweis in L1 ist falsch (Idee 5 statt 4); zugeordnet zu A3. Als Teil von BT4 geführt, nicht als eigener Hauptbeitrag. Die CL-Einschränkung des Kreuzkorrelationstests ist ergänzt (Douma u. a. 2008 [nur Abstract]). |
| L2-K7-1 | korrigiert | korrekt | Hauptbefund | U58. Der sichtbare Rohtext steht in ch3 Z. 764–774, dazu ‚Messdaten.‘ in Z. 775. Z. 757–762 sind Kommentar. Bestätigt: Z. 625 (textbf ohne Backslash), Z. 218 (Fragment) und Z. 506 (Esemble). |
| L1-7.1 | korrigiert | korrekt | zusammengelegt | In U58. Zeilen 760–776 → 764–775. Die Doppelung zu Z. 617–755 ist bestätigt: direkte Methode Z. 656, indirekte Z. 678. |
| L1-7.2 | bestätigt | korrekt | zusammengelegt | In U58. Vorschlag präzisiert: Nur das Fragment ab ‚Der Koopman-Operator …‘ in Z. 218 streichen. ‚DMD ist eng … verbunden.‘ kann als Überleitung bleiben. |
| L1-7.3 | bestätigt | korrekt | zusammengelegt | In U58. ch3 Z. 625 bestätigt. |
| L1-7.4 | bestätigt | korrekt | zusammengelegt | In U58. Z. 552 betrifft nur den Dateinamen und ist im PDF unsichtbar. ‚Identifiaktion‘ in ch2 Z. 296 bestätigt. Das Label closed_loop_identifkation ist in ch3 Z. 618 definiert und wird in ch2 Z. 296 verwendet. Ergänzt: \ref ohne ‚Abschnitt~‘. |
| L2-K7-2 | bestätigt | korrekt | Hauptbefund | U59. Die drei Lesarten von ‚Stufe‘ sind mit Zeilen bestätigt. Alle Fundstellen von ‚Bündel‘ per grep bestätigt (deckt sich mit Auftrag B, T1). Präzisiert: Der ‚HT/LT-Kühler‘ in Z. 200–202 und 221 ist ein eigener Wärmeübertrager und darf beim Ersetzen nicht angefasst werden. |
| L1-7.6 | bestätigt | korrekt | zusammengelegt | In U59. Kern von Auftrag B, T1 übernommen (Vorschlag ‚Kühlerstufe‘, vollständige Zeilenliste). |
| L2-K7-3 | bestätigt | korrekt | Hauptbefund | U60. Alle genannten Zeilen bestätigt. Eine Einzelheit berichtigt: ‚e = Gleichungsfehler‘ stimmt nicht. Der Gleichungsfehler heißt v (ch3 Z. 814–817), e ist das Residuum (ch3 Z. 93). Zeilen für μ, p und q ergänzt. |
| L1-7.7 | bestätigt | korrekt | zusammengelegt | In U60. λ hat sogar vier Bedeutungen (LASSO-Gewicht ch3 Z. 428, 498 kommt dazu). Kern von Auftrag B, T2 (ρ_Δu) übernommen. |
| L2-K7-4 | bestätigt | korrekt | Hauptbefund | U61. Labels und Notizen per grep bestätigt. Ergänzt: Folgen der Labels (ref in Z. 37 zeigt auf den SINDy-Abschnitt, Z. 529 erbt die Nummer von Z. 506), \anno in ch2 Z. 905–907 und die Notiz in ch2 Z. 741. ch2 Z. 549–550 ist nur ein Kommentar. ‚Label einer gestrichenen Tabelle‘ ist nicht prüfbar. |
| L2-K7-5 | bestätigt | korrekt | Hauptbefund | U62. Präzisiert: ch2 Z. 830–831 trennt kA und U_eff A bewusst. Uneinheitlich sind Z. 842 und 929–930 (kA im dynamischen Kontext). Ergänzt: λ(\mrel,·) gegen λ(ṁ_L,·). Die unnummerierte Zweistufenform in Z. 573–577 ist bestätigt. |
| L1-5.1 | bestätigt | korrekt | zusammengelegt | In U62 (K7 statt K5). Präzisiert: Das direkte Gegenstück zu eq.grundlagen.basic.dynamik ist die unnummerierte Relaxation in Z. 854–856. eq.energiebilanz.dyn ist die Bilanz dahinter. Kettenvorschlag mit Auftrag B, G1 übernommen. |
| L2-K7-6 | bestätigt | korrekt | Hauptbefund | U63. Z. 948, 964, 989–990 und 995 bestätigt. Makros ohne {} in ch2 Z. 458 und ch3 Z. 841 bestätigt, sofern kein \xspace verwendet wird. EMEC nach E1.3 (L2) = EMEC-SINDy. Ergänzt: uneinheitliche Schreibweise eDMDc/\edmdc und SINDyc/SINDYc. |
| L1-7.5 | bestätigt | teilweise | zusammengelegt | In U63 (Z. 948, 995). ‚zudem‘ in ch2 Z. 1039 ist eine Stilfrage und kein Fehler. Es steht deshalb getrennt als schwacher weiterer Befund, zusammen mit ch3 Z. 693 und 1116. |

## E1.2 und E1.3

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| E1.2 ch2 89–95 | bestätigt | korrekt | übernommen | Taupunkt Z. 93–94 bestätigt. Magnus nachgerechnet: 3 bar abs 51,50 °C; 4 bar abs 57,45 °C, 3 bar Überdruck 57,5 °C. L2 schrieb rund 57 °C, jetzt rund 57,5 °C mit Hinweis auf die Rundung in E1.1 K3. Folgerung Z. 112–114 ergänzt. Zeile an den Anfang sortiert. |
| E1.2 ch2 330–396 | bestätigt | korrekt | übernommen | Gesamtform und LT-Spanne (Z. 387–391) per Zahlentest bestätigt. Ergänzt: Zuordnung zur EB21-Notiz Z. 316–320 (PH, P3, cFix). |
| E1.2 ch2 398–425 | bestätigt | korrekt | übernommen | Gleichung Z. 404–413; Ventil nur an der LT-Stufe (Z. 359, 553) bestätigt. Zeichen ε_L gibt es in der Arbeit nicht, ersetzt durch 0 ≤ ε ≤ ε_Q ≤ 1 nach Z. 591. |
| E1.2 ch2 427–448 | bestätigt | korrekt | übernommen | λ = c_λ·mrel steht in Z. 446, τ-Formel in Z. 834–835 (L2: 835). λ_0 = U_eff A/C_eff nachgerechnet. Euler-Pol 1 − Δtλ geprüft; ergänzt: kein Vorzeichenwechsel nur bei Δtλ ≤ 1. |
| E1.2 ch2 539–546 | bestätigt | korrekt | übernommen | Gegenstrom bei C_r = 0,9999 ergibt N/(1+N), bei C_r → 0 ergibt 1 − e^−N (Zahlentest). Einzustandsstatik in Z. 848–850 verortet; Hinweis: U_eff A ist nicht kA (Z. 830–831). |
| E1.2 ch2 568–577 | bestätigt | korrekt | übernommen | Unnummerierte Form Z. 573–577; w1 + w2 + w3 = 1 und alle ≥ 0 nachgerechnet. Stützt Z. 555–556. Hinweis auf „Bündel“ in Z. 551–558 ergänzt. |
| E1.2 ch2 643–716 | bestätigt | korrekt | übernommen | Umstellungen und q_rel = mrel·√(T/T_ref) nachgerechnet; Endogenität ṁ_proxy = ṁ·√(T_m/T_in) per Zahlentest bestätigt. Relative Empfindlichkeit ½ dT_m/T_m als eigene Algebra ergänzt. |
| E1.2 ch2 775–802 | bestätigt | korrekt | übernommen | Gl. Z. 796–802 einstufig; zweistufige Kettenregel per finiter Differenz bestätigt, w3 = (1−ε_HT)(1−ε_LT). Copilot-Stichpunkt Z. 806–811 enthält den richtigen partiellen Term. |
| E1.2 ch2 834–840 | bestätigt | korrekt | übernommen | Nenner ṁc_p + kA/2 und ε = 2N/(2+N) nachgerechnet (N = 3 ergibt 1,2). |
| E1.2 ch2 910–920 | bestätigt | korrekt | übernommen | Umformung a·d − b·Spanne gegen die Bilanz nachgerechnet; b/a = N/(1+N) = ε_stat, 1/a = τ. |
| E1.2 ch2 1036–1038 | korrigiert | korrekt | übernommen | Aussage steht in Z. 1037–1038. Widerspruch zu Z. 279–281 und 742 bestätigt; ergänzt: „nahezu linear“ (Z. 279–281) und „linear“ (Z. 742) weichen voneinander ab. |
| E1.2 ch2 1046–1059 | bestätigt | korrekt | übernommen | e = r − y in Z. 1048, K_c ohne Vorzeichen; negative Streckenverstärkung laut Z. 288–291 und 781; Z. 1056–1057 gegen Z. 273–274 bestätigt. |
| E1.2 ch2 1061–1082 | bestätigt | korrekt | übernommen | argmin nur über Δu (Z. 1066), s_k fehlt; keine Regel Δu_k = 0 ab N_u, keine Ratengrenze, keine Endkosten. QP-Aussage in Z. 1080–1082. „siehe K1“ zu „siehe E1.1 K1“ gemacht. |
| E1.2 ch3 63–98 | bestätigt | korrekt | übernommen | ‖·‖²_2 in Z. 68 für Matrizen; Pseudoinverse über die Normalgleichungen in Z. 76–77. |
| E1.2 ch3 126–141 | korrigiert | korrekt | übernommen | Auf Z. 134–137 präzisiert (σ_j = 0 in Z. 136). Begründung ergänzt: Zentrieren macht aus der konstanten Spalte eine Nullspalte. |
| E1.2 ch3 143–147 | bestätigt | korrekt | übernommen | Aussage in Z. 145. |
| E1.2 ch3 241–262, 265, 293 | korrigiert | korrekt | übernommen | Präzisiert auf Z. 246–255, 265 und 293–294. Zahlentest: X1·X0⁺ ist die transponierte LS-Lösung mit Θ = X0ᵀ. Neu (bei der Zusammenführung geprüft): N steht in Z. 243 für die Zustandsdimension, in Z. 247–248 für die Zahl der Snapshots. |
| E1.2 ch3 339–366 | bestätigt | korrekt | übernommen | Gleichung Z. 343–347 ohne Bu-Term; Begründung in Z. 360–366. „siehe K3“ zu „siehe E1.1 K3“ gemacht. |
| E1.2 ch3 369–383 | korrigiert | korrekt | übernommen | Delays und Takens in Z. 375–383, Takens-Satz in Z. 378–380. Verweis auf Stark 1999 in E1.3. |
| E1.2 ch3 421–430, 495–500 | korrigiert | korrekt | zusammengelegt | Präzisiert auf Z. 426–428 und 496–498; STLSQ Z. 421–425 ohne Rechenfehler. Mit L1-3.4 zusammengelegt (Norm ungequadratet). Vorschlag für die Form je Zustandsspalte ergänzt. Neu: λ ist viermal belegt (ch3 Z. 423, 428/498; ch2 Z. 437–446, 1068). |
| E1.2 ch3 529–548 | korrigiert | korrekt | übernommen | map-Form steht in Z. 543–547; Z. 529 ist nur das Label. Per Zahlentest bestätigt: gleiches Ξ wie bei der Vorwärtsdifferenz. |
| E1.2 ch3 633–646 | korrigiert | korrekt | übernommen | Aussage „mittelwertfrei genügt“ in Z. 642–645; Präzisierung auf Z. 642–646. |
| E1.2 ch3 657–671 | korrigiert | korrekt | übernommen | Präzisiert auf Z. 662–671 (Bias Z. 662–665, „davon unabhängig“ Z. 665–666, −K⁻¹ Z. 668–671). Statischer Zahlentest ohne Verzug: ĝ − g0 = −(1+g0K)/K·Φ_u^e/Φ_u, geht gegen −1/K, also Grenzfall bestätigt. Die Forssell/Ljung-Formel ist ohne Original nicht prüfbar. |
| E1.2 ch3 674–676 | bestätigt | korrekt | übernommen | HO-ARX in Z. 674–676; Kern aus L2-K4-2 kurz angegeben, „siehe E1.1 K4“. |
| E1.2 ch3 789–804, 825–832 | bestätigt | korrekt | übernommen | Gl. Z. 791–795 und die Form mit Vorsteuerung und Störgrößen nachgerechnet. Verweis auf das Reglervorzeichen ergänzt. |
| E1.2 ch3 806–823 | bestätigt | korrekt | übernommen | Gl. Z. 810–815; Kreuzterm Z. 822–823; Kurzfassung des K3-Befunds ergänzt. |
| E1.2 ch3 845–859, 893–897 | bestätigt | korrekt | übernommen | PE ohne Mittelwertabzug in Z. 847–848: r_u(0) = 0 bei u = 0, > 0 bei u = c. Ventil zu nach ch2 Z. 290–291. Kollinearität von g(u_sat)·ΔT und ΔT bestätigt. |
| E1.3 ch3 Z. 323–325 | bestätigt | korrekt | zusammengelegt | Key in Z. 323 (und Z. 1004). Mit L1-3.2 zusammengelegt. Verweis auf den eingeschränkten Beleg durch Korda & Mezić JNS aus dem zweiten Prüflauf ergänzt. |
| E1.3 ch3 Z. 303–307 | bestätigt | teilweise | übernommen | Key in Z. 307. Von „gestützt“ auf „teilweise“ herabgestuft: Der zweite Prüflauf sah im Abstract von Korda & Mezić JNS nur die Konvergenz für N → ∞ (Observablen), nicht die Aussage für M → ∞ (L²(μ)-Projektion) und nicht die Einschränkung auf autonome Systeme. |
| E1.3 ch3 Z. 600–603 | bestätigt | korrekt | übernommen | Key in Z. 603. Metadaten im zweiten Prüflauf bestätigt, Heft 2219 und DOI ergänzt. Champion 2019 laut zweitem Lauf nur indirekt. |
| E1.3 ch3 Z. 608–610 | korrigiert | teilweise | übernommen | Um Z. 326–327 erweitert (gleiche Überzeichnung zu Bold). Abdullah 2021: „Lyapunov-MPC“ im zweiten Lauf nicht gesehen, ersetzt durch singuläre Störungstheorie. „Proportionale Fehlerschranken“ Schimperna/Bold zugeordnet, nicht Nüske. |
| E1.3 ch3 Z. 353–356 | bestätigt | nicht prüfbar | übernommen | Key in Z. 353. Nicht im zweiten Prüflauf; Inhalt nur aus L2. |
| E1.3 ch3 Z. 357–359, 1103–1111 | bestätigt | teilweise | übernommen | Key in Z. 357 und 1111. Die von L2 gelesene Closed-Loop-Herkunft der Daten hat der zweite Prüflauf nicht gesehen, als ungeprüft markiert. Autorenliste ergänzt. |
| E1.3 ch3 Z. 381–383 | bestätigt | nicht prüfbar | übernommen | Key in Z. 381. Key-Inhalt nicht im zweiten Prüflauf. Kamb 2020 laut zweitem Lauf nur teilweise stützend, Vergleich mit Monomen nicht gesehen. |
| E1.3 ch3 Z. 378–380 | bestätigt | teilweise | übernommen | Takens: Endseite 381 im zweiten Lauf nicht gesehen, jetzt „ab S. 366“. Stark 1999 bestätigt. Die Zahl 2d+1 ist ohne Beleg und am Original zu prüfen. |
| E1.3 ch3 Z. 444–447 | bestätigt | korrekt | übernommen | Key in Z. 445. Zweiter Lauf bestätigt Abstract und JFM 838, 42–67; DOI nicht gesehen. Dimensionstreue in Z. 447–449. |
| E1.3 ch3 Z. 30, 449–450 | korrigiert | korrekt | übernommen | Key in Z. 30 und 450; Buckingham-Halbsatz Z. 448–450. Zweiter Lauf: Nielsen 2025 hat keinen Autor Wulff. Bakarji: DOI und Seiten nicht unabhängig gesehen. |
| E1.3 ch3 Z. 666–671 | korrigiert | korrekt | übernommen | Key in Z. 667 (Kommentar mit „Theorem 1“) und 671; Stelle auf 667–671. DOI aus dem zweiten Lauf ergänzt. Shardt & Huang Automatica: DOI nicht bestätigt. Söderström & Stoica nur bibliografisch. |
| E1.3 ch3 Z. 624–628 | korrigiert | korrekt | übernommen | Key in Z. 626 (auch 754, 1015); Stelle auf 625–628, dazu Z. 752–754. Laut zweitem Lauf steht „Nebenbedingung“ nicht wörtlich im Abstract. Querverweise auf L1-3.6 (E1.1 K3) und textbf (E1.1 K7). |
| E1.3 ch3 Z. 956–958 | bestätigt | korrekt | übernommen | Key in Z. 194, 607 und 956. Seiten und DOI auch im zweiten Lauf nicht gesehen. |
| E1.3 ch3 Z. 976–982 | bestätigt | korrekt | übernommen | Key in Z. 976; Band und Seiten im zweiten Lauf nicht gesehen. Z. 980–981 trifft nur Baum und Random Forest, ergänzt. |
| E1.3 ch3 Z. 998–1003 | bestätigt | teilweise | übernommen | Keys in Z. 999 und 1000. Meda: Rangfolge Polynom/RBF vor NN im zweiten Lauf nicht gesehen, Autoren nicht gesehen. Zinage: im Abstract „Experimentaldaten“ statt „Prüfstandsdaten“; Metadaten offen. |
| E1.3 ch3 Z. 1141–1144 | bestätigt | korrekt | übernommen | Key in Z. 1144. Hinweis ergänzt: Closed-Loop-Herkunft der Yahagi-Daten nicht belegt. |
| E1.3 ch3 Z. 1144–1147 | bestätigt | korrekt | zusammengelegt | Satz in Z. 1144–1147. Mit L1-3.7 zusammengelegt. Neue Quellen im zweiten Lauf bestätigt (nur Abstract); Wirgin als Preprint. |
| E1.3 ch3 Z. 993–996 | bestätigt | teilweise | übernommen | Key in Z. 996 (auch 458). Band 66(11) von OASIS 2020 im zweiten Lauf nicht gesehen, entfernt. Autorenreihenfolge OASIS-P ungeklärt. Neu: Z. 457–458 geprüft. |
| E1.3 ch3 Z. 986–987 | korrigiert | korrekt | übernommen | Keys in Z. 986–987; „PKW“ und „regelbasiert“ stehen in Z. 989, Stelle daher 986–990. IJCAS-, TCYB- und EMEC-Metadaten im zweiten Lauf bestätigt; das Preprint-Jahr 2025 erklärt das Jahr im yonezawa-Key. Beide Keys fehlen in thesis_keys.txt, weil das Zitat über zwei Zeilen läuft; in ch3 vorhanden. |
| L1-3.2 | bestätigt | korrekt | zusammengelegt | In E1.3, Zeile ch3 Z. 323–325, eingearbeitet: Umformulierung und Hinweis zur Prüfung am Original mit (L1) bzw. (L1+L2) markiert. |
| L1-3.4 | bestätigt | korrekt | zusammengelegt | L1 nannte Z. 426–430 und 496–498; in der Zusammenführung Z. 426–428 und 496–498. In E1.2, Zeile ch3 Z. 426–428, eingearbeitet; Vorschlag „quadriert vereinheitlichen“ übernommen. |
| L1-3.7 | bestätigt | korrekt | zusammengelegt | L1 nannte Z. 1144–1146, der Satz reicht bis Z. 1147. In E1.3, Zeile ch3 Z. 1144–1147, eingearbeitet: Begrenzung auf die Übertragbarkeit und Hinweis auf das Fach des Erstgutachters (L1), Trennung Validierung/Verifikation (L2). |

## E1.4 Verteidigungsfragen

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L1-Frage 1 | keine Zeilenangabe | korrekt | zusammengelegt | Mit L2-F1 zu F1 (H) zusammengelegt. Verweis 'Auftrag D, Frage 1' aufgelöst: SINDy wählt Terme statt Moden, EDMD ist Galerkin-Projektion, kein ROM im klassischen Sinn, näher an sensorbasierten Modellen; Shift-Mode entspricht Beobachter-Offset nur als eigene Einordnung. L1-Deutung 'Projektion auf eine Mode' mit L2-Rührkessel-Algebra in einem Stichpunkt vereint (Verweis D12). |
| L1-Frage 2 | keine Zeilenangabe | korrekt | zusammengelegt | Mit L2-F2 zu F2 (H). 'Bezug EMA: Auftrag D, Frage 4' aufgelöst: stationärer Kalman-Filter = exponentielle Glättung, alpha = L, L²/(1−L) = q/r (gegen D-Anhang nachgerechnet). Pannocchia 2015 (ECC, Entwurf aus B) als nicht gegengeprüft markiert. |
| L1-Frage 3 | bestätigt | korrekt | zusammengelegt | ch3 Z. 201–205 geprüft. Mit L2-F7 zu F7 (M). Entwurfs-Keys billings…2013, piroddi…2003, aguirreBirdsEyeView2019 als Autor Jahr; Aguirre 2019 als arXiv-Preprint, nicht gegengeprüft. L1 (Bibliothek aus Kühlerphysik) und L2 (vordefinierte Bibliothek trennt nicht) als Inhalts- gegen Verfahrensunterschied getrennt. |
| L1-Frage 4 | bestätigt | korrekt | zusammengelegt | Gl. eq.grundlagen.cl.bias (ch3 Z. 810–815) und ch3 Z. 922–925 geprüft. Mit L2-F4 zu F4 (beide). Wu 2026 (Preprint) aus Auftrag D, Frage 3 als Stichpunkt ergänzt. |
| L1-Frage 5 | keine Zeilenangabe | korrekt | zusammengelegt | Mit L2-F8 zu F8 (M). 'E3 Idee 3' auf A5 umgestellt. Entwurfs-Keys farina…2010, somalwar…2025, ribeiro…2018 als Autor Jahr; Farina & Piroddi 2010 und Somalwar u. a. 2025 (Preprint) nicht gegengeprüft. Inhalt aus Auftrag B, B2.5 übernommen. |
| L1-Frage 6 | bestätigt | teilweise | zusammengelegt | ch3 Z. 363–366 geprüft. 'Bilineares eDMDc verliert den QP' stimmt nur für Stellgröße × Zustand; für die Ladeluftstrecke ist die Spanne exogen (ch2 Z. 929–934), ein LTV-QP bleibt (L2-K3-3). In F3 (beide) mit L2-F3 zusammengelegt und die Fallunterscheidung ergänzt. cisneros…2016 als Cisneros, Voss, Werner 2016. |
| L1-Frage 7 | keine Zeilenangabe | korrekt | weiterer Befund | Unter 'Weitere Fragen'. 'E3 Idee 7' auf S5 umgestellt. Bezug ch3 Z. 608–610 und ch2 Z. 1064–1070 ergänzt und geprüft: Gl. eq.grundlagen.mpc hat keine Endkosten (als Zusammenführung markiert). kaptanoglu…2021 als Kaptanoglu u. a. 2021. |
| L1-Frage 8 | bestätigt | korrekt | zusammengelegt | ch3 Z. 520–524 geprüft. Mit L2-weitere 5 unter 'Weitere Fragen' zusammengelegt. 'Auftrag D, Frage 6' aufgelöst: Hyperparameter nur auf Auswahldaten (Cawley & Talbot 2010), gepaarter Vergleich (Diebold & Mariano 1995, Künsch 1989). Ideen S3, S4. |
| L1-Frage 9 | keine Zeilenangabe | korrekt | zusammengelegt | Mit L2-F6 zu F6 (H). 'Auftrag D, Frage 5' aufgelöst: Skelton 1989, Gevers 2005, Hjalmarsson 2005, Li & Lee 1996 (Skelton und Li & Lee nicht gegengeprüft). K = b/(1−a) und Empfindlichkeit a/(1−a) aus Auftrag B, B2.4 nachvollzogen. skogestad…2005 als Skogestad & Postlethwaite 2005. |
| L1-Frage 10 | bestätigt | korrekt | zusammengelegt | ch2 Z. 125–126 (Prüfkommentar zum Band der 51/60DF-Flotte) geprüft. Mit L2-weitere 2 unter 'Weitere Fragen' zusammengelegt. quade…2018 als Quade u. a. 2018; Ideen D3, D4, D9 zugeordnet. |
| L2-F1 | bestätigt | korrekt | zusammengelegt | ch3 Z. 27–41, 444–450 und ch2 Z. 825–865, 860–865 geprüft; ch3 Z. 303–312 als Bezug ergänzt. Mit L1-Frage 1 zu F1. Grenzfall n → ∞ gilt bei fester Wassertemperatur; so ergänzt. |
| L2-F2 | bestätigt | korrekt | zusammengelegt | ch2 Z. 1082–1091 und ch3 Z. 909–925 geprüft. Mit L1-Frage 2 zu F2. Rangbedingungen nachgerechnet (Determinante 1−a bzw. b); 'stationärer Gain ≠ 0' zu 'B ≠ 0' präzisiert. |
| L2-F3 | bestätigt | teilweise | zusammengelegt | ch2 Z. 1034–1041, 1111, 206–219 und ch3 Z. 1202–1204 geprüft. Korrigiert: 'ChATCo schaltet die Störgrößen über das Kennfeld auf' ist zu weit, das Kennfeld nutzt nur relative Leistung und Sollwert − TLT (ch2 Z. 271–274); in Frage und Stichpunkt präzisiert. Mit L1-Frage 6 zu F3 (beide). T_col,in usw. auf Makros umgestellt; Odelson 2006 steht nur noch in F2. |
| L2-F4 | bestätigt | korrekt | zusammengelegt | ch3 Z. 654–721, 681–682, 696–700, 764–775, 869–875 und ch2 Z. 237 (52 °C) geprüft. Mit L1-Frage 4 zu F4. Prüflauf-Hinweis ergänzt: Chiuso 2007 ist nicht als Erstdefinition von PBSID belegt (Notiz ch3 Z. 692). |
| L2-F5 | bestätigt | korrekt | übernommen | ch3 Z. 1141–1147, 1145–1146, 922–925 geprüft. Als F5 (H) übernommen. Hjalmarsson-Aussage stand wie ein wörtliches Zitat in Anführungszeichen; als Paraphrase des Abstracts umformuliert. Zeile 'Heute dünn' fehlte, aus L1-3.7 ergänzt. |
| L2-F6 | bestätigt | korrekt | zusammengelegt | ch2 Z. 264–268, 781–793, 1061–1082 geprüft. Mit L1-Frage 9 zu F6. Stichpunkt 'bekannter Koeffizient, LTV-QP' nach F3 verschoben; Vorzeichen-Stichpunkt aus L2-K3-4 ergänzt (ch3 Z. 668–671 geprüft); Prüfhinweis zu Maciejowski 2002 aus verifiziert.json. |
| L2-F7 | bestätigt | korrekt | zusammengelegt | ch3 Z. 197–205, 411–431 geprüft. Mit L1-Frage 3 zu F7. Prüfhinweis ergänzt: ERR-Auswahl bei Chen, Billings, Luo 1989 im Abstract-Auszug nicht gesehen. |
| L2-F8 | bestätigt | teilweise | zusammengelegt | ch3 Z. 42–49, 519–526 und ch2 Z. 999, 1061–1073 geprüft. Korrigiert: 'Bei 500-ms-Takt' setzt den Modelltakt mit dem ChATCo-Takt (ch2 Z. 275) gleich; der MPC-Takt steht laut ch2 Z. 1088–1091 in sec.methodik.mpc, nicht in kontext/. Mit L1-Frage 5 zu F8. |
| L2-F9 | bestätigt | korrekt | übernommen | ch3 Z. 806–823, 1024–1029 geprüft. Als F9 (M) übernommen; letzter Stichpunkt um L1-6.4 und L1-Idee 4 (A3) ergänzt. |
| L2-F10 | bestätigt | korrekt | übernommen | ch3 Z. 845–889 und ch2 Z. 270–274, 398–419 geprüft. Als F10 (M) übernommen; Stichpunkte aus L1-4.6 (Proctor-Beleg passt nur mittelbar, ch3 Z. 877–884) und L2-K4-3 (drei Fälle) ergänzt. |
| L2-weitere 1 | keine Zeilenangabe | teilweise | weiterer Befund | Bezug ch3 Z. 303–307, 323–325 ergänzt und geprüft. Die 'Reglermannigfaltigkeit' ist eine eigene Folgerung und nicht durch den Abstract von Korda & Mezić 2018 gedeckt; Datenmaß und Beschränkung auf autonome Systeme wurden laut verifiziert.json nicht gesehen. Mit L1-3.2 (Überzeichnung in ch3 Z. 323–325) ergänzt. |
| L2-weitere 2 | keine Zeilenangabe | korrekt | zusammengelegt | Mit L1-Frage 10 unter 'Weitere Fragen' zusammengelegt; Bezug ch2 Z. 722 und ch3 Z. 1170–1173 ergänzt und geprüft. |
| L2-weitere 3 | keine Zeilenangabe | korrekt | weiterer Befund | Bezug ch3 Z. 1161–1174 ergänzt und geprüft: Dort stehen nur Interpretierbarkeit und Übertragbarkeit als Gründe, nicht die QP-Tauglichkeit. Aussage aus Auftrag D, Frage 6 ergänzt (Feedforward-Netze sind NARX-Modelle, Ljung u. a. 2020, nicht gegengeprüft). |
| L2-weitere 4 | keine Zeilenangabe | korrekt | weiterer Befund | Frage wörtlich formuliert; Bezug ch2 Z. 264–268, 275, 860–868 und ch3 Z. 899–905 ergänzt und geprüft; mit L1-4.2 (Verhältnis Reglertakt zu Modelltakt) ergänzt. Ideen A9, A15. |
| L2-weitere 5 | keine Zeilenangabe | korrekt | zusammengelegt | Mit L1-Frage 8 unter 'Weitere Fragen' zusammengelegt (zeitreihengerechte Kreuzvalidierung, Bergmeir & Benítez 2012; Bergmeir, Hyndman, Koo 2018). |

## E2.1 Beiträge

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L1-Beitrag 1 | bestätigt | teilweise | zusammengelegt | ch3 Z. 1094-1102 geprüft (NMPC am simulierten Mittelwertmodell). QP- und LPV-Teil geht in BT1 ein, der Bibliotheksteil (A3.3) in BT3. 'Affin in Zustand und Ventilfunktion' trägt nur, wenn das Ventil allein im Zielwert steht und g(valveCA) linear bzw. virtuelle Stellgröße ist; das ist ergänzt. Cisneros u. a. 2016 ist im Prüflauf bestätigt. Sheikh u. a. 2024 und die SQP-Aussage zu Kaiser 2018 ('laut Autoren-Code') sind als nicht gegengeprüft markiert. Die Gegenposition Koelewijn u. a. 2024 aus A3.4 ist ergänzt. |
| L1-Beitrag 2 | bestätigt | teilweise | zusammengelegt | ch3 Z. 1018-1029 und 1138-1147 geprüft; der Leerbefund trägt (A3.5 und L2 E2.3). Als Alleinstellung sind Messdaten allein zu schwach: Rupprecht (ch3 Z. 1048-1050) und Vagapov 2022 (ch3 Z. 1058-1060) arbeiten mit Messungen. ch3 Z. 1140-1142 und die Zirkularität in ch3 Z. 1144-1147 sind überzogen (E1.1 K3, E1.3). Der Punkt ist in BT3 aufgegangen. |
| L1-Beitrag 3 | bestätigt | teilweise | zusammengelegt | ch3 Z. 1024-1027 geprüft. Der Leerbefund zu den Residuentests ist eine Validierungslücke (Idee A3) und keine Lücke des Gain-Kriteriums; so ist er in BT4 gekennzeichnet. Verweis Auftrag D, Frage 5 aufgelöst: Gevers 2005 und Hjalmarsson 2005 sind im Prüflauf bestätigt, Skelton 1989, Li/Lee 1996 und Darby/Nikolaou 2009 tragen 'L1, nicht gegengeprüft'. B2.4 (K = b/(1-a), Empfindlichkeit a/(1-a)) ist übernommen. |
| L1-Beitrag 4 | bestätigt | korrekt | zusammengelegt | ch3 Z. 626-627 und 752-754 geprüft; Dahdah setzt einen bekannten Regler voraus, laut Prüflauf passt auch der Abstract. Die Dreiteilung aus ch3 Z. 909-925 ist als Anker ergänzt. Die Einschränkung zum Modussprung (Ventil im Dieselbetrieb bei 100 %, ch2 Z. 288-289; E1.1 K4) ist aus L1-Befund 4.1 übernommen. Der Punkt ist mit L2-BT2 zu BT2 zusammengelegt. |
| L1-Beitrag 5 | keine Zeilenangabe | teilweise | übernommen | Übernommen als BT6, ausdrücklich nur als Kandidat, der an A18 hängt. Die Aussage 'Bibliothek mit freiem Absolutterm nicht invariant' gilt für ein festes Modell mit verschobenen Eingängen. Bei einer LS-Neuschätzung mit Konstante verschiebt sich die Vorhersage exakt (Zahlentest a18_check.py, A18 Variante b). Gegenstellen: ch2 Z. 935-937 lässt einen linearen Tout-Term zu, und mrel enthält die absolute Temperatur (ch2 Z. 664-691). Auflösung der Verweise: B G1 ist sympy-geprüft; Otto u. a. und Zar 1968 aus A3.1 sind nicht gegengeprüft. Die L1-Aussage zur Zentrierung ist nach E1.1 K4 eingeschränkt. |
| L2-BT1 | bestätigt | korrekt | zusammengelegt | ch2 Z. 929-934 geprüft, das Zitat stimmt. Grundlage von BT1. Zu Cisneros u. a. 2020: Laut Prüflauf lässt der Abstract die Scheduling-Größen offen; deshalb ist Cisneros 2016 (Zustandstrajektorie, bestätigt) als Beleg für zustandsabhängiges Scheduling vorangestellt. Pan/Li 2024 (McCormick-Konvexifizierung) und Ripa u. a. 2025 sind im Prüflauf bestätigt. Ergänzt: der Leerbefund ch3 Z. 1026-1028, die Nachbarn Zhang 2022 und Kaleli 2020 sowie die Exogenitätsgrenze (ch2 Z. 777-780). |
| L2-BT2 | keine Zeilenangabe | korrekt | zusammengelegt | L2 nennt nur Keys mit Seiten. Bei der Zusammenführung an ch3 gefunden: Z. 634 (S. 713), 638 (S. 153), 655, 863 und 871 (Abschn. 13.4). Wu 2026 (arXiv 2605.17966) und 'MPC closed-loop identification without excitation' (Autoren nicht gesehen) sind im Prüflauf bestätigt. Ergänzt: Yahagi 2026 als nächster Nachbar mit CL-Daten (ch3 Z. 1106-1109); laut E1.3 trägt der Abstract die CL-Herkunft nicht. |
| L2-BT3 | keine Zeilenangabe | korrekt | zusammengelegt | Die Beschreibungen der Keys passen zu ch3 Z. 1094-1111 und 1044-1068. EMEC-SINDy (arXiv 2503.05154) ist bestätigt; bei Paniccia u. a. 2025 hat der Prüflauf die Venue korrigiert (Aeronautical Journal). Ergänzt aus L1: Akan-Arbeit als nächster Treffer (Titel bestätigt, Autoren im Prüflauf nicht gesehen). Ergänzt aus E1.1: Loiseau-Prinzip, Grey-Box-Widerspruch ch3 Z. 36-41 und Linearität in den Parametern (ch2 Z. 604-619 gegen ch3 Z. 573-575). |
| L2-BT4 | keine Zeilenangabe | teilweise | zusammengelegt | Zu Tufa/Ka 2016: Laut Prüflauf geht die Folgerung 'Gain als MPC-Gütegröße etabliert' über den Abstract hinaus; in BT4 abgeschwächt und gekennzeichnet. Badwe u. a. 2009 und Gevers 2005 sind bestätigt. lovland ist an ch3 Z. 667-671 gefunden. Ergänzt: zweistufige Gain-Form (E1.2) und Mitbewegung in der DoE-Sekante (E1.1 K4). Zusammengelegt mit L1-Beitrag 3. |
| L2-BT5 | keine Zeilenangabe | korrekt | übernommen | bruntonModernKoopmanTheory2022 S. 305-306 an ch3 Z. 327-331 gefunden; arXiv 2605.18720 ist bestätigt (Autoren nicht gesehen). Ergänzt: Daráš u. a. 2026 (bestätigt) und Vega-Zambrano 2025 (L1, nicht gegengeprüft). Die L2-Empfehlung 'ch3 Z. 1196-1197 ersetzen' ist geprüft: Der Satz steht im Copilot-Block ch3-16 (ch3 Z. 1176-1213), nicht im Fließtext der Einordnung (ch3 Z. 1122-1174). Deshalb wird die Liste als Absatz nach ch3 Z. 1159 empfohlen. |

## E2.2 und E2.3 Verwandte, Leerbefunde

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| Vagapov u. a. 2022 | korrigiert | korrekt | zusammengelegt | L1 nannte ch3 Z. 1058–1068; der Eintrag beginnt in ch3 Z. 1057, daher 1057–1068. Inhalt nach ch3, nicht neu geprüft. 'Pkw-Kühler' stammt aus L2 und steht nicht in ch3. |
| Vagapov 2024 | bestätigt | korrekt | zusammengelegt | ch3 Z. 1069–1081 bestätigt. L1 und L2 inhaltlich gleich; die Abgrenzungen beider Läufe zusammengeführt. |
| Beran, Gärtner, Koch 2021 | bestätigt | korrekt | zusammengelegt | ch3 Z. 976–982 bestätigt. Prüflauf Nr. 21 bestätigt. Begleitbeitrag vom Motorenkongress (Nr. 22, korrigiert) ergänzt: Messungen am Motor dienen dort nur als Benchmark der Simulation. |
| JMSE 2026 Art. 845 (Charge-Air Cooler, Large Marine Diesel) | bestätigt | teilweise | übernommen | Nur L2. Die L2-Tabelle sagt 'vor allem Ansauglufttemperatur', das Prüflauf-Abstract (Nr. 79) sagt 'vor allem Ansaugluftfeuchte'. Den Widerspruch in der Zelle benannt. Feuchte passt zu ch2 Z. 952–955 (Arava, Kondensation). |
| Choi, Yoon, Kim, Ham 2026 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Prüflauf Nr. 100 bestätigt. |
| Zhang, Amini u. a. 2022 (ACC, arXiv 2202.12803) | keine Zeilenangabe | korrekt | zusammengelegt | In L1 und L2 unabhängig gefunden, dient als Positivkontrolle für E2.3 Zeile 1. Prüflauf Nr. 99 hat die Autorenliste vervollständigt. Die Angabe zur Wandtemperaturdynamik stammt aus L1 (G). |
| Kaleli 2020 | keine Zeilenangabe | korrekt | zusammengelegt | In L1 und L2 unabhängig gefunden (Positivkontrolle). L1 hatte nur die PII; die DOI aus dem Prüflauf Nr. 160 stand nur im Zusammenfassungstext. Koautoren und Band offen. |
| Patil, Theotokatos, Tsitsilonis 2025 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Prüflauf Nr. 101 korrigiert (Autoren, Jahr). |
| Yahagi u. a. 2025 IJCAS (yahagiSparseIdentificationNonlinear2025) | bestätigt | teilweise | zusammengelegt | ch3 Z. 1094–1102 bestätigt. 'Simulation' steht nur in ch3 Z. 1100–1101, nicht im Prüflauf-Auszug. Widerspruch bei der Key-Zuordnung: Auftrag A vermutet arXiv 2503.05154, L2 und der Inhalt von ch3 passen zu IJCAS. |
| Yahagi u. a. 2026 bilineares Koopman (arXiv 2602.15422) | bestätigt | teilweise | zusammengelegt | ch3 Z. 1103–1111 bestätigt. 'Serien-PID' steht nur in ch3 Z. 1106–1107; der Prüflauf (Nr. 36) sah keine CL-Herkunft. Autorenliste korrigiert. |
| Yahagi u. a. 2025 EMEC-SINDy (arXiv 2503.05154) | bestätigt | korrekt | zusammengelegt | L2-Tabelle und Auftrag A (A3.5). Key vermutlich yahagiSparseIdentificationNonlinear ohne Jahr (ch3 Z. 986), dazu 'EMEC-nahe' in ch3 Z. 995. Prüflauf Nr. 35 bestätigt. |
| Yonezawa u. a. 2026 SINDy-LOM (IEEE TCyb) | bestätigt | korrekt | zusammengelegt | L1 führte die Arbeit als 'Yonezawa u. a. 2025 (Bib)', L2 als TCyb 2026. Es ist dieselbe Arbeit (arXiv 2507.18220). Key yonezawaSparseIdentificationNonlinear2025 in ch3 Z. 987, Zuordnung vermutet. |
| Zinage u. a. 2022 | bestätigt | korrekt | zusammengelegt | Zitiert in ch3 Z. 1000. Prüflauf Nr. 26 bestätigt; Autoren, Band und DOI dort nicht gesehen. Turbinengrößen aus L1 (G). |
| Paniccia u. a. 2025 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Prüflauf Nr. 130 korrigiert. |
| Grasev 2026 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 131 korrigiert. Jahr: 2025 laut DOI, 2026 laut Heft. |
| Valábek u. a. 2026 CEP (Deep Koopman MPC, experimentell) | keine Zeilenangabe | nicht prüfbar | übernommen | L2, †, nicht gegengeprüft. |
| Valábek, Horváthová, Klaučo 2025 (arXiv 2511.04437, EMPC) | keine Zeilenangabe | nicht prüfbar | zusammengelegt | Steht in der L1-Tabelle und in der L2-†-Liste (nicht in der L2-Tabelle). N=3 bei der Zusammenführung vergeben. Verhältnis zur CEP-Fassung 2026 offen. |
| Valábek u. a. 2026 SSRN 7493739 | keine Zeilenangabe | nicht prüfbar | übernommen | L2, †. Die Datenangabe 'laut Prüflauf offen' zu 'offen' korrigiert, weil ein †-Eintrag keinen Prüflauf hatte. |
| Daráš, Valábek, Klaučo 2026 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 159 korrigiert (Autoren). |
| Pan, Li 2024 (Kälteanlage, Koopman-Bilinearform) | keine Zeilenangabe | korrekt | zusammengelegt | L2-Tabelle und Auftrag A (A3.5, gleiche PII). Nr. 114 bestätigt; die DOI stand nur im Suchtext. |
| Ripa u. a. 2025 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 113 korrigiert (Autoren). |
| Cisneros, Datar, Göttsch, Werner 2020 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 108 bestätigt. Datenangabe präzisiert: Experiment am 3-DOF-Steuermomentkreisel. |
| Lin, Oncken, Agarwal 2024 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 129 bestätigt. |
| Abdullah, Christofides 2023 (CERD) | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 133 korrigiert. |
| Akan u. a. 2024 / Model Discrepancy Learning for HEN | keine Zeilenangabe | korrekt | zusammengelegt | Die Identität ist über die gleiche PII S2405896324011005 in Auftrag A und im Prüflauf Nr. 165 gesichert. Autoren und Band nur L1 (S), im Prüflauf nicht gesehen. Fouling ist laut Prüflauf nur ein Beispiel. Ob die Messdaten von einer realen Anlage stammen, ist offen. |
| Vega-Zambrano u. a. 2025 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur L1 (G/S), nicht gegengeprüft, N=3 neu vergeben. In E2.3 Zeile 9 als weiterer naher Modellklassenvergleich aufgeführt. |
| Miyashita, Susuki, Ishigame 2022 | keine Zeilenangabe | nicht prüfbar | zusammengelegt | L1-Tabelle (G: DOI, Seiten), Auftrag A (T) und die L2-†-Liste. N=3 neu vergeben. |
| Ou u. a. 2024 (Wafertemperatur, SINDy-MPC) | keine Zeilenangabe | nicht prüfbar | übernommen | Nur L1: PII und Titel (T), Autoren und Band (S), Datenherkunft widersprüchlich. N=3 neu vergeben. |
| Wu 2026a (Control-Channel Informativity EDMDc) | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 164 bestätigt. Autor nur aus der Zusammenfassung. |
| Wu 2026b (Diagnostic Certificates Koopman) | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 166 korrigiert. |
| Dahdah, Forbes 2024 | bestätigt | teilweise | zusammengelegt | ch3 Z. 626–627 und 752–754 bestätigt. L1 nennt die Arbeit in Beitrag 4. 'Unter Nebenbedingungen' (ch3 Z. 753) steht laut Prüflauf Nr. 19 nicht wörtlich im Auszug. |
| Løvland, Imsland, Grimstad 2025 | bestätigt | teilweise | übernommen | Fundstelle ch3 Z. 667–671 ergänzt. −K⁻¹ ist im Prüflauf-Auszug (Nr. 18) nicht gesehen, am Volltext (Theorem 1) prüfen. |
| MPC closed-loop identification without excitation 2021 | keine Zeilenangabe | korrekt | übernommen | Nur L2, Nr. 117 bestätigt. Der Umschalt-Auszug stammt möglicherweise aus der IFAC-2020-Fassung. |
| Pan, Li 2023 (JDSMC, EV-Thermomanagement) | keine Zeilenangabe | korrekt | zusammengelegt | L2-Randanker und Auftrag A (A3.5). Nr. 121 korrigiert; ausdrücklich Grey-Box. |
| CEP 2025 Koopman-MPC integriertes EV-Thermomanagement | keine Zeilenangabe | korrekt | übernommen | L2-Randanker, Nr. 115 bestätigt, Autoren nicht gesehen. |
| Meda u. a. 2025/2026 | bestätigt | teilweise | übernommen | L2-Randanker. ch3 Z. 999 nennt 'Antriebsstrang', laut Prüflauf geht es um Klimatisierung (Querverweis auf E1.3). |
| Abdullah, Wu, Christofides 2021; Abdullah, Christofides 2023 (CCE) | keine Zeilenangabe | korrekt | übernommen | L2-Randanker, Nr. 4 und Nr. 5 bestätigt. |
| Verhoek u. a. 2021 | keine Zeilenangabe | korrekt | übernommen | L2-Randanker, Nr. 158 korrigiert. |
| Shi u. a. 2023 (ORC qLPV) | keine Zeilenangabe | korrekt | zusammengelegt | L2-Randanker und Auftrag A (A3.4, gleiche PII). Nr. 119 korrigiert. In E2.3 Zeile 4 als gemeinsamer nächster Treffer beider Läufe. |
| Sheikh, Donkers, Bergveld 2024 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur L1 (Auftrag A, A2), nicht gegengeprüft. Als Randanker für BT1 und BT3 aufgenommen (methodische Analogie, Batterie). |
| arXiv 2605.18720 (Kontinuumsroboter) | keine Zeilenangabe | korrekt | übernommen | L2-Randanker, Nr. 116 bestätigt. Die Güte-Kennzahlen aus dem Abstract bewusst nicht übernommen. |
| Raffa Ugolini u. a. 2024 | keine Zeilenangabe | korrekt | übernommen | L2-Randanker, Nr. 125 korrigiert. |
| Jeon, Jung u. a. 2021–2025 (Schiffskühlkreise) | keine Zeilenangabe | nicht prüfbar | übernommen | L2, †. |
| arXiv 2003.07465 (hysteresegeregeltes Pumpensystem) | keine Zeilenangabe | nicht prüfbar | zusammengelegt | L2 † und Auftrag A (A3.3, 'ohne Belegwert'). |
| ORC Koopman-MPC CEP 2023 (PII S0967066123002484) | keine Zeilenangabe | nicht prüfbar | zusammengelegt | Auftrag A (A3.5, T) und L2-†-Liste; stand in keiner der beiden Tabellen, jetzt Randanker. |
| Neural Koopman ORC (Appl. Therm. Eng.) | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Auftrag A (A3.5, T), Datenstatus unklar. |
| Koopman-VAE Fehlerdiagnose RLT (Energy Build.) | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Auftrag A (A3.5, T); kein MPC. |
| Iacob, Tóth, Schoukens 2024 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Auftrag A (A3.4). Randanker und Teilstütze in E2.3 Zeile 4. |
| Koelewijn u. a. 2024 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Auftrag A (A3.4). Gegenposition: SINDy dort 'generally still nonlinear' (S). |
| Jordanou u. a. 2025 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Auftrag A (A3.4, T). |
| Loiseau 2020 (Thermosiphon) | keine Zeilenangabe | korrekt | zusammengelegt | Auftrag A (A3.3) und Prüflauf Nr. 168 (korrigiert: begutachtete Fassung, DOI). |
| Ito, Hato, Kano 2023 | keine Zeilenangabe | korrekt | zusammengelegt | Auftrag A (A3.3) und Prüflauf Nr. 122 (korrigiert). |
| Manzoor, Rawashdeh, Mohammadi 2023 (Koopman-Survey Fahrzeuge) | keine Zeilenangabe | korrekt | zusammengelegt | Auftrag A (A3.5, nicht ausgewertet) und Prüflauf Nr. 120; nur als Einstieg für eine Nachsuche. |
| Du, Lai, Liu, Wang 2026 (PC-SINDYc Microgrid) | keine Zeilenangabe | korrekt | übernommen | Stand bisher nur in der L2-Quellenliste, jetzt Randanker. Nächster Treffer für 'physikgeleitete Bibliothek plus MPC', in E2.3 Zeile 3 genannt. Prüflauf Nr. 135. |
| Zhang, Qi u. a. 2024 (NSVB-MPC PEMFC-Temperatur) | keine Zeilenangabe | korrekt | übernommen | Stand bisher nur in der L2-Quellenliste, Nr. 132 korrigiert, jetzt Randanker. |
| Sirola u. a. 2026 (Ladeluftsystem Digital Twin) | keine Zeilenangabe | korrekt | übernommen | Stand bisher nur in der L2-Quellenliste, Nr. 103; Autoren nur aus der Zusammenfassung. |
| Jagadeesh u. a. 2026 (LLK-Emulation Prüfstand) | keine Zeilenangabe | korrekt | übernommen | Stand bisher nur in der L2-Quellenliste, Nr. 104; Zahlen aus dem Abstract nicht übernommen. |
| Stoumpos u. a. 2020 (DF-Schiffsmotor Digital Twin) | keine Zeilenangabe | korrekt | übernommen | Stand bisher nur in der L2-Quellenliste, Nr. 105; physikalisches Modell mit Betriebsartumschaltung. |
| Maya-Rodriguez u. a. 2025 (CNN Wärmeübertrager) | keine Zeilenangabe | korrekt | übernommen | Die L2-E2.3 nannte nur 'CNN-Blackbox', jetzt mit Metadaten aus Nr. 169. |
| Rupprecht 2016 | bestätigt | korrekt | zusammengelegt | Unter 'Ältere Anker' eingeordnet; ch3 Z. 1044–1056 bestätigt. |
| Kaiser, Kutz, Brunton 2018 | bestätigt | teilweise | zusammengelegt | Unter 'Ältere Anker' eingeordnet. Nr. 48 bestätigt. 'SQP laut Autoren-Code' nur aus L1, am Text nicht geprüft. Das Zitat in ch3 Z. 600–603 ist laut E1.3 nicht gestützt. |
| Esmaili u. a. 2017 | keine Zeilenangabe | korrekt | übernommen | Unter 'Ältere Anker' (L2), Nr. 127 korrigiert. |
| Cisneros, Voss, Werner 2016 | keine Zeilenangabe | korrekt | zusammengelegt | Unter 'Ältere Anker'. L1 über Auftrag A2 (T), L2-Quellenliste mit Nr. 147 bestätigt; DOI nirgends gesehen. |
| Joshi u. a. 2009 | keine Zeilenangabe | korrekt | übernommen | Unter 'Ältere Anker' (L2-Quellenliste, E3-Anker), Nr. 153 bestätigt. |
| Ältere Titel ohne Inhalt (marine cooling system CEP; Intake Air Temperature Test Bench Energy Procedia) | keine Zeilenangabe | nicht prüfbar | übernommen | Aus 'Offen' von L1, nur Titel und PII (T); als 'nur Titel gesehen' unter 'Ältere Anker'. |
| Castiglione 2020 | keine Zeilenangabe | nicht prüfbar | verworfen | In L1 nur Titelsuche L1-33 und 'Offen' (Autoren nur S), ohne Inhalt oder Tabelleneintrag. Nur in der Anfrageliste erwähnt. |
| US-Patente 8099222, 9394858 | keine Zeilenangabe | nicht prüfbar | verworfen | Laut L1 bewusst kein Beleg; nur in E2.3 Zeile 11 als Befund des Suchwegs genannt. |
| Tufa, Ka 2016; Badwe u. a. 2009 | keine Zeilenangabe | teilweise | übernommen | E2.3 Zeile 8. Der L2-Satz 'Gain-Fehlanpassung als MPC-Gütegröße etabliert' geht laut Prüflauf Nr. 109 über das Abstract hinaus; in der korrigierten Form übernommen. |
| Otto u. a. 2023; Zar 1968 (A3.1) | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Auftrag A, als nächste Treffer der neuen E2.3-Zeile 13 (BT6). |
| CIMAC-2025-Beitrag 308 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur L2, ohne Titel gesehen; unverändert in E2.3 Zeile 11. |

## E3 Zusammenführung

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| L1-Idee 1 | keine Zeilenangabe | korrekt | zusammengelegt | In S2 (Rang 2) als QP-Tauglichkeitstabelle eingebaut: Termtypen x Modellklassen, Bedingungen (a)-(d) aus L2 als Spalten; Anker Cisneros, Voss, Werner 2016 und Auftrag B (B1, B2.3) übernommen. |
| L1-Idee 2 | keine Zeilenangabe | korrekt | übernommen | Neu als A18 (Rang 8, N4, S 2-4 h). Algebra selbst nachgerechnet, Zahlentest mit synthetischen Signalen (merge/a18_check.py): exakt verschoben genau dann, wenn Summe der Temperaturkoeffizienten 1 (Map-Form) bzw. 0 je Faktor (kontinuierlich); Konstante stört nicht. Präzisiert: °C/K-Tausch nur mit festem Modell aussagekräftig, bei LS-Neuschätzung mit Konstante trivial erfüllt; 'Absolutterm' von 'Absolutglied' (ch3 Z. 896) abgegrenzt; versteckte Bezugstemperatur T* = c_0/(1-s) ergänzt. |
| L1-Idee 3 | keine Zeilenangabe | korrekt | zusammengelegt | In A5 (jetzt Top 5, Rang 5) als Persistenzreferenz ŷ_{k+h/k} = y_k ergänzt; Anker Somalwar u. a. 2025 und Nelles 2020 (Auftrag B) mit Herkunftskennung; N von 4 auf 5 angehoben. |
| L1-Idee 4 | bestätigt | teilweise | zusammengelegt | In A3 (Rang 4). ch3 Z. 1024-1027 bestätigt. Vorschlag 'Autokorrelation der Freilaufresiduen' berichtigt: Weißheitstest nur für Einschrittresiduen, Freilaufresiduen nur Kreuzkorrelation mit Eingängen. Kreuzkorrelation mit der Last und Billings 2013 (Kapitel Model Validation) übernommen. |
| L1-Idee 5 | keine Zeilenangabe | korrekt | zusammengelegt | Geteilt: Konditionszahl/VIF und Hinweis 'VIF zeigt nicht, welche Terme sich ersetzen' nach A2 (Rang 3); Block-Bootstrap, Inklusionshäufigkeit, Efron & Tibshirani 1993, Raue u. a. 2009, Saltelli u. a. nach A4 (Rang 40). Einschränkungen ergänzt: Profil-Likelihood bei linearen Modellen exakt quadratisch (= LS-Kovarianz), Sobol-Indizes setzen unabhängige Eingänge voraus. |
| L1-Idee 6 | keine Zeilenangabe | korrekt | zusammengelegt | Als Stufe 0 in A13 (Ereignistabelle Sprung u_HP gegen Last- und T_LTCW-Änderung). Hintergrund L1-4.1 mit ch2 Z. 288-289 und ch3 Z. 869-873, 891-897 geprüft. A13 dadurch M 5-7 h, Rang 25 statt 11; Stufe 0 allein S 2-3 h vorziehbar. |
| L1-Idee 7 | keine Zeilenangabe | korrekt | zusammengelegt | In S5 als Kurzfassung (S 1-2 h): Eigenkoeffizient a(mrel) in (0,1), τ = -Δt/ln a (Auftrag B, B2.1); Khalil 2002 als Anker mit Herkunftshinweis. |
| L1-Idee 8 | keine Zeilenangabe | korrekt | zusammengelegt | Formulierung (linearer Schlupfterm, exakte Strafe) in S2; Nachweis in der CL-Simulation in D7 (Rang 39). Kerrigan & Maciejowski 2000 ist im Prüflauf bestätigt. |
| L1-Idee 9 | keine Zeilenangabe | korrekt | zusammengelegt | In A10 (Rang 41): Zielwert als gewichtete Summe aus Auftrag B G1, Risiko 'Referenz erreicht SINDYc = Bibliothek trifft die Physik' übernommen; Stunden aus L2 (M 8-12 h). |
| L1-Idee 10 | keine Zeilenangabe | korrekt | zusammengelegt | In A7 (Rang 16): Anker Skogestad & Postlethwaite 2005 und Yousefi u. a. 2015 (beide im Prüflauf) ergänzt; Hinweis 'Simulationsaussage' übernommen. |
| L1-Idee 11 | keine Zeilenangabe | korrekt | zusammengelegt | In D5 (Rang 27) als Kurzfassung S 1-2 h; rawlingsModelPredictiveControl20202020 als Anker. |
| L1-Idee 12 | keine Zeilenangabe | korrekt | zusammengelegt | In S3 (Rang 9): Schema Training/Auswahl/Test, Informationskriterien nur nachgelagert (ch3 Z. 519-524 geprüft), Varma & Simon 2006 aus Auftrag D. |
| L1-Idee 13 | bestätigt | teilweise | übernommen | Neu als B8 (Rang 12, N3, S 2-3 h). ch2 Z. 905-907 und 877-884 bestätigt. L1 übernahm die Beschriftung 1/(kA) aus dem Bildvermerk; ch2 Z. 830-831 trennt U_eff A vom kA der Statik, daher berichtigt. Konflikt HT-Block gegen einstufige Bilanz (ch2 Z. 888-896) als Risiko ergänzt; Spannungsteiler-Deutung (ε = N/(1+N), τ) als eigene Algebra. |
| L1-Idee 14 | keine Zeilenangabe | korrekt | übernommen | Neu als B9 (Rang 13, N3, S 2-3 h). Gewichte aus Auftrag B G1; eigene Algebra ergänzt: Ventil verschiebt Zielwert im Dreieck auf einer Geraden von T_zw zur T_LTCW-Ecke, Gain = -(T_zw - T_LTCW)·dε_LT/du. Annahme 'ε_LT wächst mit Hub' mit ch2 Z. 812-814 als Vorbehalt. |
| L1-Idee 15 | bestätigt | korrekt | zusammengelegt | In B3 (Rang 15): gleiche Matrix wie L2; ch3 Z. 907-925 bestätigt; Randspalten QP-tauglich (S2) und verschiebungsinvariant (A18) ergänzt. |
| L1-Idee 16 | bestätigt | korrekt | zusammengelegt | In B2 (Rang 17): Konfundierungspfad = Pfad B in L2; ch3 Z. 650-651 und 877-884 bestätigt. |
| L1-Idee 17 | bestätigt | korrekt | zusammengelegt | In D3 (Rang 10): ch2 Z. 125-126 bestätigt (Band nur als Kommentar, Key fehlt); rupprechtAnalysisSimulationOptimisation2016 mit ch2 Z. 554-555 ergänzt; Hinweis auf A18 (Temperaturniveau). |
| L1-Idee 18 | bestätigt | korrekt | zusammengelegt | In D9 (Rang 43) als Diskussions-Kurzfassung (rund 1 h); ch3 Z. 458-460 bestätigt; Quade u. a. 2018 als Anker. |
| L1-Idee 19 | keine Zeilenangabe | korrekt | zusammengelegt | In D2 (Rang 19): Herleitung aus Auftrag D Frage 4 (d̂_k = (1-L)d̂_{k-1} + L z_k, L²/(1-L) = q/r) übernommen und von Hand nachgerechnet; Harvey 1989 und Tatjewski 2014 mit Herkunftskennung. |
| L1-Idee 20 | keine Zeilenangabe | korrekt | übernommen | Neu als D12 (Rang 7, N4, S 2-3 h). Inhalt aus Auftrag D Frage 1 und L2-F1; eigene Algebra ergänzt: Mittelung der 1D-Bilanz auf die konstante Mode plus Rührkessel-Schließung ergibt Gl. eq.energiebilanz.dyn; Zellformel ε_n aus L2 nachgerechnet (n=1: N/(1+N), n→∞: 1-e^{-N}). |
| L1-Große Idee 1 | keine Zeilenangabe | korrekt | zusammengelegt | Adaptive/online nachgeführte SINDYc-Modelle: mit L2 'Adaptiver MPC' in E3.4 zusammengelegt. |
| L1-Große Idee 2 | keine Zeilenangabe | korrekt | übernommen | Mehrgrößenregelung mit LP-Ventil: in E3.4 mit Hinweis, dass die harte Grenze 'Stellglied nur HP-Ventil' sie für die Arbeit ausschließt. |
| L1-Große Idee 3 | bestätigt | korrekt | zusammengelegt | NMPC auf bilinearem EDMDc (ch3 Z. 339-366 bestätigt): mit L2 'Stufen 3-5 aus D10' in E3.4 zusammengelegt. |
| L1-Große Idee 4 | keine Zeilenangabe | korrekt | zusammengelegt | Versuchsplanung für geregelte Feldanlagen (bomboisLeastCostlyIdentification2006): mit L2 'Dither-Feldversuch' in E3.4 zusammengelegt. |
| L1-Große Idee 5 | bestätigt | korrekt | übernommen | Ökonomisches MPC mit Derating-Grenze (ch2 Z. 39-41 bestätigt): in E3.4 übernommen, Anker Valábek u. a. 2025 (Titel (T), Inhalt (S)). |
| L2-S1 | bestätigt | korrekt | zusammengelegt | Rang 1. Alle Zeilenangaben gegen kontext/ geprüft. Um L1-E1-Punkte ergänzt (L1-3.1, 3.3, 3.4, 3.6, 3.7, 7.4, 7.5, 7.7; Zeilen geprüft, Beleg für L1-3.6 auf ch3 Z. 632-636 präzisiert). Hinweis: nur im E1-Prüfprotokoll bestätigte Befunde abarbeiten. |
| L2-S2 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 2 (L2: 4). Mit L1-Idee 1 und 8 zusammengelegt; Zeilenangaben der neuen Tabelle (ch3 Z. 363-366, ch2 Z. 447-448) geprüft. F-Verweis berichtigt: L2 nannte F1, gemeint sind F2, F3, F6. |
| L2-A2 | bestätigt | korrekt | zusammengelegt | Rang 3 (L2: 2). Mit Konditionierungsteil von L1-Idee 5 zusammengelegt; Hinweis Differenz- gegen Absolutspalten als eigene Überlegung ergänzt. |
| L2-B1 | keine Zeilenangabe | korrekt | übernommen | Rang 3 gemeinsam mit A2, unverändert. |
| L2-A3 | bestätigt | korrekt | zusammengelegt | Rang 4 (L2: 3). Mit L1-Idee 4 zusammengelegt (Last als Kreuzkorrelationsgröße, Billings 2013). |
| L2-A5 | bestätigt | korrekt | zusammengelegt | Rang 5 (L2: 12), Top 5 nach Regel 'beide Läufe hoch'. Persistenzreferenz aus L1-Idee 3; N von 4 auf 5 angehoben (beantwortet F8 direkt), im Steckbrief begründet. |
| L2-D1 | bestätigt | korrekt | übernommen | Rang 6 (L2: 5), fällt aus den Top 5, weil L1 keine Idee dazu hatte. BT-Namen an feste IDs angepasst, BT6 nur mit A18. |
| L2-S3 | korrigiert | korrekt | zusammengelegt | Rang 9. Zeilenangabe 'ch3 Z. 1188-1196' (retrospektiv kennzeichnen) auf ch3 Z. 1198-1202 berichtigt. Mit L1-Idee 12 zusammengelegt. |
| L2-D3 | bestätigt | korrekt | zusammengelegt | Rang 10 (L2: 7). Mit L1-Idee 17 zusammengelegt. |
| L2-D4 | bestätigt | korrekt | übernommen | Rang 11. Zeilenangabe ch2 Z. 718-724 präzisiert auf 717-724 (Verschmutzung Z. 722). |
| L2-A1 | bestätigt | korrekt | übernommen | Rang 14 (L2: 9), unverändert. |
| L2-A7 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 16 (L2: 10), direkt hinter A1 und B3. Mit L1-Idee 10 zusammengelegt. |
| L2-A13 | bestätigt | korrekt | zusammengelegt | Rang 25 (L2: 11). Stufe 0 aus L1-Idee 6 ergänzt; Aufwand Stufe 0+1 M 5-7 h (Schätzung mit Überlappung zur First-Stage-Regression). |
| L2-B3 | bestätigt | korrekt | zusammengelegt | Rang 15 (L2: 13), direkt hinter A1 (letzte Voraussetzung, A3/A5 in Top 5). Mit L1-Idee 15 zusammengelegt. |
| L2-B2 | bestätigt | korrekt | zusammengelegt | Rang 17 (L2: 14). Mit L1-Idee 16 zusammengelegt. |
| L2-A12 | keine Zeilenangabe | korrekt | übernommen | Rang 18 (L2: 15), unverändert. |
| L2-D2 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 19 (L2: 16). Mit L1-Idee 19 zusammengelegt (Kalman-EMA-Herleitung aus Auftrag D). |
| L2-S6 | keine Zeilenangabe | korrekt | übernommen | Rang 20 (L2: 17), unverändert. |
| L2-A6 | bestätigt | korrekt | übernommen | Rang 21 (L2: 18). Kennfeld-Schranke von Hand nachgerechnet (Ableitung nach T_LTCW bei festem r, Last, T_col,in, T_HTCW); stimmt unter den genannten Voraussetzungen. |
| L2-B7 | keine Zeilenangabe | korrekt | übernommen | Rang 22 (L2: 19). Seitenangabe S. 305-306 stammt aus ch3 Z. 328; Zeilenbezug ergänzt. |
| L2-S4 | keine Zeilenangabe | korrekt | übernommen | Rang 23 (L2: 20), unverändert. |
| L2-D10 | keine Zeilenangabe | korrekt | übernommen | Rang 24 (L2: 21), unverändert; Stufen 3-5 in E3.4 mit L1-Große Idee 3 zusammengeführt. |
| L2-A9 | bestätigt | korrekt | übernommen | Rang 26 (L2: 22), unverändert. |
| L2-D5 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 27 (L2: 23). Mit L1-Idee 11 zusammengelegt. |
| L2-A14 | bestätigt | korrekt | übernommen | Rang 28 (L2: 24), unverändert. |
| L2-B6 | keine Zeilenangabe | korrekt | übernommen | Rang 29 (L2: 25), unverändert. |
| L2-A8 | bestätigt | korrekt | übernommen | Rang 30 (L2: 26), unverändert. |
| L2-S5 | bestätigt | korrekt | zusammengelegt | Rang 31 (L2: 27). Mit L1-Idee 7 zusammengelegt (Kurzfassung vorziehbar). |
| L2-D11 | keine Zeilenangabe | korrekt | übernommen | Rang 32 (L2: 28), unverändert; verweist auf E4. |
| L2-D6 | keine Zeilenangabe | korrekt | übernommen | Rang 33 (L2: 29), unverändert. |
| L2-B4 | bestätigt | korrekt | übernommen | Rang 34 (L2: 30), unverändert. |
| L2-D8 | bestätigt | korrekt | übernommen | Rang 35 (L2: 31), unverändert. |
| L2-B5 | bestätigt | korrekt | übernommen | Rang 36 (L2: 32), unverändert. |
| L2-A15 | bestätigt | korrekt | übernommen | Rang 37 (L2: 33), unverändert. |
| L2-A16 | keine Zeilenangabe | korrekt | übernommen | Rang 38 (L2: 34). Einstufige Bias-Algebra geprüft; Verweis auf A18 ergänzt (gemeinsamer Fühlerbias = Verschiebung). |
| L2-D7 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 39 (L2: 35). Nachweis der exakten Straffunktion aus L1-Idee 8 ergänzt; Grenzen mit ch2 Z. 108-109 und 39-41 belegt (geprüft). |
| L2-A4 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 40 (L2: 36). Streuungsteil von L1-Idee 5 ergänzt; Raue u. a. 2009 und Saltelli u. a. als Optionen mit eigener Einschränkung. |
| L2-A10 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 41 (L2: 37). Mit L1-Idee 9 zusammengelegt. |
| L2-A11 | bestätigt | korrekt | übernommen | Rang 42 (L2: 38), unverändert. |
| L2-D9 | keine Zeilenangabe | korrekt | zusammengelegt | Rang 43 (L2: 39). Mit L1-Idee 18 zusammengelegt. |
| L2-A17 | keine Zeilenangabe | korrekt | übernommen | Rang 44 (L2: 40), unverändert. |

## E3 Gegenprüfung (Korrekturen)

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| A13 | keine Zeilenangabe | falsch | übernommen | "Stufe 0 allein S 2–3 h" widersprach der L1-Schätzung 3–5 h (steht so in der Zuordnungstabelle in E3.0). Stufe 0 jetzt S 3–5 h (L1). Stufe 0 und 1 zusammen: 3–5 h plus 4–6 h minus 1–2 h, also M 6–9 h statt 5–7 h. N je Stunde damit 5/7,5; A13 steht jetzt auf Rang 30 statt 25, bei gleichem N je Stunde vor S5 und D11. Tabellenzeilen 25–30 neu geordnet, Steckbrief A13 hinter A8 verschoben, A9/D5/A14/B6/A8 auf 25–29 umnummeriert, Hinweis in E3.2 neu gerechnet. Andere out_*.md verweisen nicht auf Rangnummern. |
| D10 | keine Zeilenangabe | falsch | übernommen | "M 10–15 h" für Stufe 2 verletzt die Skala in E3.0 (M bis 12 h). Auf L 10–15 h gesetzt, mit Vermerk (Zusammenführung: L2 schrieb M). |
| A11 | korrigiert | falsch | übernommen | Die Kritik an Simulationsdaten steht in ch3 Z. 1141–1147, nicht in Z. 1143–1150 (ab Z. 1149 beginnt der MPC-Absatz). Stelle berichtigt, mit Vermerk (Zusammenführung). |
| S1 | korrigiert | teilweise | übernommen | Beleg zu L1-3.6 steht in ch3 Z. 633–637 statt 632–636. "λ dreifach belegt" auf vier Bedeutungen erweitert, wie in E1.1 K7 (ch2 Z. 438 und 855, ch2 Z. 1068, ch3 Z. 423, ch3 Z. 428 und 498). Beim Ersetzen von „Bündel“ zusätzlich ch2 Z. 551–557 und 905–907 genannt. |
| A18 | korrigiert | teilweise | übernommen | Die \mrel-Definition reicht bis ch2 Z. 691; Stelle von Z. 670–685 auf Z. 670–691 erweitert. In Variante (b) war „nur die Konstante wandert“ bei Produkten unvollständig: Auch die Koeffizienten der φ_j allein wandern. Ergänzt und mit synthetischem LS-Zahlentest nachgeprüft (Temperaturkoeffizienten gleich, Vorhersage um c verschoben). Die übrige Algebra (Summenbedingung, T* = c_0/(1−s)) mit a18_check.py nachgerechnet und bestätigt. |
| A3 | bestätigt | teilweise | übernommen | „Freilaufresiduen sind per Konstruktion nicht weiß“ war zu stark. Neu: „im Allgemeinen nicht weiß (kein Rauschmodell; bei ARX-Struktur gefiltertes Rauschen e/A)“. Die Folgerung (nur Kreuzkorrelation mit dem Eingang prüfen) bleibt. |
| B8 | bestätigt | teilweise | übernommen | Der Steckbrief teilte U_eff·A nach Gl. eq.k.zusammensetzung auf, obwohl er selbst festhält, dass ch2 Z. 830–831 U_eff·A vom kA der Statik trennt. Die Aufteilung ist jetzt als sinngemäß gekennzeichnet und soll in der Bildunterschrift als Annahme stehen. Algebra geprüft: Spannungsteiler, ε = N/(1+N), τ = C_eff/(G_L+G_W). |
| B9 | bestätigt | teilweise | übernommen | „\mrel verschiebt über ε_HT und ε_LT die Lage der Geraden“ war ungenau. Richtig ist: ε_HT verschiebt den Startpunkt T_zw auf der Kante \Tin–\THT und damit die Gerade; ε_LT verschiebt den Punkt auf der Geraden. Gewichte und Stellwirkung nachgerechnet. |
| A14 | bestätigt | teilweise | übernommen | Die Ankerzeile fehlte (schon in L2). Ergänzt: Diebold & Mariano 1995 (L2-Quelle, verifiziert) sowie die Proxyvarianten in ch2 Z. 684–691 und 705–712. |
| D11 | bestätigt | teilweise | übernommen | Die Ankerzeile fehlte. Ergänzt: Quellen aus E4.2 mit dem dort angegebenen Status und die eigene Ableitung in E4.3 zu ch2 Z. 958–961. |
| A17 | bestätigt | teilweise | übernommen | Die Ankerzeile fehlte. Ergänzt ohne neue Literatur: Ventil im Dieselbetrieb 100 % offen (ch2 Z. 288–289); in der Sättigung ist nur der Störpfad identifizierbar (ch3 Z. 891–897). |
| D3 | bestätigt | teilweise | übernommen | Im Steckbriefkopf fehlte die Datenangabe; ergänzt als „nein (Diskussion)“. Der L1-Anker „Auftrag A (PG 51/60DF)“ war verloren gegangen und ist wieder da: Project Guide 51/60DF Marine, Auftrag A 7f, (T), [nur bibliografisch], Ausgabe offen. |
| D4 | bestätigt | teilweise | übernommen | Im Steckbriefkopf fehlte die Datenangabe; ergänzt als „nein (Diskussion); Trendanalyse mit vorhandenen Felddaten“. Formelzeichen `dε/du_HP` durch `dε/d\valveCA` ersetzt. |
| A2 | bestätigt | teilweise | übernommen | Im Formelausdruck stand `r − T_LTCW` statt des Makros; ersetzt durch `r − \TLT`, wie in A6. |
| S3 | bestätigt | teilweise | übernommen | `T_LTCW`-Niveau durch \TLT-Niveau ersetzt (Makro). |
| S2 | bestätigt | teilweise | übernommen | Das Stichwort zu F3 passte nicht zum zusammengeführten E1.4 (F3 = QP-Tauglichkeit und Störgrößen über den Horizont). Angepasst. |
| D1 | bestätigt | teilweise | übernommen | Die Einordnung von BT5 und BT6 widersprach E2.1. Angeglichen: BT5 steht als methodische Sorgfalt im Methodikkapitel, nicht in der Beitragsliste; BT6 nur nach A18 und dann als Unterpunkt von BT3. |
| S5 | keine Zeilenangabe | teilweise | übernommen | Bei Khalil 2002 (Quelle aus Auftrag B, nicht verifiziert) fehlte die Herkunftskennung, die E3.0 verlangt. Ergänzt: BibTeX dort nur aus (T)- und (G)-Feldern. |
| E3.0 | keine Zeilenangabe | teilweise | übernommen | Die Abhängigkeitsregel („stehen direkt hinter ihrer letzten Voraussetzung“) widersprach wörtlich genommen der Lage von S6, S4, A14, B5, A4 und A15. Neu gefasst: Keine Idee steht vor ihrer Voraussetzung; nur wer nach N je Stunde davor stünde, rückt direkt dahinter. Das betrifft nur B3. „41 Ideen mit Steckbrief“ berichtigt zu 41 IDs in 40 Steckbriefen. Aufwandsregel präzisiert: L1-Zusatzaufwand bei A13 ist eingerechnet; die Erweiterung der neuen Ideen ist je Idee begründet. |
| E3.2 | keine Zeilenangabe | teilweise | übernommen | Der Tabellenlegende fehlte die Herkunftsmarke; (L1+L2) ergänzt. Ohne Änderung geprüft: alle 45 IDs (41 aus L2, dazu A18, B8, B9, D12) stehen in Tabelle und Steckbriefen; alle 20 L1-Ideen sind nach den FESTEN IDS zugeordnet; Rang, Aufwand und N stimmen in Tabelle und Steckbriefen überein; die Reihenfolge ab Rang 6 folgt N je Stunde. Die Summen stimmen (Top 5: 19–31 h, Rang 1–13: 36–58 h). Alle Keys stehen in ch2/ch3. Jede neue Quelle findet sich in L1, L2, A, B, D oder verifiziert.json. |

## Quellen aus L1 und A, B, D

| Kennung | Zeilen | Urteil | Verwendet | Notiz |
|---|---|---|---|---|
| Aguirre 2019 (arXiv:1907.06803) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu, nicht in verifiziert.json. Key aguirreBirdsEyeView2019 in L1 (Verteidigungsfrage 3); A2-Entwurf unverändert in out_bib_L1.bib. |
| Castiglione 2020 | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Name und Jahr in L1 (Offen); keine Metadaten in irgendeiner Eingabedatei; kein Key, kein BibTeX. Suchweg nennt daneben SAE 2021-01-0225, Zuordnung nicht ableitbar. |
| Champion u. a. 2020 (IEEE Access 8) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. In L1-2.4 nur namentlich (Auftrag A); Key nicht wörtlich in L1/L2, A2-Entwurf trotzdem in out_bib_L1.bib (Erweiterung der Key-Regel, im Herkunftskommentar vermerkt). |
| Efron & Tibshirani 1993 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. L1-Entwurf E unverändert in out_bib_L1.bib; ISBN (G). |
| Farina & Piroddi 2010 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. Key in L1 (Verteidigungsfrage 5); A2-Entwurf in out_bib_L1.bib; Verwechslungshinweise aus A übernommen. |
| Kaptanoglu u. a. 2022 (PySINDy, JOSS) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. In L1-2.4 nur namentlich; A2-Entwurf in out_bib_L1.bib. A-Status 'Volltext gelesen' betrifft nur das Repo-Manuskript; hier als [nur bibliografisch] geführt. |
| Khalil 2002 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. Key in L1 (Idee 7, jetzt S5); B2.4-Entwurf in out_bib_L1.bib. |
| MAN/Everllence PG 51/60DF Marine | bestätigt | nicht prüfbar | übernommen | Neu, aus A1 Nr. 7f (L1 Idee 17 als 'Auftrag A (PG 51/60DF)'); ch2 Z. 125–126 nennt PG 51/60DF-M S. 117 Tab. 74. Ausgabe/Jahr offen; kein BibTeX (A: erst nach Titelblatt). |
| Miyashita u. a. 2022 (SICE) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu, nicht in verifiziert.json; in L2 nur in der †-Liste. L1-Entwurf in out_bib_L1.bib. |
| Nelles 2020 (2. Aufl.) | keine Zeilenangabe | teilweise | übernommen | B nennt 2. Aufl. 2020; verifiziert.json Nr. 60 führt 1. Aufl. 2000 (DOI der 2. Aufl. dort nur in URL gesehen). B-Entwurf in out_bib_L1.bib mit Hinweis 'nur eine Auflage übernehmen'; zusätzlich im Abgleich. |
| Ou u. a. 2024 (Chem. Eng. Res. Des.) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu; Autoren und Venue nur (S)/ungeprüft, Entwurf nur mit Titel und URL. Datenherkunft laut L1 widersprüchlich. |
| Pannocchia 2015 (ECC, Tracking MPC) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. L1 'Pannocchia 2015 (B)'; D-Entwurf (ersetzt B-Entwurf) in out_bib_L1.bib. Nicht identisch mit verifiziert.json Nr. 73 (IFAC 2015). |
| Raue u. a. 2009 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. L1-Entwurf E in out_bib_L1.bib; DOI (G). |
| Saltelli u. a. 2007/2008 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. Jahr uneinheitlich, Key hängt am Jahr; Entwurf ohne year-Feld unverändert übernommen. |
| Sheikh u. a. 2024 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. In L1 nur namentlich (Beitrag 1, jetzt BT1); A2-Entwurf in out_bib_L1.bib (Erweiterung der Key-Regel). |
| Somalwar u. a. 2025 (arXiv:2504.01766) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. Key in L1 (Verteidigungsfrage 5); A2-Entwurf in out_bib_L1.bib; Autoren nur (S). |
| Valábek u. a. 2025 (arXiv:2511.04437) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu; in L2 nur †-Liste. Nicht identisch mit verifiziert.json Nr. 159 (Daráš u. a. 2026). |
| Vega-Zambrano u. a. 2025 | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. Artikelnummer nur aus DOI abgeleitet; Inhaltsaussagen nur (S). |
| Zheng u. a. 2018/2019 (SR3) | keine Zeilenangabe | nicht prüfbar | übernommen | Neu. In L1-2.4 nur namentlich; A2-Entwurf in out_bib_L1.bib; Jahr und damit Key offen. |
| Intake Air Temperature and Humidity on the Test Bench (Energy Procedia) | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Titel und PII (T) in L1 Offen; kein Autor, kein Jahr, kein BibTeX. |
| Single-phase marine cooling system (Control Eng. Pract.) | keine Zeilenangabe | nicht prüfbar | übernommen | Nur Titel und PII (T) in L1 Offen; kein Autor, kein Jahr, kein BibTeX. |
| bomboisLeastCostlyIdentification2006 | keine Zeilenangabe | nicht prüfbar | übernommen | Key der Arbeit, nicht im Prüflauf; in Key-Liste (ch3 Z. 747). |
| bruntonSparseIdentificationNonlinear2016 | bestätigt | korrekt | übernommen | L1-3.6 'Brunton u. a. 2016, S. 713' = ch3 Z. 634; nicht im Prüflauf. |
| faselEnsembleSINDyRobustSparse2022 | keine Zeilenangabe | nicht prüfbar | übernommen | Key der Arbeit, nicht im Prüflauf. |
| forssellClosedloopIdenticationRevisited1999 | keine Zeilenangabe | nicht prüfbar | übernommen | Key der Arbeit, nicht im Prüflauf. |
| kordaLinearPredictorsNonlinear2018 | bestätigt | korrekt | übernommen | L1-3.2 (ch3 Z. 323–325) deckt sich mit L2 E1.3; verifiziert.json Nr. 0 ist die andere Korda-Mezić-Arbeit (Konvergenz), als Verwechslungsgefahr vermerkt. |
| ljungSystemIdentificationTheory1999 | keine Zeilenangabe | nicht prüfbar | übernommen | Key der Arbeit, nicht im Prüflauf. |
| maederLinearOffsetfreeModel2009 | bestätigt | nicht prüfbar | übernommen | ch2 Z. 1086–1088; nicht identisch mit verifiziert.json Nr. 74 (Morari & Maeder 2012). |
| muskeDisturbanceModelingOffsetfree2002 | bestätigt | nicht prüfbar | übernommen | ch2 Z. 1086–1088; nicht im Prüflauf. |
| pannocchiaDisturbanceModelsOffsetfree2003 | bestätigt | nicht prüfbar | übernommen | ch2 Z. 1086–1088; nicht im Prüflauf. |
| manganModelSelectionDynamical2017 | bestätigt | nicht prüfbar | übernommen | L1 Frage 8 verweist auf ch3 Z. 520–524, Zitat in ch3 Z. 521; nicht im Prüflauf. |
| proctorGeneralizingKoopmanTheory2018 | bestätigt | nicht prüfbar | übernommen | L1-4.6 ch3 Z. 877–884, Zitat in ch3 Z. 883; nicht im Prüflauf. |
| rawlingsModelPredictiveControl20202020 | keine Zeilenangabe | nicht prüfbar | übernommen | Key der Arbeit, nicht im Prüflauf. |
| rupprechtAnalysisSimulationOptimisation2016 | bestätigt | nicht prüfbar | übernommen | L1 E2-Tabelle ch3 Z. 1044–1056, Zitat Z. 1056; nicht im Prüflauf. |
| suiMeanValueFirst2022 | keine Zeilenangabe | nicht prüfbar | übernommen | Key der Arbeit, nicht im Prüflauf. |
| vagapovDynamicModelTemperature2022 | bestätigt | nicht prüfbar | übernommen | ch3 Z. 1058–1068, Zitat Z. 1068; nicht im Prüflauf. |
| vagapovModellierungIdentifikationUnd2024 | bestätigt | nicht prüfbar | übernommen | L1 'Vagapov 2024, Diss.'; ch3 Z. 1069–1081, Zitat Z. 1081; nicht im Prüflauf. |
| Akan u. a. 2024 | keine Zeilenangabe | teilweise | zusammengelegt | verifiziert.json Nr. 165. A-Autoren und Band nur (S), vom Prüflauf nicht gefunden. |
| Belsley, Kuh, Welsch 1980 | keine Zeilenangabe | teilweise | zusammengelegt | Nr. 82. ISBN identisch (eigene Umrechnung 10/13-stellig); Nachdruck laut Prüflauf 2004, nicht 2005; L1-Entwurf mischt Jahr 1980 mit Reihe des Nachdrucks. |
| Beran, Gärtner, Koch 2021 | bestätigt | korrekt | zusammengelegt | Nr. 21; ungeprüfte L1-Nachnamen bestätigt. Nr. 22 ist ein anderer Beitrag derselben Autoren. |
| Bhadriraju u. a. 2021 (OASIS-P) | bestätigt | nicht prüfbar | zusammengelegt | Nr. 27; L1 nur Key (ch3 Z. 458–460). Nr. 28 ist OASIS 2020. |
| Billings & Voon 1986 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 51; keine Abweichung. |
| Billings 2013 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 49; Buch-DOI gleich, Prüflauf ergänzt ISBN und Kapitel-DOI. |
| Cisneros, Voss, Werner 2016 | keine Zeilenangabe | teilweise | zusammengelegt | Nr. 147; Seiten, '55th' und DOI aus A im Prüflauf nicht gesehen. |
| Dahdah & Forbes 2024 | bestätigt | teilweise | zusammengelegt | Nr. 19; L1 schreibt 'u. a.', es sind zwei Autoren. ch3 Z. 626, 754 bestätigt. |
| Kaiser, Kutz, Brunton 2018 | bestätigt | korrekt | zusammengelegt | Nr. 48; ch3 Z. 603 bestätigt. |
| Kaleli 2020 | keine Zeilenangabe | teilweise | zusammengelegt | Nr. 160; DOI ergänzt, 104424 vermutlich Artikelnummer, Band 100 nicht bestätigt, Koautoren offen. |
| Kaptanoglu u. a. 2021 (Trapping) | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 139; keine Abweichung. |
| Kerrigan & Maciejowski 2000 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 149; ungeprüfte B-Angaben bestätigt. |
| Künsch 1989 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 80; keine Abweichung. |
| Loiseau & Brunton 2018 | keine Zeilenangabe | nicht prüfbar | zusammengelegt | Nr. 39; L1 nur Key. |
| Meinshausen & Bühlmann 2010 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 85; Seiten bestätigt. |
| Piroddi & Spinelli 2003 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 53; Seiten und Initialen bestätigt. |
| Quade u. a. 2018 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 144; keine Abweichung. |
| Ribeiro & Aguirre 2018 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 61; ungeprüfte B-Angaben bestätigt, DOI gegen Crossref prüfen. |
| Skogestad & Postlethwaite 2005 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 83; ISBN gleich. |
| Yahagi u. a. 2025 (IJCAS) | bestätigt | korrekt | zusammengelegt | Nr. 29; DOI gleich; Key-Zuordnung weiter offen. |
| Yahagi u. a. 2025 (arXiv:2503.05154) | keine Zeilenangabe | teilweise | zusammengelegt | Nr. 35; D-Entwurf mit Titel v1, Prüflauf mit späterem Titel; L2 ordnet dem Key ohne Jahr zu. |
| Yahagi u. a. 2026 (arXiv:2602.15422) | bestätigt | teilweise | zusammengelegt | Nr. 36; Autoren vervollständigt; 'Prüfstand unter PID' im Abstract-Auszug nicht gesehen. |
| Yonezawa u. a. 2025 (arXiv:2507.18220) | keine Zeilenangabe | teilweise | zusammengelegt | Nr. 16; Zeitschriftenfassung 2026, Key-Jahr 2025. |
| Yousefi u. a. 2015 | keine Zeilenangabe | korrekt | zusammengelegt | Nr. 111; B-Angaben (S) bestätigt, Autoren ergänzt. |
| Zhang u. a. 2022 (arXiv:2202.12803) | keine Zeilenangabe | teilweise | zusammengelegt | Nr. 99; L1 'and others', Prüflauf vollständige Autoren, ACC 2022. |
| Zinage u. a. 2022 | bestätigt | korrekt | zusammengelegt | Nr. 26; ch3 Z. 1000; IFAC-Fassung per PII gefunden, Autoren/DOI nicht gesehen. |
| Indirekte Verweise (A3.1–A3.5, B2.1–B2.5, D Fragen 1, 4, 5, 6) | keine Zeilenangabe | teilweise | weiterer Befund | Nicht einzeln aufgenommen; nur Zuordnung zu verifiziert.json-Nr. (u. a. Nr. 17, 34, 38, 41–43, 53, 55, 61, 64, 65, 67, 72, 73, 75, 83, 92, 114, 119–122, 126, 131, 137, 142, 149, 165, 168). |
| Patente US 8099222, US 9394858 | keine Zeilenangabe | nicht prüfbar | verworfen | L1 nutzt sie bewusst nicht als Beleg. |
| PySINDy-Doku docs/tips.rst | keine Zeilenangabe | nicht prüfbar | verworfen | GitHub-Datei, kein zitierfähiger Beleg; Ersatz Kaptanoglu u. a. 2022 oder desilvaPySINDyPythonPackage2020. |
| Autoren-Code Kaiser (eurika-kaiser/SINDY-MPC) | keine Zeilenangabe | nicht prüfbar | verworfen | Trägt L1-Aussage 'NMPC mit SQP', ist aber kein Beleg; am Papertext prüfen. |

## BibTeX-Gegenprüfung

- Paket 1 (verifiziert.json Nr. 0–33): 34 Einträge, 3 Änderungen.
  - `atamAdvancedAirPath2018` (Nr. 20): title: Eigenname geschützt, 'Diesel' zu '{Diesel}' (Wert unverändert, einheitlich mit {Koopman}/{Lyapunov} in den anderen Einträgen)
  - `beranModelbasedApproachControl2021` (Nr. 21): Kommentar korrigiert: Laut bemerkung wurden im Suchergebnis alle drei Autoren nur mit Initialen gesehen (Beran, T., Gärtner, J., Koch, T.), nicht nur der zweite. Neuer Kommentar: Vornamen Tobias und Thomas stammen aus dem Autorenfeld des Datensatzes. author-Feld unverändert, entspricht dem Datensatz
  - `yahagiSparseIdentificationNonlinear2025` (Nr. 29): title: Eigenname geschützt, 'Diesel' zu '{Diesel}' (Wert unverändert)
- Paket 2 (verifiziert.json Nr. 34–67): 34 Einträge, 1 Änderungen.
  - `nellesNonlinearSystemIdentification2000` (Nr. 60): address von {Berlin, Heidelberg} auf {Berlin/Heidelberg} gesetzt, wörtlich wie im venue des Datensatzes ("Springer, Berlin/Heidelberg (XVII, 786 S.)")
- Paket 3 (verifiziert.json Nr. 68–101): 34 Einträge, 4 Änderungen.
  - `qinSurveyIndustrialModel2003` (Nr. 71): author von Initialen auf die Form des Datensatzes geändert: {Qin, S. Joe and Badgwell, Thomas A.}. Kommentar sagt jetzt, dass die Vornamen laut Prüflauf aus Vorwissen stammen und im Suchergebnis nur Initialen standen (prüfen).
  - `pannocchiaOffsetfreeMPCExplained2015` (Nr. 73): author von Initialen auf die Form des Datensatzes geändert: {Pannocchia, Gabriele and Gabiccini, Marco and Artoni, Alessio}. Kommentar mit Hinweis auf Vorwissen des Prüflaufs und Initialen im Suchergebnis angepasst.
  - `morariNonlinearOffsetfreeModel2012` (Nr. 74): author von Initialen auf die Form des Datensatzes geändert: {Morari, Manfred and Maeder, Urban}. Kommentar ergänzt: Vornamen aus dem Autorenfeld des Datensatzes, im Suchergebnis nur Initialen.
  - `hirshSparsifyingPriorsBayesian2022` (Nr. 97): eprint {2107.02107} und archivePrefix {arXiv} entfernt. Die arXiv-Nummer steht nur in der Bemerkung des Prüflaufs, nicht in venue oder url. Sie ist jetzt als Kommentarzeile zum Prüfen vermerkt.
- Paket 4 (verifiziert.json Nr. 102–135): 34 Einträge, 0 Änderungen.
- Paket 5 (verifiziert.json Nr. 136–169): 34 Einträge, 2 Änderungen.
  - `theilerTestingNonlinearityTime1992` (Nr. 141): Kommentarzeile korrigiert: „laut Finder“ entfernt. Der Datensatz sagt nur, dass Farmer, J. D. als fünfter Autor in keinem Ergebnis gesehen wurde, und nicht, woher die Angabe stammt. Neu: „Farmer, J. D. als fünfter Autor im Prüflauf in keinem Ergebnis gesehen (Autorenfeld des Datensatzes); Liste und Reihenfolge prüfen“. Felder unverändert. Gleiche Änderung in bib_5_bauen.py nachgezogen.
  - `jonssonUseExtendedKalman2007` (Nr. 145): Kommentarzeile korrigiert: „(vom Finder)“ entfernt, weil das nicht im Datensatz steht. Der Datensatz sagt nur, dass die Initialen im Ergebnis nicht gesehen wurden. Neu: „Initialen laut Autorenfeld des Datensatzes G. R. Jonsson, S. Lalot, O. P. Palsson, B. Desmet, im Suchergebnis nicht gesehen, prüfen“. Das author-Feld bleibt bei den gesehenen Nachnamen. Gleiche Änderung in bib_5_bauen.py nachgezogen.

## Endprüfung der zusammengeführten Datei

Sieben Prüfagenten mit getrennten Blickwinkeln (Schreibregeln in drei Abschnitten, Querverweise, Quellenbelege in zwei Abschnitten, Stichprobe von 35 Zeilenangaben und fünf Rechnungen), danach Einarbeitung durch zwei Agenten nacheinander.

- stil-1: 22 Funde
- stil-2: 11 Funde
- stil-3: 31 Funde
- verweise: 24 Funde
- quellen-1: 16 Funde
- quellen-2: 24 Funde
- stichprobe: 6 Funde
- einarbeiten:1: 67 umgesetzt, 1 nicht umgesetzt (Doppelungen oder schon erledigt)
- einarbeiten:2: 44 umgesetzt, 19 nicht umgesetzt (Doppelungen oder schon erledigt)

### Umgesetzte Änderungen

- stil-1, 86: Zeilenkorrektur ersetzt. ch2 hat 1113 Zeilen (awk NR=1113; wc zählt 1112, weil der letzte Zeilenumbruch fehlt). Die Notiz steht in Z. 1111, Z. 1113 ist eine weitere Kommentarfrage.
- stil-1, 482: `B ≠ 0` ersetzt durch die Bedingung für den stationären Gain `C(I − A)^{−1}B ≠ 0` (Schur-Komplement nachgerechnet; L2 schrieb ebenfalls „stationärer Gain ≠ 0“).
- stil-1, 226: „(übernächster Punkt)“ ersetzt durch „(Punkt „Konfundierung zu eng …“ unten)“. Das erledigt auch den gleichlautenden Fund der Linse verweise zu Z. 226.
- stil-1, 344: Kennzeichnung „beide L1, nicht gegengeprüft“ ergänzt. Otto und Ahmadi stehen nicht in verifiziert.json.
- stil-1, 7: Neuer Lesehinweis „Befundkennungen der Einzelläufe“ (L1-x.y, L2-Kx-y, L1-Frage n, L2-Fn, L1-Beitrag n) nach Z. 7 eingefügt. Die Struktur ist gegen L1.md und L2.md geprüft.
- stil-1, 21: Die Formulierung „Lücke bestätigt“ ist durch den Leerbefund mit „kein Nachweis der Nichtexistenz“ ersetzt.
- stil-1, 651: „in der Literatur nicht ausdrücklich zu finden“ → „in der Suche nicht ausdrücklich gefunden“.
- stil-1, 29: Zitat mit Auslassungszeichen („Brennstoffmodus … wirkt nur über die Eingänge“). Wortlaut gegen ch2 Z. 958–959 geprüft.
- stil-1, 551: Wort „nichtlineare“ im Zitat ergänzt, geprüft an ch3 Z. 202–203.
- stil-1, 463: Den Lesehilfe-Bandwurmsatz in vier Stichpunkte aufgeteilt.
- stil-1, 539: Grammatik korrigiert: „vom Verhältnis von wahrem zu modelliertem Gain“.
- stil-1, 93: „Umkehrspanne“ → „Umkehrspiel“.
- stil-1, 95: „Umkehrspanne“ → „Umkehrspiel“.
- stil-1, 496: „verliert den konvexen QP“ → „verliert das konvexe QP“.
- stil-1, 409: „Gegenstromer“ → „Gegenstrom-Wärmeübertrager“.
- stil-1, 444: Satz ergänzt: „Für SINDy in der Sichtung nicht gefunden.“
- stil-1, 483: EMA eingeführt und „vorhanden“ relativiert: „eine Implementierung der exponentiellen Glättung (EMA), falls im Code vorhanden, …“.
- stil-1, 617: „L2(μ)“ → „L²(μ)“.
- stil-1, 443: „eDMDc“ → „\edmdc“.
- stil-1, 51: Semikolons als Trenner in der Quellenaufzählung. Den Text „Wu 2026“ habe ich wie im Fund vorgegeben stehen lassen; dieselbe Mehrdeutigkeit wie in Z. 846 besteht auch hier und in Z. 513, 699 und 1924, nicht geändert.
- stil-1, 566: „im Reglertakt“ → „im MPC-Takt … (ch2 Z. 1089 nennt ihn „Reglertakt“)“.
- stil-1, 292: Verweis präzisiert zu „(K1, Bedingung (b); K5, Punkt „Die Rate trägt nur den schwachen Rest“)“.
- stil-2, 807: Beitragsformulierung BT6 lautet jetzt „… mit freiem Absolutterm nur bei passenden Koeffizienten (Summenbedingung)“, Herkunft „(L1; bei der Zusammenführung an die Einordnung unten angepasst)“. Den ersten Satz in Z. 820 habe ich durch „Die Einschränkung „nur bei passenden Koeffizienten“ betrifft das feste Modell (Variante a).“ ersetzt.
- stil-2, 1116: „kein Literaturmaß“ → „ob es dafür ein etabliertes Literaturmaß gibt, nicht geprüft“.
- stil-2, 754: „sondern auch an seiner Stellverstärkung `∂\Tout/∂\valveCA`“ (partielle Ableitung wie in ch2 Z. 809).
- stil-2, 1267: `T_stat` → `\Tstat` in der zweistufigen Mischungsform.
- stil-2, 1269: `∂T_stat/∂\valveCA` → `∂\Tstat/∂\valveCA`.
- stil-2, 1331: Alle vier `T_stat` durch `\Tstat` ersetzt. Anker in Z. 1334 ist jetzt Gl. `eq.grundlagen.basic.stufen` (zweistufig), dazu die einstufige Ersatzform Gl. `eq.Tout.stat`. Hinweis: E1.1 K6 (Z. 332) und Z. 1476 verwenden für die zweistufige Form weiter `T_stat`. Das lag außerhalb des Funds und ist nicht geändert.
- stil-2, 1117: k-Schritt → h-Schritt und `h = 1 … N`. In Z. 1116 „(Einschritt, Freilauf, h-Schritt)“.
- stil-2, 1249: Komma durch Semikolon ersetzt („steigt `T_stat`; `dε/d\valveCA` und …“).
- stil-2, 1338: „- Mitte Gl.“ → „- Bildmitte: Gl.“.
- stil-2, 846: „Wu 2026 (Autor, Kriterium)“ → „Wu 2026a (…)“.
- stil-2, 978: „Für EDMDc Wu 2026“ → „Wu 2026a“.
- stil-3, 1587: In Tabelle E4.2 die Titel aus quellen_E.bib (Tag methanol-E4) bei Pan 2015, Dierickx 2023 (SAE), Karvounis 2025 (ATE 281), Karvounis 2025 (Fuel 381), Pu 2024, Dierickx 2023 (Fuel 345), Kiouranakis 2025 und Dierickx 2021 ergänzt. Bei den sieben Einträgen ohne DOI oder URL steht „DOI/URL nicht gesehen“. Der PII-Eintrag hat „Jahr nicht gesehen“ und die ScienceDirect-URL aus der Bib. In der Kandidatenzeile steht der Status [nur bibliografisch] jetzt je Quelle. Z. 1587 bleibt unverändert.
- stil-3, 1452 (Bias): „Niveaueffekt, vom Beobachter ausgleichbar“ ist ersetzt. Neu steht dort: betriebspunktabhängiges Niveau, der Beobachter gleicht nur den Niveauanteil aus, die Spanne ändert sich um ±b und trifft den Ventil-Gain (ch2 Z. 775–782), nur ein gleicher Bias auf \Tin und \TLT lässt die Spanne unverändert. Die Algebra habe ich nachgerechnet.
- stil-3, 1452 (\mrel): „trifft Dynamik und Gain“ → „trifft im festen Modell Dynamik und Gain; beim Neufit … in die Koeffizienten (ch2 Z. 697–700)“.
- stil-3, 1526: Satz nach Vorschlag ersetzt: echter Wechsel des Regelgesetzes im Unterschied zur Diesel-Sättigung. Verweis auf „E1.1 K4“ korrigiert.
- stil-3, 1495: Goel u. a. 2020 als IEEE Control Systems Magazine 40(4) laut Prüflauf, dazu arXiv-Preprint 2003.03523.
- stil-3, 1494: Goel u. a. 2020 als „IEEE Control Syst. Mag., auch als arXiv-Preprint“.
- stil-3, 1506: Goel u. a. 2020 wie bei Z. 1494 angepasst.
- stil-3, 1773: out_bib_L1.bib → `quellen_E.bib`. Ebenso Z. 1819 („als Entwurf nicht in `quellen_E.bib`“), Z. 1839 („… nicht in `quellen_E.bib`, dort steht nur die Fassung des Prüflaufs“) und Z. 1855 („zusätzlich in `quellen_E.bib` (Tag …)“). Geprüft: alle 17 Einträge aus out_bib_L1.bib stehen in quellen_E.bib, Otto, Ahmadi und die übrigen nur indirekt genannten Quellen nicht.
- stil-3, 1839 (verifiziert.json Nr.): Die Alternative aus dem Fund ist umgesetzt. Alle 170 Einträge der Gruppe 1 tragen jetzt „Nr. x ·“ mit der Nummer aus verifiziert.json. Die Zuordnung lief über den Titel, eins zu eins geprüft, Stichproben stimmen: Belsley 82, Bakarji 38, Loiseau 168, Nelles 60, Zinage 26, Goel 156. Die Lesart-Zeile verweist auf diese Nummer, dazu kommt ein neuer Stichpunkt im Kopf der Quellenliste.
- stil-3, 1918: Einträge in der Quellenliste markiert. Badwe: Echo-Risiko, Autoren, Band, Seiten und DOI nur aus der Suchzusammenfassung. Meda u. a. 2026: Echo-Risiko, auf der ASME-Seite prüfen. Douma: Autoren nur aus dem Suchtext. Die Texte stammen aus verifiziert.json Nr. 110, 25 und 63. Z. 1918 trennt jetzt „Autoren nur aus Suchzusammenfassung“ (Douma, Sirola) von „Echo-Gefahr“ (Meda 2026, Badwe), weil verifiziert.json ein Echo nur für Meda 2026 und Badwe nennt.
- stil-3, 1642: Die Springer-URL bei He & Asada 1993 ist als reine Fundstelle gekennzeichnet (Kapitel von Nelles 2020, Original in IEEE Xplore nicht gefunden).
- stil-3, 1717: Die abgebrochene Korrektur bei Shook u. a. 1991 ist mit dem Inhalt aus verifiziert.json Nr. 86 vervollständigt.
- stil-3, 1588: BibTeX-Zeile präzisiert zu „Die Quellen der Gruppe 1, die Entwürfe der Gruppe 2 mit „BibTeX: ja“ und die Methanol-Quellen der Tabelle E4.2 …“. quellen_E.bib hat 198 Einträge = 170 + 11 + 17.
- stil-3, 1922: `boldDataDrivenMPCStability2025` = arXiv 2505.05951 als fraglich markiert (Bold ist dort vierte Autorin, Erstautorin Schimperna). Verweis auf „Quellenliste Gruppe 1 Nr. 1“ statt „Z. 1710“, weil sich die Zeilen verschoben haben.
- stil-3, 1448: Shardt & Huang 2011 eindeutig gemacht: „(J. Process Control 21, Totzeit und Abtastzeit)“.
- stil-3, 1637 (Dopplung): „Korrektur: Korrektur:“ achtmal durch „Korrektur:“ ersetzt (Z. 1637, 1666, 1682, 1693, 1707, 1743, 1746, 1751), „Korrektur: Korrektur/Ergänzung:“ zweimal durch „Korrektur/Ergänzung:“ (Z. 1720, 1739).
- stil-3, 1637 (abgeschnitten): „… (L2)“ → „gesehen; IEEE-DOI nicht gesehen. (L2)“ nach verifiziert.json Nr. 156.
- stil-3, 1666: Loiseau-Bemerkung vervollständigt (Theor. Comput. Fluid Dyn. 2020, DOI in der Springer-URL gesehen, Endseite nicht gesehen).
- stil-3, 1680: Narasingam-Bemerkung vervollständigt (Nr. 162).
- stil-3, 1689: Pan/Li-Bemerkung vervollständigt, ohne Ich-Form (Nr. 121).
- stil-3, 1696: Peretzki-Bemerkung vervollständigt (Nr. 84).
- stil-3, 1718: Shook 1992-Bemerkung vervollständigt (Nr. 87).
- stil-3, 1609: „siehe Bemerkung“ ersetzt durch „Suchzusammenfassung nennt Bhadriraju, Khan, Kwon; auf der Verlagsseite prüfen“ (Nr. 27).
- stil-3, 1650: Die entstellte Klammer ist ersetzt, allerdings abgewandelt: „Chemical Engineering and Processing (gesehen; Zusatz „: Process Intensification“ möglich, nicht gesehen)“. Laut verifiziert.json und quellen_E.bib wurde nur „Chemical Engineering and Processing“ gesehen, deshalb nicht den vollen Namen als belegt eingesetzt.
- stil-3, 1917: DOI-Hinweis nach Gruppen getrennt: Gruppe 1 nur gesehene DOIs, Gruppe 2 DOIs aus Lauf 1 bzw. A, B, D (G/T), nicht gegengeprüft.
- stil-3, 1920: „vermutlich Wiley-Neuausgabe“ → „laut Prüflauf Wiley-Series-Nachdruck 2004“.
- stil-3, 1939: Annahmen ergänzt (35 °C, 80 % r. F., 1,013 bar), 4 bar absolut mit rund 57,5 °C wie in Z. 405. Nachgerechnet mit taupunkt.py: 57,44 °C bei 4,0 bar absolut, 57,51 °C bei 4,013 bar absolut. Z. 210 behält die Rundung auf 57 °C, Z. 405 erklärt sie.
- stil-3, 1550: Zitat zerlegt: „keine Kondensation“ und „konstante Stoffwerte“ (ch2 Z. 509).
- stil-3, 1515: Zitat wörtlich „Stellglied nur das HP-Ventil“ (Auftrag E).
- stil-3, 1487: Wirgin 2004 als arXiv-Preprint gekennzeichnet.
- stil-3, 1404: „dürfen nur genannt werden, soweit sie freigegeben sind“.
- verweise, 226: Doppelter Fund, zusammen mit stil-1 Z. 226 einmal umgesetzt.
- verweise, 1062: „ch3 Z. 757–775“ → „ch3 Z. 764–775“. An kontext/ch3.tex geprüft: Z. 757–762 sind Kommentar.
- verweise, 887: Die Datenspalte der Zinage-Zeile in E2.2 (b) lautet jetzt „Experimentaldaten laut Abstract (L2 schrieb „Prüfstand“)“.
- verweise, 1506 (jetzt 1511): Anker in E3.4. Statt des OASIS-P-Keys steht jetzt Bhadriraju u. a. 2020 (OASIS, AIChE J.), mit Hinweis, dass der Key OASIS-P meint (E1.3). Den Goel-Teil hatte Teil 1 schon berichtigt.
- verweise, 615 (jetzt 620): Beleg für die Nachführung in F-Frage (H) Übertragbarkeit ist jetzt Bhadriraju u. a. 2020 (OASIS). Der L1-Key ist als OASIS-P zur Fehlerprognose gekennzeichnet, mit Verweis auf E1.3.
- verweise, 725 (jetzt 730): BT3 nennt jetzt „E2.3 Zeilen 1 und 2, nach der Zusammenführung Stärke stark auf Websuch-Ebene“ statt „Stärke mittel“.
- verweise, 698 (jetzt 703): BT2 nennt jetzt „Stärke nach der Zusammenführung stark (E2.3 Zeile 5)“.
- verweise, 1822 (jetzt 1828): Zuordnung bei Auftrag A, A3.3 von BT1 auf BT3 berichtigt.
- verweise, 1958 (jetzt 1964): Satz lautet jetzt „keine Zahl zur Modellgüte“. Die Formelwerte (E1.1 K3: 0,77 gegen 0,86; E1.2: C_r = 0,9999; E1.1 K5: ε-NTU-Schwellen) sind als reine Illustrationen benannt.
- verweise, 19 (jetzt 20): Kurzfassung führt die Grey-Box-Einordnung jetzt als „dazu die unter K4 geführte Grey-Box-Einordnung, die der eigenen Linie widerspricht“.
- verweise + quellen-1, 263 (jetzt 264): Status von Akan u. a. 2024 lautet jetzt „Titel und Venue im Prüflauf bestätigt, Nr. 165, Autoren dort nicht gesehen, siehe E2.2“ statt „nicht gegengeprüft“.
- verweise + quellen-2, 1918 (jetzt 1924 und 1654): Die Echo-Markierungen für Meda, Badwe und Douma hatte Teil 1 schon gesetzt. Neu ist der Echo-Hinweis am Eintrag Jonsson u. a. 2007 (Nr. 145, aus der Bemerkung in verifiziert.json); Jonsson steht jetzt auch in der Offen-Liste unter „markiert bei“.
- verweise, 1288 (jetzt 1293): ch3 Z. 907–925 zu 909–925 geändert (an kontext/ch3.tex geprüft).
- verweise, 1095 (jetzt 1100): ch3 Z. 885–889 zu 886–889 geändert (geprüft).
- verweise, 1409 (jetzt 1414): ch3 Z. 307–311 zu 308–312 geändert (geprüft).
- quellen-1, 610 (jetzt 615): Die falsche Zuschreibung „statt zufälliger Aufteilung“ ist ersetzt. Neu: gewöhnliche K-fach-CV laut Abstract zulässig bei rein autoregressiven Modellen mit unkorrelierten Fehlern (Bergmeir, Hyndman, Koo 2018), sonst Blöcke (Idee S3); Bergmeir & Benítez 2012 fanden empirisch keine praktischen Folgen.
- quellen-1, 655 (jetzt 660): BT1-Überschrift eingeschränkt. Durchfluss als Stellgröße trägt nur der Abstract von Ripa u. a. 2025. Bei Pan, Li 2024 steht laut Prüflauf nur „Eingang-Zustand-Bilinearität“, das Produkt Medienstrom × Temperaturdifferenz nicht.
- quellen-1, 444 (jetzt 445): E1.3 nennt statt „Bold u. a. 2025, Nachfolger Schimperna“ jetzt den Key `boldDataDrivenMPCStability2025` mit dem Vermerk, dass die Zuordnung offen ist (Verweis auf Offen). Beim Befund „praktische asymptotische Stabilität“ steht jetzt die Prüflauf-Bemerkung zu Nr. 2 (älterer Beitrag arXiv 2408.12457); ob der Key diese Arbeit meint, bleibt offen.
- quellen-1, 978 (jetzt 983): Wu 2026a in E2.3 Zeile 5: Herkunft lautet jetzt „L2 und Auftrag D, Frage 3, aus Lauf 1“ statt „nur L2“.
- quellen-1, 977 (jetzt 982): „qLPV mit Zustandsscheduling“ ersetzt durch „qLPV-MPC … Scheduling-Größen laut Prüflauf im Abstract nicht erkennbar“.
- quellen-1, 227 (jetzt 228): Van den Hof & Schrama 1993 ist jetzt Kandidat für die Notiz Z. 702–703. Vermerkt ist, dass die Eignung laut Prüflauf nicht geprüft ist, dazu eine Warnung vor der gleichnamigen CDC-Vorfassung 1992.
- quellen-1, 227 (jetzt 228): Chiuso 2007 nur noch mit Vorbehalt. Laut Prüflauf ist PBSID dort eine bestehende Klasse, als Erstdefinition also nicht belegt; die Erstquelle ist getrennt zu suchen.
- quellen-1, 262 (jetzt 263): Bei Champion u. a. 2019 steht jetzt „[nur Abstract; zeigt das laut Prüflauf nur indirekt, E1.3]“.
- quellen-1, 448 (jetzt 449): „Metadaten bestätigt“ geändert zu „Metadaten laut L2 (…; nicht im zweiten Prüflauf)“.
- quellen-1, 502 (jetzt 507): Falcone u. a. 2007: „Zuordnung zur sukzessiven Online-Linearisierung laut Prüflauf nicht im Abstract-Auszug“ statt „nur teilweise gesehen“.
- quellen-1, 104 (jetzt 105): Yahagi 2026 nutzt die Daten jetzt „laut ch3“. Ergänzt: Die Closed-Loop-Herkunft hat der Prüflauf im Abstract-Auszug nicht gesehen (E1.3).
- quellen-1, 513 (jetzt 518, 521, 704, dazu 52 und 1930): „Wu 2026“ an allen Stellen zu „Wu 2026a“ vereinheitlicht (arXiv 2605.17966).
- quellen-1, 1825 (jetzt 1831): Jahr ergänzt: „Åström & Wittenmark 1997 (3. Aufl.; Jahr nur aus dem Key des B-Entwurfs)“.
- quellen-2, 1919 (jetzt 1925): Die Offen-Liste der ungeprüften Quellen enthält jetzt auch die Methanol-Quellen aus E4.2.
- quellen-2, 1520 (jetzt 1525): E4-Lesehinweis ergänzt: ✓ ist kein Prüfvermerk, keine dieser Quellen steht im zweiten Prüflauf.
- quellen-2, 1028 (jetzt 1033): E3.0 lautet jetzt „(Quellenliste, Gruppe 1); ausgenommen sind die †-Quellen (Gruppe 3) und die Methanol-Quellen aus E4.2“.
- quellen-2, 1495 OASIS (jetzt 1500): D9-Anker nennt jetzt Bhadriraju u. a. 2020 (OASIS, AIChE J.); der vorhandene Key ist als OASIS-P zur Fehlerprognose gekennzeichnet.
- quellen-2, 1491 (jetzt 1496): D9-Kurzfassung nennt jetzt Bhadriraju u. a. 2020 (OASIS) statt des OASIS-P-Keys, mit Verweis auf E1.3.
- quellen-2, 1506 (jetzt 1511): wie der verweise-Fund zu 1506. Den OASIS-Teil habe ich ersetzt, der Goel-Teil stand schon richtig.
- quellen-2, 1358 (jetzt 1363): Falcone u. a. 2007 in S2: „MPC für aktive Lenkung in zwei Varianten unterschiedlichen Rechenaufwands; sukzessive Linearisierung laut Prüflauf nicht im Abstract-Auszug, am Original prüfen“.
- quellen-2, 1112 (jetzt 1117): Douma u. a. 2008 jetzt „zur Gültigkeit des Kreuzkorrelationstests“: Standardtest gilt nur, wenn das System im Modellsatz liegt; ein Bezug zum geschlossenen Kreis ist im Auszug nicht gesehen.
- quellen-2, 1398 (jetzt 1403): Løvland in A13 ergänzt um „laut ch3-Kommentar Z. 667 Theorem 1; im Abstract nicht gesehen, siehe E1.3“.
- quellen-2, 1412 (jetzt 1417): „Goyal, Duff, Benner“ zu „Goyal, Pontes Duff, Benner“ berichtigt.
- quellen-2, 1507 (jetzt 1512): „Goyal, Duff, Benner“ zu „Goyal, Pontes Duff, Benner“ berichtigt.
- quellen-2, 1516 (jetzt 1521): Valábek u. a. 2025 in E3.4 ergänzt um „nicht gegengeprüft, in L2 nur in der †-Liste“.
- quellen-2, 1101 (jetzt 1106): Belsley, Kuh, Welsch 1980 jetzt „Kandidat“ für den VIF-Beleg. Laut Prüflauf trägt die Verlagsbeschreibung nur Kollinearitätsdiagnostik allgemein; die VIF-Stelle ist im Buch nachzuschlagen.
- quellen-2, 1920 Nelles (jetzt 1926): „vermutlich die zweite Auflage“ ersetzt durch: L1 und Auftrag B nennen ausdrücklich die 2. Aufl. aus dem B-Entwurf (ISBN, DOI), das Jahr 2020 ist dort ungeprüft.
- quellen-2, 1922 (jetzt 1928): abgekürzten Key `yonezawa…2025` zu `yonezawaSparseIdentificationNonlinear2025` ausgeschrieben (ch3 Z. 987 geprüft).
- quellen-2, 1782 (jetzt 1788, dazu 1840): Vorbehalt aus A.md ergänzt: Ob die Aussage im Kaptanoglu-Papier steht, hat Auftrag A nicht geprüft.
- stichprobe, 269 (jetzt 270): „noch kleiner“ ersetzt durch die Elastizität N/(e^N − 1). Bei gleichem N ist sie erst ab N ≈ 1,8 kleiner als 1 − ε der Bilanzform und ab N ≈ 1,15 kleiner als die der Rate; bei gleichem ε ist sie stets größer. Schwellen in Python nachgerechnet (1,793 bzw. 1,146).
- stichprobe, 196 (jetzt 197): ch2 Z. 536–538 zu ch2 Z. 590–591 geändert, dort steht ε = (C_min/C_L) ε_Q (geprüft).
- stichprobe, 697 (jetzt 702): Dahdah-Verweis lautet jetzt „ch3 Z. 752–754, geprüft; Z. 626–627 nennt nur die Verzerrung bei naivem EDMD“ (geprüft).

### Nicht umgesetzt

- stil-3, 1839: Der Teil „verifiziert.json nach ergebnisse/E_mehrwert_ideen_2026-09-25_dateien/ kopieren und in der Dateiliste aufführen“ ist nicht ausgeführt. Dieser Auftrag erlaubt nur Änderungen an gesamt_merged.md, deshalb habe ich die Alternative umgesetzt (Nr. vor jedem Eintrag der Gruppe 1). Wenn die Datei trotzdem mitgeliefert werden soll, muss der Zusammenbau-Schritt sie kopieren und in „So nutzt du die Dateien lokal“ nennen.
- verweise, 1495: bereits in Teil 1 umgesetzt. Goel u. a. 2020 steht in Z. 1499 und 1500 schon als IEEE Control Syst. Mag. mit arXiv-Vorfassung.
- verweise, 1922 (Bold-Key): bereits in Teil 1 umgesetzt. Z. 1928 führt die Zuordnung zu arXiv 2505.05951 als „fraglich“, mit Verweis auf Schimperna als Erstautorin (Nr. 1). Z. 437/438 bleibt unverändert, weil die Zuordnung offen ist.
- verweise, 1773: bereits in Teil 1 umgesetzt. Kein Verweis auf out_bib_L1.bib mehr, Z. 1779 nennt quellen_E.bib.
- verweise, 1819: bereits in Teil 1 umgesetzt (Z. 1825 nennt quellen_E.bib).
- verweise, 1855: bereits in Teil 1 umgesetzt (Z. 1861 nennt quellen_E.bib mit Tag lauf1-nicht-gegengeprueft).
- verweise, 1839 (verifiziert.json-Verweise): in Teil 1 anders gelöst. Gruppe 1 trägt vor jedem Eintrag „Nr. x“, und der Lesehinweis der Quellenliste (Z. 1591) sagt, dass „verifiziert.json Nr. x“ darauf zeigt. Die Lesart in Z. 1845 ist angepasst. Die Nummern lassen sich damit lokal nachschlagen.
- verweise + stichprobe, 482 (Rangbedingung): bereits in Teil 1 umgesetzt (Z. 487 nennt C(I − A)^{−1}B ≠ 0, wie E1.1 K2).
- verweise, 1526 (E1 K4): bereits in Teil 1 umgesetzt, der Text „E1 K4“ kommt nicht mehr vor.
- verweise + quellen-2, 1448 (Shardt & Huang): bereits in Teil 1 umgesetzt (Z. 1453 nennt J. Process Control 21, Totzeit und Abtastzeit).
- quellen-1, 887 (Cummins/Prüfstand): bereits in Teil 1 umgesetzt (Z. 892: „Experimentaldaten laut Abstract (L2 schrieb „Prüfstand“)“).
- quellen-1, 344 (Otto, Ahmadi & El Khadir): bereits in Teil 1 umgesetzt (Z. 345: „beide L1, nicht gegengeprüft“).
- quellen-2, 1922 (Bold-Key): Die Offen-Zeile hatte Teil 1 schon auf „fraglich“ gesetzt. Den Hinweis auf arXiv 2408.12457 (Prüflauf-Bemerkung zu Nr. 2) habe ich in E1.3 Z. 445 eingefügt, nicht noch einmal in Offen.
- quellen-2, 1494 (Goel, Preprint): bereits in Teil 1 umgesetzt (Z. 1499).
- quellen-2, 1495 (Goel, Metadaten): bereits in Teil 1 umgesetzt (Z. 1500).
- quellen-2, 1917 (DOIs in quellen_E.bib): bereits in Teil 1 umgesetzt (Z. 1923 unterscheidet Gruppe 1 und Gruppe 2).
- quellen-2, 1487 (Wirgin): bereits in Teil 1 umgesetzt (Z. 1492: „arXiv-Preprint“).
- quellen-2, 1920 (Belsley-DOI): bereits in Teil 1 umgesetzt (Z. 1926: „laut Prüflauf Wiley-Series-Nachdruck 2004“).
- stichprobe, 1062 (Entwurfsreste): bereits in Teil 1 umgesetzt (Z. 1067 nennt ch3 Z. 764–775).
- stichprobe, 1334 (eq.Tout.stat): bereits in Teil 1 umgesetzt (Z. 1339 nennt Gl. eq.grundlagen.basic.stufen, die einstufige Form nur als Ersatzform).

## Nachtrag: Korrekturen aus Lauf 1 nach der Zusammenführung (Commit 9390bfd)

- Anlass: Die Sitzung von Lauf 1 hat nach dem Schnappschuss für die Zusammenführung einen eigenen adversarialen Prüfdurchlauf gepusht (Commit 9390bfd, „Korrekturen aus adversarialem Prüfdurchlauf eingearbeitet“, 184 Zeilen neu, 133 entfernt). Damit nichts verloren geht, ist jede dieser Korrekturen einzeln gegen die Gesamtdatei abgeglichen.
- Vorgehen: Wortdiff 653ece4 → 9390bfd in 51 Punkte K01–K51 zerlegt; sechs Prüfer (je Abschnitt einer) haben jeden Punkt an den genannten Zeilen in `kontext/ch2.tex` bzw. `ch3.tex` nachgelesen und in der ganzen Gesamtdatei gesucht. Status: abgedeckt (schon inhaltlich drin), teilweise (Kern drin, Detail fehlt oder eine von L1 zurückgenommene Aussage stand noch drin), fehlt, verworfen (L1-Korrektur sachlich falsch; kam nicht vor).
- Umsetzung: 88 Edit-Vorschläge, zwei davon für dieselbe Stelle (Modussprung in F4 und in Idee A13) zusammengelegt, 86 angewendet. Neue oder geänderte Stellen tragen die Marke „(L1-Korrektur)“.
- Zurückgenommene Aussagen, die jetzt überall ersetzt sind: „Dieselbetrieb ist Sättigung, kein zweites Reglergesetz“ (jetzt: eigene Betriebsart, formal Regler `F = 0`, Ljung-Argument mit Einschränkungen haltbar); „Sparsifizierung ersetzt die Trunkierung“ (jetzt: Regression ersetzt die Projektion, die Trunkierung ist die Wahl eines Zustands); „Pkw“ bei Vagapov 2024 (jetzt Nutzfahrzeug nach Titel der Diss.); „Wandtemperatur-Dynamik beeinflusst die Güte“ bei Zhang u. a. 2022; „Datenherkunft widersprüchlich“ bei Ou u. a. 2024 (jetzt CFD laut Abstract, S); `a ∈ (0,1)` als Stabilitätsbedingung (jetzt `|a| < 1`, `(0,1)` nur Plausibilität).
- BibTeX (`quellen_E.bib`, jetzt 197 Einträge): Entwurf `ouSparseIdentificationModeling2024` entfernt (Autoren und Jahr nur S, jetzt Kandidat ohne Key); bei `valabekDeepKoopmanEconomic2025` das Autorenfeld in einen `% ungeprüft:`-Kommentar verschoben (L1: nur S; L2 hat dieselben Namen nur einmal gesehen, †); bei `saltelliGlobalSensitivityAnalysis2008` Hinweis, dass das Key-Jahr ungeprüft ist. Kaleli 2020 bleibt, weil der L2-Prüflauf den Eintrag geprüft hat (Nr. 160, korrigiert). Zhang u. a. 2022 und Beran u. a. 2021 standen schon mit geprüften Metadaten aus dem L2-Prüflauf in der Datei.
- `ideen_E3.csv` unverändert: In E3.2 hat sich nur eine Anmerkungszeile unter der Tabelle geändert, keine Tabellenzeile.

| Nr. | L1-Stelle | Inhalt (Kurzform) | Status | Umsetzung |
|---|---|---|---|---|
| K01 | L1 1.4 | Stelle ARX ch3 Z. 155–195, NARX Z. 197–205 ergänzt. | abgedeckt | kein Edit |
| K02 | L1 2.3 | Grundlagenlücken präzisiert: Diskretisierung nur als Halbsatz (ch2 Z. 1089–1091); Totzeit nur physikalisch (ch2 Z. … | abgedeckt | kein Edit |
| K03 | L1 2.4 | SINDy-Solver: STLSQ, LASSO, Elastic Net stehen da (ch3 Z. 421–430); SR3 und Ungleichungsnebenbedingungen (Vorzeichen) … | teilweise | 2 Edits |
| K04 | L1 2.5 | POD-Galerkin: Galerkin nur für EDMD (ch3 Z. 303–307), Loiseau nur als Bibliotheksempfehlung (ch3 Z. 444–447). | teilweise | 1 Edit |
| K05 | L1 3.3 | „ändert nichts an den Limitierungen der linearen Modellklasse“ (ch3 Z. 201–205): SINDy nur in den Parametern linear, in … | teilweise | 2 Edits |
| K07 | L1 3.5 | Modell aus Modell „kann Güte der Quelle nicht übertreffen“ ch3 Z. 1141–1146; Z. 1141–1144 nennt Yahagi u. a. 2026 als … | abgedeckt | kein Edit |
| K08 | L1 3.6, neu | Kreuzterm im geschlossenen Kreis nicht unbedingt ≠ 0 (ch3 Z. 822–823, 838–840, 891–893): bei weißem Gleichungsfehler … | teilweise | 3 Edits |
| K06 | L1 alt 3.4 → neu 7.3 | LASSO-Zielfunktion ch3 Z. 427 mit ‖·‖₂², Bildunterschrift Z. 496–498 mit ‖·‖₂ (formal Square-Root-LASSO, anderer … | teilweise | 1 Edit |
| K09 | L1 4.1 | Modussprung (ch3 Z. 869–873, Ljung Abschn. 13.4): Ljung-Argument formal haltbar: fester Stellwert im Dieselbetrieb (ch2 … | teilweise | 10 Edits |
| K10 | L1 4.3 | Zentrierung (ch3 Z. 126–141): Spaltenzentrierung von Θ (Z. 130–137) ändert bei vorhandener, nicht bestrafter Konstante … | teilweise | 2 Edits |
| K11 | L1 5.1 | Doppelungen präzisiert: `eq.grundlagen.basic.stufen` ↔ unnummerierte Zweistufenform ch2 Z. 573–577 (und Z. 551–556); … | teilweise | 1 Edit |
| K12 | L1 5.3 | Biasgleichung gilt für jedes parameterlineare Modell, mit Korrektur K08. Aussage zur Schwellwertauswahl steht bereits … | teilweise | 1 Edit |
| K13 | L1 5.6 | „analoge Sensitivität ist für SINDy zu erwarten“ (ch3 Z. 625–628) von Korrektheit nach Durchdringung verschoben (nur … | teilweise | 1 Edit |
| K14 | L1 6.2 | Deutung als quasi-LPV-Modell (T_col,in, T_LTCW, ṁ_rel gehen schwach mit dem Hub mit, ch2 Z. 517–519, 775–780), Stelle … | teilweise | 3 Edits |
| K15 | L1 6.3 | Verschiebungsinvarianz: ch2 Z. 392–396 (Differenzen); in ch3 fehlt die Aussage. Exakt nur mit festgehaltenem ṁ_rel oder … | teilweise | 1 Edit |
| K16 | L1 7.1 | Rohentwurf ch3 Z. 761–777 (Z. 764–772 Tippfehler); Z. 761–774 (auskommentierte Überschrift und Rohentwurf) entfernen; … | abgedeckt | kein Edit |
| K17 | L1 7.2 | ch3 Z. 218–222: Satzfragment in Z. 218 doppelt zu Z. 220–222; Fragment „Der Koopman-Operator wirkt linear auf einen … | abgedeckt | kein Edit |
| K18 | L1 7.3 | „Esemble“ in ch3 Z. 506 Überschrift; Z. 552 nur Dateiname (optional, nur mit Umbenennung der Bilddatei); `\textbf` Z. … | abgedeckt | kein Edit |
| K19 | L1 7.6 | λ dreifach belegt: ch2 Z. 438, 1068; ch3 Z. 423, 428, 498. | abgedeckt | kein Edit |
| K20 | L1 F1 POD-Galerkin | Ein-Moden-Galerkin mit konstanter Ansatzfunktion ergibt eine Mitteltemperatur; T_eng,in als Zustand setzt … | teilweise | 2 Edits |
| K21 | L1 F3 NARX | Gemeinsam: Schätzung auf dem Einschrittfehler wie beim klassischen NARX (OLS/ERR); Unterschied nur zu … | teilweise | 1 Edit |
| K22 | L1 F4 CL-Verzerrung | Direkte Methode konsistent, wenn das Störmodell stimmt (weißer Gleichungsfehler), der Kreis eine Verzögerung enthält … | teilweise | 4 Edits |
| K23 | L1 F6 QP-Tauglichkeit | Affin in Zustand und g(u_HP) bei gegebenem Verlauf der Betriebsgrößen; QP nur mit linearem g oder v=g(u_HP) als … | teilweise | 2 Edits |
| K24 | L1 F7 Stabilität | Modell: skalar /a(ṁ_rel)/<1 für alle Betriebspunkte reicht; a∈(0,1) zusätzlich als Plausibilität, schließt Oszillation … | teilweise | 1 Edit |
| K25 | L1 Beitrag 1 = BT1 | „affin in Zustand und in g(u_HP) … unter angebbaren Bedingungen in einen linearen QP-MPC“. Bedingung: g linear oder … | teilweise | 3 Edits |
| K26 | L1 Beitrag 2 = BT3 Messdaten | Lücke: an Ladeluftkühler bzw. Ladelufttemperatur keine SINDy-/Koopman-Arbeit mit Messdaten; am Motorluftpfad mit … | teilweise | 2 Edits |
| K27 | L1 Beitrag 3 = BT4 Bewertung | Identifikation für die Regelung ist allgemein etabliert (Auftrag D, Frage 5); eine SINDy-/Koopman-Arbeit mit … | teilweise | 4 Edits |
| K28 | L1 Beitrag 5 = BT6 Invarianz | „Die Differenzbibliothek dieser Arbeit erzwingt Verschiebungsinvarianz der Prognose, solange die Betriebspunktfaktoren … | teilweise | 2 Edits |
| K29 | Verwandte, Kopf | Inhalte aus Suchzusammenfassungen (S) oder GitHub-Dateien (G), kein Volltext; „laut Abstract … (S)“ heißt … | teilweise | 1 Edit |
| K30 |  | Vagapov 2024 Diss.: Nutzfahrzeug (Titel der Diss. „Modellierung, Identifikation und modellbasierte Regelung des … | teilweise | 4 Edits |
| K31 |  | Zinage u. a. 2022: laut Abstract EDMD besser als NARX (G); für die Austrittstemperatur bei hoher Turbinendrehzahl NARX … | teilweise | 1 Edit |
| K32 |  | Kaleli 2020 und Ou 2024 in L1 jetzt „Kandidat“ (kein BibTeX-Entwurf, Autoren und Jahr nur S). | teilweise | 2 Edits |
| K33 |  | Zhang u. a. 2022: transiente thermische Motordynamik beeinflusst die Saugrohrdruck-Antwort, MPC laut Abstract robust … | teilweise | 1 Edit |
| K34 |  | Ou u. a. 2024: Daten laut Abstract aus CFD-Modell (Ansys Fluent), Messdaten nicht erwähnt (S); ersetzt „Datenherkunft … | teilweise | 2 Edits |
| K35 | L1 Idee 1 QP-Tabelle = S2 | Spalten: Terme Zustand×Zustand, Ventil×Zustand, g(u_HP) linear oder monoton invertierbar, Scheduling-Größen eingefroren … | teilweise | 2 Edits |
| K36 | L1 Idee 2 Invarianztest = A18 | ṁ_rel dabei festhalten; Absolutterm-Modelle bestehen nur bei Verstärkungssumme 1; Abweichung davon berichten (statt … | abgedeckt | kein Edit |
| K37 | L1 Idee 4 Residuentests = A3 | Weißheitstest auf Einschritt-Residuen bzw. Residuen eines Modells mit Störmodell; Kreuzkorrelationstest Residuum–u_HP … | teilweise | 5 Edits |
| K38 | L1 Idee 7 Stabilität | a(ṁ_rel) in (0,1) nur Plausibilität, Stabilität schon bei /a/<1; eingefrorene Eigenwerte bei mehreren Zuständen nicht … | teilweise | 1 Edit |
| K39 | L1 Idee 11 Rechenzeit | gegen den MPC-Takt aus Abschnitt `sec.methodik.mpc` (zum Vergleich Serienregler 500 ms, ch2 Z. 275), nicht gegen … | teilweise | 2 Edits |
| K40 | L1 Idee 12 Hyperparameter | Anker Cawley & Talbot 2010, Varma & Simon 2006 (Auftrag D, Frage 6). | abgedeckt | kein Edit |
| K41 | L1 Idee 13 Ersatzschaltbild = B8 | zu Gl. `eq.energiebilanz.dyn`: C_eff als Kapazität am Knoten T_eng,in, Leitwert ṁ_L c_p,L von Quelle T_col,in, Leitwert … | abgedeckt | kein Edit |
| K42 | L1 Ideen 19/20 | Anker Beobachter: `muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003` (Bib); … | abgedeckt | kein Edit |
| K43 | L1 große Ideen | Anker ergänzt: Online-Nachführung `bhadrirajuOASISPOperableAdaptive2021` (Bib), Quade u. a. 2018; MIMO mit LP-Ventil … | teilweise | 4 Edits |
| K44 | L1 Methodenanker | Statusspalte [nur bibliografisch] je Anker; Nutzenangaben als „(eigene Einschätzung)“ bzw. „(S)“ gekennzeichnet; Raue … | teilweise | 3 Edits |
| K45 | BibTeX Saltelli | Key-Jahr 2008 ungeprüft; Erscheinen Dez. 2007 laut Suchzusammenfassung (S); Key erst in Zotero nach Festlegen des … | teilweise | 3 Edits |
| K46 | BibTeX Valábek | Autorenfeld nur (S) → aus dem Eintrag in Kommentar verschoben; Nachname im Key damit ebenfalls nur (S). | teilweise | 4 Edits |
| K47 | BibTeX Zhang 2022 | Autoren (S) s. K33; ACC 2022 (T). | teilweise | 3 Edits |
| K48 | BibTeX Kaleli, Ou | Entwürfe entfernt, Kandidaten ohne Key (Autoren und Jahr nur S). Kaleli ist aber im L2-Prüflauf (Nr. 160, korrigiert) … | teilweise | 4 Edits |
| K49 | BibTeX Beran | schon in der Bib (`beranModelbasedApproachControl2021`, ch3 Z. 976); nur DOI 10.1007/s41104-021-00087-0 (T) gegen … | teilweise | 3 Edits |
| K50 | Offen | neue Punkte: Valábek-Autoren nur S; Kandidaten Kaleli/Ou mit Angaben; Beran-DOI abgleichen; Vagapov-Titel/URL für … | teilweise | 5 Edits |
| K51 | Anhang E | „Rechercheagent“ → „Copilot“ (in L1; in der Gesamtdatei nur prüfen, ob „Rechercheagent“ vorkommt und ob das zu ändern … | fehlt | 1 Edit |

### Gegenprüfung des Nachtrags

- Drei skeptische Prüfer (E1; E2; E3, E4, Quellen, Offen) haben jede eingearbeitete Änderung an `kontext/`, an den Schreib- und Quellenregeln und am Rest der Datei zu widerlegen versucht: 75 Änderungsblöcke geprüft, 17 beanstandet; dazu Stellen außerhalb der Blöcke, die durch die Korrekturen widersprüchlich geworden waren.
- Algebra bestätigt: Frisch-Waugh-Lovell bei Zentrierung mit unbestrafter Konstante; `E{φ v} = 0` bei weißem `v` und Verzug im Kreis; `|a| < 1` als Stabilitätsbedingung des skalaren Modells; `v = g(\valveCA)` als Entscheidungsvariable; Verschiebungsinvarianz exakt nur mit festem \mrel oder `q_rel`.
- 26 Fixes angewendet:
  - E1: „(DoE)“ ist ein Zusatz der Zusammenführung zu L1 K12 („Prüfstands- gegen Regelkreisdaten“) und widerspricht der per L1-Korrektur festgelegten Validierungsrolle der DoE-Daten (K4 Z. 230, F4 Z. 519, BT2 „DoE zurückhalten“).
  - E1: „deshalb“ hängt am vorhergehenden Satz („sonst bilinear“) statt an der Begründung: Das Scheduling geht schwach mit dem Hub mit.
  - E1: Das Gegenmittel (Schätzung auf unabhängig angeregten Daten, Validierung auf geregelten) und das Bewertungsschema (DoE zur Validierung) stehen unmarkiert gegeneinander; in K4 Z. 230 ist derselbe Konflikt mit „aber“ gekennzeichnet.
  - E1: Beides sind hinreichende, keine notwendigen Bedingungen. Das macht die Stelle konsistent mit E3 S5 („nachweisen“).
  - E1: Subjekt verrutscht: Nicht die Lags „gelten“, sondern der Test auf diesen Lags trägt nur bei weißen Residuen (K37).
  - E1: Außerhalb der Hunks (F4, Stichpunkt Literaturlage): Nach der L1-Korrektur zur DoE-Validierung darf das Schema „Fit auf Open-Loop-Daten“ nicht mehr als feststehende Wahl der Arbeit gelten.
  - E1: Außerhalb der Hunks (K3 Kurzbefund ch3 Z. 1149–1152): K30 präzisiert Vagapov 2024 auf „Nutzfahrzeug“; E2 Z. 852 und Offen Z. ~1940 sind schon angepasst.
  - E1: Außerhalb der Hunks (K6, Beitragsliste): Der verwiesene K6-Punkt heißt nach der L1-Korrektur „quasi-LPV-Deutung“.
  - E1: Außerhalb der Hunks und älter als die L1-Korrektur (E1.2-Tabelle): Die Zeile hat 6 statt 4 |, weil die Betragsstriche als Spaltentrenner zählen. Die Umformulierung ist gleichwertig und ohne |.
  - E1: Neue Zeile 8: Die Pfadangabe weicht vom Lesehinweis in Z. 10 und von der Dateiliste ab.
  - E2: Gleiche Einschränkung wie in F6 (Z. 502) und E1.1 K1 (Z. 83). Der übergeordnete L2-Punkt nennt „stückweise linear mit festen Stützstellen“ als eigenen QP-Weg; das widerspricht nach der L1-Korrektur „nur lineares g oder v = g(\valveCA)“ in BT1.
  - E2: Nach E1.1 K6 (Z. 317) ist bei festem Hub g(\valveCA)·ΔT kollinear mit ΔT. Identifizierbar ist nur a_0 + a_2 g(100 %), der ventilfreie Störpfad a_0 allein nicht.
  - E2: So lautet K26 bei L1 und die Fassung in E2.3 Zeile 1. Ohne die Einschränkung widerspricht die Stelle Z. 746, wo Rupprecht und Vagapov 2022 mit Messdaten genannt sind.
  - E2: Direkt nach „Sparsamkeit geht erst verloren …“ liest sich der Satz als Sparsamkeitsverlust reiner Differenzen. Nach der Algebra und nach E1.1 K4 (Z. 265) verschiebt sich nur das Absolutglied.
  - E2: L1 hat nur Vagapov 2024 („Pkw“ zu „Nutzfahrzeug“) korrigiert. Die Aussage zu Vagapov 2022 ist eine Folgerung der Zusammenführung und braucht die richtige Herkunftsmarke.
  - E2: „ihn“ hat in der Zelle keinen Bezug (grammatisch „Suchweg“ aus dem Spaltenkopf); gemeint ist der Residuen-Leerbefund.
  - E2: K50 verlangt diese Suchlücke unter Offen. Die neue Aussage in BT4 (Z. 769) steht bisher weder in „Offen zu E2.1“ noch im Abschnitt „Offen / nicht belegt“.
  - E3Q: K23/K25 (Δv-Strafe, Schranken in v) fehlen in S2. Ohne diesen Hinweis widerspricht (c) dem Stichpunkt „Nebenbedingungen …, alle linear: |Δu_k| ≤ Δu_max“, weil die Ratenschranke mit v = g(u) nichtlinear wird (E1.1 K1, Z. 84).
  - E3Q: Nach der L1-Korrektur (K14/K35, Z. 659, 1083, 1974) gehen \Tin, \TLT und \mrel mit dem Hub mit, die Termform ist also quasi-LPV. Die Spaltenzahl der Tabellenzeile bleibt 3.
  - E3Q: Der Test läuft im selben Stichpunkt auch gegen \Tin, \TLT und \mrel. Laut S2 liegen diese Größen schwach im Kreis. Dann gilt das Rückführungsargument (Ausschlag beim wahren Modell bei farbigen Residuen) auch für sie.
  - E3Q: Die Aussage steht nicht in L1 und war ohne Marke (Zusammenführung). Sie ist zu schwach: Enthielte der Modellsatz Strecke und H0, wären die Einschrittresiduen asymptotisch weiß. Offen ist nur die Größe der Verzerrung.
  - E3Q: Widerspruch im Stichpunkt: Das Beispiel „Ventilterm bei schwacher Anregung = praktisch nicht identifizierbar“ ist beim parameterlinearen Modell unmöglich, denn das quadratische Profil schneidet jede Schwelle. Die Ergänzung steht innerhalb der schon markierten …
  - E3Q: B5 (Z. 1452, außerhalb der Hunks) liest sich mit „Diesel/Sättigung“ noch als Gleichsetzung, die L1 zurückgenommen hat (K09; Nachtrag oben: „überall ersetzt“).
  - E3Q: `kaleliDevelopmentPredictiveBased2020` steht als Fassung des Prüflaufs in quellen_E.bib; „ohne BibTeX-Entwurf“ gilt nur für L1. Die Zeitschrift von Ou ist laut L1_neu ebenfalls nur (S).
  - E3Q: Ljung Abschn. 13.4 (Modussprung) steht doppelt in Offen (Z. 1943 und die ausführlichere neue Z. 1975).
  - E3Q: K50 und der Offen-Abschnitt von L1_neu führen diesen Punkt als neu. In der Gesamtdatei steht er nur in E2 (Z. 770), nicht in „Offen / nicht belegt“.
