# Auftrag E: Mehrwert und Ideensammlung aus Gutachtersicht

Ergebnis der Cloud-Sitzung vom 25.09.2026 zu `auftraege/E_mehrwert_ideen.md`. Prüfung durch Copilot lokal gegen Zotero und die Originale, bevor etwas in die Arbeit übernommen wird.

Hinweis zur Ablage: Auf diesem Branch liegt bereits `ergebnisse/E_mehrwert_ideen_2026-09-25.md` aus einer anderen, parallelen Cloud-Sitzung (Commit 653ece4). Diese Datei ist ein zweites, unabhängig erarbeitetes Ergebnis zum selben Auftrag und liegt deshalb unter eigenem Namen daneben. Die beiden Ergebnisse sind nicht zusammengeführt; Copilot kann sie nebeneinander prüfen.

## Lesehinweise

- Grundlage: `kontext/ch2.tex` und `kontext/ch3.tex` vollständig gelesen (Kopie vom 25.09.2026). Zeilenangaben „ch2 Z. …“ und „ch3 Z. …“ beziehen sich auf diese Kopien; nichts in `kontext/` wurde verändert.
- Netz: Nur die Websuche war nutzbar. Abrufe von Verlagsseiten, doi.org und arxiv.org waren gesperrt. Deshalb ist **kein Volltext gelesen**; der beste Status jeder Quelle ist [nur Abstract], viele sind [nur bibliografisch]. Seitenangaben und wörtliche Zitate fehlen aus diesem Grund.
- Quellenprüfung: Jede neu gefundene Quelle wurde in einem zweiten, unabhängigen Suchlauf auf Autoren, Jahr, Titel, Venue und DOI geprüft (170 Quellen: 116 bestätigt, 54 korrigiert, keine erfunden). 33 Quellen aus der letzten Nachrecherche konnten nicht mehr gegengeprüft werden, weil das Suchbudget der Sitzung (200 Suchen) erschöpft war; sie tragen ein †.
- „Eigene Algebra“ heißt: in dieser Sitzung von Hand oder mit kurzen Zahlentests nachgerechnet, keine Literaturaussage. Copilot rechnet nach.
- Keine Zahlen zur Modellgüte. Alle Ideen beschreiben Verfahren; Kennwerte kommen aus Thomas' Daten.
- Keine Firmeninterna über `kontext/` hinaus. Öffentliche Herstellerseiten (nur E4.5) sind als „kein wissenschaftlicher Beleg“ markiert.
- Schreibweise wie in der Arbeit: \Tout (`T_eng,in`), \Tin (`T_col,in`), \TLT, \THT, \valveCA (`u_HP`), \mrel, `Δp_HP`; HT und LT bezeichnen die Stufe des Kühlers.

## Kurzfassung

- **E1 Lektorat:** je Kriterium K1–K7 sechs Befunde mit Zeilenbezug, dazu 64 nachgerechnete Gleichungen und 19 geprüfte Zitatstellen. Schwerste Korrektheitsbefunde: Vorzeichen des PI-Reglers, „bilinear, deshalb kein QP“ falsch begründet (die Spanne besteht aus Störgrößen, nicht aus dem Zustand), map-Form ist keine eigene Form, Sollwertlage und Taupunkt widersprüchlich. Größte Methodikhebel: Störgrößen und QP-Bedingungen im MPC ausschreiben, Beobachter mit Detektierbarkeit, Konfundierung weiter fassen als R² gegen die Last, Modellvalidierung als Grundlage einführen.
- **E1.4:** zehn Verteidigungsfragen (Henning: reduzierte Modelle, Beobachter, Störgrößenvorschau, bekannte Wahrheit, Robustheit; Merkel: NARMAX/FROLS, Einschritt- gegen Simulationsfehler, Residuentests, Konfundierung; beide: CL-Methode) mit Antwortskizze und Beleg.
- **E2:** fünf Beitragsformulierungen; tragfähig sind BT1 (QP-taugliche Modellform aus der Stufenbilanz), BT2 (welche Modelleigenschaft aus Regelkreisdaten rückgewinnbar ist, geprüft gegen Prüfstands-DoE) und BT3 (physikalisch motivierte \sindyc-Bibliothek am Großmotor). Nächste Verwandte in vier Gruppen; keine gefundene Arbeit vereint Ladelufttemperatur, sparse Regression, Regelkreisdaten und Prüfung der Stellwirkung.
- **E3 Top 5:** (1) Korrekturpaket ch2/ch3, (2) Konfundierungsdiagnose mit multiplem R², VIF und Belsley-Zerlegung plus Streubild Feld gegen DoE, (3) Residuentests je Modell, (4) QP-Brücke mit Prädiktor, Nebenbedingungen und Beobachter, (5) Beitragsliste. Zusammen rund 18–29 h, drei davon ohne Messdaten.
- **E4 Methanol (Zusatz):** Die Aussage ch2 Z. 958–961 („Brennstoffmodus wirkt nur über die Eingänge“) gilt nur, solange zwischen den Messstellen von \Tin und \Tout kein Stoff zugeführt wird; vier kleine Ideen für die Arbeit, Hinweise für die Firma getrennt.

## E1 Lektorat aus Gutachtersicht (ch2, ch3)

Zeilenangaben beziehen sich auf `kontext/ch2.tex` und `kontext/ch3.tex` (Kopie vom 25.09.2026). Je Kriterium die stärksten Befunde, sortiert nach Gewicht. „Eigene Algebra“ heißt: in dieser Sitzung nachgerechnet, keine Literaturaussage; Copilot prüft nach.

### E1.1 Befunde je Kriterium

#### K1 Erfüllung der Aufgabenstellung (Modell für einen linearen QP-MPC)

- **ch2 Z. 1061–1091, 1111–1113: Das MPC-Problem enthält die Störgrößen nicht.**
  - Gl. `eq.grundlagen.mpc` kennt nur `u`, `y`, `s`. Die Folge `d_k = (T_col,in, T_LTCW, T_HTCW, ṁ_rel)` über den Horizont fehlt, obwohl fast alle Bibliotheksterme Produkte mit Störgrößen sind (Z. 407–411, 921–925). Die eigene Notiz Z. 1111 („Störgrößenprädiktion … erwähnen“) bestätigt die Lücke.
  - Offen bleibt, wie aus \sindyc, \edmdc und ARX je ein Prädiktor wird (Diskretisierung, Liftung, Zustandsraumrealisierung).
  - Vorschlag: allgemeine Prädiktorform `x_{k+1} = A(d_k) x_k + B(d_k) u_k + E(d_k)` anschreiben; Annahme zur Fortschreibung der Störgrößen festlegen (eingefroren, Lastplan, gemessen); die Informationsannahme „aufgezeichnete Zukunft bei OL-Prognosen“ aus ch3 Z. 1202–1204 hierher holen.
- **ch2 Z. 1080–1082: „linear in der Stellgröße“ reicht für ein QP nicht.**
  - Die Vorhersage muss über den ganzen Horizont affin in `Δu_0 … Δu_{N_u−1}` sein. Gegenbeispiel (eigene Algebra): `x_{k+1} = f(x_k) + b u_k` mit nichtlinearem `f` liefert `x_2 = f(f(x_0)+b u_0) + b u_1`, nicht affin in `u_0`.
  - Bedingungen als Stichpunkte: (a) \Tout nur mit exogenen Faktoren multipliziert; (b) Rate unabhängig von \valveCA (Z. 437–438 mit `λ(\mrel, \valveCA)` verletzt das, Produkt \valveCA·\Tout); (c) `g(\valveCA)` linear oder als virtuelle Stellgröße `v = g(u)` mit monotoner Rücktransformation; (d) Störgrößen über den Horizont vorgegeben.
- **ch2 Z. 266–268 gegen Z. 1064–1074: Ratenbegrenzung fehlt im QP.**
  - Der Text nennt die endliche Stellgeschwindigkeit, die Nebenbedingung `|Δu_k| ≤ Δu_max` fehlt. Ebenso fehlt `Δu_k = 0` für `k ≥ N_u`.
  - Offen, welches Signal \valveCA ist: Reglerausgang vor der Linearisierungskurve, Positions-Sollwert oder Positionsrückmeldung (Z. 255, 277–281). Davon hängen Ventil-Gain und QP-Linearität ab.
  - „Totzeit nur beim Richtungswechsel“ (Z. 267–268) ist Umkehrspiel (Lose), keine Totzeit; im linearen QP nicht abbildbar, also Robustheitsfrage.
- **ch2 Z. 117–120, 1071–1072: Obergrenze fehlt als Beschränkung.**
  - Derating ab 55 °C (Z. 39–41) ist die folgenreichere Grenze; Gl. `eq.grundlagen.mpc` hat nur die weiche Untergrenze. „Enges Sollwertband“ ist nirgends definiert.
  - Vorschlag: `y_k ≤ y_max + s_k` als zweite weiche Beschränkung (bleibt QP) oder begründen, warum sie fehlt.
- **ch3 Z. 1122–1159: Die Einordnung nennt den Kern der Arbeit nicht.**
  - Weder Closed-Loop-Identifikation noch Ventil-Gain noch Prüfung gegen Prüfstands-DoE kommen vor, obwohl Z. 617–925 genau das zum Kernproblem machen.
  - Ungenutzte Anker aus dem eigenen Kapitel: Yahagi 2026 arbeitet mit Prüfstandsdaten unter Serien-PID (Z. 1106–1107); Rupprecht findet gute Temperaturwiedergabe, aber Abweichungen am Reglerausgang (Z. 1052–1053). Das motiviert die getrennte Gain-Prüfung.
- **ch3 Z. 1188 gegen ch2 Z. 211–212: „LT-Ventil“ in der Forschungsfrage ist mehrdeutig.**
  - ch2 beschreibt ein zweites Ventil, das den LT-Vorlauf regelt (also `T_LTCW`, eine Störgröße). Stellgröße ist das HP-Ladeluftkühler-Ventil \valveCA. Gerade in der Forschungsfrage ist die Verwechslung kritisch.

#### K2 Umfang der Ergebnisse (was für Kap. 5–7 gebraucht wird, aber fehlt)

- **ch2 Z. 1082–1088: Beobachter nur als Halbsatz.**
  - Es fehlen Störmodelltyp (Eingangs- oder Ausgangsstörung), erweitertes System `[x; d]`, Detektierbarkeitsbedingung (Kern von \cite{pannocchiaDisturbanceModelsOffsetfree2003}, \cite{maederLinearOffsetfreeModel2009}), Beobachtertyp (Kalman-Filter, `Q`, `R`), ungemessene Zustände (`T_zw`, Wand, Wasser).
  - Bei einer Messgröße \Tout höchstens ein integrierender Störzustand (Rangbedingung). Henning fragt hier mit Sicherheit nach.
- **ch3 Z. 1024–1026 gegen Z. 1–616: Validierung wird als Literaturlücke reklamiert, aber nicht eingeführt.**
  - Residuentests (Autokorrelation, Kreuzkorrelation mit dem Eingang, Kohärenz) und die Unterscheidung Einschritt-, k-Schritt- und Simulationsfehler fehlen in beiden Kapiteln. ch2 spricht von „Transientenfehler“ (Z. 491) und „Nutzen im Freilauf“ (Z. 999) ohne Definition.
  - Vorschlag: kurzer Grundlagenblock „Modellvalidierung“; Beleg \cite{ljungSystemIdentificationTheory1999} (Kapitel am Original prüfen); nichtlineare Korrelationstests nach Billings (siehe Quellenliste).
- **ch3 Z. 197–205: NARX/NARMAX ohne Primärquelle, FROLS fehlt.**
  - Die sparse Termauswahl der NARMAX-Schule (Orthogonal Least Squares mit Fehlerreduktionsverhältnis) ist der direkte Vorläufer der SINDy-Termauswahl. Ohne sie bleibt offen, was \sindyc gegenüber Polynom-NARX mit Termauswahl neu leistet (Merkel).
  - Z. 204–205 („ändert nichts an den Limitierungen der linearen Modellklasse“) ist unklar; gemeint ist wohl „linear in den Parametern, gleiche LS-Grenzen“.
- **ch2 Z. 1093–1094, ch3 Z. 600–610: SINDy-MPC-Kernreferenz fehlt an der richtigen Stelle.**
  - ch2 kündigt an, ch3 ordne MPC an Verbrennungsmotoren ein; der Abschnitt existiert nicht mehr (Kommentar ch3 Z. 1008–1009).
  - \cite{kaiserSparseIdentificationNonlinear2018} ist nach Key die SINDy-MPC-Arbeit (Kaiser, Kutz, Brunton, Proc. R. Soc. A 2018, siehe Quellenliste), wird aber nur für „Bibliothekswahl offen“ zitiert. „Für SINDy-MPC ist die Theorie weniger ausgereift“ (Z. 608–610) steht ohne Beleg.
- **ch3 Z. 52–122: Kovarianz der LS-Schätzung fehlt.**
  - `cov(ξ̂) = σ²(ΘᵀΘ)⁻¹` bei weißem Residuum ist das Werkzeug für ein Unsicherheitsband des Ventil-Gains (eine der vier Bewertungsgrößen). VIF ist genau der Faktor, um den diese Varianz durch Kollinearität steigt. Bei autokorrelierten Residuen unterschätzt die Formel die Varianz.
- **ch3 Z. 241–262, 303–307: DMD ohne SVD-/POD-Trunkierung, Galerkin-Brücke fehlt.**
  - Für Henning (POD-Galerkin) wäre ein Satz einschlägig: EDMD ist Galerkin-Projektion des Koopman-Operators, POD-Galerkin Projektion der Bewegungsgleichung auf POD-Moden. In dieser Arbeit ist der Zustand niedrigdimensional, die Liftung vergrößert statt zu reduzieren.

#### K3 Korrektheit

- **ch2 Z. 112–114 gegen Z. 237–239: Sollwertlage widerspricht sich.**
  - Z. 114: Sollwert „im oberen Teil des Bandes“. Bei 50–60 °C liegt 52 °C im unteren Fünftel. Derating beginnt nach Z. 39–41 schon bei 55 °C.
  - Vorschlag: Lage und Herkunft von 52 °C klarstellen (Werksvorgabe oder eigene Festlegung, dann Entwurfsentscheidung in Kap. 4). Bezugsgröße des Deratings (Ladeluft, Ansaugluft?) in PG S. 58 prüfen.
- **ch2 Z. 89–95, 112–114: Taupunkt-Argument hängt am Ladedruck.**
  - 51,5 °C bei 35 °C, 80 % r. F. und 3 bar ist mit der Magnus-Näherung reproduzierbar, aber nur bei 3 bar absolut. Eigene Rechnung (Illustration, kein Motorwert): 4 bar absolut ergibt rund 57 °C, also über dem Sollwert. Den Ladedruck am HP-Kühler des 49/60DF nennt der Text nicht.
  - Folge: Die Kette „Taupunkt über 50 °C, darum Sollwert oben“ trägt so nicht. Taupunkt mit PG-Ladedruck nachrechnen oder PG-Angabe zitieren; „3 bar“ als absolut/relativ kennzeichnen.
- **ch3 Z. 360–366 gegen ch2 Z. 929–934: bilinear und „Verlust des QP“ ist falsch begründet.**
  - ch3 folgert aus „Ventilwirkung skaliert mit der Temperaturspanne“ die zustandsbilineare Form `(N z_k) u_k` und den Verlust des konvexen QP. Die Spanne `T_col,in − T_LTCW` besteht aus gemessenen Störgrößen, nicht aus dem Zustand; ch2 Z. 929–934 sagt genau das.
  - Eigene Algebra: `T_{k+1} = a(d_k) T_k + c(d_k) + b(d_k) u_k` ist über den Horizont affin in der Stellfolge, sofern `d` bekannt oder eingefroren ist. Nicht konvex wird es erst bei Stellgröße × Zustand.
  - Vorschlag: zwei Fälle trennen (zustandsbilinear, SQP nach \cite{kelmanBilinearModelPredictive2011}; störgrößenbilinear, LTV-QP). Folge für \edmdc: Störgrößen als exogene Eingänge, nicht im gelifteten Zustand führen.
- **ch2 Z. 1048–1056 und ch3 Z. 786–787: Vorzeichen des Reglers.**
  - Die Strecke hat negative Verstärkung (Ventil auf = mehr Kühlung, Z. 289–290). Mit `e = r − y` und `K_c > 0` schließt das Ventil bei zu hoher Temperatur: Mitkopplung. `K_c < 0` angeben oder `e = y − r` definieren; gleiches gilt für `C(q)`.
  - Folge für ch3 Z. 666–671: Der Grenzwert `−K⁻¹` ist dann positiv, die wahre Ventilverstärkung negativ. Ein aus Felddaten geschätzter Gain mit falschem Vorzeichen ist ein erwartbares Zeichen dominierender Rückführung (eigene Algebra).
- **ch3 Z. 529–548: Die „diskrete map-Form“ ist keine eigene Form.**
  - `x_{k+1} = x_k + Δt Θ(x_k) Ξ` ist im LS-Sinn identisch mit der kontinuierlichen Form mit Vorwärtsdifferenz (eigene Algebra: gleiche Zielfunktion bis auf den Faktor `Δt²`). „Vorteil: keine Ableitung nötig“ stimmt nicht.
  - Echte diskrete Form: `x_{k+1} = Θ(x_k, u_k, d_k) Ξ`. Relevanter Vorteil für die Arbeit: direkt Einschrittprädiktor im MPC-Takt.
- **ch3 Z. 143–147: „die numerische Ableitung geht gegen null“ ist falsch.**
  - Gegen null gehen die Inkremente `x_{k+1} − x_k`; der Rauschanteil der Ableitungsschätzung wächst mit `1/Δt`. Zeitdiskret wandern die Eigenwerte gegen 1 (schlechte Kondition).
- Ergänzende Kurzbefunde zu K3 (nicht mitgezählt):
  - ch2 Z. 742 und 279–281 (Ventilkennlinie je Pfad nahezu linear) gegen Z. 1037–1038 („Totzone und Sättigung in der Ventilkennlinie“): „Streckenverstärkung über dem Ventilhub“ schreiben.
  - ch3 Z. 1149–1152 („keine behandelt die Ladelufttemperatur“) gegen Z. 1069–1081 (Vagapov 2024, prädiktive Stufe für die Lufttemperatur nach dem Kühler): auf Großmotor und datengetriebenes Modell einschränken.
  - ch3 Z. 1141–1142 („Messdaten fast immer aus Simulationen“) gegen eigene Sichtung (Rupprecht, Vagapov 2022, Sui mit Prüfstandsdaten): auf SINDy-/Koopman-Arbeiten am Motor einschränken.
  - ch3 Z. 819–823: Kreuzterm im geschlossenen Kreis nicht allgemein ungleich null. Bei weißem `v` und mindestens einem Takt Verzug im Kreis verschwindet er (Konsistenzbedingung der direkten Methode, Z. 827–832). Richtig: ungleich null bei farbigem `v` oder ohne Verzug im Modelltakt.
  - ch3 Z. 838–840: Sättigung beseitigt nur die Rückführungskorrelation im `u`-Teil des Regressors, nicht den Kreuzterm über verzögerte Ausgänge bei farbigem `v`.
  - ch3 Z. 323–325: Korda/Mezić überzeichnet (siehe E1.3).
  - ch2 Z. 796–802: Gain-Gleichung nutzt die einstufige Ersatzform. Zweistufig fehlt der `T_HTCW`-Term, das Gewicht von `T_col,in` ist `(1−ε_HT)(1−ε_LT)` statt `1−ε` (eigene Algebra, E1.2).

#### K4 Methodik (Entwurfsentscheidungen hinterfragt, Ergebnisse systematisch geprüft)

- **ch3 Z. 27–41 gegen Z. 1155–1159 und ch2 Z. 420–422: Grey-Box-Einordnung widerspricht der eigenen Linie.**
  - Z. 36–38 macht \sindy/\edmd mit physikalischer Bibliothek zu „vollwertigen Grey-Box-Modellen“, Z. 41 verortet die Arbeit im „Black-Box- und Grey-Box-Bereich“. Z. 453–457 definiert Grey-Box als physikalischen Prior plus gelerntes Residuum, also ein anderes Konzept. Z. 1155–1159 und ch2 Z. 420–422 sagen richtig: Physik liefert nur Termformen.
  - Vorschlag: Z. 1155–1159 als Referenzformulierung nach vorn ziehen; Grey-Box eng definieren und abgrenzen. Einordnungsbegriff „semi-physikalische Modellierung“ (Ljung) als Kandidat prüfen.
- **ch3 Z. 654–721: Aufzählung ohne Entscheidung.**
  - Direkte, indirekte Methode, Joint-IO/dual-Youla, PBSID, IV, Zwei-Stufen, Bias-Korrektur, BELS werden genannt; welche die Arbeit nutzt und warum die anderen ausscheiden, steht nirgends.
  - Aus dem eigenen Text folgt: indirekt braucht linearen, exakt bekannten Regler (Z. 681–682), die ChATCo ist adaptiv, nichtlinear, mit Anti-Windup (ch2 Z. 270–277). IV/Zwei-Stufen brauchen bewegten Sollwert (Z. 697–700), gefahren wird fest 52 °C. Die Prüfstands-DoE ist ein Experiment mit gesetzten Ventilsprüngen.
  - Vorschlag: Stichpunkttabelle „Verfahren · Voraussetzung · im Feld erfüllt? · am Prüfstand erfüllt?“ und ausdrückliche Festlegung.
  - Dazu ch3 Z. 674–676, Zielkonflikt HO-ARX gegen Informativität: Eigene Algebra (Copilot prüft): Unter reinem PI bei festem Sollwert ist ARX mit `n_a ≥ 2`, `n_b ≥ 2`, `n_k = 1` nicht identifizierbar (Gram-Matrix in einer Simulation singulär), ARX(1,1,1) schon. HO-ARX hilft gegen den Rauschmodellfehler, verschärft aber den Rangverlust. Informativität kommt dann nur aus nichtlinearer, adaptiver Vorsteuerung, Sättigung und Moduswechsel.
- **ch3 Z. 877–889 gegen ch2 Z. 271–274: Konfundierung zu eng gefasst.**
  - Das Kennfeld hat zwei Eingänge (relative Leistung und Sollwert − `T_LTCW`) und wird adaptiv nachgeführt. `T_LTCW` steht selbst in der Bibliothek; ein Bestimmtheitsmaß nur gegen die Last unterschätzt die Konfundierung.
  - Vorschlag: multiples `R²` von \valveCA gegen alle Bibliotheksspalten (= `1 − 1/VIF` der Ventilspalte); Adaption als langsamen Rückführpfad benennen. Drei Fälle trennen: exakter Rangverlust, Beinahe-Kollinearität (Varianz, mehr Daten helfen), Fehlspezifikation des Störpfads (Bias, mehr Daten helfen nicht).
- **ch2 Z. 217–219, 517–519, 799–801: `T_LTCW` ist nicht rein exogen.**
  - Der Text sagt selbst, dass der Ventilhub `T_LTCW` verschiebt; Gl. `eq.grundlagen.gain.epsntu` enthält `dT_LT/d\valveCA`. Rückwirkungspfad: \valveCA → Wärmeeintrag in den LT-Kreis → LT-Regler → `T_LTCW`. Analog formt der LP-Kühlerregler `T_col,in` mit (Z. 157–160, 253–261).
  - Vorschlag: „Ventil-Gain“ ausdrücklich als partielle Größe bei festgehaltenen gemessenen Störgrößen definieren und in Kap. 5/6 identisch verwenden; `T_LTCW` und `T_col,in` als Regressoren mitführen; Rückwirkung als Modellfehler benennen, den der Beobachter trägt. Leitplanke (Kühlwasser ist Störgröße) bleibt gewahrt.
- **ch2 Z. 604–619, 848–857 gegen ch3 Z. 573–575: nichtlineare Parameter.**
  - Ein angepasster Exponent `p` in `ṁ^p` oder ein Zielwert `1 − exp(−NTU(ṁ, u))` mit geschätzter NTU ist nichtlinear in den Parametern und mit STLSQ auf fester Bibliothek nicht schätzbar. ch3 sagt, alle Verfahren seien linear in den Parametern. Ohne Klarstellung wird der Zielwert eine physikalisch parametrierte Statik (Grey-Box) und nichtlinear in \valveCA.
  - Vorschlag: Exponent über ein festes Raster als Bibliotheksspalten (`\mrel^p` für wenige `p`) oder äußere 1-D-Suche mit Auswahl auf Validierungsdaten; ε-NTU nur zur Motivation der Termform.
- **ch3 Z. 869–873: Modussprung als „natürliches Instrument“ ist nicht abgesichert.**
  - Beim Wechsel Gas/Diesel ändern sich zugleich Brennverfahren, `T_col,in`, `ṁ_rel` und das Niveau (ch2 Z. 958–961); danach steht das Ventil in Sättigung (Z. 891–897). Als Instrument im IV-Sinn wirkt der Modus direkt auf die Strecke. Ljung Abschn. 13.4 stützt die Informativität, nicht die Trennung vom Modusversatz. Der Kommentar Z. 647–649 („SdT trägt nur das Allgemeine“) wird verletzt.
  - Vorschlag: nach Kap. 5 verschieben, Bedingung nennen (gleichzeitige Störgrößenänderungen gemessen in der Bibliothek, Modus-Offsetterm), „Instrument“ durch „informativer Abschnitt“ ersetzen.

#### K5 Durchdringung

- **ch2 Z. 848–857: Die „Konsistenzgrenze“ ist eine Modellreduktion.**
  - Eigene Algebra: `n` gleiche Rührkesselzellen gegen `T_LTCW` ergeben `ε_n = 1 − (1 + N/n)^{−n}`; `n = 1` liefert `N/(1+N)`, `n → ∞` liefert `1 − e^{−N}`. Die Lücke zwischen Bilanzstatik und ε-NTU-Statik ist damit der Diskretisierungsfehler der Ortsreduktion.
  - Anschluss an Henning (reduzierte Modelle): Einzustandsmodell als Ein-Zellen-Näherung bzw. Projektion der ortsabhängigen Bilanz auf eine konstante Ansatzfunktion; Prüfung der Modellordnung (Z. 860–865) mit der Zellzahl verknüpfen.
- **ch2 Z. 543–546, 733–741: zwei Wirkwege des Ventils.**
  - Das Ventil senkt `ṁ_W` und damit `C_W`. Die Annahme `C_W ≫ C_L` versagt zuerst im Flankenbereich, in dem die Ventilautorität messbar ist (Z. 785–786). Bei kleinen Hüben gilt luftseitig `ε ≈ C_W/C_L`, also etwa proportional zu `ṁ_W(\valveCA)`; bei großen Hüben wirkt das Ventil über `α_W` und `kA` und sättigt.
  - Vorschlag: beide Wege nebeneinanderstellen (eigene Algebra); qualitative Erklärung der S-förmigen Streckenverstärkung ohne Messzahl.
- **ch2 Z. 434–448, 929–934: „die Rate trägt nur den schwachen Rest“ ist nicht belegt.**
  - Eigene Algebra aus Gl. `eq.energiebilanz.dyn`: Elastizitäten gegenüber `U_eff A` sind `d ln ε / d ln N = 1 − ε` und `d ln λ / d ln N = ε`. Für `ε > 0,5` reagiert die Rate relativ stärker auf den Wasserdurchsatz als der Temperaturänderungsgrad.
  - Folge: „Ventil nur im Zielwert“ ist eine Modellentscheidung wegen des QP (sonst Produkt \valveCA·\Tout), keine Folge der Physik. So benennen und in Kap. 5/6 prüfen, ob die identifizierte Zeitkonstante bei DoE-Sprüngen von der Ventilstellung abhängt.
- **ch2 Z. 1082–1088 mit ch3 Z. 909–921: offsetfrei korrigiert das Niveau, nicht den Gain.**
  - Der Störgrößenbeobachter gleicht Niveaufehler stationär aus, Fehler der Stellverstärkung nicht. Deshalb ist der Ventil-Gain die kritische Modelleigenschaft für den Regler. Verschmutzung (ch2 Z. 722) ändert `kA` und damit den Gain, nicht nur das Niveau.
- **ch3 Z. 275–281, 314–341: Ventil-Gain je Modellklasse.**
  - Eigene Algebra: Bei ARX, DMDc und eDMDc mit linearem, nicht geliftetem `u` ist die Stellwirkung `C A^j B` bzw. stationär `B(1)/A(1)`, unabhängig vom Arbeitspunkt. Die physikalische Stellwirkung skaliert dagegen mit der Kühlerspanne (ch2 Z. 781–786).
  - Vorschlag: kleine Übersicht „Modellklasse · Form des Ventil-Gains (konstant / ∝ Spanne / zustandsabhängig) · QP-Tauglichkeit · Identifizierbarkeit aus CL-Daten“.
- **ch2 Z. 437–438, 854–871: gleiche Dynamik für alle Kanäle.**
  - Die Relaxationsform erzwingt für Ventil- und Störkanal dieselbe Zeitkonstante. Physikalisch läuft der Ventilpfad über Wassertransport; die wasserseitige Totzeit ist etwa `V_Rohr/V̇_W(\valveCA)`, also bei kleinem Hub am größten (eigene Überlegung). Als Vereinfachung benennen; kanalspezifische Filterzustände als Bibliotheksspalten bleiben linear im Parameter.

#### K6 Selbstständigkeit und Kreativität

- **ch3 Z. 877–925: Eigenleistung steht unmarkiert im Stand der Technik.**
  - Vorsteuerung als Rangproblem, Sättigung mit Absolutglied, Reglertakt gegen Modelltakt, Dreiteilung Niveau/Dynamik/Stellwirkung sind eigene Übertragungen, teils ohne Beleg (Z. 899–905, 909–918). Sie lesen sich wie Literatur oder wie unbelegte Behauptung.
  - Vorschlag: nach Kap. 5 verschieben oder mit „Eigene Einordnung:“ einleiten; die Dreiteilung als eigenen Analyserahmen in die Beitragsliste.
- **ch3 Z. 434–450 gegen ch2 Z. 398–425: eigene Bibliotheksherleitung erscheint als Übernahme.**
  - Die physikalisch motivierte Bibliothek wird auf \cite{loiseauConstrainedSparseGalerkin2018} zurückgeführt; ein Verweis auf die eigene Reduktion der Kühlerbilanz (Gl. `eq.grundlagen.basic.produkte`, `…ltspanne`) fehlt. Harte Nebenbedingungen wie bei Loiseau nutzt die Arbeit nicht erkennbar.
  - Vorschlag: „Die Termfamilien folgen aus der eigenen Reduktion der Kühlerbilanz (Gl. …); Loiseau/Brunton ist Vorbild für das Prinzip.“
- **ch3 Z. 1122–1174, 1196–1197: keine Beitragsliste.**
  - Der einzige Satz zum Beitrag spielt ihn auf „Umsetzung und Prüfung“ herunter. Verstreute Eigenleistungen bleiben unverbunden (Bibliothek aus der Bilanz, Proxy aus `Δp_HP`, CL-Analyse gegen Prüfstands-Wahrheit, Konfundierungsmaß, Dreiteilung, Gain-Konvention ch2 Z. 790–793). Vorschlag siehe E2.1.
- **ch2 Z. 322, 469, 497, 581, 633, 761, 806, 888, 985; ch3 Z. 1041, 1178: „Copilot:“-Überschriften im gesetzten Text.**
  - Sie erscheinen als `\textbf` im PDF, ausgerechnet an den Kernstücken (Grundherleitung, Proxy, Festhaltebedingung). So wird die Eigenleistung sichtbar einem Werkzeug zugeschrieben. Vor jeder PDF-Weitergabe ausformulieren oder auskommentieren; Werkzeugnutzung einmal in der Hilfsmittelerklärung offenlegen.
- **ch2 Z. 271–274: ungenutztes Vorwissen im Serienkennfeld.**
  - Eigene Algebra (Voraussetzungen: Kennfeld auslesbar und konvergiert, Linearisierungskurve berücksichtigt, `T_LTCW` exogen): Stationär gilt `r = T_stat(u, T_LTCW, …)` und `u = K(Last, r − T_LTCW)`. Mit `x = r − T_LTCW` und `∂T_stat/∂T_LTCW = ε_LT` folgt `|∂T_stat/∂u| = ε_LT/|∂K/∂x| < 1/|∂K/∂x|`. Ein konvergiertes Kennfeld liefert eine Obergrenze des stationären Ventil-Gains aus Felddaten, ohne neue Versuche. Siehe Idee A6 in E3.
- **ch2 Z. 407–425, 611–613, 781–782: erwartete Vorzeichen ungenutzt.**
  - Die Herleitung liefert Vorzeichen (Ventilterm senkt \Tout beim Öffnen; `λ > 0` und mit \mrel wachsend; Massenstromterm abhängig von `p < 1`). Als Prüfkriterium oder als Nebenbedingung der Regression (constrained SINDy) nicht genutzt.

#### K7 Qualität der Ausarbeitung

- **ch3 Z. 757–775, 625, 218, 506: sichtbare Entwurfsreste.**
  - Z. 764–775 Rohtext mit Tippfehlern („Motehode“, „Indirkete Methdoe;“), Z. 775 beginnt mit „Messdaten.“; Z. 625 fehlt der Backslash vor `textbf`; Z. 218 Satzfragment „unendlichdimsensionalen“; Z. 506 Überschrift „Esemble“ im Inhaltsverzeichnis.
- **ch2 Z. 184–185: Konvention Stufe/Bündel widerspricht der Vorgabe und dem eigenen Text.**
  - Z. 184–185: Stufe = LP/HP, Bündel = HT/LT. Z. 362–365, 392, 498, 892 sprechen von HT-/LT-Stufe, Z. 253–254 nennt LP/HP „Kühlstufe“. Drei Lesarten eines Wortes, das die Systemgrenze trägt. Vorschlag: HT/LT = Stufe des HP-Kühlers; LP/HP = Aufladestufe bzw. LP-/HP-Kühler; alle „Bündel“ ersetzen, Kommentar Z. 186–187 löschen.
- **Symbole mehrfach belegt (beide Kapitel).**
  - `λ`: Rate (ch2 438, 855), MPC-Gewicht (ch2 1068), STLSQ-Schwelle (ch3 423), LASSO-Gewicht (ch3 428, 498). `N`: `U_eff A/(ṁ c_p)` (ch2 849), Horizont (ch2 1062), Zustandsdimension (ch3 243), Snapshot-Zahl (ch3 247), bilineare Matrix (ch3 346). `K`: Koopman-Matrix, Rückführung, `K_c`. `e`: Regelabweichung, Gleichungsfehler, Rauschen. `μ`, `p`, `a/b`, `C`, `q` ebenfalls.
  - Vorschlag: Symbolverzeichnis; z. B. Horizont `N_p`, Snapshot-Zahl `m`, Schwelle `η`, MPC-Gewicht `ρ`, Rückführung `F`.
- **Tote Labels und Arbeitsnotizen im Satz.**
  - Labels: ch3 Z. 393–394, 433–434 (auskommentierte `\subsection` mit aktiven Labels), Z. 529 und 590 (Label ohne Überschrift; Z. 588 verweist auf den eigenen Abschnitt), Z. 761–762 und ch2 Z. 549–550 (totes `ssec.grundlagen.clid`), ch2 Z. 305–307 (drei Labels auf einer Section, eines zur gestrichenen Tabelle). Die CL-Gleichungen tragen `eq.grundlagen.cl.*`, stehen aber in ch3.
  - Arbeitsnotizen: „(Key fehlt)“, „Key prüfen“, „Beleg nachschlagen“, „Ein Satz mit \verb|\ref|, kein Absatz.“ (ch2 Z. 1001), `\anno` (ch3 Z. 688, 692, 702). Endcheck per Suche nach „Key“, „nachschlagen“, „nachtragen“, „\verb“, „Copilot“.
- **ch2 Z. 309–465 gegen 467–1003: zwei parallele Herleitungsketten.**
  - Derselbe Stoff mit anderer Notation: `\Tstat` zweistufig (Z. 376) gegen `T_stat` einstufig (Z. 855); `y` gegen \Tout; `kA` gegen `U_eff A`. Die zentrale Zweistufen-Exponentialform (Z. 574–577) ist unnummeriert, obwohl Z. 994–995 sie als Modellgrundlage nennt. Vorschlag: eine Kette Bilanz → ε-NTU je Stufe → Reihenschaltung (nummeriert) → Stellverstärkung → Dynamik → Termfamilien.
- **ch3 Z. 948, 964, 989, 995: Sprache.**
  - „Intern … LT Cooling Water Temperatur“, „schwergängigen Diesel-Antriebs“ (heavy-duty), „regelbasiert einsetzbar“ (gemeint: regelungstechnisch), „EMEC-nahe Ansätze“ (nicht eingeführt); Makros `\sindyc`/`\edmdc` ohne `{}` verschlucken Leerzeichen (ch2 Z. 458, ch3 Z. 841).

### E1.2 Rechenprüfung der Gleichungen (Kurzfassung)

64 Gleichungen und Umformungen nachgerechnet (von Hand und mit kurzen Zahlentests in reinem Python; sympy war nicht installiert).

| Stelle | Ergebnis | Kern des Befunds |
|---|---|---|
| ch2 330–396 (Luftleistung, kA, Stufen, LT-Spanne) | korrekt | Geschlossene Gesamtform ergänzen: `\Tstat = \Tin − [ε_HT + ε_LT(1−ε_HT)](\Tin − \THT) − ε_LT(\THT − \TLT)` |
| ch2 398–425 (Produktterme) | Annahme fehlt | Ventilterm gehört nur zur LT-Stufe (`a_2 = 0` für HT); affines ε kann [0,1] verlassen, Schranke `ε_L ≤ ε_Q ≤ 1` als Plausibilitätsprüfung |
| ch2 427–448 (Relaxation) | Annahme fehlt | `λ = c_λ \mrel` widerspricht der τ-Formel Z. 835; konsistent `λ = λ_0 + c_λ \mrel`. Euler stabil nur für `0 < Δt·λ < 2` |
| ch2 539–546 (ε-NTU, `C_r → 0`) | korrekt | `C_r → 1` ergibt `N/(1+N)`: die Einzustandsstatik verhält sich wie ein Gegenstromer mit `C_r = 1`, nicht wie `C_r → 0` |
| ch2 568–577 (Zweistufen-Exponentialform) | korrekt | Konvexe Kombination `\Tout = w_1 \TLT + w_2 \THT + w_3 \Tin`, `w_1 = 1−e^{−N_LT}`, `w_2 = e^{−N_LT}(1−e^{−N_HT})`, `w_3 = e^{−(N_HT+N_LT)}`; nummerieren |
| ch2 643–716 (Druckverlust-Proxy, \mrel, `q_rel`) | korrekt, eine Annahme fehlt | Proxy mit Eintrittsdichte ist schwach endogen: `ṁ_proxy = ṁ·√(T_m/T_col,in)`, `T_m` hängt über \Tout von \valveCA ab. Klein, kann aber Ventilwirkung in `\mrel·ΔT`-Terme verschieben; in DoE-Sprüngen bei konstanter Last prüfen |
| ch2 775–802 (Gain-Kettenregel) | Annahme fehlt | Nur einstufig exakt; zweistufig `d\Tout/d\valveCA = −(T_zw − \TLT) e^{−N_LT} dN_LT/d\valveCA + w_1 d\TLT/d\valveCA + w_2 d\THT/d\valveCA + w_3 d\Tin/d\valveCA` |
| ch2 834–840 (τ, Mitteltemperatur-Variante) | Annahme fehlt | Mitteltemperatur-Ansatz gibt stationär `ε = 2N/(2+N)`, für `N > 2` größer 1, also nur zur Zeitkonstanten-Abschätzung |
| ch2 910–920 (a/b-Umformung) | korrekt | Plausibilitätsprüfung für Fits: `a = 1/τ`, `0 < b < a`, `b/a = ε_stat` |
| ch2 1036–1038 (Ventilkennlinie) | fehlerhaft | Widerspruch zu Z. 279–281, 742 |
| ch2 1046–1059 (PI) | Vorzeichenfalle | `K_c < 0` oder `e = y − r`; Z. 1056–1057 („Integralanteil trägt das Niveau“) gegen Z. 273–274 (Kennfeld wird nachgeführt, bis PI → 0) |
| ch2 1061–1082 (MPC, QP-Aussage) | fehlerhaft / unvollständig | QP-Bedingung siehe K1; `s_k` als Entscheidungsvariable, `Δu_k = 0` für `k ≥ N_u`, Ratengrenze, keine Endkosten |
| ch2 89–95 (Taupunkt) | Annahme fehlt | Magnus: 3 bar abs → 51,5 °C; 4 bar abs → rund 57 °C (Illustration) |
| ch3 63–98 (LSQ) | korrekt | Für Matrizen Frobenius-Norm `‖·‖_F²` schreiben; numerisch QR/SVD statt Normalgleichungen |
| ch3 126–141 (Normierung) | Begründungsfehler | `σ_j = 0` betrifft die Skalierung, nicht die Zentrierung; Skalierung ohne Zentrierung mit Spaltennorm bzw. RMS |
| ch3 143–147 (Abtasttakt) | fehlerhaft | siehe K3 |
| ch3 241–262, 265, 293 (DMD, DMDc, eDMD) | fehlerhaft (Notation) | Zeilenkonvention: `Θ = X_0ᵀ`, `Y = X_1ᵀ`, `Ξ = Aᵀ` |
| ch3 339–366 (bilinear) | Annahme fehlt | Ohne konstante Observable fehlt reiner Eingangsterm; Begründung siehe K3 |
| ch3 369–383 (Delays, Takens) | Annahme fehlt | Takens gilt für autonome Systeme; mit Eingang hängt `x_{k−i}` von der Eingangsgeschichte ab |
| ch3 421–430, 495–500 (STLSQ, LASSO, Bildunterschrift) | fehlerhaft | Matrix minus Vektor; `Θᵀξ_k` dimensionsfalsch; Norm ungequadratet |
| ch3 529–548 (map-Form) | fehlerhaft | siehe K3 |
| ch3 633–646 (DMDc unter Rückführung) | Annahme fehlt | „mittelwertfrei genügt“ ist nicht das Kriterium: `δ` unabhängig vom Rauschen und persistent anregend |
| ch3 657–671 (Bias direkte Methode, `−K⁻¹`) | Annahme fehlt | Bias ∝ `|H_0 − Ĥ|` und Rauschanteil an der Eingangsleistung, nicht allgemein ∝ Rauschvarianz; „davon unabhängig“ → „als Grenzfall“ |
| ch3 674–676 (HO-ARX) | Zielkonflikt | siehe K4 |
| ch3 789–804, 825–832 (`u = SCr − SCHe`, `Φ_ue`) | korrekt | Mit Vorsteuerung und Störgrößen: `u = S(Cr + u_ff) − SC(G_d d + He)` |
| ch3 806–823 (LS-Bias) | Annahme fehlt | siehe K3; „Ē{φφᵀ} invertierbar“ an die Gleichung schreiben |
| ch3 845–859, 893–897 (PE, Sättigung) | korrekt mit Grenzen | Ventil bei 0 % (Preheating) ist nicht PE der Ordnung 1; in der physikalischen Bibliothek wird `g(u_sat)·ΔT` kollinear mit `ΔT` selbst |

### E1.3 Zitatprüfung ausgewählter Stellen (Abstract-Ebene)

Geprüft per Websuche gegen Abstract-Auszüge; kein Volltext. „Gestützt“ heißt: der Abstract trägt die Aussage. Metadaten der genannten Quellen in der Quellenliste.

| Stelle | Key | Ergebnis | Befund und Vorschlag |
|---|---|---|---|
| ch3 Z. 323–325 | `kordaLinearPredictorsNonlinear2018` | nicht gestützt | Abstract (Automatica 93, 149–160): gelifteter, näherungsweise linearer Prädiktor; MPC darauf mit Aufwand einer linearen MPC; keine Konvergenzaussage. Die Konvergenz stammt aus Korda & Mezić 2018, *J. Nonlinear Sci.* 28, 687–710: für Stichprobenzahl → ∞ gegen die L²(μ)-Projektion auf den Observablen-Unterraum, für autonome Systeme. „Für nichtlineare MPC“ → „für lineare MPC nichtlinearer Systeme“; Satz teilen, keine Konvergenzgarantie für eDMDc mit Eingang behaupten |
| ch3 Z. 303–307 | `williamsDataDrivenApproximation2015` | gestützt (durch den Abstract von Korda & Mezić 2018, *J. Nonlinear Sci.*) | Korda & Mezić 2018 als Primärbeleg ergänzen; „Datenlimit“ = Stichprobenzahl → ∞, Projektion bezüglich der Datenverteilung (Betriebsbereich) |
| ch3 Z. 600–603 | `kaiserSparseIdentificationNonlinear2018` | nicht gestützt | Key ist SINDy-MPC im Low-Data-Limit (Proc. R. Soc. A 474, 20180335); keine Aussage zur Bibliothekswahl. In den \sindyc-Abschnitt verschieben (SINDYc/DMDc/NN in MPC entspricht dem Aufbau der Arbeit). Für „Bibliothekswahl offen“: Yonezawa u. a. 2026 oder Champion u. a. 2019 |
| ch3 Z. 608–610 | ohne Beleg; `boldDataDrivenMPCStability2025` | teilweise | „SINDy-MPC-Theorie weniger ausgereift“ präzisieren: Stabilität für SINDy-MPC nur für spezielle Strukturen (Lyapunov-MPC bei Abdullah, Wu, Christofides 2021), datenbasierte proportionale Fehlerschranken liegen für kEDMD vor (Nüske u. a. 2023; Bold u. a. 2025), für SINDy in der Sichtung nicht. Bold u. a.: „praktische asymptotische Stabilität“, nicht allgemein „Stabilitätsgarantien“; Nachfolger Schimperna u. a. 2026 |
| ch3 Z. 353–356 | `bruderAdvantagesBilinearKoopman2021` | teilweise | Abstract: jedes eingangsaffine System hat eine unendlichdimensionale bilineare, nicht notwendig lineare Realisierung; Demonstration an einem **simulierten** Roboterarm. „Experimentell“ und „bei gleichem Datenbudget“ nicht gedeckt |
| ch3 Z. 357–359, 1103–1111 | `yahagiGeneralizedBilinearKoopman2026` | gestützt / Details nicht prüfbar | arXiv 2602.15422 (Preprint, so kennzeichnen); Dieselmotor-Luftpfad, Training mit transienten Daten aus Closed-Loop-Versuchen (laut Auszug). Serien-PID, Ausgänge, Ausblick nur im Volltext prüfbar |
| ch3 Z. 381–383 | `bruntonModernKoopmanTheory2022` | nicht prüfbar | Metadaten bestätigt (SIAM Review 64(2), 229–340, DOI 10.1137/21M1401243); Vergleich Delay gegen Monome nicht im Abstract. Seite suchen oder abschwächen; stützend Kamb u. a. 2020 |
| ch3 Z. 378–380 | ohne Beleg | nicht prüfbar | Takens 1981, LNM 898, S. 366–381, DOI 10.1007/BFb0091924 (nur bibliografisch); für angeregte Systeme Stark 1999. „unter milden Bedingungen“ → „generisch, mindestens 2d+1 Verzögerungen, autonomes System“ |
| ch3 Z. 444–447 | `loiseauConstrainedSparseGalerkin2018` | teilweise | Abstract: POD plus SINDy mit energieerhaltenden Nebenbedingungen, Strömungs-ROM. „Empfehlen … Bibliothek aus Erhaltungsgleichungen“ ist nur sinngemäß gedeckt; abschwächen zu „zeigen an Strömungs-ROMs“. Dimensionstreue ist eigene Folgerung |
| ch3 Z. 30, 449–450 | `wulffPhysicsinformedRegressionModels2025` | nicht auffindbar | Unter Autor und Titel kein Treffer; nächster Kandidat: Nielsen, Jacobsen, Olson, Sørensen, Engsig-Karup 2025, „Physics-Informed Regression“, arXiv 2508.19249 (Preprint, kein Wulff unter den Autoren). Key in Zotero klären. Buckingham-π-Halbsatz mit Bakarji u. a. 2022 belegen oder streichen |
| ch3 Z. 666–671 | `lovlandClosedloopIdentificationChallenge2025` | teilweise | Metadaten stimmen (IEEE CCTA 2025, arXiv 2509.01188). Abstract behandelt die stationäre Sensitivität für Feedback-Optimierung, nicht eine dynamische Strecke; `−K⁻¹` und Theorem 1 nicht im Abstract. Klassischen Anker ergänzen: Box & MacGregor 1974 oder Söderström & Stoica 1989 (im Buch prüfen); Shardt & Huang 2011, *Automatica* 47(7), für Identifizierbarkeit aus Routinedaten |
| ch3 Z. 624–628 | `dahdahClosedloopKoopmanOperator2024` | teilweise | Metadaten: *Mach. Learn.: Sci. Technol.* 5(2), 2024, DOI 10.1088/2632-2153/ad45b0. Dass naives EDMD verzerrt, steht nicht ausdrücklich im Abstract. Verfahren setzt bekannten Regler voraus; ChATCo ist adaptiv und nichtlinear |
| ch3 Z. 956–958 | `atamAdvancedAirPath2018` | teilweise | IEEE Access 6 (Seiten und DOI im Prüflauf nicht gesehen, in Zotero ergänzen). Erweitertes LPV-**Modell** aus physikalischem Modell für Gain-Scheduling-Regler; physikalisch-modellbasiert, nicht datengetrieben. Für Z. 194 und 607 trägt der Abstract nichts |
| ch3 Z. 976–982 | `beranModelbasedApproachControl2021` | teilweise | *Automotive and Engine Technology*, DOI 10.1007/s41104-021-00087-0 (Band und Seiten im Prüflauf nicht gesehen). Ladeluftkühlung im Ejektor-Kältekreis; Regression/Baum/Random Forest bilden Lastfälle auf optimierte Stelleinstellungen ab (Kennfeldersatz), kein dynamisches Modell; Daten aus Dymola-Simulation. Lineare/polynomiale Regression ist lesbar. „Direkteste Arbeit“ abschwächen, Lücke neu fassen: dynamisches, in der Stellgröße lineares Modell von \Tout fehlt |
| ch3 Z. 998–1003 | `medaKoopmanBasedMethodsEV2025`, `zinageDataDrivenModeling2022` | teilweise | Meda & Stockar betrifft die **Klimatisierung** eines E-Fahrzeugs (nicht Antriebsstrang), Simulationsdaten; Polynom- und RBF-Liftings besser als gelerntes Dictionary. Folgearbeit Koopman-MPC: Meda u. a. 2026, *J. Dyn. Syst. Meas. Control* 148(1). Zinage u. a.: EDMD einer Abgasturbine aus **Prüfstandsdaten** eines Nfz-Diesels, besser als NARX (für Merkel anschlussfähig). „Moderate Datenmengen“ nicht gedeckt |
| ch3 Z. 1141–1144 | `yahagiGeneralizedBilinearKoopman2026` | teilweise | „Eine Ausnahme“ zu eng: Zinage 2022 nutzt ebenfalls Motormessdaten |
| ch3 Z. 1144–1147 | eigenes Argument | teilweise | Stimmt für Güte gegenüber der Realität. Simulationsdaten dienen in der Literatur aber gezielt der Modellreduktion (Benner, Gugercin, Willcox 2015; Operator Inference: Peherstorfer, Willcox 2016; Kramer, Peherstorfer, Willcox 2024) und der Methodenverifikation mit bekannter Wahrheit (Kaptanoglu u. a. 2023; Schoukens & Noël 2017). Grenze: „inverse crime“ bei gleichem Generator- und Schätzmodell (Wirgin 2004). Vorschlag: Validierung (Messdaten) und Verifikation (bekannte Wahrheit) trennen; siehe Idee A11 |
| ch3 Z. 993–996 | `bhadrirajuOASISPOperableAdaptive2021` | nicht gestützt | „EMEC“ ist EMEC-SINDy der Yahagi-Gruppe (arXiv 2503.05154, Preprint). OASIS-P ist Fehlerprognose; die adaptive SINDy-Identifikation ist OASIS (Bhadriraju u. a. 2020, *AIChE J.* 66(11), DOI 10.1002/aic.16980) |
| ch3 Z. 986–987 | `yahagiSparseIdentificationNonlinear`, `…2025`, `yonezawa…2025` | Metadaten fraglich | Key ohne Jahr vermutlich EMEC-SINDy (Preprint). IJCAS-Arbeit: *Int. J. Control Autom. Syst.* 23, 620–629, DOI 10.1007/s12555-024-0452-9 (offsetfreies NMPC am Diesel-Luftpfad). SINDy-LOM: Journalfassung *IEEE Trans. Cybern.* 56(5), 2026, DOI 10.1109/TCYB.2026.3652850. „PKW“ nicht im Abstract; „regelbasiert“ → „für die Regelung einsetzbar“ |

### E1.4 Zehn Verteidigungsfragen mit Antwortskizze

Belege: vorhandene Keys (in der Arbeit zitiert) oder neue Quellen aus der Quellenliste (Autor Jahr, Status dort). Antwortskizzen sind Stichpunkte zum Vorbereiten, keine Ergebnisse.

**F1 (Henning) Reduzierte Modelle.** „Sie berufen sich auf Loiseau & Brunton (constrained sparse Galerkin). Wo ist in Ihrer Arbeit die Projektion, welcher Zustandsraum wird reduziert, und in welchem Sinn ist ein Einzustandsmodell für \Tout ein reduziertes Modell?“ (ch3 Z. 27–41, 444–450; ch2 Z. 825–865)
- POD-Galerkin: bekannte Feldgleichung auf empirische Moden projiziert, ODE-Koeffizienten folgen aus der Projektion (Noack u. a. 2003; Rowley & Dawson 2017).
- Hier gibt es weder räumlich aufgelöste Referenzgleichung noch gemessenes Temperaturfeld. Reduziert wird vorab über Annahmen (`C_eff` bündelt die Speicher, Trennung Statik/Dynamik); \sindyc schätzt die Koeffizienten der reduzierten ODE direkt. Das ist strukturierte Systemidentifikation, kein ROM im Galerkin-Sinn.
- Brücke (eigene Algebra, E1 K5): `n` Rührkesselzellen ergeben `ε_n = 1 − (1 + N/n)^{−n}`; `n = 1` ist die Einzustandsstatik `N/(1+N)`, `n → ∞` die ε-NTU-Statik. Die Lücke ist der Diskretisierungsfehler der Ortsreduktion.
- Trunkierungsverlust als Parallele: POD verliert Moden (Closure), hier fehlen nicht aufgelöste Speicher (zweiter Pol, ch2 Z. 860–865); sie landen im Residuum oder in gefilterten Eingängen.
- Belege: `loiseauConstrainedSparseGalerkin2018` (Key vorhanden); Noack u. a. 2003; Rowley & Dawson 2017.
- Heute dünn: kein Absatz zu POD/Galerkin; Grey-Box-Einordnung ch3 Z. 36–41 widerspricht der eigenen Linie.

**F2 (Henning) Beobachter im offsetfreien MPC.** „Welches Störmodell (Eingang oder Ausgang), welcher Beobachter, woher `Q` und `R`, und ist das erweiterte System detektierbar, auch in Totzone und Sättigung?“ (ch2 Z. 1082–1091; ch3 Z. 909–925)
- Erweitertes System `x⁺ = Ax + Bu + B_d d`, `d⁺ = d`, `y = Cx + C_d d`; offsetfrei, wenn `(A, C)` detektierbar und `rank [[I−A, −B_d],[C, C_d]] = n + n_d`; bei einer Messgröße `n_d = 1` (`pannocchiaDisturbanceModelsOffsetfree2003`, `muskeDisturbanceModelingOffsetfree2002`, beide Keys vorhanden).
- Ausgangsstörung (`B_d = 0`, `C_d = 1`): Bedingung erfüllt, solange `A` keinen Eigenwert 1 hat (stabile Relaxation). Eingangsstörung (`B_d = B`): braucht stationären Gain ≠ 0, in Totzone und Sättigung schwach (eigene Folgerung, prüfen).
- Kalman-Filter für Random-Walk-Störung plus weißes Messrauschen hat eine stationäre Verstärkung, die einer exponentiellen Glättung entspricht; der EWMA ist die optimale Prognose für einen Random Walk mit überlagertem Rauschen (Muth 1960). Eine EMA-Implementierung ist so als stationärer KF lesbar, Glättungsfaktor ↔ `Q/R`.
- Geschwindigkeitsform (Δu) entspricht einem bestimmten Störmodell mit Beobachter (Pannocchia, Gabiccini, Artoni 2015); klären, ob Gl. `eq.grundlagen.mpc` die Integralwirkung schon enthält.
- `Q/R` aus Betriebsdaten per Autokovarianz-LS (Odelson, Rajamani, Rawlings 2006); Innovationsfolge auf Weißheit testen.
- Offsetfrei korrigiert das Niveau, nicht den Gain (Dreiteilung ch3 Z. 909–925).
- Heute dünn: Störmodell, Beobachterverstärkung, Detektierbarkeit fehlen ganz.

**F3 (Henning) Störgrößen über den Horizont und Mehrwert gegenüber ChATCo.** „Was nimmt der MPC online für `T_col,in`, `T_LTCW`, `T_HTCW`, \mrel an? Wie viel Vorteil bleibt ohne perfekte Vorschau, wenn ChATCo die Störgrößen schon über das Kennfeld aufschaltet?“ (ch2 Z. 1034–1041, 1111; ch3 Z. 1202–1204)
- Varianten: (a) über den Horizont konstant (Halteglied, entspricht Random-Walk-Prognose); (b) Störmodell im erweiterten Zustand, Prognose mit Kalman-Filter; (c) Vorschau aus der Leistungsanforderung, nur wenn anlagenseitig verfügbar.
- Zeitskalen: `T_HTCW` schwankt wenig, `T_LTCW` folgt langsam der Umgebung (ch2 Z. 206–219), dort ist Konstanthalten vertretbar; `T_col,in` und \mrel springen mit der Last.
- Faire Referenz ist PI plus Vorsteuerung, nicht reines PI. Mehrwert des MPC: dynamische statt statischer Störgrößenaufschaltung, arbeitspunktabhängige Stellwirkung, weiche Grenzen, Ratenbegrenzung.
- Analogie: MPC mit Wetterprognose in der Gebäudeklimatisierung, dort ist der Prognosebeitrag eigener Untersuchungsgegenstand (Oldewurtel u. a. 2012). Getrennt zeigen: perfekte Vorschau (obere Schranke) und eingefrorene Störgrößen (realistisch). Siehe Idee A8.
- Belege: `rawlingsModelPredictiveControl20202020` (Key vorhanden); Oldewurtel u. a. 2012; Odelson u. a. 2006.

**F4 (beide) Methode der Closed-Loop-Identifikation.** „Welche der vorgestellten Methoden wenden Sie an, wenn der Sollwert fest bei 52 °C steht und der Serienregler adaptiv ist und sättigt? Welches Störmodell haben \sindyc und ARX, und warum sollte die Schätzung konsistent sein?“ (ch3 Z. 654–721, 764–775, 869–875)
- Indirekt scheidet aus: linearer, exakt bekannter, zeitinvarianter Regler nötig (ch3 Z. 681–682); ChATCo hat adaptives Kennfeld, Anti-Windup, Stellgrenzen.
- IV/Zwei-Stufen scheiden in Reinform aus: brauchen bewegten Sollwert als exogenes Instrument (Van den Hof & Schrama 1993); die Last wirkt direkt auf die Strecke und ist kein Instrument für den Stellkanal.
- PBSID (Chiuso 2007) wäre konsistent für lineare Modelle, behebt aber keine fehlende Anregung.
- Bleibt die direkte Methode: Stellkanal aus der Prüfstands-DoE mit gesetzten Ventilsprüngen, Felddaten für Störpfad und Validierung. Konsistenz verlangt das wahre Störmodell im Modellsatz (`forssellClosedloopIdenticationRevisited1999`); \sindyc und ARX haben Gleichungsfehlerstruktur mit implizitem Störmodell. Kontrolle mit HO-ARX oder BJ auf den Prüfstandsdaten.
- Modussprung: macht Daten informativ (Ljung Abschn. 13.4), ist aber mit Brennstoff- und Betriebspunktwechsel konfundiert.
- Heute dünn: keine ausdrückliche Methodenentscheidung; ch3 Z. 764–775 Rohtext.

**F5 (Henning) Zirkularität von Simulationsdaten und „bekannte Wahrheit“.** „Warum prüfen Sie Ihre Closed-Loop-Aussagen nicht an einem Simulator mit bekanntem Modell? Und ist der Prüfstand wirklich bekannte Wahrheit?“ (ch3 Z. 1141–1147, 922–925)
- Zwei Zwecke trennen: (a) Regelmodell der realen Strecke, dafür Messdaten; (b) Verifikation der Identifikationsmethode, dafür ist eine Umgebung mit bekanntem Modell üblich (Benchmarks mit bekannten Gleichungen: Kaptanoglu u. a. 2023; Schoukens & Noël 2017). Das Argument in Z. 1145–1146 betrifft nur (a).
- Grenze: gleiches Generator- und Schätzmodell ist ein „inverse crime“ und zu optimistisch (Wirgin 2004); Generatorstruktur darf nicht der Bibliothek entsprechen.
- „So gut wie möglich modellieren, dann für den Zweck vereinfachen“ (Hjalmarsson 2005): ein Ersatzmodell kann für den Zweck besser geeignet sein (QP-tauglich), ohne die Quelle an Genauigkeit zu übertreffen.
- Der Prüfstand liefert bekannte Anregung, kein wahres Modell; „Wahrheit“ ist ein gemessener Sprung mit Rauschen und Arbeitspunktbezug.
- Siehe Idee A11 (Twin-Experiment).

**F6 (Henning) Robustheit gegen Gain-Fehler, Rate und Totzeit im QP.** „Wie robust ist der MPC gegen einen falschen Ventil-Gain (Betrag, im Extrem Vorzeichen)? Wie gehen Ratenbegrenzung, Transporttotzeit und die Verzögerung beim Richtungswechsel ein, wenn das QP keine Δu-Schranke hat?“ (ch2 Z. 264–268, 781–793, 1061–1082)
- Offsetfrei gegen stationäre Fehler; Stabilität hängt vom Verhältnis wahrer zu modelliertem Gain ab: zu großer Modell-Gain macht träge, zu kleiner aggressiv, Vorzeichenfehler destabilisiert. Rahmen: robuste MPC (Bemporad & Morari 1999); praktisch Gain-Band aus der DoE als Unsicherheit, Nachweis per Simulation mit Gain-Faktoren (Idee A7).
- Bekannter Koeffizient statt festem Gain: `b_k = b(T_zw − \TLT, \mrel)` aus Messgrößen, über den Horizont eingefroren, ergibt ein LTV-QP (vgl. sukzessive Online-Linearisierung bei Falcone u. a. 2007).
- `|Δu_k| ≤ Δu_max` als lineare Ungleichung (Maciejowski 2002); Transporttotzeit als ganzzahlige Eingangsverschiebung, QP bleibt linear; Umkehrspiel ist nicht LTI, als Unsicherheit führen.
- Heute dünn: keine Δu-Schranke, keine Robustheitsbetrachtung.

**F7 (Merkel) SINDy gegen NARMAX mit FROLS.** „Worin unterscheidet sich Ihr \sindyc mit STLSQ-Schwellwert von polynomialem NARMAX mit FROLS-Termauswahl über die Error Reduction Ratio? Warum nicht FROLS?“ (ch3 Z. 197–205, 411–431)
- Gemeinsam: linear in den Parametern, Kandidatenbibliothek, sparsame Termauswahl, Instanzen von Gl. `eq.lsq`; das Argument „vordefinierte Bibliothek“ trennt nicht.
- Unterschiede: Lernziel (Ableitung bzw. Folgewert mit Zustandsform gegenüber `y(k)` aus verzögerten Ein-/Ausgängen); Auswahl (FROLS vorwärts, orthogonalisiert, ERR je Term, Chen, Billings, Luo 1989; STLSQ rückwärts über Schwellwert); NARMAX schätzt MA-Rauschterme mit (Billings 2013), \sindyc hat kein explizites Störmodell.
- Begründung STLSQ: kleine, physikalisch vorstrukturierte Bibliothek. Zugeben: FROLS wäre auf derselben Bibliothek billig als Vergleich rechenbar (Idee A12).
- Z. 204–205 korrigieren: gemeint sind die Grenzen der LS-Schätzung, nicht der „linearen Modellklasse“.

**F8 (Merkel) Einschritt- gegen Simulationsfehler.** „Nach welchem Kriterium wählen Sie Terme und Hyperparameter: Einschritt- oder Simulationsfehler? Was tun Sie mit einem Modell, das einschrittig gut ist und im Freilauf driftet?“ (ch3 Z. 42–49, 519–526; ch2 Z. 999, 1061–1073)
- Bei 500-ms-Takt und langen thermischen Zeitkonstanten ist `y(k) ≈ y(k−1)`; der Einschrittfehler ist klein und sagt wenig über Dynamik und Gain (an Daten zeigen).
- Polynomiale NARX: Auswahl nach Prädiktionsfehler liefert oft schlechte Simulationsmodelle, deshalb Simulationsfehler als Auswahlkriterium (Piroddi & Spinelli 2003); beim NN-Training dieselbe Frage (Ribeiro & Aguirre 2018).
- Eigene Linie: Schätzung per LS (Einschritt/Ableitung), Auswahl und Bewertung auf OL-Simulation und k-Schritt-Vorhersage über den MPC-Horizont (Idee A5).
- Belege: `manganModelSelectionDynamical2017` (Key vorhanden); Piroddi & Spinelli 2003; Ribeiro & Aguirre 2018.

**F9 (Merkel) Residuentests für nichtlineare Modelle unter Rückführung.** „Sie bemängeln, dass SINDy-/Koopman-Arbeiten ihre Residuen nicht prüfen. Prüfen Sie Ihre, mit welchen Tests, und gelten diese im geschlossenen Kreis?“ (ch3 Z. 1024–1029, 806–823)
- Linear: Autokorrelation, Kreuzkorrelation Residuum–Eingang (`ljungSystemIdentificationTheory1999`, Kapitel prüfen); Portmanteau (Ljung & Box 1978).
- Nichtlinear: Korrelationstests nach Billings & Voon 1986, höherer Ordnung nach Billings & Zhu 1994; passen zur Frage, ob die Bibliothek Terme vergisst.
- Geschlossener Kreis: Kreuzkorrelation mit \valveCA ist in einer Lag-Richtung auch beim wahren Modell ungleich null; nur kausal zulässige Lags werten oder gegen exogene Größen; Test gegen \valveCA auf DoE-Daten rechnen.
- Standard-Kreuzkorrelationstest ist nur unter der Annahme gültig, die er prüfen soll (Douma, Bombois, Van den Hof 2008, *Automatica*; Autoren im Prüflauf nur aus Zusammenfassung); als Falsifikationstest einsetzen.
- Einschritt-Residuen und Simulationsresiduen trennen (Idee A3).

**F10 (Merkel) Konfundierung und Anregung für Produktterme.** „Reicht ein `R²` der Stellgröße gegen die Last? Ist Ihr Datensatz für Terme `g(\valveCA)·ΔT` ausreichend anregend?“ (ch3 Z. 845–889; ch2 Z. 270–274, 398–419)
- `R²` gegen die Last unterschätzt: Kennfeld hat zwei Eingänge, `T_LTCW` steckt in den ΔT-Spalten. Besser VIF bzw. multiples `R²` der Stellgrößenspalten gegen alle übrigen Spalten, Konditionszahl und Varianzzerlegung (Belsley, Kuh, Welsch 1980), getrennt für Prüfstand und Feld (Idee A2).
- Adaptive Kennfeld-Nachführung erzeugt Variation, wird aber aus dem PI-Anteil gespeist: Rückführung, keine exogene Anregung.
- PE-Definition gilt für in `u` lineare Modelle; Produktterme brauchen Amplitudenvielfalt über Stellbereich und Betriebspunkte; Rang/Kondition der Informationsmatrix (`geversIdentificationInformationMatrix2009`, Key vorhanden). Abdeckung der DoE als Bild zeigen (Idee B1).

Weitere Kandidaten (kurz, falls Zeit):
- (Henning) Konvergenz von eDMD „im Datenlimit“: bezüglich welchen Maßes? Unter Regelung liegen die Felddaten auf einer Reglermannigfaltigkeit (Korda & Mezić 2018, *J. Nonlinear Sci.*).
- (Henning) Übertragbarkeit auf andere Baureihen und Verschmutzung: Termstruktur übertragbar, Koeffizienten und Bänder nicht; Verschmutzung verschiebt den Gain, der Beobachter nur das Niveau.
- (Merkel) Warum keine NARX-NN-Obergrenze? Stärkster Grund: QP-Tauglichkeit (Stellgröße nicht linear mit bekanntem Koeffizienten); Obergrenze als reine OL-Referenz denkbar (Chen, Billings, Grant 1990; Schoukens & Ljung 2019).
- (Merkel) Ordnung, Totzeit, Modelltakt: Totzeit aus DoE-Sprüngen (Björklund & Ljung 2003), Einfluss Totzeit/Abtastzeit auf Identifizierbarkeit aus Routinedaten (Shardt & Huang 2011).
- (Merkel) Hyperparameterwahl ohne Testdaten-Verbrauch, zeitreihengerechte Kreuzvalidierung (Bergmeir & Benítez 2012; Bergmeir, Hyndman, Koo 2018).

## E2 Beitrag der Arbeit schärfen

### E2.1 Beitragsformulierungen BT1–BT5 (Stichpunkte, sortiert nach Tragfähigkeit)

Jede Formulierung nennt die Lücke, ihren Beleg und was Kap. 5–7 zeigen müssen. Keine Ergebniszahlen; „zeigt“ steht erst, wenn die Voraussetzung erfüllt ist, sonst „prüft“.

**BT1 QP-taugliche Modellform aus der Stufenbilanz.**
- Diese Arbeit zeigt, dass die HT-/LT-Stufenbilanz des HP-Ladeluftkühlers eine \sindyc-Modellform nahelegt, in der \valveCA nur im stationären Zielwert und dort nur multipliziert mit gemessenen exogenen Größen auftritt (z. B. `g(\valveCA)(\Tin − \TLT)`, `\mrel g(\valveCA)(\Tin − \TLT)`), nicht mit \Tout. Bei bekannten oder eingefrorenen Störgrößen ist der Prädiktor zeitvariant-linear in \valveCA, das MPC-Problem bleibt ein konvexes QP.
- Lücke: Wärmeübertrager-Arbeiten führen das Produkt Durchfluss × Temperaturdifferenz als bilinear in Stellgröße und Zustand (Koopman-Bilinearform, dann NMPC/SQP: Pan, Li 2024, Kälteanlage, *Control Eng. Pract.* 147; Ripa u. a. 2025, Gegenstrom-Wärmeübertrager, Preprint) oder als quasi-LPV mit zustandsabhängigem Scheduling (Cisneros u. a. 2020). Eine Form mit Scheduling nur über gemessene Störgrößen trat für Ladeluft oder Wärmeübertrager in der Suche nicht auf (Leerbefund, Suchweg in E2.3).
- Ehrlich einordnen: LTV-MPC mit Eingangsmatrix aus Messgrößen ist regelungstechnisch Standard. Neu ist, dass die Streckenphysik genau diese Form trägt (ch2 Z. 929–934) und \sindyc sie mit festen Termformen aus Daten schätzt.
- Voraussetzung: Kap. 5 schreibt `B_k = b((\Tin − \TLT)_k, \mrel_k)` aus und zeigt die Konvexität; Informationsannahme für Störgrößen festlegen; `g(\valveCA)` linear oder stückweise linear mit festen Stützstellen. Kap. 6 zeigt die Kosten der Vereinfachung gegen eine Variante mit Ventil in der Rate (bilinear) in OL, DoE und Ventil-Gain; Mitbewegung von \Tin und \TLT mit \valveCA am Prüfstand prüfen.

**BT2 Welche Modelleigenschaft ist aus Regelkreisdaten rückgewinnbar, geprüft gegen Prüfstands-Wahrheit.**
- Diese Arbeit prüft getrennt nach Niveau, Dynamik (Zeitkonstante, Totzeit) und Stellwirkung (Ventil-Gain), welche Eigenschaft eines aus Regelkreisdaten geschätzten ARX-, \sindyc- und \edmdc-Modells mit den Ventilsprüngen und der DoE am Prüfstand übereinstimmt, und ob der betriebliche Wechsel Diesel → Gas im Feld als Anregung des Stellkanals reicht.
- Lücke: Die CL-Theorie behandelt Informativität und Konsistenz für das Modell als Ganzes (`forssellClosedloopIdenticationRevisited1999`, `ljungSystemIdentificationTheory1999` Abschn. 13.4, `geversIdentificationInformationMatrix2009`). SINDy-/Koopman-Arbeiten benennen das Rangproblem (`bruntonSparseIdentificationNonlinear2016` S. 713, `proctorDynamicModeDecomposition2016` S. 153) oder setzen einen bekannten Regler voraus (`dahdahClosedloopKoopmanOperator2024`). Ein Abgleich einer CL-Schätzung gegen offene Sprungversuche derselben Anlage trat in der Suche nicht auf. Nächste Verwandte: Wu 2026 (arXiv-Preprint, theoretisches Kriterium für die Informativität des Stellkanals bei EDMDc aus Daten eines bestehenden Reglers).
- Ehrlich einordnen: Dass Reglerumschaltung Daten informativ macht, ist bekannt (Ljung; geplante Gewichtsumschaltung im MPC: „MPC closed-loop identification without excitation“, *J. Process Control* 2021, Autoren im Prüflauf nicht gesehen). Neu wäre nur der ungeplante betriebliche Wechsel, und der ist mit Brennstoff- und Niveauwechsel konfundiert.
- Voraussetzung: Kennwert je Eigenschaft (Kap. 5); Modelle nur aus CL-Abschnitten des Prüfstands schätzen, DoE zurückhalten (Kap. 6); für den Modussprung zeigen, dass Stellsprung und Modus-Offset trennbar sind. Gelingt das nicht, Beitrag auf „notwendig, nicht hinreichend“ zurücknehmen.

**BT3 Physikalisch motivierte \sindyc-Bibliothek für die Ladelufttemperatur eines Großmotors aus Messdaten.**
- Diese Arbeit zeigt am 49/60DF, wie eine \sindyc-Bibliothek für \Tout aus der HT-/LT-Stufenbilanz statt aus einer Polynombibliothek entsteht: Temperaturdifferenzen (`\Tin − \THT`, `\THT − \TLT`, `\Tin − \TLT`) mal Betriebspunktfaktor \mrel (aus `Δp_HP`, Druck, Temperatur), Ventilfunktion und Relaxationsterm. Die Physik legt nur die Termformen fest; welche Termfamilien die sparse Regression stabil behält, wird geprüft.
- Lücke: SINDy-Motorarbeiten betreffen den Diesel-Luftpfad (Ladedruck, AGR) überwiegend auf Simulationsdaten (`yahagiSparseIdentificationNonlinear2025`; Yahagi u. a. 2025, EMEC-SINDy, Preprint); die Koopman-Arbeit mit Prüfstandsdaten betrifft Ladedruck und Luftmasse (`yahagiGeneralizedBilinearKoopman2026`); Ladelufttemperatur-Arbeiten sind physikalisch (`vagapovDynamicModelTemperature2022`, `rupprechtAnalysisSimulationOptimisation2016`) oder Kennfeldersatz per Regression/Random Forest auf Simulationsdaten (`beranModelbasedApproachControl2021`). SINDy mit realen Triebwerksdaten gibt es (Paniccia u. a. 2025, Turbowellentriebwerk, Preprint), nicht für Großmotoren.
- Ehrlich einordnen: Eine reine Erstanwendung ist schwach und nur für den Suchumfang belegbar; tragfähig wird BT3 durch die Herleitung der Termformen und den Proxy \mrel.
- Voraussetzung: jede Bibliotheksspalte auf eine Gleichung aus ch2 zurückführen; Vergleichsbibliothek (Polynom) ähnlicher Spaltenzahl; Stabilität der Termauswahl (Ensemble, VIF) und Vorzeichenkonsistenz zeigen.

**BT4 Ventil-Gain als eigenes Bewertungskriterium neben dem Vorhersagefehler.**
- Diese Arbeit bewertet ein Streckenmodell für den MPC neben OL- und CL-Fehler an seiner Stellverstärkung `d\Tout/d\valveCA` gegen die Prüfstandssprünge, mit fester Konvention (Sekante oder lokale Steigung, Arbeitspunkt, partielle Wirkung bei festgehaltenen Störgrößen), und prüft, ob die Rangfolge nach RMSE und nach Gain übereinstimmt.
- Lücke: Die gefundenen SINDy-/Koopman-Vergleiche bewerten mit NRMSE, MSE, R² oder Regelgüte; Stellverstärkung gegen Sprungversuche tritt dort nicht als eigenes Kriterium auf. Gegenbeispiel: In der Prozessregelung ist Gain-Fehlanpassung als MPC-Gütegröße etabliert (Tufa, Ka 2016; Badwe u. a. 2009; Identification for Control: Gevers 2005).
- Ehrlich einordnen: Neu ist nicht das Kriterium, sondern sein Einsatz beim Vergleich sparser und gelifteter Modellklassen auf CL-Daten, bei denen eine Verschiebung des Schätzers zu erwarten ist (`lovlandClosedloopIdentificationChallenge2025`). Besser als Prüftor der Bewertungsleiter zusammen mit BT2 führen.
- Voraussetzung: DoE-Referenz mit Unsicherheit; Rangfolgen nebeneinander; in der MPC-Simulation zeigen, wie sich ein Gain-Fehler auf die Regelgüte auswirkt (Idee A7).

**BT5 Vergleich ARX, \sindyc, \edmdc als Ablation auf gemeinsamer Kleinste-Quadrate-Basis.**
- Diese Arbeit ordnet Unterschiede zwischen ARX, \sindyc und \edmdc einer einzelnen Entwurfsentscheidung zu (Bibliothek Θ, Lernziel Y, Regularisierung), bei gleichen Daten, Eingängen, Abtastung und Normierung.
- Lücke: Modellklassenvergleiche gibt es (SINDy-MPC gegen DMDc und NN: `kaiserSparseIdentificationNonlinear2018`; N4SID/SINDYc/ARX an einem Kontinuumsroboter: arXiv 2605.18720, Preprint, Autoren offen; Koopman gegen NARX an Motordaten: `zinageDataDrivenModeling2022`), keiner ändert je Variante nur eine Entwurfsentscheidung an einer thermischen Industriestrecke mit CL-Daten.
- Ehrlich einordnen: schwächster der fünf; als Versuchsplan formulieren, nicht als „fairer Vergleich“ allgemein.
- Voraussetzung: Plausibilitätsprüfung, dass \edmdc mit reinen Delays das ARX-Ergebnis reproduziert (`bruntonModernKoopmanTheory2022` S. 305–306); Auswahl nur auf Entwicklungsdaten.

Empfehlung für die Beitragsliste in ch3 (Abschnitt Einordnung): BT1, BT2 und BT3 als Hauptbeiträge, BT4 als Bewertungsbeitrag innerhalb von BT2, BT5 als methodische Sorgfalt im Methodikkapitel. Die Formulierung „Der eigene Beitrag liegt in ihrer nachvollziehbaren Umsetzung und Prüfung“ (ch3 Z. 1196–1197) ersetzen.

### E2.2 Nächste Verwandte 2019–2026

- Auswahl aus den Suchläufen BL und V1 bis V6 (zusammen rund 160 ausgeführte Suchanfragen am 25.09.2026, Protokoll in E2.3) und den Keys, die ch3 schon zitiert. Alle Angaben nur aus Abstracts oder bibliografischen Einträgen, kein Volltext gelesen.
- Nähe (N, 1–5) = eigene Einschätzung: 5 gleiche Frage an vergleichbarer Anlage, 1 nur Methodenanker.
- Metadaten jeder neuen Arbeit in einem zweiten, unabhängigen Suchlauf geprüft (Quellenliste: „bestätigt“ oder „korrigiert“). Ausnahme: mit † markierte Arbeiten aus der letzten Nachrecherche, deren Zweitprüfung am erschöpften Suchbudget scheiterte. Bei „Autoren offen“ stand die Autorenliste in keinem Suchergebnis.
- Ältere Anker außerhalb 2019–2026 (Rupprecht 2016, Kaiser u. a. 2018, Esmaili u. a. 2017) stehen nur in den Abgrenzungen.

#### (a) Ladeluft, Kühler, Motor-Luftpfad und Motorkühlung

| Arbeit | N | Daten | Was sie macht | Was sie nicht macht | Abgrenzung dieser Arbeit |
|---|---|---|---|---|---|
| Vagapov u. a. 2022, `vagapovDynamicModelTemperature2022` | 4 | Prüfstand und Fahrzeug | Hammerstein-Modell der Ladelufttemperatur: nichtlineare Kühlerstatik plus lineare Dynamik, Ordnungsreduktion (nach ch3 Z. 1057–1068) | kein Regler, physikalisch parametriert, Pkw-Kühler | Termformen aus der Stufenbilanz, Koeffizienten aus Daten per \sindyc; zweistufiger Kühler eines Großmotors; Stellwirkung gegen DoE geprüft |
| Vagapov 2024, `vagapovModellierungIdentifikationUnd2024` | 4 | Fahrzeugversuch | prädiktive äußere Stufe für die Lufttemperatur nach dem Kühler, Vorgaben an Pumpe und Ventil; volle Kaskade verfehlt die Rechenzeit (ch3 Z. 1069–1081) | kein datengetriebenes Modell, Regelgüte nur grob untersucht | ein Stellglied, lineares QP, Rechenzeit als eigene Prüfung (Idee D5) |
| Beran, Gärtner, Koch 2021, `beranModelbasedApproachControl2021` | 3 | Simulation (Dymola) | Regression, Entscheidungsbaum, Random Forest bilden Lastfälle auf optimierte Stelleinstellungen einer Ladeluftkühlung im Ejektor-Kältekreis ab | kein dynamisches Modell, keine Messdaten | dynamisches, in \valveCA lineares Modell von \Tout aus Messdaten (E1.3) |
| JMSE 2026, Bd. 14, Art. 845 „An Assessment of the Operation Under Different Ambient Conditions of the Charge–Air Cooler for a Large Marine Diesel Engine“ (Autoren offen) | 3 | Simulation (laut Abstract) | Einfluss der Umgebungsbedingungen, vor allem der Ansauglufttemperatur, auf den Ladeluftkühler eines großen Schiffsdiesels | keine Regelung, kein datengetriebenes Modell | Regelgröße \Tout mit Kühlwassertemperaturen als Störgrößen; ob es die in ch2 Z. 954 zitierte „Arava 2026“ ist, prüft Copilot |
| Choi, Yoon, Kim, Ham 2026 (Int. J. Engine Res.) | 3 | Betriebsdaten zweier Schiffsmotoren | Hybrid aus Physik und Daten für Turbolader-Schiffsmotoren mit minimalem Datenbedarf (Kennfeld, Werksabnahme), Digital-Twin-Ziel | keine Ladelufttemperaturregelung, kein MPC, CL-Verzerrung nicht erkennbar | Großmotor-Nachbar mit Betriebsdaten; hier sparse Regression und Prüfung gegen Prüfstands-DoE |
| Zhang, Amini, Kolmanovsky, Tsutsumi, Nakada 2022 (ACC 2022, arXiv-Preprint) | 3 | Simulation (GT-Power) | ratenbasiertes LPV-Modell des Diesel-Luftpfads aus transienten Antworten, MPC für AGR/VGT, robust gegen Fehler der Motorthermik | keine Messdaten, Thermik nur als Störung | gleiche Idee „parametervariant, im QP linear“; hier Temperatur als Regelgröße, Scheduling über gemessene Störgrößen |
| Kaleli 2020 (Control Eng. Pract., Koautoren offen) | 3 | Echtzeitumsetzung am Motor (laut Titel) | MPC eines autonomen Kühlsystems am Ottomotor; MIMO-Modell per Systemidentifikation, acht lokale lineare Modelle, Temperaturgrenzen als Nebenbedingungen | keine Ladeluft, keine sparse oder Koopman-Modelle | Nachbar für „lokal lineares Modell im QP“; hier ein Modell mit Betriebspunktfaktoren statt Modellbank |
| Patil, Theotokatos, Tsitsilonis 2025 (J. Mar. Eng. Technol.) | 2 | Simulation (kalibriertes 0D-Modell), Werksdaten | Fehlerdiagnose eines Viertakt-Schiffsdiesels, darunter Verschmutzung des Ladeluftkühlers, per Regression auf Zylinderdruck-Harmonischen | keine Regelung, keine Ladelufttemperaturdynamik | Anker für Fouling als Grenze und Ausblick (Idee D4) |

#### (b) SINDy und Koopman an Motoren und Triebwerken

| Arbeit | N | Daten | Was sie macht | Was sie nicht macht | Abgrenzung dieser Arbeit |
|---|---|---|---|---|---|
| Yahagi, Seto, Yonezawa u. a. 2025, `yahagiSparseIdentificationNonlinear2025` (Int. J. Control Autom. Syst. 23, 620–629) | 4 | Simulation (Mittelwertmodell) | SINDy-Modell von Ladedruck und AGR-Rate, darauf NMPC (VGT, AGR-Ventil) | keine Temperatur als Regelgröße, keine Messdaten, kein QP | Ladelufttemperatur, Messdaten aus Prüfstand und Feld, lineares QP |
| Yahagi, Yonezawa, Yonezawa, Seto, Kajiwara 2026, `yahagiGeneralizedBilinearKoopman2026` (arXiv-Preprint 2602.15422) | 4 | Motorprüfstand unter Serien-PID | verallgemeinerte bilineare Koopman-Realisierung aus Ein-/Ausgangsdaten, Mehrschrittprognose von Ladedruck und Luftmasse | Regler erst als nächste Aufgabe; Rückführungsverzerrung laut ch3 nicht behandelt | gleiche Datenlage (Serienregler im Kreis), hier mit getrennter Prüfung des Stellkanals gegen DoE |
| Yahagi, Yonezawa, Seto, Yonezawa, Kajiwara 2025 (arXiv-Preprint 2503.05154, EMEC-SINDy) | 3 | Simulation (Diesel-Luftpfad, verrauscht) | Ensemble-SINDy mit Bibliotheks-Bagging, Elite-Auswahl, Mehrschrittbewertung | keine Messdaten, keine Temperatur | Termstabilität per Block-Bootstrap statt iid-Bagging (Idee A4) |
| Yonezawa, Yonezawa, Yahagi u. a. 2026 (IEEE Trans. Cybern. 56(5), 2475–2488) | 3 | laut Abstract nicht erkennbar | äußere Schleife optimiert Basisfunktionen nach rekursiver Langzeitvorhersage, innere Schleife sparse Regression | Bibliothek nicht aus Physik | hier Bibliothek aus der Stufenbilanz fest vorgegeben, Langzeitgüte als Bewertung (Idee A5) statt als Optimierungsziel |
| Zinage u. a. 2022, `zinageDataDrivenModeling2022` (IFAC-PapersOnLine, Autoren im Prüflauf nicht gesehen) | 3 | Prüfstand (Nfz-Diesel) | EDMD der Turboladerturbine aus Messdaten, besser als abgestimmtes NARX | keine Regelung, keine Temperaturstrecke | Motormessdaten mit Koopman; hier Vergleich mit ARX und \sindyc und Prüfung des Stellkanals |
| Paniccia u. a. 2025 (arXiv-Preprint 2502.14120; Fassung in The Aeronautical Journal) | 2 | Flugversuchsdaten | SINDy für Kraftstoffstrom → Drehmoment eines Turbowellentriebwerks aus realen Daten | keine Regelung; Journalfassung erwähnt laut Suchergebnis nur neuronale Netze | Beleg, dass SINDy mit realen Triebwerksdaten funktioniert; nicht für Großmotoren |
| Grasev 2026 (Nonlinear Dynamics) | 2 | Betrieb im geschlossenen Kreis (laut Abstract) | Koopman-Eigenfunktionsmodell eines Turbostrahltriebwerks, Rotordynamik per SINDy, optimaler Regler mit Kalman-Schätzer | keine Diskussion der Rückführungsverzerrung im Abstract erkennbar | Identifikation aus CL-Daten ebenfalls; hier Prüfung gegen offene Sprünge |

#### (c) SINDy- und Koopman-MPC an thermischen und verfahrenstechnischen Anlagen

| Arbeit | N | Daten | Was sie macht | Was sie nicht macht | Abgrenzung dieser Arbeit |
|---|---|---|---|---|---|
| † Valábek, Horváthová, Pannocchia, Klaučo 2026 (Control Eng. Pract., PII S0967066125004253) | 4 | Laborversuch (Pasteurisierungsanlage) | Deep-Koopman-MPC mit NN-Liftung, im Liftraum lineares Modell, Zustandskorrektur aus Messungen, Echtzeit, Vergleich mit Subspace-Modell | keine deutbare Bibliothek, keine CL-Identifikation erkennbar | Bibliothek aus Termformen statt NN, Koeffizienten deutbar, Ventil-Gain direkt prüfbar |
| † Valábek, Horváthová, Klaučo 2026 (SSRN-Preprint 7493739) | 4 | laut Prüflauf offen | Koopman-MPC gegen lineares MPC am Plattenwärmeübertrager: stationär gleich, Vorteil erst fern vom Arbeitspunkt, aggressiver im Stellen | keine sparse Bibliothek, keine Felddaten | gleiche Fairness-Frage (Idee B7); ihr Befund ist ein prüfbares Argument für Betriebspunktfaktoren |
| Daráš, Valábek, Klaučo 2026 (arXiv-Preprint 2604.00524) | 3 | NN-Digital-Twin als Strecke | DeePC gegen Koopman-MPC an einer Pasteurisierungsanlage (3×3) | keine Messdaten als Strecke | Modellklassenvergleich im selben MPC; hier mit DoE-Prüfung |
| Pan, Li 2024 (Control Eng. Pract. 147, 105936) | 4 | laut Abstract nicht erkennbar | Koopman-Bilinearform für Kälteanlagen mit Eingang-Zustand-Bilinearität, NMPC, Konvexifizierung per McCormick-Hüllen | kein lineares QP, Bilinearität über den Zustand | E1.1 K3: hier Stellgröße × gemessene Störgröße, damit LTV-QP ohne Konvexifizierung |
| Ripa, Astolfi, Hamroun, Regruto 2025 (arXiv-Preprint 2507.16553) | 3 | realer Gegenstrom-Wärmeübertrager | Durchfluss als Stellgröße ergibt bilineares Modell aus Volumendiskretisierung, Integralregler mit Beobachter | kein MPC, kein datengetriebenes Modell | gleiche Bilinearität Durchfluss × Temperatur; hier datengetrieben und im QP über bekannte Koeffizienten |
| Cisneros, Datar, Göttsch, Werner 2020 (IFAC-PapersOnLine 53(2), 6062–6068) | 3 | Anwendung Steuermomentkreisel (laut Suchauszug) | datengetriebenes quasi-LPV-Modell mit Koopman-Werkzeugen, qLPV-MPC | keine thermische Anlage | Stufe 3 der Stufenleiter (Idee D10); hier Scheduling nur über gemessene Störgrößen |
| Lin, Oncken, Agarwal 2024 (Ann. Nucl. Energy 200, 110399) | 3 | laut Abstract nicht eindeutig | drei datengetriebene MPC-Modelle für einen Heat-Pipe-Mikroreaktor, darunter lineares Zustandsraummodell mit \sindyc kalibriert | keine CL-Verzerrung, keine Stellwirkungsprüfung erkennbar | \sindyc im MPC an thermischer Anlage; hier Messdaten und DoE-Prüfung |
| Abdullah, Christofides 2023 (Chem. Eng. Res. Des. 196, 750–769) | 2 | Simulation (Prozessbeispiele) | SINDy mit Online-Aktualisierung gegen Drift im Lyapunov- und ökonomischen MPC | keine Messdaten | Nachführung nur als Ausblick (Idee D9) |
| „Model Discrepancy Learning for Heat Exchanger Networks“ 2024 (IFAC-PapersOnLine, Autoren offen) | 3 | Messdaten gegen Simulationsmodell | \sindyc und LS lernen die Diskrepanz zwischen Messung und First-Principles-Modell eines Wärmeübertragernetzes | Greybox-Korrektur, kein MPC | hier kein Referenzmodell als Basis, \sindyc direkt auf \Tout; Physik nur für Termformen |

#### (d) Identifikation aus dem geschlossenen Kreis im SINDy- und Koopman-Rahmen

| Arbeit | N | Daten | Was sie macht | Was sie nicht macht | Abgrenzung dieser Arbeit |
|---|---|---|---|---|---|
| Wu 2026 (arXiv-Preprint 2605.17966, Autor laut Suchzusammenfassung) | 5 | Theorie, Beispiele | EDMDc aus Daten eines bestehenden Reglers sagt Verhalten gut vorher, identifiziert aber nicht die Wirkung neuer Stellbefehle; Kriterium: Restkovarianz des Eingangs nach Projektion auf den Merkmalsraum (Schur-Komplement) | keine reale Anlage, kein Abgleich gegen offene Versuche | Anwendung derselben Frage mit Prüfstands-Wahrheit; das Kriterium ist die Varianzform des multiplen R² in Idee A2 |
| Wu 2026 (arXiv-Preprint 2605.09545) | 3 | Duffing, Van der Pol, Lorenz | Diagnosezertifikate für Datenqualität und Identifizierbarkeit bei Koopman-Regression (Abdeckung, Entartung, Regressionsspektrum) | keine reale Anlage, Rückführung nicht behandelt | Prüfwerkzeug für die Segmentauswahl (Idee B5) |
| Dahdah, Forbes 2024, `dahdahClosedloopKoopmanOperator2024` | 4 | Simulation und Experiment | Koopman-Identifikation von geschlossenem Kreis und Strecke bei bekanntem Regler | setzt bekannten, festen Regler voraus | ChATCo ist adaptiv und sättigt (E1.3); hier DoE statt Reglerwissen |
| Løvland, Imsland, Grimstad 2025, `lovlandClosedloopIdentificationChallenge2025` | 4 | Theorie, Beispiel | Schätzung aus CL-Daten ohne Sollwertanregung strebt gegen −K⁻¹ | keine sparse oder Koopman-Modelle | Reglerinversionstest (Idee A13) überträgt die Aussage auf den PI-Regler |
| „MPC closed-loop identification without excitation“ 2021 (J. Process Control, Autoren offen) | 3 | Prozess (laut Abstract) | Umschalten der Eingangsgewichtung im MPC macht CL-Daten informativ | kein betrieblicher Betriebsartenwechsel, keine nichtlinearen Bibliotheken | hier ungeplanter Wechsel Diesel → Gas als mögliche Anregung, konfundiert mit Brennstoff und Niveau |
| Grasev 2026 | 2 | siehe (b) | siehe (b) | siehe (b) | siehe (b) |

#### Weitere, entferntere Treffer (nur als Randanker)
- Koopman-MPC im Fahrzeug-Thermomanagement mit Simulationsdaten: Pan, Li 2023 (J. Dyn. Syst. Meas. Control 145(5), 051005); Control Eng. Pract. 2025 zum integrierten Thermomanagement (Autoren offen); Meda u. a. 2025/2026 (`medaKoopmanBasedMethodsEV2025`, J. Dyn. Syst. Meas. Control 148(1)).
- SINDy-MPC in der Verfahrenstechnik: Abdullah, Wu, Christofides 2021 (Zwei-Zeitskalen-Prozesse, Comput. Chem. Eng. 153); Übersicht Abdullah, Christofides 2023 (Comput. Chem. Eng. 174).
- LPV- und Mehrschrittprädiktoren: Verhoek, Abbas, Tóth, Haesaert 2021 (datengetriebene prädiktive Regelung für LPV-Systeme); Shi u. a. 2023 (qLPV-MPC für ORC-Abwärmenutzung, Energy 271).
- Modellklassenvergleich an einer Anlage: arXiv-Preprint 2605.18720 (N4SID, SINDYc, ARX am Kontinuumsroboter, Autoren offen); Raffa Ugolini u. a. 2024 (SINDy gegen harte Nichtlinearitäten, Benchmark).
- † Schiffskühlkreise mit PID und Vorsteuerung (Jeon, Jung u. a. 2021–2025, JMSE; Übertragungsfunktionen aus Betriebsdaten, CL-Verzerrung im Abstract nicht erkennbar) und † SINDy an einem hysteresegeregelten Pumpensystem mit Zweipunktregler in der Bibliothek (arXiv 2003.07465, Autorenzuordnung uneindeutig).

### E2.3 Leerbefunde und Suchwege

- Geltungsbereich: WebSearch-Auszüge am 25.09.2026, keine Datenbank (Scopus, Web of Science, Google Scholar), kein Volltext, Zotero-Stand der Arbeit laut ch3 Z. 1018–1029. Ein Leerbefund heißt „in diesem Suchweg nicht gefunden“, nicht „existiert nicht“. Formulierung in der Arbeit entsprechend: „In der gesichteten Literatur … nicht gefunden“.
- Suchläufe: BL (Beitragslücken, 25 Anfragen), V1 (Ladeluft/Kühler datengetrieben, 22), V2 (SINDy an Motoren und thermischen Anlagen, 22), V3n (Koopman/DMDc-MPC mit Messdaten, 25), V4n (Großmotor- und Schiffskühlkreise, 25), V5/V5n (CL-Identifikation mit SINDy/Koopman, 6 + 23), V6/V6n (LTV/LPV-MPC, Gain als Kriterium, 3 + 12). Die ersten Läufe V3, V4 und Teile von V5, V6 brachen am gemeinsamen Suchbudget ab und wurden als V3n bis V6n wiederholt.

| Lücke (Beitrag aus E2.1) | Suchweg (Beispiele der Anfragen) | Befund | Stärke |
|---|---|---|---|
| Datengetriebenes Dynamikmodell der Ladelufttemperatur eines Groß-, Gas- oder DF-Motors aus Messdaten, für MPC (BT3) | V1: 22 Anfragen, u. a. „charge air cooler outlet temperature data-driven model engine identification“, „intake manifold temperature prediction neural network“, IEEE/SAE/MDPI-Filter, deutsch „Ladelufttemperatur Regelung Gasmotor Modell Identifikation“; V4n Anfragen 1, 7, 21 | keine Arbeit 2019–2026; nur Vagapov 2022/2024 (Pkw), Beran 2021 (Simulation), JMSE 2026 (Simulation), Patente | mittel (zwei unabhängige Läufe) |
| SINDy/SINDYc mit Ladelufttemperatur oder Ladeluftkühler (BT3) | BL Anfr. 1, 20; V2 Anfragen 3, 12, 13, 20; V5n Anfrage 16 | keine; SINDy am Motor nur Diesel-Luftpfad der Yahagi-Gruppe (Simulation) und Triebwerke (Paniccia 2025, Grasev 2026) | mittel |
| Physikalisch motivierte SINDy-Bibliothek (Temperaturdifferenz × Betriebspunktfaktor) an realen Wärmeübertragerdaten (BT3) | BL Anfr. 18; V5n Anfragen 2, 9, 23 („sparse identification nonlinear dynamics heat exchanger experimental data“, „physics-informed SINDy library thermal system measured data“) | keine; nächste Treffer Diskrepanzlernen am Wärmeübertragernetz (IFAC 2024, Greybox-Korrektur), CNN-Blackbox, PINN-Arbeiten | mittel |
| Stellgröße × ausschließlich exogene Temperaturdifferenz als LTV-QP (BT1) | BL Anfr. 4, 14, 16, 23; V6n Anfragen 3, 6, 9 („linear parameter-varying MPC heat exchanger outlet temperature scheduling measured inlet temperature flow rate convex QP“) | keine; gefunden nur Bilinearität über den Zustand (Pan, Li 2024 mit McCormick-Konvexifizierung; Ripa u. a. 2025), qLPV mit Zustandsscheduling (Cisneros u. a. 2020; Shi u. a. 2023) | mittel; Volltexte von Cisneros 2020 und Shi 2023 prüfen, ob Scheduling nur über exogene Größen möglich ist |
| SINDy/SINDYc aus CL-Daten mit Bias-, IV- oder Informativitätsanalyse (BT2) | BL Anfr. 6, 24; V5n Anfragen 1, 5, 7, 10, 17 („SINDy closed-loop data feedback identification bias sparse regression“, EDMD + instrumental variables) | keine für SINDy; für EDMDc nur Wu 2026 (Preprint, Theorie); für DMD nur Messrausch-Bias ohne Rückführung | mittel bis stark |
| Abgleich einer CL-Schätzung gegen offene Sprungversuche derselben Anlage (BT2) | BL Anfr. 24; V5n | keine SINDy- oder Koopman-Arbeit; klassische CL-Identifikation unter MPC (Esmaili u. a. 2017) ohne diesen Abgleich im Abstract | schwach bis mittel |
| Betrieblicher Betriebsartenwechsel als Anregung (BT2) | BL Anfr. 9, 17 | keine; nur geplante MPC-Gewichtsumschaltung (J. Process Control 2021) | schwach |
| Ventil-Gain gegen Sprungversuch als eigenes Bewertungskriterium bei SINDy/Koopman (BT4) | BL Anfr. 12, 19, 25; V6n Anfrage 1 („identification for control steady-state gain“) | keine für SINDy/Koopman; in der Prozessregelung ist Gain-Fehlanpassung als MPC-Gütegröße etabliert (Tufa, Ka 2016; Badwe u. a. 2009) | mittel; Gegenbeispiele ehrlich nennen |
| Vergleich ARX/SINDYc/EDMDc an einer thermischen Industriestrecke auf gleichen Daten (BT5) | BL Anfr. 8, 10 | kein Treffer an thermischer Industrieanlage; Vergleiche an Roboter (arXiv 2605.18720), Pasteurisierung (DeePC gegen Koopman, Daráš u. a. 2026), Wärmeübertrager (Koopman gegen linear, Valábek u. a. 2026) | schwach |
| Koopman/EDMDc-MPC an Hubkolbenmotoren mit Prüfstands- oder Felddaten | V3n Anfragen 9, 12, 21 | keine; nur Yahagi 2026 (Prädiktion, noch kein Regler) und Triebwerke | mittel |
| MPC der Ladelufttemperatur an mittelschnelllaufenden Gas-/DF-Motoren; CIMAC-Beiträge | V4n Anfragen 1, 4, 9, 17, 21, 24 (CIMAC-Domains) | keine; CIMAC-2025-Beitrag 308 (Ladungstemperatur im Methanol-DF-Kontext) nur ohne Titel gesehen | schwach (CIMAC-Archiv nicht durchsuchbar) |
| Einfluss der Ladelufttemperatur auf Klopfen und Methanschlupf an mittelschnelllaufenden Gas-/DF-Motoren | V4n Anfragen 3, 6, 15 | keine Studie mit Ladelufttemperatur als Variationsgröße; nur Lambda-, AGR-, Einspritzstudien | schwach |

- Nicht mehr durchführbar (Suchbudget der Sitzung erschöpft): zweite Prüfung der 33 Quellen aus V3n bis V6n; gezielte Suche nach SINDYc-MPC an HVAC-Wärmeübertragern; deutsche Anfragen zu modellprädiktiver Ladelufttemperaturregelung mit Mischventil.

## E3 Ideen mit Mehrwert, priorisiert

### E3.0 Lesehilfe

- IDs nach Kategorie: **A** Analyse, **B** Abbildung, **D** Diskussion/Ausblick, **S** methodische Absicherung. E1.4 und E4 verweisen auf diese IDs.
- **Nutzen N** (eigene Schätzung, 1–5): 5 = schließt eine absehbare Gutachterfrage zu K3/K4 oder macht einen Beitrag aus E2 erst belastbar; 4 = hebt K4, K5 oder K6 spürbar; 3 = Abrundung, Diskussionstiefe, K7; 2 = nur falls Zeit bleibt.
- **Aufwand**: nach der oberen Stundengrenze S bis 6 h, M bis 12 h, L darüber; Stunden grob, ohne Einarbeitung in neue Werkzeuge und ohne Rechenzeit.
- **Reihenfolge**: Rang 1–5 = empfohlene Top 5 (größte Hebel laut Auftrag: K3, K4, K6, jeweils Aufwand S). Ab Rang 6 streng nach N je Stunde (N geteilt durch Stundenmitte), bei Gleichstand höheres N zuerst. Ideen, die Ergebnisse anderer brauchen, stehen direkt hinter diesen.
- **Daten**: „nein“ = ohne Messdaten machbar; „vorhanden“ = mit den vorhandenen Prüfstands- und Felddaten, ohne neue Messung.
- Alle Ideen liefern nur das Verfahren. Kennwerte, Schwellen und Ergebnisse kommen aus Thomas' Daten; hier steht keine Zahl zur Modellgüte.
- Harte Grenzen eingehalten: keine neue Prüfstandsmessung; Stellglied nur das HP-Ventil (\valveCA); `T_LTCW` und `T_HTCW` nur als Störgrößen; MPC bleibt lineares QP. Was bis 19.10.2026 nicht machbar ist, steht in E3.4.
- Literaturanker: `key` = Key schon in der Arbeit; „Autor Jahr“ = neue Quelle, Metadaten in der Quellenliste, Status höchstens [nur Abstract].

### E3.1 Top 5

**1. S1 Korrekturpaket ch2/ch3** · K3, K7 · S, 4–6 h · Daten: nein · N5
- Kurz: alle Befunde aus E1.1 (K3, K7), E1.2 (Gleichungen) und E1.3 (Zitate „nicht gestützt“ oder „Metadaten fraglich“) in einem Durchgang abarbeiten.
- Reihenfolge nach Fehlerwirkung: Reglervorzeichen (ch2 Z. 1048–1056, ch3 Z. 786–787); bilinear und „Verlust des QP“ (ch3 Z. 360–366); map-Form (ch3 Z. 529–548); Ableitung gegen null (ch3 Z. 143–147); zweistufige Gain-Gleichung (ch2 Z. 796–802); Sollwertlage und Taupunkt (ch2 Z. 89–114); Zitatzuordnungen (OASIS/OASIS-P, EMEC-SINDy, Beran, Korda/Mezić).
- Danach Aufräumen: „Copilot:“-Überschriften im Satz (ch2 Z. 322, 469, 497, 581, 633, 761, 806, 888, 985; ch3 Z. 1041, 1178), Entwurfsreste (ch3 Z. 757–775, 625, 218, 506), Bündel → Stufe (ch2 Z. 184–185), doppelt belegte Symbole, verwaiste Labels.
- Artefakt: Änderungsliste mit Zeilenbezug, danach ein Satzlauf ohne Warnungen zu undefinierten Referenzen.
- Anker: keine neue Literatur; korrigierte Metadaten aus E1.3 und der Quellenliste.
- Risiko: Zeilenangaben beziehen sich auf die Kopie vom 25.09.2026. Korrekturen, die auf eigener Algebra beruhen (E1.2), vor Übernahme selbst nachrechnen.

**2. A2 + B1 Konfundierung als Zahl und als Bild** · K4, K3, K5 · S, 3–5 h (A2) plus 2–4 h (B1) · Daten: vorhanden · N5
- A2: Für jede Bibliothek (\sindyc-Terme, ARX-Regressor, \edmdc nur die \valveCA-Spalten) die spaltenskalierte Matrix Θ per SVD zerlegen: Konditionsindizes und Varianzzerlegungsanteile je Koeffizient nach Belsley, Kuh, Welsch 1980; dazu VIF_j = 1/(1 − R_j²) mit dem multiplen R_j² jeder \valveCA-Spalte gegen alle übrigen Spalten.
- Getrennt für Prüfstand mit DoE, Prüfstand geregelt, Feld Gasbetrieb. Dieselbe Skalierung wie im Schätzer (ch3 Z. 126–141).
- Brücke zum Konfundierungsmaß der Arbeit (ch3 Z. 885–889): Das Bestimmtheitsmaß von \valveCA gegen die Last erfasst nur einen Eingang des Kennfelds; der zweite (`r − T_LTCW`, ch2 Z. 270–274) steckt in den Temperaturdifferenz-Spalten. Das multiple R_j² ist das passende Maß. Eigene Überlegung: Liegt die Last (oder \mrel) selbst im Spaltenraum, ist ihr einfaches R² eine untere Schranke für R_j².
- Termauswahl: Bei korrelierten Spalten wird auch die Auswahl unzuverlässig, nicht nur der Wert (Irrepresentable Condition, Zhao & Yu 2006, für Lasso formuliert; Übertragung auf STLSQ als eigene Folgerung kennzeichnen).
- B1: Streubild \valveCA über Last oder \mrel; Feld als graue Dichte, Prüfstand geregelt blau, DoE-Sprünge als eigene Marker; Dieselabschnitte (Sättigung) und Preheating getrennt. Zweites Feld: Residuum \valveCA minus Kennfeldfit als Histogramm, also der von der Vorsteuerung unabhängige Stellanteil. Zeigt ohne Formel, dass Felddaten auf einer Kurve liegen und die DoE die Fläche füllt.
- Artefakt: Tabelle Konditionsindex/Varianzanteile/VIF je Datensatz, ein Bild mit zwei Feldern.
- Anker: Belsley, Kuh, Welsch 1980 (liefert den fehlenden Beleg für VIF in ch3 Z. 113–114); Zhao & Yu 2006; `geversIdentificationInformationMatrix2009` (Key vorhanden).
- Risiko: Konditionsindizes hängen von Skalierung und Zentrierung ab (Wahl festschreiben). Kennfeldinhalte sind Firmeninterna: nur normierte Achsen und aus Daten gefittete Zusammenhänge zeigen. Nach Sparsifizierung ändert sich Θ, deshalb volle und reduzierte Bibliothek zeigen.

**3. A3 Residuentests je Modell** · K4, K3, K6 · S, 3–5 h · Daten: vorhanden · N5
- Einschrittresiduen von ARX, \sindyc und \edmdc auf Testdaten: Autokorrelation mit Band ±1,96/√N und Portmanteau-Test (Ljung & Box 1978).
- Kreuzkorrelation Residuum gegen \valveCA, \Tin, \TLT, \mrel. Im geschlossenen Kreis ist die Korrelation bei Verschiebungen, in denen das Residuum der Stellgröße vorausläuft, auch beim richtigen Modell ungleich null; nur die Richtung „Eingang läuft voraus“ prüft das Modell. Test gegen \valveCA zusätzlich auf DoE-Abschnitten rechnen.
- Nichtlineare Korrelationstests nach Billings & Voon 1986 (Korrelationen mit quadrierten Residuen und Eingängen), höherer Ordnung nach Billings & Zhu 1994: Hinweis auf fehlende Bibliotheksterme, z. B. `\mrel·(\Tin − \TLT)`.
- Einschritt- und Freilaufresiduen nicht mischen (Freilauffehler sind per Konstruktion nicht weiß). Bei kontinuierlichem \sindyc Residuen der Ableitung und der Temperatur trennen.
- Schließt die Lücke, die ch3 Z. 1024–1029 selbst benennt (gesichtete SINDy-/Koopman-Arbeiten prüfen Residuen nicht), mit eigener Auswertung. Zugleich Antwort auf F9.
- Artefakt: je Modell ein 2×2-Bild (ACF, CCF \valveCA, CCF \Tin, nichtlinearer Test), Tabelle mit Ljung-Box-Statistik und größtem Korrelationsbetrag als Effektgröße.
- Anker: Billings & Voon 1986; Billings & Zhu 1994; Ljung & Box 1978; `ljungSystemIdentificationTheory1999` (Key vorhanden, Kapitel zur Residuenanalyse am Original prüfen); zur Gültigkeit im geschlossenen Kreis Douma u. a. 2008 (Metadaten korrigiert, Quellenliste).
- Risiko: Bei großem N lehnt fast jeder Test ab; deshalb Effektgröße berichten und auf dem Modelltakt rechnen. Ergebnis kann alle Modelle als nicht weiß ausweisen; das ist ein Befund, keine Niederlage.

**4. S2 QP-Brücke im Methodikteil** · K4, K5, K1 · S, 4–6 h · Daten: nein · N5
- Prädiktor mit Störgrößen ausschreiben: `x_{k+1} = A(d_k) x_k + B(d_k) u_k + E(d_k)`, `d_k = (\Tin, \TLT, \THT, \mrel)`; je Modellklasse zeigen, wie daraus der Prädiktor entsteht (ARX als Zustandsraum, \edmdc mit Störgrößen als exogenen Eingängen, \sindyc diskretisiert im MPC-Takt).
- Bedingungen, unter denen die Vorhersage über den Horizont affin in der Stellfolge ist (E1.1 K1, eigene Algebra): (a) \Tout nur mit exogenen Faktoren multipliziert; (b) Rate unabhängig von \valveCA; (c) `g(\valveCA)` linear oder virtuelle Stellgröße `v = g(u)` mit monotoner Rücktransformation; (d) Störgrößen über den Horizont vorgegeben.
- Nebenbedingungen ergänzen, alle linear: `|Δu_k| ≤ Δu_max`, `Δu_k = 0` für `k ≥ N_u`, weiche Obergrenze `y_k ≤ y_max + s_k`; Transporttotzeit als ganzzahlige Eingangsverschiebung. Umkehrspiel des Antriebs ist nicht LTI, als Robustheitsfrage führen.
- Offsetfreie Erweiterung konkret: Störmodell (Ausgangs- oder Eingangsstörung), erweitertes System, Rangbedingung `rank[[I − A, −B_d], [C, C_d]] = n + n_d` mit `n_d ≤` Zahl der Messgrößen (hier eins), stationäres Kalman-Filter mit `Q`, `R`. Für Henning: Beim reinen Ausgangsstörmodell mit Random-Walk-Störung und weißem Messrauschen entspricht das stationäre Kalman-Filter einer exponentiellen Glättung (Muth 1960 zur Optimalität der exponentiellen Glättung; Übertragung auf den Beobachter als eigene Deutung kennzeichnen).
- Schlupfstrafe prüfen: rein quadratische Strafe lässt kleine Verletzungen zu; ein zusätzlicher linearer Term mit `s ≥ 0` bleibt QP (Kerrigan & Maciejowski 2000 zur exakten Straffunktion; Übertragung als eigene Folgerung kennzeichnen).
- Beantwortet F1, F2, F6 vorab; macht Beitrag BT1 aus E2.1 prüfbar.
- Anker: `pannocchiaDisturbanceModelsOffsetfree2003`, `muskeDisturbanceModelingOffsetfree2002`, `maederLinearOffsetfreeModel2009`, `rawlingsModelPredictiveControl20202020` (Keys vorhanden); Pannocchia, Gabiccini, Artoni 2015 (Übersicht offsetfreie MPC); Maciejowski 2002 (Ratenbeschränkung); Muth 1960; Kerrigan & Maciejowski 2000.
- Risiko: Überschneidung mit dem geplanten MPC-Methodikabschnitt; dort einbauen statt verdoppeln. Rangbedingung und Muth-Aussage stammen nicht aus einem in dieser Werkbank gelesenen Volltext, Copilot prüft am Original.

**5. D1 Beitragsliste und Abgrenzung in ch3** · K6, K5 · S, 2–3 h · Daten: nein · N5
- Formulierungen BT1–BT3 aus E2.1 als Hauptbeiträge, BT4 als Bewertungsbeitrag innerhalb von BT2, BT5 als methodische Sorgfalt; ersetzt ch3 Z. 1196–1197 („Der eigene Beitrag liegt in ihrer nachvollziehbaren Umsetzung und Prüfung“).
- Eigenleistungen, die heute unmarkiert im Stand der Technik stehen (ch3 Z. 877–925: Konfundierungsmaß, Dreiteilung Niveau/Dynamik/Stellwirkung), in den Methodikteil verschieben oder als eigene Festlegung kennzeichnen (E1.1 K6).
- Nächste Verwandte aus E2.2 als Abgrenzungstabelle übernehmen (nach Copilot-Prüfung).
- Artefakt: Beitragsabsatz mit drei bis fünf Punkten, Abgrenzungstabelle.
- Anker: E2.1 und E2.2.
- Risiko: Beiträge dürfen nicht mehr versprechen als Kap. 5–7 zeigen; Formulierung erst nach den Ergebnissen festziehen („zeigt“ nur bei erfüllter Voraussetzung, sonst „prüft“).

### E3.2 Gesamttabelle

| Rang | ID | Idee | Kategorie | Kriterien | Aufwand | Daten | N | braucht |
|---|---|---|---|---|---|---|---|---|
| 1 | S1 | Korrekturpaket ch2/ch3 | Absicherung | 3, 7 | S 4–6 h | nein | 5 | – |
| 2 | A2 | Konfundierungsdiagnose (multiples R², VIF, Belsley) | Analyse | 3, 4, 5 | S 3–5 h | vorhanden | 5 | – |
| 2 | B1 | Streubild \valveCA über Last, Feld gegen DoE | Abbildung | 4, 5, 7 | S 2–4 h | vorhanden | 5 | mit A2 |
| 3 | A3 | Residuentests je Modell | Analyse | 3, 4, 6 | S 3–5 h | vorhanden | 5 | – |
| 4 | S2 | QP-Brücke: Prädiktor, Nebenbedingungen, Beobachter | Absicherung | 1, 4, 5 | S 4–6 h | nein | 5 | – |
| 5 | D1 | Beitragsliste und Abgrenzung | Diskussion | 5, 6 | S 2–3 h | nein | 5 | E2 |
| 6 | S3 | Datenvertrag und Leakage-Prüfung | Absicherung | 3, 4, 7 | S 3–5 h (ohne Neurechnung) | vorhanden | 5 | – |
| 7 | D3 | Übertragbarkeit auf die 51/60DF-Flotte (Diskussion) | Diskussion | 2, 5, 6 | S 2–3 h | nein | 3 | – |
| 8 | D4 | Fouling als langsame Parameterdrift (Diskussion) | Diskussion | 4, 5 | S 2–3 h | nein | 3 | – |
| 9 | A1 | Ventil-Gain-Karte mit Band und DoE-Überdeckung | Analyse | 3, 4, 5, 6 | S 4–6 h | vorhanden | 5 | – |
| 10 | A7 | Gain-Toleranz des MPC (Grundversion) | Analyse | 1, 4, 6 | S 4–6 h | vorhanden | 5 | S2, A1 |
| 11 | A13 | CL-Bias-Diagnose Stufe 1: Reglerinversion, Instrumentstärke | Analyse | 4, 5, 6 | S 4–6 h | vorhanden | 5 | Reglerparameter |
| 12 | A5 | k-Schritt-Fehler über den MPC-Horizont | Analyse | 1, 4, 5 | S 3–5 h | vorhanden | 4 | – |
| 13 | B3 | Ampelmatrix Niveau/Dynamik/Stellwirkung | Abbildung | 1, 4, 5, 7 | S 2–4 h | vorhanden | 4 | A1, A3, A5 |
| 14 | B2 | Blockschaltbild mit zwei Fehlerpfaden | Abbildung | 4, 5, 7 | S 3–5 h | nein | 4 | – |
| 15 | A12 | FROLS/ERR gegen STLSQ auf derselben Bibliothek | Analyse | 4, 5 | S 3–5 h | vorhanden | 4 | – |
| 16 | D2 | Niveau- gegen Gain-Fehler im offsetfreien MPC | Diskussion | 3, 4, 5 | S 3–5 h | nein | 4 | S2 |
| 17 | S6 | Placebo-Test und Plausibilität des Ventil-Gains | Absicherung | 3, 4, 6 | S 3–5 h | vorhanden | 4 | A1 |
| 18 | A6 | Kennfeld-Schranke des stationären Ventil-Gains | Analyse | 5, 6 | S 2–4 h | vorhanden (Kennfeld) | 3 | – |
| 19 | B7 | Modellfamilien-Landkarte über den LSQ-Kern | Abbildung | 4, 5, 7 | S 2–4 h | nein | 3 | – |
| 20 | S4 | Gepaarter Modellvergleich (Block-Bootstrap, Diebold-Mariano) | Absicherung | 3, 4, 7 | S 3–6 h | vorhanden | 4 | S3 |
| 21 | D10 | Stufenleiter LTV-QP bis NMPC (Ausblicktabelle) | Diskussion | 4, 5, 6 | S 3–4 h | nein | 3 | S2 |
| 22 | A9 | Totzeit aus DoE-Sprüngen | Analyse | 3, 4, 5 | S 4–6 h | vorhanden | 4 | – |
| 23 | D5 | Rechenzeit und QP-Größe | Diskussion | 1, 5, 7 | S 3–5 h | nein | 3 | S2 |
| 24 | A14 | Proxy-Sensitivität \mrel, q_rel, Last | Analyse | 3, 4, 5 | S 3–5 h | vorhanden | 3 | S4 |
| 25 | B6 | Pareto-Front Sparsität gegen Freilauffehler | Abbildung | 2, 4, 5 | S 3–5 h | vorhanden | 3 | – |
| 26 | A8 | Wert der Störgrößenvorschau im MPC | Analyse | 3, 4, 6 | M 4–7 h | vorhanden | 4 | S2 |
| 27 | S5 | Stabilitäts- und Ruhelagenprüfung | Absicherung | 1, 3, 4 | M 4–8 h | vorhanden | 4 | – |
| 28 | D11 | Weitere Betriebsart, Methanol (E4: M1, M2, M4) | Diskussion | 1, 5, 6 | S 2–4 h | nein | 2 | – |
| 29 | D6 | Gültigkeitsbereich überwachen, Rückfall auf ChATCo | Diskussion | 3, 5, 6 | S 4–6 h | vorhanden | 3 | – |
| 30 | B4 | \|S\| über Periodendauer mit Störspektren | Abbildung | 4, 5, 6 | M 4–7 h | vorhanden | 3 | Reglerparameter |
| 31 | D8 | Mindestanregung (Dither) aus DoE-Daten | Diskussion | 2, 4, 5, 6 | M 6–10 h | vorhanden | 4 | – |
| 32 | B5 | Datenlandkarte mit gleitender Konditionszahl | Abbildung | 2, 4, 7 | M 6–10 h | vorhanden | 4 | S3 |
| 33 | A15 | Abtastzeit-Sensitivität | Analyse | 4, 5, 6 | M 5–8 h | vorhanden | 3 | A9 |
| 34 | A16 | Sensorbias-Sensitivität (Errors-in-Variables) | Analyse | 3, 4, 5 | M 5–8 h | vorhanden | 3 | – |
| 35 | D7 | Back-off an Taupunkt und Derating | Diskussion | 3, 5, 6 | M 5–8 h | vorhanden | 3 | A5 |
| 36 | A4 | Termstabilität und Koeffizientenintervalle (Block-Bootstrap) | Analyse | 3, 4, 6 | M 8–12 h | vorhanden | 4 | S3 |
| 37 | A10 | Physikalische Referenz als Nullmodell | Analyse | 3, 4, 5 | M 8–12 h | vorhanden | 4 | – |
| 38 | A11 | Twin-Experiment: Auswertekette mit bekannter Wahrheit | Analyse | 4, 5, 6 | M 8–12 h | nein | 4 | – |
| 39 | D9 | Online-Nachführung als RLS-Replay | Diskussion | 4, 5, 6 | M 6–10 h | vorhanden | 3 | – |
| 40 | A17 | Dieselabschnitte als Probe für andere Betriebsart (E4 M3) | Analyse | 2, 4, 6 | M 6–12 h | vorhanden | 3 | – |

- A13 Stufe 2 (IV gegen direkt, Hausman) kostet weitere 4 h und steht in E3.3 bei A13.
- Summe Top 5 rund 18–29 h; Rang 1–13 rund 42–67 h. Bis 19.10.2026 realistisch: Top 5 plus eine Auswahl aus Rang 6–13.

### E3.3 Steckbriefe ab Rang 6

**6. S3 Datenvertrag und Leakage-Prüfung** · K3, K4, K7 · S, 3–5 h ohne Neurechnung · vorhanden · N5
- Tabelle „Datenvertrag“: jeder Prüfstands- und Feldabschnitt (Versuchslauf, Betriebsart, Zeitraum) bekommt genau eine Rolle: Training, Auswahl oder Test. DoE-Ventilsprünge als Testsatz für den Ventil-Gain reservieren.
- Alle Hyperparameter (STLSQ-Schwelle, ARX-Ordnungen, Liftung, Filter, Totzeitverschiebung) nur auf Auswahldaten wählen; Test einmal am Ende. Wurde schon mit Testdaten gewählt, das offen als retrospektiv kennzeichnen (ch3 Z. 1188–1196).
- Aufteilung nur in zusammenhängenden Blöcken, an Blockgrenzen eine Lücke von mindestens Modellgedächtnis plus Totzeit (hv-block, Racine 2000); innerhalb der Auswahl geblockte Kreuzvalidierung (Bergmeir & Benítez 2012; Bergmeir, Hyndman, Koo 2018: gewöhnliche K-fold nur bei unkorrelierten Residuen, Verbindung zu A3).
- Leakage-Liste: Normierung nur mit Trainingsstatistik (ch3 Z. 126–139); nichtkausale Filter und zentrale Differenzen nicht über Blockgrenzen; Betriebsartenfilter vor der Aufteilung.
- Anker: Racine 2000; Bergmeir & Benítez 2012; Bergmeir, Hyndman, Koo 2018; Cawley & Talbot 2010 (Auswahlverzerrung durch Modellwahl).
- Risiko: Wenige DoE-Blöcke machen den Testsatz klein. Feldblöcke sind nicht stationär (Jahreszeit, `T_LTCW`-Niveau), nach Bedingungen schichten. Findet sich Leakage, kostet die Neurechnung zusätzlich M.

**7. D3 Übertragbarkeit auf die 51/60DF-Flotte** · K2, K5, K6 · S, 2–3 h als Diskussion; M 8–12 h mit Daten · N3
- Diskussion: Termstruktur übertragbar, Koeffizienten, Sollwert und Band nicht (51/60DF-Band laut ch2-Kommentar abweichend, ch2 Z. 114–126). Ventilkanal im Feld durch Vorsteuerung konfundiert, nur Niveau- und Störpfadterme vergleichbar.
- Mit Daten einer zweiten Baureihe (falls \Tin, \TLT, \THT, `Δp_HP` vorhanden): gleiche Pipeline, Termtabelle mit Vorzeichen und Ensemble-Streuung; Zahl nötiger Änderungen (Term hinzu, Term weg, Koeffizient neu) als Übertragbarkeitsmaß nach Quade u. a. 2018.
- Ausblick: gemeinsame Struktur über mehrere Motoren per Gruppen-Sparsamkeit mit motorabhängigen Koeffizienten (Rudy u. a. 2019).
- Anker: Quade u. a. 2018; Rudy u. a. 2019; `faselEnsembleSINDyRobustSparse2022` (Key vorhanden).
- Risiko: Andere Sensorlage oder fehlendes `Δp_HP` ändern die Definition von \mrel. Keine Aussagen zur Flotte über `kontext/` hinaus.

**8. D4 Fouling als langsame Parameterdrift** · K4, K5 · S, 2–3 h als Diskussion; M 4–8 h mit Trendanalyse · N3
- Wirkungskette aus der eigenen Herleitung: Verschmutzungswiderstand als Serienwiderstand in Gl. `eq.k.zusammensetzung` senkt kA, NTU und ε der betroffenen Stufe; bei gleicher Kühlerspanne steigt `T_stat`, `dε/du_HP` und der Ventil-Gain verschieben sich (Gl. `eq.grundlagen.gain.epsntu`).
- Luftseitige Verschmutzung erhöht `Δp_HP` bei gleichem Massenstrom; \mrel überschätzt dann den Durchsatz (Grenze in ch2 Z. 718–724 schon genannt).
- Einordnung: Niveauanteil fängt der offsetfreie Beobachter, Gain-Anteil nicht (Verbindung zu D2).
- Mit Daten über mehrere Monate: Residuum des festen Modells oder geschätzter Störzustand je Zeitabschnitt, nach Last- und Spannenklasse gruppiert.
- Anker: Jonsson u. a. 2007 (EKF-Parameterschätzung zur Fouling-Erkennung am Wärmeübertrager); Joshi u. a. 2009 (Ladeluftkühler-Zustand eines mittelschweren Diesels aus der Saugrohrtemperatur, nur als Prinzip); Patil, Theotokatos, Tsitsilonis 2025 (Fouling des Ladeluftkühlers als Fehlerfall, Modell- und Werksdaten eines Schiffsdiesels).
- Risiko: Ein Residuentrend ist nicht eindeutig Fouling (Sensordrift, Umgebung, Betriebsprofil). Keine Aussagen zur Wartungspraxis über `kontext/` hinaus.

**9. A1 Ventil-Gain-Karte mit Band und DoE-Überdeckung** · K3, K4, K5, K6 · S, 4–6 h · vorhanden · N5
- Stationären Gain `∂\Tout/∂\valveCA` aus jedem Modell auf einem Gitter (\mrel × Kühlerspanne `\Tin − \TLT`, `\THT` am Median) berechnen: \sindyc aus dem Gleichgewicht `f(y*, u, d) = 0` mit `dy*/du = −(∂f/∂u)/(∂f/∂y)`; ARX `B(1)/A(1)`; \edmdc `C(I − A)⁻¹B`. Konvention aus ch2 Z. 790–793 angeben (Sekante oder Steigung, Hubband, Arbeitspunkt, Festhaltebedingung).
- Band ohne Resampling über die Delta-Methode mit der LS-Kovarianz `σ²(ΘᵀΘ)⁻¹` (E1.1 K2); mit A4 später durch Bootstrap-Replikate ersetzen.
- DoE-Sekanten des Prüfstands an ihren Arbeitspunkten eintragen und auszählen, wie viele im Band liegen; Anteil mit plausiblem Vorzeichen berichten.
- Extrapolationsmaske über Hebelwerte `h = φᵀ(ΘᵀΘ)⁻¹φ`; Gitterpunkte ohne Datenstütze ausgrauen.
- Plausibilität gleich mitprüfen: Vorzeichen (negativ unter Festhaltebedingung, sofern ε mit dem Hub wächst), Betrag wächst mit der Spanne, fällt bei weit offenem Ventil (ε nahe 1).
- Aussage für das QP: reicht ein fester Stellkoeffizient oder muss er je Takt aus dem Betriebspunkt gesetzt werden (bekannter Koeffizient, QP bleibt linear)?
- Anker: `ljungSystemIdentificationTheory1999` (Key vorhanden, Kovarianz der Schätzung); Belsley, Kuh, Welsch 1980 (Hebelwerte); Bombois u. a. 2001 (Robustheitsanalyse über die Unsicherheitsmenge, nur Ausblick); `erikssonModelingControlEngines2014` (Key vorhanden).
- Risiko: Das Band enthält die Varianz, nicht den Rückführungs-Bias; Feldschätzungen können eng und trotzdem verschoben sein (DoE ist der Kontrollfall). Bei \edmdc mit Lift ist das Gleichgewicht nicht immer eindeutig; dann Gain aus der k-Schritt-Antwort mit fester Konvention. Wenige DoE-Punkte nur als Marker, nicht interpolieren.

**10. A7 Gain-Toleranz des MPC** · K1, K4, K6 · S, 4–6 h Grundversion; M 8–12 h erweitert · vorhanden · N5
- Grundversion: im vorhandenen CL-Simulationsaufbau Strecke = am DoE bestätigtes Modell, Reglermodell = dasselbe Modell mit skaliertem Ventilkoeffizienten (Faktorraster für Unter- und Überschätzung). Je Faktor die CL-Kennwerte der Arbeit; Beobachter, Horizont, Gewichte unverändert.
- Bild: CL-Kennwert über Gain-Verhältnis mit markiertem tragbarem Bereich; darin die in A1 gemessenen Gain-Abweichungen von ARX, \sindyc, \edmdc eintragen. Macht Beitrag BT4 aus E2.1 (Ventil-Gain als Kriterium) aus dem Verwendungszweck begründbar.
- Erweitert: zusätzlich Zeitkonstante und Totzeit skalieren; Kreuzsimulation (MPC auf Modell A, Strecke Modell B); Aktor in der Strecke (Ratenbegrenzung, Umkehrspiel, Sättigung, Takt 500 ms); Referenz ChATCo-Nachbau unter denselben Fehlern.
- Anker: Gevers 2005 (Identification for Control: Modellgüte am Verwendungszweck messen); Hjalmarsson 2005; Bemporad & Morari 1999; Tufa, Ka 2016 und Badwe u. a. 2009 (Modell-Strecken-Fehlanpassung im MPC, Metadaten korrigiert); `rawlingsModelPredictiveControl20202020` (Key vorhanden).
- Risiko: Die Strecke ist selbst ein Modell; Toleranzaussage relativ zu diesem Ersatz formulieren. Fällt die Toleranz sehr breit aus, verliert das Gain-Kriterium Gewicht; auch das ist ein verwertbarer Befund.

**11. A13 CL-Bias-Diagnose: Reglerinversion, Instrumentstärke, IV gegen direkt** · K4, K5, K6 · Stufe 1 S 4–6 h, Stufe 2 plus rund 4 h · vorhanden · N5
- Stufe 1: aus Felddaten geschätzten Frequenzgang des Stellkanals (lineare ARX-Referenz) gegen `−1/C(e^{jω})` des Serien-PI und gegen den Prüfstands-Frequenzgang aus der DoE legen. Grundlage: Grenzwert `−K⁻¹` bei verschwindender Sollwertanregung (`lovlandClosedloopIdentificationChallenge2025`); Übertragung auf den dynamischen PI-Regler ist eigene Überlegung.
- Eigene Folgerung prüfen: `−1/C` geht beim PI-Regler für `ω → 0` gegen null; ein kleiner stationärer Feld-Gain kann Reglerartefakt statt geringer Ventilautorität sein. Mit Reglervorzeichen aus S1 ist ein Feld-Gain mit falschem Vorzeichen ein Warnzeichen für dominierende Rückführung.
- Instrumentstärke: First-Stage-Regression von \valveCA auf den Modusindikator Diesel/Gas plus Störgrößen, F-Wert bzw. partielles R² (Staiger & Stock 1997). Nur der Übergang trägt Information, in der Dieselsättigung ist der Kanal nicht identifizierbar (ch3 Z. 891–897).
- Stufe 2: Ventilkoeffizient direkt (LS) und per IV/Zwei-Stufen schätzen, Differenz per Hausman-Vergleich (Hausman 1978) oder robuster per Block-Bootstrap; beide neben den DoE-Gain mit gleicher Konvention stellen.
- Anker: `lovlandClosedloopIdentificationChallenge2025`, `gilsonInstrumentalVariableMethods2005` (Keys vorhanden); Staiger & Stock 1997; Hausman 1978; Box & MacGregor 1974 (Analyse geschlossener Kreise).
- Risiko: Reglerparameter müssen vorliegen und dürfen nur soweit freigegeben genannt werden. Adaptive Kennfeldnachführung, Anti-Windup und Sättigung machen den Regler zeitvariant: Test als Diagnose, nicht als Beweis. Fällt der Moduswechsel mit Lastwechseln zusammen, ist das Instrument nicht exogen (E1.1 K4).

**12. A5 k-Schritt-Fehler über den MPC-Horizont** · K1, K4, K5 · S, 3–5 h · vorhanden · N4
- Je Modell den k-Schritt-Fehler für `k = 1 … N` (Horizont aus dem Methodikkapitel) auf Testdaten, gestartet aus gemessenem Zustand; Freilauf als Grenzfall, Einschrittfehler nur als Nebenkennwert.
- Zwei Informationsannahmen: (a) aufgezeichnete zukünftige Störgrößen (Orakel, ch3 Z. 1202–1204), (b) letzter Messwert über den Horizont gehalten. Der Abstand zeigt den Wert einer Störgrößenprognose (Übergang zu A8).
- Prüfen, ob sich die Kurven der Modelle kreuzen; dann ist die Modellwahl horizontabhängig.
- Optional: λ und Ordnungen auf Auswahldaten nach Simulations- oder Mehrschrittfehler wählen (Antwort auf F8).
- Anker: Piroddi & Spinelli 2003 (Simulationsfehler als Auswahlkriterium bei NARX); Gopaluni, Patwardhan, Shah 2004 (MPC-relevante Identifikation, Mehrschrittkriterium; Jahr korrigiert); Shook, Mohtadi, Shah 1991/1992 (Metadaten korrigiert, Quellenliste); `manganModelSelectionDynamical2017` (Key vorhanden).
- Risiko: Ohne Beobachter unterschätzt die Kurve, was der offsetfreie MPC korrigiert; in der Bildunterschrift sagen. Instabile Modelle divergieren im Freilauf (mit S5 koppeln).

**13. B3 Ampelmatrix Niveau/Dynamik/Stellwirkung** · K1, K4, K5, K7 · S, 2–4 h · vorhanden · N4 · nach A1, A3, A5
- Zeilen: ARX, \edmdc-Varianten, \sindyc-Varianten; Spaltengruppen Niveau, Dynamik, Stellwirkung, jeweils unter OL, CL, DoE-Validierung, Ventil-Gain.
- Ampel nach Schwellen, die vor der Auswertung im Methodikkapitel stehen; Kennzahl klein in der Zelle; grau = nicht prüfbar (z. B. Stellwirkung aus Feldabschnitten in Sättigung). Farbe plus Symbol für Graustufendruck.
- Synthesebild für das Ergebniskapitel: zeigt die Dreiteilung aus ch3 Z. 907–925 und dass gute OL-Güte keine richtige Stellwirkung garantiert.
- Anker: `ljungSystemIdentificationTheory1999`; `rupprechtAnalysisSimulationOptimisation2016` (Keys vorhanden, getrennte Prüfung von Temperatur und Stellsignal).
- Risiko: Nachträglich verschobene Schwellen wären Rückschaufehler; Schwellen datiert festschreiben. Zahlen im Anhang als Tabelle mitführen.

**14. B2 Blockschaltbild mit zwei Fehlerpfaden** · K4, K5, K7 · S, 3–5 h · nein · N4
- Blöcke: ChATCo (Kennfeld-Vorsteuerung plus PI mit Anti-Windup, 500 ms), Ventilantrieb mit Ratenbegrenzung, Strecke (HP-Kühler mit HT- und LT-Stufe), Störübertragung; Störgrößen \Tin, \TLT, \THT, \mrel; Messgröße \Tout.
- Pfad A (Farbe 1): Rauschen → \Tout → PI → \valveCA, der Kreuzterm der Bias-Gleichung (Rückkopplungsfall). Pfad B (Farbe 2): Last → Vorsteuerung → \valveCA und parallel Last → \Tin/\mrel → Strecke, die schlecht konditionierte Informationsmatrix (Vorsteuerungsfall).
- Zusatzmarken: Schalter „Sättigung“ unterbricht Pfad A; additiver Eingang für DoE-Sprünge; Modussprung als exogene Umschaltung. Legende verweist auf die Terme von Gl. `eq.grundlagen.cl.bias`.
- Erweitert den vorhandenen Bildvorschlag (ch3 Z. 650–651) statt ein zweites Bild zu erzeugen.
- Anker: `forssellClosedloopIdenticationRevisited1999`, `ljungSystemIdentificationTheory1999` (Abschn. 13.4), `proctorGeneralizingKoopmanTheory2018` (Keys vorhanden).
- Risiko: Überladung; höchstens zwei Signalfarben plus Grau. Stil wie die TikZ-Bilder in ch2 (abbBlau/abbGrau). Keine Kennfeldinhalte.

**15. A12 FROLS/ERR gegen STLSQ auf derselben Bibliothek** · K4, K5 · S, 3–5 h · vorhanden · N4
- Auf der physikalisch motivierten Bibliothek die Termauswahl einmal per Forward-Regression mit orthogonaler Zerlegung und Error Reduction Ratio (Chen, Billings, Luo 1989) und einmal per STLSQ; gleiche Daten, gleiches Lernziel.
- Vergleichen: gewählte Terme, Reihenfolge der Aufnahme, OL-Fehler, Ventil-Gain. Stimmen die Terme überein, ist die Auswahl robust gegen das Verfahren; weichen sie ab, zeigt das die Rolle der Kollinearität (Verbindung zu A2).
- Beantwortet F7 (Merkel) mit einer eigenen Rechnung statt einer Behauptung.
- Anker: Chen, Billings, Luo 1989; Billings 2013 (NARMAX-Buch, Metadaten korrigiert); `bruntonDiscoveringGoverningEquations2016` (Key vorhanden).
- Risiko: FROLS-Implementierung selbst schreiben oder prüfen (kurze Schleife mit Gram-Schmidt). ERR ist bei korrelierten Spalten reihenfolgeabhängig; das gehört zum Befund.

**16. D2 Niveau- gegen Gain-Fehler im offsetfreien MPC** · K3, K4, K5 · S, 3–5 h · nein · N4 · nach S2
- Diskussion an die Dreiteilung knüpfen: Ein integrierender Störzustand gleicht einen konstanten Niveauversatz stationär aus; ein falscher Ventil-Gain bleibt in Prädiktion und Stellschrittgröße wirksam.
- Kurzer Nachweis im vorhandenen MPC: Fall A additiver Niveauversatz, Fall B multiplikativer Gain-Fehler; je ein Zeitverlauf \Tout und \valveCA.
- Für Henning: Störgrößenbeobachter als stationäres Kalman-Filter deuten; Ausblick Gain als Random-Walk-Parameter im erweiterten Kalman-Filter, nur mit Anregung sinnvoll (Verbindung zu D8).
- Anker: `pannocchiaDisturbanceModelsOffsetfree2003`, `muskeDisturbanceModelingOffsetfree2002`, `maederLinearOffsetfreeModel2009` (Keys vorhanden); Morari & Maeder 2012 (nichtlineare offsetfreie MPC).
- Risiko: Überschneidung mit S2; falls der Beobachter dort schon analysiert ist, nur die Zuordnung zur Dreiteilung ergänzen.

**17. S6 Placebo-Test und Plausibilität des Ventil-Gains** · K3, K4, K6 · S, 3–5 h · vorhanden · N4 · nach A1
- \valveCA innerhalb homogener Blöcke zyklisch um mehr als die Einschwingzeit verschieben oder blockweise permutieren, neu fitten. Bleibt ein Gain ähnlicher Größe, stammt er aus der Konfundierung mit der Last (Surrogatdaten-Logik: Nullhypothese erzeugen, Statistik vergleichen).
- Histogramm der Placebo-Gains mit dem echten Gain markiert; Tabelle Vorzeichenverletzungen aus A1.
- Anker: Theiler u. a. 1992 (Surrogatdaten); Gevers 2005; `loiseauConstrainedSparseGalerkin2018` (Key vorhanden, nur falls Vorzeichen als Nebenbedingung erzwungen wird).
- Risiko: Verschobenes \valveCA bleibt über langsame Trends mit Störgrößen korreliert, deshalb nur innerhalb homogener Blöcke. Ersetzt die DoE-Wahrheit nicht.

**18. A6 Kennfeld-Schranke des stationären Ventil-Gains** · K5, K6 · S, 2–4 h · vorhanden (Kennfeld) · N3
- Eigene Algebra (E1.1 K6, ungeprüft): Stationär gilt `r = T_stat(u, \TLT, …)` und `u = K(Last, r − \TLT)`. Mit `x = r − \TLT` und `∂T_stat/∂\TLT = ε_LT` folgt bei konvergiertem Kennfeld `∂T_stat/∂u · ∂K/∂x = ε_LT`, also `|∂T_stat/∂u| < 1/|∂K/∂x|`.
- Ein konvergiertes Serienkennfeld liefert damit eine Obergrenze des stationären Ventil-Gains aus Felddaten ohne neuen Versuch. Vergleich mit A1 und DoE als Plausibilitätsprüfung.
- Voraussetzungen offenlegen: Kennfeld auslesbar und konvergiert (Integralanteil des PI stationär nahe null), Linearisierungskurve berücksichtigt, \TLT exogen (E1.1 K4 zeigt, dass das nur näherungsweise gilt).
- Anker: keine Literatur; eigene Herleitung aus ch2 Z. 270–274 und Gl. `eq.Tout.stat`.
- Risiko: Kennfeld ist Firmeninternum; nur normierte Steigungen zeigen. Die Herleitung ist in dieser Werkbank nicht gegengeprüft; vor Übernahme selbst nachrechnen.

**19. B7 Modellfamilien-Landkarte über den LSQ-Kern** · K4, K5, K7 · S, 2–4 h · nein · N3
- Mitte Gl. `eq.lsq`; drei Spalten der Entwurfsentscheidungen: Merkmale Θ (verzögerte y, u / Temperaturdifferenz × Betriebspunktfaktor / Liftung mit Delays), Lernziel (`y_{k+1}` / Ableitung / gelifteter Folgezustand), Regularisierung (keine / STLSQ / Ridge). Jede gerechnete Variante als Pfad.
- Kanten für Grenzfälle: \edmdc auf Delay-Koordinaten = ARX (`bruntonModernKoopmanTheory2022` S. 305–306); SINDy als sparsifizierte NARX.
- Randspalte „QP-tauglich“ nach den Bedingungen aus S2.
- Macht Beitrag BT5 aus E2.1 (Ablation) als Bild sichtbar; ersetzt oder ergänzt fig.lsq.
- Anker: `bruntonModernKoopmanTheory2022`, `proctorDynamicModeDecomposition2016`, `kelmanBilinearModelPredictive2011` (Keys vorhanden).
- Risiko: Überschneidung mit fig.lsq und fig.sindyc.pipeline; eines davon ersetzen.

**20. S4 Gepaarter Modellvergleich** · K3, K4, K7 · S, 3–6 h · vorhanden · N4 · nach S3
- Fehlerkennwerte aller Modelle auf denselben Testblöcken; je Block die Differenz (gepaart, weil alle Modelle dieselben Störgrößenverläufe sehen).
- Intervall der Differenz per Moving-Block-Bootstrap (Künsch 1989) oder Stationary Bootstrap (Politis & Romano 1994); Blocklänge nach Politis & White 2004 mit Korrektur Patton, Politis, White 2009; zwei bis drei Blocklängen als Sensitivität. Bei unabhängigen Versuchsläufen auf Laufebene resamplen.
- Ergänzend Diebold-Mariano-Test auf die Verlustdifferenz (lässt serielle Korrelation zu).
- Für alle vier Bewertungsgrößen gleich: OL, CL, DoE-Validierung, Ventil-Gain-Fehler.
- Artefakt: Tabelle „Differenz mit 95-%-Intervall“; wo das Intervall null enthält, „Unterschied nicht aufgelöst“ schreiben.
- Anker: Künsch 1989; Politis & Romano 1994; Politis & White 2004; Diebold & Mariano 1995.
- Risiko: Wenige DoE-Blöcke ergeben breite Intervalle; das ist ehrlich. Der DM-Test ist für Prognosen formuliert, Übertragung im Text begründen.

**21. D10 Stufenleiter LTV-QP bis NMPC** · K4, K5, K6 · S, 3–4 h für die Ausblicktabelle · nein · N3
- Stufen: (1) lineares QP mit festem Gain; (2) LTV-QP: Spanne je Takt aus gemessenen oder eingefrorenen Störgrößen, Koeffizient von \valveCA bekannt, bleibt QP; (3) quasi-LPV-MPC mit Iteration (Cisneros, Voss, Werner 2016; Cisneros u. a. 2020 datengetrieben mit Koopman); (4) bilineares Koopman-Modell mit SQP (`bruderAdvantagesBilinearKoopman2021`, `kelmanBilinearModelPredictive2011`); (5) volles NMPC.
- Je Stufe: Anforderung an das Modell (Gain über dem Arbeitsbereich), Rechenaufwand, Verlust der Konvexität.
- Stufe 2 ist mit dem vorhandenen Produktterm ohne Messung simulierbar (M 10–15 h, eher nach der Abgabe); Stufen 3–5 nur Ausblick.
- Anker: Cisneros, Voss, Werner 2016; Cisneros u. a. 2020; Pan, Li 2024 (Koopman-Bilinearform mit NMPC an einer Kälteanlage); Falcone u. a. 2007 (sukzessive Linearisierung im MPC); Keys wie oben.
- Risiko: Stufen 3–5 verletzen die QP-Vorgabe und bleiben Ausblick.

**22. A9 Totzeit aus DoE-Sprüngen** · K3, K4, K5 · S, 4–6 h · vorhanden · N4
- \valveCA mit AR-Modell vorweißen, \Tout mit demselben Filter; Kreuzkorrelation als Impulsantwortschätzung, erste signifikante Verzögerung als Totzeit. Zweiter Schätzer: ARX-Verlust über `n_k`; dritter: Schwelle auf der Sprungantwort.
- Totzeit je Sprung über \mrel, Ausgangsstellung und Sprungrichtung: prüft die Verweilzeit-Hypothese `m_s/ṁ_L` (ch2 Z. 866–871) und den Einfluss des Richtungswechsels am Antrieb (ch2 Z. 263–268).
- Ergebnis: feste Totzeit für das MPC-Modell oder dokumentierte Bandbreite; Verhältnis Totzeit/Abtastzeit als Eingang für A15.
- Anker: Björklund & Ljung 2003; Shardt & Huang 2011 (Totzeit und Abtastzeit bei CL-Identifikation aus Routinedaten); `vagapovDynamicModelTemperature2022` (Key vorhanden).
- Risiko: Sensor-PT1 und thermische Speicher verschmieren die Totzeit; nur als scheinbare Totzeit bezeichnen. Wenige Sprünge je Arbeitspunkt ergeben breite Streuung.

**23. D5 Rechenzeit und QP-Größe** · K1, K5, K7 · S, 3–5 h · nein · N3
- QP-Dimension aus der eigenen Formulierung: `N_u` Stellschritte plus Schlupfvariablen, Zahl der Ungleichungen; bei skalarem \valveCA klein.
- Lösungszeit je Takt aus der CL-Simulation (Median, Maximum, Iterationen) dem 500-ms-Takt gegenüberstellen, als Rechnerangabe, nicht als Steuergerätezeit.
- Explizite MPC einordnen (stückweise affine Rückführung, kein Online-QP; Bemporad u. a. 2002); strukturausnutzende Online-Löser (Wang & Boyd 2010). Anschluss an `vagapovModellierungIdentifikationUnd2024` (Key vorhanden), wo die Rechenzeit ein Thema war.
- Risiko: PC-Zeiten sind nicht auf ein Steuergerät übertragbar. Mit Störgrößenvorschau wächst die explizite Lösung stark.

**24. A14 Proxy-Sensitivität** · K3, K4, K5 · S, 3–5 h · vorhanden · N3 · nach S4
- Identische Pipeline, nur der Durchsatzproxy getauscht: \mrel, q_rel (ch2 Z. 705–712), Last als Minimalvariante. Vergleich: OL-Fehler, gewählte Terme, Ventil-Gain-Profil, Kollinearität mit \valveCA (A2).
- Test auf gleiche Güte je Horizont mit Diebold & Mariano 1995 (HAC-Varianz), auf festem Testdatensatz.
- Macht den in ch2 Z. 728–731 angekündigten Vergleich belastbar.
- Risiko: Kein Nachweis gegenüber dem wahren Luftmassenstrom. Unterschiede können klein sein; auch das ist ein Befund (Proxywahl unkritisch).

**25. B6 Pareto-Front Sparsität gegen Freilauffehler** · K2, K4, K5 · S, 3–5 h · vorhanden · N3
- Abszisse Zahl aktiver Terme bzw. Parameter; Ordinate Freilauffehler auf Auswahldaten; zweite Kurve Trainings-Einschrittfehler (Überanpassung sichtbar). ARX-Ordnungen und \edmdc-Liftungen als Referenzpunkte.
- Punktfarbe: Abweichung des Ventil-Gains gegen DoE; zeigt, ob sparsame Modelle mit gutem Freilauf auch die Stellwirkung treffen.
- Anker: `manganModelSelectionDynamical2017`, `bruntonDiscoveringGoverningEquations2016` (Keys vorhanden).
- Risiko: Auswahl auf Testdaten wäre Leakage (S3). Divergierende Freiläufe kappen und kennzeichnen.

**26. A8 Wert der Störgrößenvorschau im MPC** · K3, K4, K6 · M, 4–7 h · vorhanden · N4 · nach S2
- Drei Informationsstufen im CL-Simulationsaufbau: (a) perfekte Vorschau, (b) letzter Messwert gehalten, (c) einfache kausale Prognose je Störgröße (AR-Modell oder exponentielle Glättung).
- Tabelle CL-Kennwerte je Stufe: welcher Anteil des MPC-Vorteils aus dem Modell und welcher aus der Vorschau stammt. Faire Referenz ist PI plus Vorsteuerung (F3).
- Füllt die offene Notiz ch2 Z. 1111.
- Anker: Oldewurtel u. a. 2012 (Wetterprognose im Gebäude-MPC, nur Methodenvorbild); Muth 1960; `rawlingsModelPredictiveControl20202020` (Key vorhanden).
- Risiko: Bei trägen Störgrößen kaum Unterschied zwischen (a) und (b); gültiger Befund. Umbauaufwand, falls der MPC-Code Störgrößen nur als Gesamtvektor übernimmt.

**27. S5 Stabilitäts- und Ruhelagenprüfung** · K1, K3, K4 · M, 4–8 h · vorhanden · N4
- \sindyc: `∂f/∂\Tout` auf einem Raster gemessener Betriebspunkte; negativ heißt lokal stabil, daraus Zeitkonstante. Physikabgleich nur als Richtung: Rate wächst mit \mrel (ch2 Z. 834–843).
- ARX und \edmdc: Eigenwerte, Scheineigenwerte nahe oder außerhalb des Einheitskreises markieren (ch3 Z. 307–311).
- Ruhelage aus `f = 0` bzw. `(I − A)z = Bu`: Existenz, Eindeutigkeit im Stellbereich, Lage im physikalischen Band zwischen Kühlwasser- und Kühlereintrittstemperatur.
- Am Rand der Datenhülle ausgewertet ergibt das den Gültigkeitsbereich für D6.
- Anker: `bruntonModernKoopmanTheory2022` (Key vorhanden, Scheineigenwerte); Kaptanoglu u. a. 2021 (Stabilität durch Konstruktion, trapping SINDy, nur Ausblick); Goyal, Duff, Benner 2025 (garantiert stabile quadratische Modelle, Metadaten korrigiert).
- Risiko: Punkte außerhalb der Datenhülle erzeugen scheinbare Verletzungen, nach Datendichte maskieren. Bei hohem \THT und niedriger Last kann die HT-Stufe die Luft erwärmen; die Bandgrenze muss das zulassen.

**28. D11 Weitere Betriebsart, Methanol** · K1, K5, K6 · S, 2–4 h · nein · N2
- Verweis auf E4.4: M1 Gültigkeitsbedingung als Gedankenexperiment, M2 Parametersatz je Betriebsart im unveränderten QP, M4 Ausblickabsatz. M3 ist als A17 geführt.
- Risiko: siehe E4; Literatur nur nach Copilot-Prüfung.

**29. D6 Gültigkeitsbereich überwachen, Rückfall auf ChATCo** · K3, K5, K6 · S, 4–6 h · vorhanden · N3
- Trainingsbereich im Raum der Betriebsgrößen: Hebelwert direkt aus der \sindyc-Regressionsmatrix, ergänzend konvexe Hülle in 2D-Projektionen. Abdeckungskarte Prüfstand gegen Feld; prüfen, ob große Feldfehler mit hohem Hebelwert zusammenfallen.
- Ausblick-Logik: MPC nur im Gültigkeitsbereich, sonst stoßfreier Rückfall auf ChATCo.
- Anker: Kahrs & Marquardt 2007 (Gültigkeitsbereich hybrider Modelle: konvexe Hülle und Konfidenzkriterium; Übertragung auf \sindyc als eigene Folgerung).
- Risiko: Hebelwert erfasst nur den Regressorraum, nicht fehlende Anregung der Dynamik; Schwelle ist Entwurfsgröße.

**30. B4 |S| über Periodendauer mit Störspektren** · K4, K5, K6 · M, 4–7 h · vorhanden · N3
- `|S(e^{jω})|` aus Prüfstands-Streckenmodell und PI-Parametern über der Periodendauer; darunter normierte Leistungsdichten von \valveCA, \Tin, \TLT aus Felddaten; Bänder `|S| < 1`, `≈ 1`, `> 1`; Marken für MPC-Horizont, dominante Zeitkonstante, Reglertakt.
- Zeigt, in welchem Periodenband Felddaten die Strecke tragen und ob das zum Horizont passt.
- Anker: Skogestad & Postlethwaite 2005 (Beleg für die |S|-Deutung, die in ch3 Z. 799–803 ohne Zitat steht); `forssellClosedloopIdenticationRevisited1999` (Key vorhanden).
- Risiko: S gilt nur für lineares G am Arbeitspunkt; Vorsteuerung, Anti-Windup, Ratenbegrenzung nicht enthalten. Kurze Feldabschnitte streuen stark (Welch-Mittelung angeben).

**31. D8 Mindestanregung (Dither) aus DoE-Daten** · K2, K4, K5, K6 · M, 6–10 h · vorhanden · N4
- Aus Prüfstandsdaten: Ausgangsrauschen bei festem Ventil und DoE-Sprunghöhen; DoE-Abschnitte auf kürzere Fenster bzw. weniger Sprünge reduzieren, Gain je Teilmenge schätzen, Streuung über Anregungsenergie auftragen und mit `σ²(ΦᵀΦ)⁻¹` vergleichen.
- Daraus Versuchsvorschlag als Ausblick: Amplitude, Signalform (PRBS/Multisinus), Dauer, nur Gasbetrieb; Nebenbedingung: Zusatzschwankung von \Tout bleibt im Band mit Abstand zur Derating-Schwelle (ch2 Z. 37–41).
- Im geschlossenen Kreis formt S den Dither; die wirksame Anregung ist kleiner als die aufgeprägte.
- Anker: `bomboisLeastCostlyIdentification2006`, `proctorDynamicModeDecomposition2016` (Keys vorhanden); Hjalmarsson 2005; Esmaili u. a. 2017 (CL-Identifikation unter MPC, Metadaten korrigiert); „MPC closed-loop identification without excitation“, J. Process Control 2021 (Autoren im Suchergebnis nicht gesehen).
- Risiko: Varianzformel gilt für weißes Rauschen im offenen Kreis; im Feld nur Größenordnung. Freigabe eines Testsignals an Serienanlagen liegt beim Hersteller.

**32. B5 Datenlandkarte mit gleitender Konditionszahl** · K2, K4, K7 · M, 6–10 h · vorhanden · N4 · nach S3
- Zeitbänder je Datensatz; je Fenster Klasse eingefärbt (Diesel/Sättigung, Gas stationär, Gas mit Laständerung, Modussprung, ausgeschlossen). Klassierung aus vorab festgelegten Kennzahlen: Varianz von \valveCA, Konditionszahl der Informationsmatrix der final gewählten Struktur, Anteil des schlechtesten Eigenvektors auf dem \valveCA-Koeffizienten.
- Auf dieselbe Zeitachse die Blöcke aus S3 mit Rollenfarbe legen.
- Anker: Shardt & Huang 2013 (Konditionszahl der Fisher-Information für Routinedaten); `bittencourtAlgorithmFindingProcess2015` (Key vorhanden); Peretzki u. a. 2011 (Metadaten korrigiert).
- Risiko: Schwellen und Fensterlänge wirken willkürlich; zwei Sätze zeigen. Hohe Information heißt Identifizierbarkeit, nicht Konsistenz (ch3 Z. 874–875).

**33. A15 Abtastzeit-Sensitivität** · K4, K5, K6 · M, 5–8 h · vorhanden · N3 · nach A9
- Prüfstandsdaten mit Anti-Aliasing-Filter auf mehrere Abtastzeiten (Vielfache der Totzeit bzw. Bruchteile der Zeitkonstante); identische Pipeline; Vergleich von Polen in kontinuierlicher Zeit, Ventil-Gain, gewählten Termen.
- Erwartung bei konsistentem Modell: Pol und Gain bleiben näherungsweise gleich; Drift zeigt Differentiationsprobleme oder eingefaltete Rückführung (ch3 Z. 899–905).
- Anker: Shardt & Huang 2011; `ljungSystemIdentificationTheory1999` (Key vorhanden).
- Risiko: Felddaten evtl. im Historian schon heruntergetastet; dann nur Prüfstand vollständig.

**34. A16 Sensorbias-Sensitivität (Errors-in-Variables)** · K3, K4, K5 · M, 5–8 h · vorhanden · N3
- Analytisch aus Gl. `eq.Tout.stat` (einstufige Ersatzform, eigene Algebra): Bias `b` auf \TLT verschiebt `T_stat` um `ε·b`, auf \Tin um `(1 − ε)·b`, also Niveaueffekt, vom Beobachter ausgleichbar. Skalenfehler an `Δp_HP` wirkt über \mrel auf Produkte und Rate, trifft Dynamik und Gain.
- Mit Validierungsdaten: Einheitsstörungen je Sensor aufprägen, (a) festes Modell simulieren, (b) neu fitten; Tabelle Sensor × Eigenschaft.
- Anker: Söderström 2007 (Errors-in-Variables-Übersicht); Isermann 2005 (Sensorüberwachung über Residuen).
- Risiko: Realistische Bias-Größen nur aus Datenblatt oder Kalibrierprotokoll; sonst nur Einheitssensitivitäten. EIV- und CL-Verzerrung getrennt halten.

**35. D7 Back-off an Taupunkt und Derating** · K3, K5, K6 · M, 5–8 h · vorhanden · N3 · nach A5
- Grenzen nur aus ch2: Band 50–60 °C, Derating ab 55 °C, Taupunkt (Vorbehalt Ladedruck, E1.1 K3). Back-off je Horizontschritt aus empirischen Quantilen des k-Schritt-Fehlers (A5) je Modell.
- Diskussion: kleinerer Prognosefehler ergibt kleineren Sicherheitsabstand; verbindet Modellgüte mit Betriebsnutzen ohne neue Messung.
- Anker: Kerrigan & Maciejowski 2000; `pucherLadeluftkuehlungUndLadeluftkuehler2012` (Key vorhanden).
- Risiko: Empirische Quantile geben keine Garantie (kein robuster MPC). Keine neuen Grenzwerte.

**36. A4 Termstabilität und Koeffizientenintervalle** · K3, K4, K6 · M, 8–12 h · vorhanden · N4 · nach S3
- Block-Bootstrap der Zeilen von Θ (Moving Block oder Stationary Bootstrap), je Replikat komplette Schätzung inklusive Schwellenwahl; Perzentil-Intervall je Koeffizient und Auswahlhäufigkeit je Term. Vergleich iid-Bagging gegen Block-Bagging (liefert die Standardvariante zu enge Bänder?).
- Heatmap: Terme × Datensätze, Farbe Auswahlhäufigkeit, Symbol Vorzeichen stabil/gemischt, physikalisch erwartetes Vorzeichen als Randspalte; vorab festgelegte Stabilitätsschwelle (Stability Selection).
- Optional: Einfaktor-Variation der Vorverarbeitung (Filter, Ableitungsverfahren nach van Breugel u. a. 2020, Totzeitverschiebung) als Spezifikationskurve.
- Replikate für das Gain-Band in A1 wiederverwenden.
- Anker: `faselEnsembleSINDyRobustSparse2022` (Key vorhanden); Künsch 1989; Politis & Romano 1994; Meinshausen & Bühlmann 2010; Hirsh u. a. 2022 (UQ-SINDy, nur Alternative im Ausblick).
- Risiko: Bei unstetigem Auswahlschritt sind Bootstrap-Intervalle nicht exakt; als empirische Stabilitätsaussage formulieren. Der Bootstrap erfasst die Varianz, nicht den Rückführungs-Bias. Rechenzeit.

**37. A10 Physikalische Referenz als Nullmodell** · K3, K4, K5 · M, 8–12 h · vorhanden · N4
- Referenz aus ch2 ohne neue Physik: Zielwert aus den Gleichungen der HT- und LT-Stufe mit NTU-Skalierung, Exponent auf \mrel, einfache Ventilfunktion; Dynamik `d\Tout/dt = λ(\mrel)(T_stat − \Tout)`; wenige Parameter per nichtlinearem LS.
- Bewertung auf derselben Leiter (OL, CL, DoE, Ventil-Gain); Querprüfung von Vorzeichen und Größenordnung der \sindyc-Produktterme gegen die linearisierte Referenz.
- Zweck: misst den Mehrwert der sparsamen Regression, statt ihn zu behaupten. Referenz, kein Zielmodell (nicht linear in \valveCA).
- Anker: `vagapovDynamicModelTemperature2022`, `suiMeanValueFirst2022`, `pucherLadeluftkuehlungUndLadeluftkuehler2012` (Keys vorhanden).
- Risiko: Schneidet die Referenz gut ab, kommt die Frage „warum nicht Greybox“; Antwort vorbereiten (QP-Linearität in \valveCA, Termauswahl aus Daten). Höchster Zeitbedarf unter den A-Ideen.

**38. A11 Twin-Experiment: Auswertekette mit bekannter Wahrheit** · K4, K5, K6 · M, 8–12 h · nein · N4
- Einzustands-Ersatzstrecke nach ch2 Gl. `energiebilanz.dyn` mit frei gewählten Parametern als Testbett (ausdrücklich kein Modell der Arbeit), ChATCo-Nachbau, Messrauschen; zwei synthetische Datensätze: geschlossener Kreis (Analogon Feld) und derselbe Kreis mit Ventilsprüngen (Analogon DoE).
- Gesamte Kette darauf: Vorverarbeitung, drei Modellklassen, Gain-Konvention, Residuentests, IV. Variiert: Vorsteuerungsanteil, Rauschniveau, Verhältnis Reglertakt zu Modelltakt. Monte-Carlo über Rauschrealisierungen.
- Beantwortet F5: Validierung (Messdaten) und Verifikation (bekannte Wahrheit) getrennt.
- Anker: `lovlandClosedloopIdentificationChallenge2025`, `forssellClosedloopIdenticationRevisited1999` (Keys vorhanden); Kaptanoglu u. a. 2023 (Benchmark mit bekannten Gleichungen); Schoukens & Noël 2017; Wirgin 2004 („inverse crime“: Generator darf nicht der Bibliothek entsprechen).
- Risiko: ch3 Z. 1143–1150 kritisiert Simulationsdaten; klar als Verifikation der Methode kennzeichnen. Befunde nur qualitativ; keine Testbett-Parameter als Motorwerte ausgeben.

**39. D9 Online-Nachführung als RLS-Replay** · K4, K5, K6 · M, 6–10 h · vorhanden · N3
- \sindyc-Struktur fest, aktive Koeffizienten per RLS mit Vergessensfaktor offline auf zeitlich geordneten Felddaten (nur Gasbetrieb). Variante A alle Koeffizienten, Variante B Ventilkoeffizient fest aus DoE.
- Prüfen, ob der Ventilkoeffizient in A bei fehlender Anregung wandert oder die Kovarianz aufbläht; Deutung über `−K⁻¹` (Løvland) und den Kompromiss Nachführung gegen Rauschunterdrückung.
- Empfehlung für später: richtungsabhängiges Vergessen (Goel u. a. 2020, Preprint) oder variabler Vergessensfaktor (Fortescue u. a. 1981).
- Anker: Ljung & Gunnarsson 1990; Goel u. a. 2020 (arXiv-Preprint, Metadaten korrigiert); Fortescue, Kershenbaum, Ydstie 1981; `bhadrirajuOASISPOperableAdaptive2021` (Key vorhanden, adaptive SINDy im Prozessumfeld; Zuordnung laut E1.3 prüfen).
- Risiko: Kein adaptiver MPC in der Arbeit, reine Offline-Analyse. Bei kurzem Zeitraum keine sichtbare Drift.

**40. A17 Dieselabschnitte als Probe für andere Betriebsart** · K2, K4, K6 · M, 6–12 h · vorhanden · N3
- Im Gasbetrieb identifizierte Modelle im Freilauf auf Dieselabschnitten auswerten; nur Störpfad prüfbar (Ventil fest 100 %), Niveauversatz berichten. Einzige vorhandene Probe für „andere Betriebsart“ (E4.4 M3).
- Risiko: Brennstoffwechsel ändert mehr als die Störgrößen (Ladeluftbedarf, Verbrennung); nur als Hinweis auf Übertragbarkeit deuten.

### E3.4 Ausblick: große Ideen nach der Abgabe

- **Dither-Feldversuch**: das in D8 hergeleitete Testsignal an einer Serienanlage fahren; braucht Freigabe des Herstellers. Anker: `bomboisLeastCostlyIdentification2006`; Hjalmarsson 2005.
- **Adaptiver MPC**: Ventilkoeffizient per RLS mit richtungsabhängigem Vergessen nachführen, Beobachter um einen Parameterzustand erweitern. Anker: Goel u. a. 2020 (Preprint); Ljung & Gunnarsson 1990.
- **Stabilität durch Konstruktion**: trapping SINDy oder stabile quadratische Modelle; setzt quadratische Bibliotheken voraus, passt nur bedingt. Anker: Kaptanoglu u. a. 2021; Goyal, Duff, Benner 2025.
- **Bayes-Unsicherheit der Koeffizienten** (UQ-SINDy) als Ersatz für A4. Anker: Hirsh u. a. 2022.
- **Stufen 3–5 aus D10**: quasi-LPV mit Iteration, bilineares Koopman-MPC mit SQP, NMPC. Verlässt die QP-Vorgabe.
- **Robuste MPC über die Unsicherheitsmenge** der Identifikation. Anker: Bombois u. a. 2001; Bemporad & Morari 1999.
- **Flottenmodell**: gemeinsame Termstruktur, motorabhängige Koeffizienten (Gruppen-Sparsamkeit). Anker: Rudy u. a. 2019.
- **Fouling-Erkennung** per erweitertem Kalman-Filter im Serienbetrieb. Anker: Jonsson u. a. 2007.
- **Explizite MPC auf dem Steuergerät**. Anker: Bemporad u. a. 2002.
- **Methanol als weitere Betriebsart**: siehe E4.5.

## E4 Zusatz: Methanol-Retrofit und Methanolmotoren (Wunsch Thomas, 25.09.2026)

Nicht Teil des Auftrags E, auf Nachfrage ergänzt. Trennung: (a) was die Arbeit trägt, (b) was nur für die Firma interessant ist. Alle Literaturangaben: Status höchstens [nur Abstract]; kein Volltext gelesen. Metadaten der mit ✓ markierten Quellen hat die Hauptsitzung selbst in Suchergebnissen gesehen; die übrigen sind Kandidaten.

### E4.1 Warum das Thema die Arbeit berührt

- ch2 Z. 958–961: „Brennstoffmodus kommt in der Bilanz nicht vor und wirkt nur über die Eingänge.“ Methanol wäre eine dritte Betriebsart neben Gas und Diesel. Die Aussage gilt dann nur unter einer Bedingung, die sich aus der eigenen Bilanz ableiten lässt (E4.3).
- Der Serien-Sollwert hängt laut Projektguide von Betriebspunkt und Kraftstoffart ab (ch2 Z. 229–236, `everllencese4960DFProject2026` S. 51, 376). Das trägt „Sollwert und Band je Betriebsart“ schon mit vorhandenen Quellen.
- ch3 Z. 869–873 nutzt den Wechsel Gas/Diesel als Informationsquelle. Eine weitere Betriebsart mit eigenem Regelgesetz wäre dieselbe Art von Abschnitt (eigene Ableitung, gleiche Vorbehalte wie in E1 K4).

### E4.2 Was die Literatur zur Rolle der Ladelufttemperatur im Methanolbetrieb sagt

| Quelle | Motor, Daten | Aussage laut Abstract | Nutzen für die Arbeit |
|---|---|---|---|
| ✓ Pan, Yao, Han, Wei, Wang (2015), *Fuel* 162, 101–110, DOI 10.1016/j.fuel.2015.08.073 [nur Abstract] | 6-Zyl. Nfz-Diesel mit Turbolader und Ladeluftkühlung, Methanol-Saugrohreinspritzung, 1500 1/min, Messung | Starke Kopplung von Ansauglufttemperatur und Methanolanteil; kältere Luft senkt indizierten Wirkungsgrad, stärker bei hohem Methanolanteil; höhere Ladungstemperatur verkürzt den Zündverzug deutlich | Wirkungskette Ladelufttemperatur → Zündverzug gilt auch im Methanol-DF, mit Methanolanteil als zusätzlichem Faktor. Kein Großmotor |
| ✓ Dierickx, Dejaegere, Van Gijzeghem, Devos u. a. (2023), SAE Technical Paper 2023-24-0046 (Journalfassung SAE Int. J. Adv. & Curr. Prac. in Mobility, Band/Seiten ungeprüft) [nur Abstract] | Dual-Fuel-Schiffsmotor mit Methanol, Messung (Motortyp im Abstract nicht genannt) | Höhere Ansauglufttemperatur verschiebt die Aussetzergrenze nur leicht; Gewinn an maximaler Substitution gering im Verhältnis zum Aufwand einer Temperaturregelung; AGR hebt die Substitutionsgrenze; NOx steigt mit Ansaugtemperatur und Ladedruck | Ehrliche Relativierung: Im Methanolbetrieb ist \Tout Randbedingung mit Zielkonflikt (Aussetzer kalt, Vorentflammung/NOx warm), nicht der Hebel für die Substitutionsrate |
| ✓ Karvounis, Theotokatos, Zoumpourlos, Coraddu (2025), *Applied Thermal Engineering* 281, 128652 [nur Abstract] | Großbohriger Viertakt-Schiffsmotor, hoher Methanolanteil bei Niedriglast, CFD (CONVERGE) | Akzeptable Verbrennung erst ab Verdichtung und Temperatur bei Einlassschluss über 17 und 380 K (Einfacheinspritzung), 16 und 380 K (Doppeleinspritzung), 14 und 360 K (geschichtet) | Niedriglast ist auch mit Methanol der kritische Bereich (Parallele zum Methanschlupf, ch2 Z. 96–102). `T_IVC` ist nicht \Tout; keine Übertragung auf das Band 50–60 °C |
| ✓ Karvounis, Theotokatos, Patil, Xiang, Ding (2025), *Fuel* 381 (Teil B), 133441 [nur Abstract] | Mittelschnelllaufender Schiffsmotor 10,5 MW bei 500 1/min, CFD | Saugrohreinspritzung bis 50 %, Direkteinspritzung bis 95 % Methanol-Energieanteil untersucht; DI klopffrei bis 95 %, NOx −85 %; bei vorgemischter Verbrennung gegenläufige Wirkungsgradtendenz | Leistungsklasse nahe am 49/60DF. Beim vorgemischten Retrofit bleibt Klopfen eine Grenze, die die Ladungstemperatur mitbestimmt (Folgerung, nicht Quelle) |
| ✓ Pu u. a. (2024), *Fuel* 372, 132131 (Autorenliste in dieser Sitzung nicht vollständig gesehen) [nur Abstract] | Schnelles Modell der Verdampfungskühlung bei Methanol-Einspritzung im Einlass | Methanol verdampft überwiegend als Wandfilm; Filmtemperatur bestimmt die Verdampfungsrate; Kühlung mindert Klopfen, kann im DF-Betrieb unvollständige Verbrennung auslösen | Termform für eine mögliche Bibliothekserweiterung (Senke ∝ Methanolmassenstrom), Koeffizient aus Daten; anlagenspezifisch |
| ✓ Titel/URL gesehen, Autoren ungeprüft: „Effect on the performance and emissions of methanol/diesel dual-fuel engine with different methanol injection positions“, *Fuel* (ScienceDirect PII S0016236121017476) [nur Abstract] | Nfz-Diesel mit Ladeluftkühlung, Methanol vor bzw. nach dem Ladeluftkühler eingespritzt | Einspritzung vor dem Ladeluftkühler verdampft wirksam, verkürzt Zündverzug und Brenndauer, senkt HC/CO | Belegt, dass der Einbringort relativ zum Kühler eine Konzeptentscheidung ist (E4.3, Fall A) |
| ✓ Dierickx, Mattheeuws, Christianen, Stenzel, Verhelst (2023), *Fuel* 345, 128254 [nur Abstract] | Mittelschnelllaufender Einzylinder, Diesel-Pilot in Methanol- bzw. H₂-Luftgemisch, Messung | Zündverzug steigt mit dem Methanol-Luft-Äquivalenzverhältnis; neue Korrelation mit Methanolterm | Analogie zur Bibliothekslogik (physikalisch motivierter Zusatzterm, Koeffizient aus Daten) |
| ✓ Karystinos, Papalambrou (2024), „Model Predictive Control for a Retrofitted Diesel Methanol Dual Fuel Engine“, CoDIT 2024, IEEE Xplore Dok. 10708167 [nur Abstract] | Schiffs-Retrofit-Motor mit zwei Steuergeräten, Prüfstand | MPC für die Drehzahl; Stellgrößen Dieselseite und Methanolmenge je Arbeitsspiel; Reglermodell aus Versuchsdaten; Echtzeitvalidierung | Nächste gefundene Arbeit „datenbasiertes Modell + MPC“ am Methanolmotor; andere Regelgröße. Für ch3 höchstens ein Satz |
| ✓ Kiouranakis, de Vos, Zoumpourlos, Coraddu, Geertsma (2025), *Renewable and Sustainable Energy Reviews* 214, 115529 [nur Abstract] | Review Heavy-Duty- und Großmotoren | In Großmotoren werden Diffusionsverfahren wegen höherer Methanolanteile bevorzugt, obwohl vorgemischte Verfahren Vorteile bei NOx und Nachrüstbarkeit haben | Einordnung „PFI-Retrofit vs. HPDI“ im Ausblick |
| ✓ Rektorik, P. (Diss. Universität Rostock, eingereicht 13.07.2024, verteidigt 25.11.2024), „Methanol als potentieller Zukunftskraftstoff für mittelschnelllaufende Großdieselmotoren“, DOI 10.18453/rosdok_id00004770 [nur Abstract] | Methanol-HPDI, Mehrstoffinjektor, CFD | Hochdruck-Direkteinspritzung und diffusives Methanol-DF-Brennverfahren für Mittelschnellläufer | Deutschsprachige Referenz, Volltext frei auf RosDok; Kapitel zur Ladelufttemperatur im Volltext prüfen |
| ✓ Dierickx u. a. (2021), *Fuel Communications* 7 (Artikelnr. ungeprüft) [nur Abstract] | Schnelllaufender Schiffsmotor, Retrofit, Methanol als Single-Point im Ansaugkanal oder Multi-Point an den Einlasskanälen | Beide Varianten als Retrofit machbar; NO und Ruß im Mittel −60 % bzw. −77 % | Einbringort (zentral stromauf vs. je Zylinder) bestimmt, ob die Verdampfungskühlung in \Tout sichtbar wird |

Kandidaten, nur bibliografisch oder ungeprüft (vor Nutzung in Zotero prüfen): Parsa, Verhelst u. a. (2025), *Energies* 18(12), 3064, DOI 10.3390/en18123064 (NN-Ersatzmodell für den Pilotzündverzug, Mittelschnellläufer); „Diesel–Methanol Dual-Fuel engine modeling including combustion characteristics and transient system dynamics“ (*Applied Thermal Engineering*, PII S1359431125037895, Autoren nicht gesehen; regelungsorientiertes Mittelwertmodell mit Klopfgrenze); FASTWATER-Demonstrator, *Transportation Research Procedia* (PII S2352146523008529); CIMAC-Congress-2025-Beiträge Nr. 102, 108, 203, 325, 362 (Titel teils abgeschnitten, Autoren offen).

### E4.3 Gedankenexperiment für die Arbeit: Wo wird eingespritzt? (eigene Ableitung aus ch2)

Bedingung, unter der ch2 Z. 958–961 gilt: Zwischen den Messstellen von \Tin und \Tout wird Wärme nur über HT- und LT-Stufe abgeführt und kein Stoff zugeführt.

- **Fall A, Einbringung vor dem Kühler, aber nach der \Tin-Messstelle:** Verdampfungssenke vor der HT-Stufe. Aus `T_zw = \THT + (\Tin − \THT) e^{−N_HT}` folgt `ΔT_zw = −ΔT_M e^{−N_HT}`; die Stellwirkung `−(T_zw − \TLT) ∂ε_LT/∂\valveCA` sinkt mit (eigene Algebra, Copilot rechnet nach). Tropfen im Kühler verletzen die Annahme „keine Kondensation, konstante Stoffwerte“.
- **Fall B, Einbringung zwischen Kühleraustritt und \Tout-Messstelle:** nicht erfasste Senke, erscheint ohne Zusatzterm als Niveauversatz im Residuum. Termform aus adiabater Mischung: Absenkung ∝ `ṁ_M/\mrel` (Methanol- zu Luftmassenstrom); Verdampfungsenthalpie und verdampfter Anteil gehen in den Koeffizienten (Muster ch2 Z. 697–703). Die eingespritzte Menge ist in der Motorsteuerung bekannt, also gemessene Störgröße; für das QP unkritisch.
- **Fall C, Einbringung stromab der \Tout-Messstelle (Einlasskanal):** Kühlerbilanz und Modell unverändert; \Tout beschreibt die Zylinderladung aber schlechter, der Sollwert wird zur Verbrennungsfrage.
- Kriterium „Term oder Grenze“ aus ch2 Z. 952–957 anwenden: Kondensation ist Grenze (Feuchte nicht gemessen, unstetig); Kraftstoffmenge ist gemessen und kann Störgröße sein.

### E4.4 Ideen für die Arbeit (bis 19.10.2026, ohne neue Messungen)

| Nr. | Idee | Aufwand | Daten | Kriterien |
|---|---|---|---|---|
| M1 | Gültigkeitsbedingung zu ch2 Z. 958–961 als 3–4 Stichpunkte (Fälle A–C) im Grenzen-Absatz, als Gedankenexperiment gekennzeichnet, ohne Zahlen | S, 2–4 h | nein | 3, 5 |
| M2 | Parametersatz je Betriebsart im unveränderten QP: `r^{(m)}`, `y_min^{(m)}` (lastabhängig, z. B. Freigabegrenze ch2 Z. 100–102), Koeffizientensatz; beim Moduswechsel festlegen, ob der Störzustand des Beobachters neu initialisiert oder übernommen wird | S, 2–3 h (Text); M mit Simulation | nein | 1, 4 |
| M3 | Dieselabschnitte als einzige vorhandene Probe für „andere Betriebsart“: im Gasbetrieb identifizierte Modelle im Freilauf auf Dieselabschnitten auswerten; nur Störpfad prüfbar (Ventil fest 100 %), Niveauversatz berichten | M, 6–12 h | vorhandene Daten | 2, 4, 6 |
| M4 | Ausblick-Absatz „weitere Betriebsart, z. B. Methanol“: Termstruktur übertragbar, Koeffizienten und Sollwert neu; OL/CL/DoE/Ventil-Gain je Betriebsart neu; Literatur nur nach Copilot-Prüfung, sonst neutral „weitere flüssige Kraftstoffe“ | S, 1–3 h | nein | 5, 6 |

M3 steht auch in der Haupttabelle E3 (Idee A17), weil sie eine umgesetzte Prüfung statt eines beschriebenen Ausblicks liefert.

### E4.5 Für die Firma interessant (nicht Teil der Arbeit)

- Signalliste für eine spätere Nachidentifikation von \Tout nach einem Methanol-Retrofit: Betriebsartsignal, eingespritzte Methanolmenge bzw. Energieanteil, Einbringort relativ zu den Messstellen von \Tin und \Tout, dazu die bisherigen Eingänge.
- ChATCo-Vorsteuerung (ch2 Z. 271–274) kennt keine Brennstoffaufteilung. Eine Verdampfungssenke vor der \Tout-Messstelle müsste der PI-Anteil nachträglich ausregeln; ein MPC mit Methanolmenge als gemessener Störgröße wäre die Alternative (eigene Ableitung, kein Ergebnis der Arbeit).
- Öffentliche Herstellerangaben (kein wissenschaftlicher Beleg, keine Firmeninterna; Nutzung in der Arbeit nur nach Absprache mit der Firmenbetreuung):
  - Everllence-Produktseite 49/60DF: Motor als „methanol-ready“ geführt, Umrüstung per Retrofit vorgesehen, Retrofit-Lösungen „in planning“ (https://www.everllence.com/marine/products/four-stroke-engines/49-60, in dieser Sitzung im Suchergebnis gesehen).
  - Everllence „Methanol dual fuel retrofit“ (https://www.everllence.com/discover-stories/methanol-dual-fuel-retrofit): laut Suchauszug eines Agenten Umbau 48/60 auf Stand 51/60R-DF-M, Saugrohreinspritzung als Favorit für Bestandsmotoren; Wortlaut ungeprüft.
  - Regelwerke, nur Titel gesehen, ungeprüft: IMO MSC.1/Circ.1621 (Methanol- und Ethanol-Richtlinien); ISO 6583:2024 (Methanol als Schiffskraftstoff).

### E4.6 Leerbefunde (Suchen in dieser Sitzung, 25.09.2026)

- Kein datengetriebenes Modell (SINDy, Koopman/EDMD, ARX) und keine MPC der Ladelufttemperatur im Methanolbetrieb gefunden (Suchen u. a. „methanol engine SINDy OR Koopman OR NARX“, „control-oriented model diesel methanol dual-fuel mean value“).
- Kein Ladelufttemperatur-Sollwert für den Methanolbetrieb eines Großmotors gefunden; nur `T_IVC` aus CFD und Laborwerte an Kleinmotoren.
- Keine wissenschaftliche Veröffentlichung zum Everllence-Umbau oder zu einer Methanol-Variante des 49/60DF gefunden, nur Herstellerseiten.
- Keine Arbeit zu Taupunkt/Kondensat im Ladeluftkühler eines Methanolmotors gefunden.
- Diese Leerbefunde gelten nur für den Suchumfang (Websuche mit Abstract-Auszügen, kein Datenbankzugang).

## Quellenliste

- Status je Quelle: [nur Abstract] = Abstract-Auszug im Suchergebnis gesehen; [nur bibliografisch] = nur Metadaten gesehen. [Volltext gelesen] kommt nicht vor.
- „Prüflauf: bestätigt/korrigiert“ = Ergebnis der zweiten, unabhängigen Suche; „Korrektur“ nennt, was gegenüber dem ersten Fund geändert wurde. Keys, die schon in der Arbeit stehen (`key`), sind hier nur aufgeführt, wenn ihre Metadaten geprüft wurden.
- Methanol-Quellen stehen mit Metadaten in der Tabelle E4.2 (in der Hauptsitzung selbst im Suchergebnis gesehen, ✓).
- BibTeX-Einträge sind bewusst nicht ausgeschrieben: Band, Seiten und Vornamen fehlen oft, weil nur Suchauszüge vorlagen. Import über die DOI-Liste in Zotero erzeugt geprüfte Einträge; Better BibTeX vergibt den endgültigen Key (die Vorschläge hinter `%` folgen dem Stil `nachnameTitelwoerterJahr`, hängen aber von der Schreibweise des Titels in Zotero ab).

### Gegengeprüfte Quellen (alphabetisch nach Erstautor)

- Fahim Abdullah, Zhe Wu, Panagiotis D. Christofides (2021): Sparse-identification-based model predictive control of nonlinear two-time-scale processes. Computers & Chemical Engineering 153, 107411. DOI 10.1016/j.compchemeng.2021.107411. https://www.sciencedirect.com/science/article/pii/S0098135421001897 [nur Abstract] · Prüflauf: bestätigt.
- Fahim Abdullah, Panagiotis D. Christofides (2023): Data-based modeling and control of nonlinear process systems using sparse identification: An overview of recent results. Computers & Chemical Engineering 174, 108247. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0098135423001175 [nur Abstract] · Prüflauf: bestätigt.
- Abdullah, F.; Christofides, P. D. (2023): Real-time adaptive sparse-identification-based predictive control of nonlinear processes. Chemical Engineering Research and Design, Bd. 196, S. 750–769. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0263876223004483 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt, weil der Finder sie offengelassen hatte: Autoren, Jahr 2023 (bestätigt), Zeitschrift, Band und Seiten, laut Treffern von ORNL, OSTI und ScienceDirect.
- V. Aran; M. Unel (2020): Diesel Engine Airpath Controller Via Data Driven Disturbance Observer. International Journal of Automotive Technology 21(4), S. 971–980 (Springer). DOI 10.1007/s12239-020-0092-x. https://link.springer.com/article/10.1007/s12239-020-0092-x [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Autoren V. Aran, M. Unel; Band 21, Heft 4, S. 971–980, August 2020 (aus Ergebnis-Zusammenfassung).
- Aghazadeh Ardebili, A.; Khalil, A.; Khalil, S.; Padoano, E.; Ficarella, A. (2025): Sparse Identification of Nonlinear Dynamics (SINDy) for Digital Twinning and Performance Modeling in Hybrid Engines. Proceedings of the ASME Turbo Expo 2025: Turbomachinery Technical Conference and Exposition (GT2025), Memphis, TN, USA, 16.-20. Juni 2025, Bd. 8, V008T23A005. DOI nicht gesehen. https://asmedigitalcollection.asme.org/GT/proceedings-abstract/GT2025/88841/V008T23A005/1220614 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel, Tagung (Turbo Expo 2025, Memphis, Juni 2025) und Band/Artikelnummer V008T23A005 in der ASME-URL gesehen.
- Atam, Ercan (im Suchergebnis als "E. Atam") (2018): Advanced Air Path Control in Diesel Engines Accounting for Variable Operational Conditions. IEEE Access, Vol. 6. DOI nicht gesehen. https://ieeexplore.ieee.org/document/8421223/ [nur Abstract] · Prüflauf: bestätigt.
- Badwe, A. S.; Gudi, R. D.; Patwardhan, R. S.; Shah, S. L.; Patwardhan, S. C. (2009): Detection of model-plant mismatch in MPC applications. Journal of Process Control, Bd. 19, S. 1305-1313. DOI 10.1016/j.jprocont.2009.04.007. https://www.sciencedirect.com/science/article/abs/pii/S0959152409000572 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Der Finder hatte die Autoren leer gelassen, Jahr und Journal waren nur vermutet.
- Bakarji, Joseph; Callaham, Jared; Brunton, Steven L.; Kutz, J. Nathan (2022): Dimensionally consistent learning with Buckingham Pi. Nature Computational Science 2, S. 834–844 (Dezember 2022); Preprint arXiv:2202.04643. DOI nicht gesehen. https://www.nature.com/articles/s43588-022-00355-5 [nur Abstract] · Prüflauf: bestätigt.
- Belsley, David A.; Kuh, Edwin; Welsch, Roy E. (1980): Regression Diagnostics: Identifying Influential Data and Sources of Collinearity. John Wiley & Sons, New York, xv + 292 S. (Erstausgabe 1980, ISBN 0-471-05856-4; Wiley-Series-Nachdruck 2004, ISBN 978-0-471-69117-4). DOI 10.1002/0471725153. https://onlinelibrary.wiley.com/doi/book/10.1002/0471725153 [nur Abstract] · Prüflauf: bestätigt.
- Alberto Bemporad, Manfred Morari (1999): Robust model predictive control: A survey. In: A. Garulli, A. Tesi (Hrsg.), Robustness in Identification and Control, Lecture Notes in Control and Information Sciences 245, Springer, London. DOI 10.1007/BFb0109870. https://link.springer.com/chapter/10.1007/BFb0109870 [nur Abstract] · Prüflauf: bestätigt.
- Alberto Bemporad, Manfred Morari, Vivek Dua, Efstratios N. Pistikopoulos (2002): The explicit linear quadratic regulator for constrained systems. Automatica 38(1), S. 3-20. DOI 10.1016/S0005-1098(01)00174-1. https://www.sciencedirect.com/science/article/abs/pii/S0005109801001741 [nur Abstract] · Prüflauf: bestätigt.
- Benner, Peter; Gugercin, Serkan; Willcox, Karen (2015): A Survey of Projection-Based Model Reduction Methods for Parametric Dynamical Systems. SIAM Review 57(4), S. 483-531. DOI nicht gesehen. https://dspace.mit.edu/bitstream/handle/1721.1/100939/Benner-2015-Survey%20of%20projection-based.pdf;sequence=1 [nur Abstract] · Prüflauf: bestätigt.
- Beran, Tobias; Gärtner, J.; Koch, Thomas (2021): A model-based approach for a control strategy of a charge air cooling concept in an ejector refrigeration cycle. Automotive and Engine Technology (Springer). DOI 10.1007/s41104-021-00087-0. https://link.springer.com/article/10.1007/s41104-021-00087-0 [nur Abstract] · Prüflauf: bestätigt.
- Beran, Tobias; Gärtner, Jan; Koch, Thomas (2021): Charge-Air Cooling of High Performance Engines in an Ejector Refrigeration Cycle. Internationaler Motorenkongress 2021, Proceedings, Springer Vieweg, Wiesbaden (Buchkapitel). DOI 10.1007/978-3-658-35588-3_19. https://link.springer.com/chapter/10.1007/978-3-658-35588-3_19 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur betrifft nur die Venue: laut Suchergebnis (KIT-IFKM-Seite) Internationaler Motorenkongress 2021 Proceedings, Springer Vieweg, Wiesbaden; Vortrag 24.02.2021.
- Bergmeir, Christoph; Benítez, José M. (2012): On the use of cross-validation for time series predictor evaluation. Information Sciences 191, S. 192–213. DOI 10.1016/j.ins.2011.12.028. https://www.sciencedirect.com/science/article/abs/pii/S0020025511006773 [nur Abstract] · Prüflauf: bestätigt.
- Bergmeir, Christoph; Hyndman, Rob J.; Koo, Bonsoo (2018): A note on the validity of cross-validation for evaluating autoregressive time series prediction. Computational Statistics & Data Analysis 120, S. 70–83. DOI 10.1016/j.csda.2017.11.003. https://www.sciencedirect.com/science/article/abs/pii/S0167947317302384 [nur Abstract] · Prüflauf: bestätigt.
- Bhadriraju, B.; Bangi, M. S. F.; Narasingam, A.; Kwon, J. S.-I. (nur Erstautor gesehen) (2020): Operable adaptive sparse identification of systems: Application to chemical processes. AIChE Journal (Band 66(11) nicht gesehen). DOI 10.1002/aic.16980. https://aiche.onlinelibrary.wiley.com/doi/abs/10.1002/aic.16980 [nur Abstract] · Prüflauf: bestätigt.
- Bhadriraju, B.; Kwon, J. S.-I.; Khan, F. (Reihenfolge unsicher, siehe Bemerkung) (2021): OASIS-P: Operable Adaptive Sparse Identification of Systems for fault Prognosis of chemical processes. Journal of Process Control 107, S. 114-126. DOI 10.1016/j.jprocont.2021.10.006. https://www.sciencedirect.com/science/article/abs/pii/S0959152421001773 [nur Abstract] · Prüflauf: bestätigt.
- Billings, S. A.; Voon, W. S. F. (1986): Correlation based model validity tests for non-linear models. International Journal of Control 44(1), S. 235–244. DOI 10.1080/00207178608933593. https://www.tandfonline.com/doi/abs/10.1080/00207178608933593 [nur Abstract] · Prüflauf: bestätigt.
- Billings, S. A.; Zhu, Q. M. (1994): Nonlinear model validation using correlation tests. International Journal of Control 60(6), S. 1107–1120. DOI 10.1080/00207179408921513. https://www.tandfonline.com/doi/abs/10.1080/00207179408921513 [nur Abstract] · Prüflauf: bestätigt.
- Billings, Stephen A. (2013): Nonlinear System Identification: NARMAX Methods in the Time, Frequency, and Spatio-Temporal Domains. John Wiley & Sons, ISBN 9781119943594. DOI 10.1002/9781118535561. https://onlinelibrary.wiley.com/doi/book/10.1002/9781118535561 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrigiert ist nur das DOI-Feld.
- Björklund, S.; Ljung, L. (2003): A review of time-delay estimation techniques. Proceedings of the 42nd IEEE Conference on Decision and Control, Maui, Bd. 3, S. 2502-2507. DOI nicht gesehen. https://www.semanticscholar.org/paper/A-review-of-time-delay-estimation-techniques-Bj%C3%B6rklund-Ljung/136fcdc2b77f12bff0380441c4881ab3c081db2f [nur Abstract] · Prüflauf: bestätigt.
- Bombois, X.; Gevers, M.; Scorletti, G.; Anderson, B. D. O. (2001): Robustness analysis tools for an uncertainty set obtained by prediction error identification. Automatica 37(10), S. 1629-1636. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0005109801001042 [nur Abstract] · Prüflauf: bestätigt.
- Ghoddousi Boroujeni, Mahrokh; Meroi, Laura; Massai, Leonardo; Galimberti, Clara L.; Ferrari-Trecate, Giancarlo (2025): Neural Identification of Feedback-Stabilized Nonlinear Systems. arXiv:2503.22601 (Preprint); IEEE-Konferenzbeitrag, IEEE Xplore Dokument 11312335. DOI nicht gesehen. https://arxiv.org/abs/2503.22601 [nur Abstract] · Prüflauf: bestätigt.
- Box, George E. P.; MacGregor, John F. (1974): The Analysis of Closed-Loop Dynamic-Stochastic Systems. Technometrics 16(3), S. 391-398. DOI 10.1080/00401706.1974.10489208. https://www.tandfonline.com/doi/abs/10.1080/00401706.1974.10489208 [nur Abstract] · Prüflauf: bestätigt.
- van Breugel, Floris; Kutz, J. Nathan; Brunton, Bingni W. (2020): Numerical Differentiation of Noisy Data: A Unifying Multi-Objective Optimization Framework. IEEE Access 8, S. 196865-196877. DOI nicht gesehen. https://ieeexplore.ieee.org/document/9241009/ [nur Abstract] · Prüflauf: bestätigt.
- Cawley, Gavin C.; Talbot, Nicola L. C. (2010): On Over-fitting in Model Selection and Subsequent Selection Bias in Performance Evaluation. Journal of Machine Learning Research 11, S. 2079-2107. DOI 10.5555/1756006.1859921. https://www.jmlr.org/papers/v11/cawley10a.html [nur Abstract] · Prüflauf: bestätigt.
- Kathleen Champion, Bethany Lusch, J. Nathan Kutz, Steven L. Brunton (2019): Data-driven discovery of coordinates and governing equations. Proceedings of the National Academy of Sciences (PNAS) 116(45), 22445-22451. DOI 10.1073/pnas.1906995116. https://www.pnas.org/doi/10.1073/pnas.1906995116 [nur Abstract] · Prüflauf: bestätigt.
- Chen, S.; Billings, S. A.; Luo, W. (1989): Orthogonal least squares methods and their application to non-linear system identification. International Journal of Control 50(5), S. 1873–1896. DOI 10.1080/00207178908953472. https://www.tandfonline.com/doi/abs/10.1080/00207178908953472 [nur Abstract] · Prüflauf: bestätigt.
- Chen, S.; Billings, S. A.; Grant, P. M. (1990): Non-linear system identification using neural networks. International Journal of Control 51(6), S. 1191–1214. DOI 10.1080/00207179008934126. https://www.tandfonline.com/doi/abs/10.1080/00207179008934126 [nur Abstract] · Prüflauf: bestätigt.
- A. Chiuso (2007): The role of vector autoregressive modeling in predictor-based subspace identification. Automatica 43(6), S. 1034-1048. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S000510980700057X [nur Abstract] · Prüflauf: bestätigt.
- Yonadan Choi, Sungjun Yoon, Tag Gon Kim, Beomcheol Ham (2026): Hybrid modeling of marine turbocharger engines with minimal data requirement: A versatile physics-data fusion approach toward digital twin applications. International Journal of Engine Research (SAGE). DOI 10.1177/14680874261419158. https://journals.sagepub.com/doi/10.1177/14680874261419158 [nur Abstract] · Prüflauf: bestätigt.
- Pablo S. G. Cisneros, Sophia Voss, Herbert Werner (2016): Efficient Nonlinear Model Predictive Control via quasi-LPV representation. 2016 IEEE 55th Conference on Decision and Control (CDC). DOI nicht gesehen. https://ieeexplore.ieee.org/document/7798752/ [nur Abstract] · Prüflauf: bestätigt.
- Pablo S. G. Cisneros; Adwait Datar; Patrick Göttsch; Herbert Werner (2020): Data-Driven quasi-LPV Model Predictive Control Using Koopman Operator Techniques. IFAC-PapersOnLine 53(2), S. 6062–6068 (21. IFAC World Congress); auch TORE TUHH handle 11420/8429. DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896320322795 [nur Abstract] · Prüflauf: bestätigt.
- Andrea Coraddu; Luca Oneto; F. Cipollini; M. Kalikatzarakis; G. J. Meijn; R. Geertsma (2021): Physical, data-driven and hybrid approaches to model engine exhaust gas temperatures in operational conditions. Ships and Offshore Structures 17(6), S. 1360–1381 (Taylor & Francis). DOI 10.1080/17445302.2021.1920095. https://www.tandfonline.com/doi/full/10.1080/17445302.2021.1920095 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Autoren (aus Suchergebnis-Zusammenfassung zum TU-Delft-Portal; Strathprints-Dateiname Coraddu_etal_SOS_2021 passt), Zeitschrift Ships and Offshore Structures, Band 17(6), S. 1360–1381.
- Steven Dahdah, James Richard Forbes (2024): Closed-loop Koopman operator approximation. Machine Learning: Science and Technology 5(2) (10.05.2024); Preprint arXiv:2303.15318. DOI 10.1088/2632-2153/ad45b0. https://iopscience.iop.org/article/10.1088/2632-2153/ad45b0 [nur Abstract] · Prüflauf: bestätigt.
- Branislav Daráš; Patrik Valábek; Martin Klaučo (2026): DeePC vs. Koopman MPC for Pasteurization: A Comparative Study. arXiv:2604.00524 (Preprint, eess.SY-Listing April 2026). DOI nicht gesehen. https://arxiv.org/abs/2604.00524 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und arXiv-ID bestätigt, April 2026 über das arXiv-Listing belegt.
- Diebold, Francis X.; Mariano, Roberto S. (1995): Comparing Predictive Accuracy. Journal of Business & Economic Statistics 13(3), S. 253-263. DOI 10.1080/07350015.1995.10524599. https://www.tandfonline.com/doi/abs/10.1080/07350015.1995.10524599 [nur Abstract] · Prüflauf: bestätigt.
- Douma, Sippe G.; Bombois, Xavier; Van den Hof, Paul M. J. (2008): Validity of the standard cross-correlation test for model structure validation. Automatica (Band/Heft/Seiten im Suchergebnis nicht angezeigt). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0005109807004311 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Autoren und Jahr ergänzt, beim Finder fehlten sie.
- Du, Mohan; Lai, Jiayi; Liu, Rong-Peng; Wang, Xiaozhe (2026): Physically Consistent SINDy (Sparse Identification of Nonlinear Dynamics) for Microgrid Identification and Real-Time Frequency Control. arXiv:2608.00213 (Preprint). DOI nicht gesehen. https://arxiv.org/abs/2608.00213 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und arXiv-Nummer 2608.00213 gesehen (abs, pdf, html).
- Ali Esmaili; Jianyi Li; Jinyu Xie; Joshua D. Isom (2017): Closed-loop identification for plants under model predictive control. Control Engineering Practice (Elsevier), PII S096706611730271X; Band und Seiten nicht gesehen. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S096706611730271X [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und ScienceDirect-PII bestätigt.
- Paolo Falcone, Francesco Borrelli, Jahan Asgari, Hongtei Eric Tseng, Davor Hrovat (2007): Predictive Active Steering Control for Autonomous Vehicle Systems. IEEE Transactions on Control Systems Technology 15, S. 566-580. DOI nicht gesehen. https://www.semanticscholar.org/paper/Predictive-Active-Steering-Control-for-Autonomous-Falcone-Borrelli/abd354d708b98fb60e0d827a41157491289e8d3c [nur Abstract] · Prüflauf: bestätigt.
- T. R. Fortescue, L. S. Kershenbaum, B. E. Ydstie (1981): Implementation of self-tuning regulators with variable forgetting factors. Automatica 17(6), S. 831-835 (Brief Paper). DOI 10.1016/0005-1098(81)90070-4. https://dl.acm.org/doi/10.1016/0005-1098(81)90070-4 [nur Abstract] · Prüflauf: bestätigt.
- Chao Fu; Xiaoxia Liang; Qian Li; Kuan Lu; Fengshou Gu; Andrew D. Ball; Zhaoli Zheng (2023): Comparative Study on Health Monitoring of a Marine Engine Using Multivariate Physics-Based Models and Unsupervised Data-Driven Models. Machines (MDPI), Bd. 11, Heft 5, Art. 557. DOI 10.3390/machines11050557. https://doi.org/10.3390/machines11050557 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel, DOI (in der Ergebnis-URL gesehen), Jahr 2023, Band 11 und Artikel 557 bestätigt.
- Gevers, Michel (2005): Identification for Control: From the Early Achievements to the Revival of Experiment Design. European Journal of Control 11(4-5), S. 335-352. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0947358005710414 [nur Abstract] · Prüflauf: bestätigt.
- Ankit Goel, Adam L. Bruce, Dennis S. Bernstein (2020): Recursive Least Squares with Variable-Direction Forgetting: Compensating for the Loss of Persistency. IEEE Control Systems Magazine 40(4), S. 80-102 (Rubrik Lecture Notes); Preprint arXiv:2003.03523. DOI nicht gesehen. https://arxiv.org/abs/2003.03523 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Autoren vollständig (Goel, Bruce, Bernstein); Zeitschrift ist IEEE Control Systems Magazine 40(4), 80-102, 2020 (Suchzusammenfassung; Dateiname 'Ankit_Forgetting_CSM.pdf' auf umich.edu passt dazu). arXiv-Einreichung 7. März 2020 …
- Gopaluni, R. B.; Patwardhan, R. S.; Shah, S. L. (2004): MPC relevant identification––tuning the noise model. Journal of Process Control 14(6), S. 699-714. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0959152403001094 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrigiert: Jahr 2004 statt 2002.
- Pawan Goyal (auch als Pawan K. Goyal), Igor Pontes Duff, Peter Benner (2025): Guaranteed stable quadratic models and their applications in SINDy and operator inference. Physica D: Nonlinear Phenomena 482, Artikel 134893 (2025); Preprint arXiv:2308.13819 (2023). DOI 10.1016/j.physd.2025.134893. https://www.sciencedirect.com/science/article/pii/S0167278925003707 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Autoren, Titel, Jahr bestätigt.
- Grasev, David (2026 (Nonlinear Dynamics, laut Suchergebnis Februar 2026); Preprint 2025): Koopman eigenfunction-based identification and optimal nonlinear control of turbojet engine. Nonlinear Dynamics (Springer Nature); Preprint arXiv:2505.10438. DOI 10.1007/s11071-025-12070-7. https://link.springer.com/article/10.1007/s11071-025-12070-7 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Autor ergänzt: David Grasev, University of Defence, Brno (Einzelautor laut Treffer).
- Hausman, J. A. (1978): Specification Tests in Econometrics. Econometrica 46(6), S. 1251-1271. DOI 10.2307/1913827. https://www.econometricsociety.org/publications/econometrica/1978/11/01/specification-tests-econometrics [nur Abstract] · Prüflauf: bestätigt.
- He, X.; Asada, H. (1993): A new method for identifying orders of input-output models for nonlinear dynamic systems. Proc. American Control Conference (ACC) 1993, San Francisco, S. 2520–2524. DOI nicht gesehen. https://link.springer.com/chapter/10.1007/978-3-030-47439-3_19 [nur bibliografisch] · Prüflauf: bestätigt.
- Hirsh, Seth M.; Barajas-Solano, David A.; Kutz, J. Nathan (2022): Sparsifying priors for Bayesian uncertainty quantification in model discovery. Royal Society Open Science 9(2), Art. 211823. DOI 10.1098/rsos.211823. https://royalsocietypublishing.org/doi/10.1098/rsos.211823 [nur Abstract] · Prüflauf: bestätigt.
- Håkan Hjalmarsson (2005): From experiment design to closed-loop control. Automatica 41(3), S. 393-438. DOI nicht gesehen. https://www.semanticscholar.org/paper/From-experiment-design-to-closed-loop-control-Hjalmarsson/83b8da41917b7859b28956db94c6e289098e3c48 [nur Abstract] · Prüflauf: bestätigt.
- Rolf Isermann (2005): Model-based fault-detection and diagnosis – status and applications. Annual Reviews in Control 29(1), S. 71-85. DOI 10.1016/j.arcontrol.2004.12.002. https://www.sciencedirect.com/science/article/abs/pii/S1367578805000052 [nur Abstract] · Prüflauf: bestätigt.
- Ito, Y.; Hato, T.; Kano, A. (2023): Physics-Informed Machine Learning for Surrogate Modeling of Heat Transfer Phenomena. Journal of Computational and Nonlinear Dynamics (ASME), Bd. 18, Nr. 11, Art. 111001. DOI nicht gesehen. https://asmedigitalcollection.asme.org/computationalnonlinear/article/18/11/111001/1166452/Physics-Informed-Machine-Learning-for-Surrogate [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und Fundstelle JCND 18(11) 111001 über den ASME-Link bestätigt.
- Rajendra Kumar Jagadeesh; P M G Bashir Asdaque; Viswanathan Rajan; Naseem Khayum; Syed Suraya; Thota S S Bhaskara Rao; Hari Prasadarao Pydi (2026): Experimental emulation of charge air cooler temperature and pressure on an engine dynamometer for air–fuel ratio optimization and pulsation reduction. Scientific Reports 16, Art. 24691 (Nature Portfolio); PMC13454573, PubMed 42218184. DOI 10.1038/s41598-026-53715-w. https://www.nature.com/articles/s41598-026-53715-w [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Autoren, Band 16, Artikelnummer 24691, DOI (DOI steht im nature.com-URL und im Ergebnistext).
- G. R. Jonsson, S. Lalot, O. P. Palsson, B. Desmet (2007): Use of extended Kalman filtering in detecting fouling in heat exchangers. International Journal of Heat and Mass Transfer 50(13-14), S. 2643-2655. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0017931006006533 [nur Abstract] · Prüflauf: bestätigt.
- Joshi, James, Meckl, King, Jennings (2009): Assessment of Charge-Air Cooler Health in Diesel Engines Using Nonlinear Time Series Analysis of Intake Manifold Temperature. Journal of Dynamic Systems, Measurement, and Control (Transactions of the ASME) 131(4). DOI nicht gesehen. https://www.researchgate.net/publication/228568042_Assessment_of_Charge-Air_Cooler_Health_in_Diesel_Engines_Using_Nonlinear_Time_Series_Analysis_of_Intake_Manifold_Temperature [nur Abstract] · Prüflauf: bestätigt.
- Kahrs, Marquardt (2007): The validity domain of hybrid models and its application in process optimization. Chemical Engineering and Processing (: Process Intensification). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0255270107001134 [nur Abstract] · Prüflauf: bestätigt.
- Kaipio, Jari; Somersalo, Erkki (2007): Statistical inverse problems: Discretization, model reduction and inverse crimes. Journal of Computational and Applied Mathematics 198(2), S. 493-504. DOI 10.1016/j.cam.2005.09.027. https://www.sciencedirect.com/science/article/pii/S0377042705007296 [nur Abstract] · Prüflauf: bestätigt.
- Kaiser, Eurika; Kutz, J. Nathan; Brunton, Steven L. (2018): Sparse identification of nonlinear dynamics for model predictive control in the low-data limit. Proceedings of the Royal Society A 474(2219), 20180335; Preprint arXiv:1711.05501. DOI 10.1098/rspa.2018.0335. https://royalsocietypublishing.org/doi/10.1098/rspa.2018.0335 [nur Abstract] · Prüflauf: bestätigt.
- Kaleli, A. (nur Erstautor im Suchergebnis; ob es Koautoren gibt, ist nicht geprüft) (2020): Development of the predictive based control of an autonomous engine cooling system for variable engine operating conditions in SI engines: design, modeling and real-time application. Control Engineering Practice (Band/Seiten nicht gesehen). DOI 10.1016/j.conengprac.2020.104424. https://www.sciencedirect.com/science/article/abs/pii/S0967066120300770 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und ScienceDirect-PII bestätigt.
- Mason Kamb, Eurika Kaiser, Steven L. Brunton, J. Nathan Kutz (2020): Time-Delay Observables for Koopman: Theory and Applications. SIAM Journal on Applied Dynamical Systems 19(2), 886-917; Preprint arXiv:1810.01479 (2018). DOI 10.1137/18M1216572. https://doi.org/10.1137/18m1216572 [nur Abstract] · Prüflauf: bestätigt.
- Kaptanoglu, Alan A.; Callaham, Jared L.; Aravkin, Aleksandr; Hansen, Christopher J.; Brunton, Steven L. (2021): Promoting global stability in data-driven models of quadratic nonlinear dynamics. Physical Review Fluids 6, 094401. DOI 10.1103/PhysRevFluids.6.094401. https://journals.aps.org/prfluids/abstract/10.1103/PhysRevFluids.6.094401 [nur Abstract] · Prüflauf: bestätigt.
- Kaptanoglu, Alan A.; Zhang, Lanyue; Nicolaou, Zachary G.; Fasel, Urban; Brunton, Steven L. (2023): Benchmarking sparse system identification with low-dimensional chaos. Nonlinear Dynamics 111(14), S. 13143-13164; Preprint arXiv:2302.10787. DOI 10.1007/s11071-023-08525-4. https://link.springer.com/article/10.1007/s11071-023-08525-4 [nur Abstract] · Prüflauf: bestätigt.
- Eric C. Kerrigan, Jan M. Maciejowski (2000): Soft constraints and exact penalty functions in model predictive control. Proceedings of the UKACC International Conference on Control (Control 2000), Cambridge, UK, September 2000, S. 2319-2327. DOI nicht gesehen. http://www-control.eng.cam.ac.uk/Homepage/papers/cued_control_53.pdf [nur Abstract] · Prüflauf: bestätigt.
- Milan Korda, Igor Mezić (2018): On Convergence of Extended Dynamic Mode Decomposition to the Koopman Operator. Journal of Nonlinear Science 28, 687–710; arXiv 1703.04680. DOI 10.1007/s00332-017-9423-0. https://link.springer.com/article/10.1007/s00332-017-9423-0 [nur Abstract] · Prüflauf: bestätigt.
- Kramer, Boris; Peherstorfer, Benjamin; Willcox, Karen E. (2024): Learning Nonlinear Reduced Models from Data with Operator Inference. Annual Review of Fluid Mechanics 56, S. 521-548. DOI 10.1146/annurev-fluid-121021-025220. https://www.annualreviews.org/content/journals/10.1146/annurev-fluid-121021-025220 [nur Abstract] · Prüflauf: bestätigt.
- Künsch, Hans R. (1989): The Jackknife and the Bootstrap for General Stationary Observations. The Annals of Statistics 17(3), S. 1217-1241. DOI 10.1214/aos/1176347265. https://projecteuclid.org/journals/annals-of-statistics/volume-17/issue-3/The-Jackknife-and-the-Bootstrap-for-General-Stationary-Observations/10.1214/aos/1176347265.full [nur Abstract] · Prüflauf: bestätigt.
- Li, Yao Cheng; Larrañaga, Ana; Brunton, Steven L.; Fasel, Urban (2026): An Introduction to Sparse Identification of Nonlinear Dynamics for Engineering Applications. arXiv:2607.15077 (Preprint). DOI nicht gesehen. https://arxiv.org/pdf/2607.15077 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel auf arXiv bestätigt.
- Lin, Linyu; Oncken, Joseph; Agarwal, Vivek (2024): Autonomous control for Heat-Pipe microreactor using Data-Driven model predictive control. Annals of Nuclear Energy, Bd. 200, Artikel 110399. DOI nicht gesehen. https://www.osti.gov/biblio/2316049 [nur Abstract] · Prüflauf: bestätigt.
- Ljung, G. M.; Box, G. E. P. (1978): On a measure of lack of fit in time series models. Biometrika 65(2), S. 297-303. DOI 10.1093/biomet/65.2.297. https://academic.oup.com/biomet/article-abstract/65/2/297/236869 [nur Abstract] · Prüflauf: bestätigt.
- L. Ljung, S. Gunnarsson (1990): Adaptation and tracking in system identification - A survey. Automatica 26, S. 7-22. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/000510989090154A [nur Abstract] · Prüflauf: bestätigt.
- Loiseau, Jean-Christophe; Brunton, Steven L. (2018): Constrained sparse Galerkin regression. Journal of Fluid Mechanics 838, S. 42–67. DOI nicht gesehen. https://www.cambridge.org/core/journals/journal-of-fluid-mechanics/article/abs/constrained-sparse-galerkin-regression/0E18A4A55FF5AC1401D236C0E4D1CAAE [nur Abstract] · Prüflauf: bestätigt.
- Jean-Christophe Loiseau (2020): Data-driven modeling of the chaotic thermal convection in an annular thermosyphon. Theoretical and Computational Fluid Dynamics 34, S. 339 ff. (2020) (Band/Startseite aus ADS-Bibcode 2020ThCFD..34..339L); Preprint arXiv:1911.07920 (2019). DOI 10.1007/s00162-020-00536-w. https://link.springer.com/article/10.1007/s00162-020-00536-w [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Finder nannte nur den arXiv-Preprint 2019 ohne Autor; es gibt die begutachtete Fassung in Theor.
- Pengyu Lu; Qing Gao; Liang Lv; Xiaoye Xue; Yan Wang (2019): Numerical Calculation Method of Model Predictive Control for Integrated Vehicle Thermal Management Based on Underhood Coupling Thermal Transmission. Energies 12(2), Artikel 259 (MDPI). DOI 10.3390/en12020259. https://www.mdpi.com/1996-1073/12/2/259 [nur Abstract] · Prüflauf: korrigiert. Korrektur: DOI in der Ergebnis-URL (doi.org) gesehen, MDPI-URL 1996-1073/12/2/259 bestätigt Band 12, Heft 2, Artikel 259.
- Cristian López, Mckenna Partridge, Sebastian De Pascuale, Jeremy Lore, Andrew Christlieb, Stephen Becker, David M. Bortz (2026): WSINDy for model predictive control with applications to fusion, drones and chaos. Proceedings of the Royal Society A 482(2346), 20260413 (01.09.2026); Preprint arXiv 2604.23269. DOI nicht gesehen. https://royalsocietypublishing.org/rspa/article/482/2346/20260413/483307/WSINDy-for-model-predictive-control-with [nur Abstract] · Prüflauf: bestätigt.
- Kristian Lindbäck Løvland, Lars Struen Imsland, Bjarne A. Grimstad (2025): On a Closed-Loop Identification Challenge in Feedback Optimization. 2025 IEEE Conference on Control Technology and Applications (CCTA); Preprint arXiv:2509.01188. DOI 10.1109/CCTA53793.2025.11151368. https://ieeexplore.ieee.org/document/11151368/ [nur Abstract] · Prüflauf: bestätigt.
- Jan M. Maciejowski (2002): Predictive Control with Constraints. Pearson Education Limited / Prentice Hall, 331 S. (IX+331), ISBN 0-201-39823-0. DOI nicht gesehen. http://www-control.eng.cam.ac.uk/jmm/mpcbook/mpcbook.html [nur bibliografisch] · Prüflauf: bestätigt.
- Manzoor, W. A.; Rawashdeh, S.; Mohammadi, A. (2023): Vehicular Applications of Koopman Operator Theory—A Survey. IEEE Access, Bd. 11, S. 25917–25931 (Preprint: arXiv:2303.10471). DOI 10.1109/ACCESS.2023.3257109. https://ieeexplore.ieee.org/document/10068492/ [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel auf arXiv (abs/2303.10471) und IEEE Xplore (Dokument 10068492) bestätigt.
- Tayyab Manzoor, Yasir Ali, Yuanqing Xia, Lijie You, Yan Wang (2026): Physics-informed sparse identification-based tube model predictive control for aerial vehicles. arXiv 2605.23354 (Preprint, eingereicht 22.05.2026). DOI nicht gesehen. https://arxiv.org/abs/2605.23354 [nur Abstract] · Prüflauf: bestätigt.
- Maya-Rodriguez, Mario C.; Carvajal-Mariscal; Lopez-Pacheco; López-Muñoz; Tolentino-Eslava (bei den Koautoren nur Nachnamen im Suchauszug, Vornamen/Initialen nicht gesehen) (2025): Model-Free Identification of Heat Exchanger Dynamics Using Convolutional Neural Networks. Modelling (MDPI), Bd. 6, Heft 4, Art. 127. DOI 10.3390/modelling6040127. https://doi.org/10.3390/modelling6040127 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und DOI stimmen: Die DOI steht als URL im Suchergebnis, dazu ResearchGate 396580862.
- Meda, Luca; Stockar, Stephanie (Autoren NICHT im Suchergebnis gesehen, nur Angabe des Finders) (2025): Koopman-Based Methods for EV Climate Dynamics: Comparing eDMD Approaches. IEEE-Konferenzbeitrag (IEEE Xplore 11151334, Konferenzname nicht gesehen); Preprint arXiv:2504.03872. DOI nicht gesehen. https://ieeexplore.ieee.org/document/11151334/ [nur Abstract] · Prüflauf: bestätigt.
- Meda, L.; de Moura Souza, D.; Canova, M.; Stockar, S. (2026): Koopman-Based Model Predictive Control for Energy-Efficient Air Conditioning in Electric Vehicles. Journal of Dynamic Systems, Measurement, and Control 148(1), 011003 (ASME). DOI nicht gesehen. https://asmedigitalcollection.asme.org/dynamicsystems/article-abstract/148/1/011003/1219636/Koopman-Based-Model-Predictive-Control-for-Energy [nur Abstract] · Prüflauf: bestätigt.
- Meinshausen, Nicolai; Bühlmann, Peter (2010): Stability selection. Journal of the Royal Statistical Society Series B (Statistical Methodology) 72(4), S. 417-473. DOI 10.1111/j.1467-9868.2010.00740.x. https://rss.onlinelibrary.wiley.com/doi/full/10.1111/j.1467-9868.2010.00740.x [nur Abstract] · Prüflauf: bestätigt.
- Manfred Morari, Urban Maeder (2012): Nonlinear offset-free model predictive control. Automatica 48(9), S. 2059-2067. DOI 10.1016/j.automatica.2012.06.038. https://dl.acm.org/doi/abs/10.1016/j.automatica.2012.06.038 [nur Abstract] · Prüflauf: bestätigt.
- Morato, Marcelo M.; Felix, Monica S. (2024): Data Science and Model Predictive Control: A survey of recent advances on data-driven MPC algorithms. Journal of Process Control (erschienen November 2024). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0959152424001677 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Der Finder hatte die Autoren leer gelassen.
- John F. Muth (1960): Optimal Properties of Exponentially Weighted Forecasts. Journal of the American Statistical Association 55(290), S. 299-306. DOI 10.1080/01621459.1960.10482064. https://www.tandfonline.com/doi/abs/10.1080/01621459.1960.10482064 [nur Abstract] · Prüflauf: bestätigt.
- Abhinav Narasingam; Sang Hwan Son; Joseph Sang-Il Kwon (im Suchergebnis als Narasingam, A.; Son, S. H.; Kwon, J. S.-I.) (2023 (Journal); Preprint 2020): Data-driven feedback stabilisation of nonlinear systems: Koopman-based model predictive control. International Journal of Control 96(3), 770–781; Preprint arXiv:2005.09741. DOI 10.1080/00207179.2021.2013541. https://www.tandfonline.com/doi/full/10.1080/00207179.2021.2013541 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Die Journalfassung existiert: Die DOI steht in der Tandfonline-URL, die Seite zeigt Vol 96, No 3. Im Journal lautet der Titel britisch 'stabilisation', im arXiv-Preprint 'stabilization'. Autoren, Jahr 2023 und Seiten 770–781 standen nur im …
- Nelles, Oliver (2000): Nonlinear System Identification: From Classical Approaches to Neural Networks and Fuzzy Models. Springer, Berlin/Heidelberg (XVII, 786 S.). DOI 10.1007/978-3-662-04323-3. https://link.springer.com/book/10.1007/978-3-662-04323-3 [nur bibliografisch] · Prüflauf: korrigiert. Korrektur: Autor, Titel, Verlag und DOI stehen auf der Springer-Seite im Suchergebnis.
- Nielsen, Jonas Søeborg; Jacobsen, Marcus Galea; Olson, Albert Brincker; Sørensen, Mads Peter; Engsig-Karup, Allan Peter (2025): Physics-Informed Regression: Parameter Estimation in Parameter-Linear Nonlinear Dynamic Models. arXiv:2508.19249 (Preprint, eingereicht 25.07.2025; DTU Compute). DOI nicht gesehen. https://arxiv.org/abs/2508.19249 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Autoren waren beim Finder nicht angegeben, jetzt aus dem Suchergebnis ergänzt (Nielsen, Jacobsen, Olson, Sørensen, Engsig-Karup).
- Noack, Bernd R.; Afanasiev, Konstantin; Morzyński, Marek; Tadmor, Gilead; Thiele, Frank (2003): A hierarchy of low-dimensional models for the transient and post-transient cylinder wake. Journal of Fluid Mechanics 497, S. 335–363. DOI nicht gesehen. https://www.cambridge.org/core/journals/journal-of-fluid-mechanics/article/abs/hierarchy-of-lowdimensional-models-for-the-transient-and-posttransient-cylinder-wake/0F114BEB5DD20B7342E99ED8D0070C01 [nur Abstract] · Prüflauf: bestätigt.
- Feliks Nüske, Sebastian Peitz, Friedrich Philipp, Manuel Schaller, Karl Worthmann (2023): Finite-Data Error Bounds for Koopman-Based Prediction and Control. Journal of Nonlinear Science 33(1), 2023; Preprint arXiv 2108.07102. DOI 10.1007/s00332-022-09862-1. https://link.springer.com/article/10.1007/s00332-022-09862-1 [nur Abstract] · Prüflauf: bestätigt.
- Oberkampf, William L.; Roy, Christopher J. (2010): Verification and Validation in Scientific Computing. Cambridge University Press, ISBN 9780521113601. DOI nicht gesehen. https://www.cambridge.org/core/books/abs/verification-and-validation-in-scientific-computing/index/EE029CB068531D278AB2631911F8BE42 [nur Abstract] · Prüflauf: bestätigt.
- Brian J. Odelson, Murali R. Rajamani, James B. Rawlings (2006): A new autocovariance least-squares method for estimating noise covariances. Automatica 42, S. 303-308. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0005109805003262 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Seitenangabe des Finders (532-540) falsch: Suchergebnisse nennen zweimal S. 303-308.
- Frauke Oldewurtel, Alessandra Parisio, Colin N. Jones, Dimitrios Gyalistras, Markus Gwerder, Vanessa Stauch, Beat Lehmann, Manfred Morari (2012): Use of model predictive control and weather forecasts for energy efficient building climate control. Energy and Buildings 45, S. 15-27. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0378778811004105 [nur Abstract] · Prüflauf: bestätigt.
- Mohammed Osman, Yuanqing Xia, Mohammed Mahdi, Tayyab Manzoor, Abdulrahman H. Bajodah (2026): An Adaptive SINDy-Lyapunov Model Predictive Control Framework for Dual-System VTOL UAVs. International Journal of Robust and Nonlinear Control 36(5), 2388-2417. DOI 10.1002/rnc.70272. https://onlinelibrary.wiley.com/doi/10.1002/rnc.70272 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Die Autorenangabe des Finders war unklar ('Osman u. a.' oder 'M. Mahdi et al.'). Korrigiert: Laut Such-Zusammenfassung sind die Autoren M. Osman, Y. Xia, M. Mahdi, T. Manzoor und A. H. Bajodah.
- Pan, C.; Li, Y. (2023): Koopman Model Predictive Control of an Integrated Thermal Management System for Electric Vehicles. Journal of Dynamic Systems, Measurement, and Control (ASME), Bd. 145, Nr. 5, Art. 051005. DOI 10.1115/1.4062160. https://asmedigitalcollection.asme.org/dynamicsystems/article/145/5/051005/1160248/Koopman-Model-Predictive-Control-of-an-Integrated [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel, Zeitschrift, Band 145(5) und Art. 051005 bestätigt (ASME Digital Collection, OUCI). Ergänzt: Autoren (nur Initialen C. Pan, Y. Li gesehen) und DOI 10.1115/1.4062160 aus der Suchzusammenfassung; das Präfix 10.1115 stand in meiner …
- Pan; Li (nur Nachnamen im Suchtext; Yaoyu Li, UT Dallas, erscheint im Umfeld als ScienceDirect-Autorenseite, Zuordnung des Vornamens prüfen) (2024): Nonlinear model predictive control of chiller plant demand response with Koopman bilinear model and Krylov-subspace model reduction. Control Engineering Practice, Bd. 147 (Juni 2024), Artikel 105936. DOI 10.1016/j.conengprac.2024.105936. https://www.sciencedirect.com/science/article/abs/pii/S0967066124000960 [nur Abstract] · Prüflauf: bestätigt.
- Paniccia, Damiano; Tucci, Francesco Aldo; Guerrero, Joel; Capone, Luigi; Sanguini, Nicoletta (Schreibweise unsicher); Benacchio, Tommaso; Bottasso, Luigi (2025): A Supervised Machine-Learning Approach For Turboshaft Engine Dynamic Modeling Under Real Flight Conditions. arXiv:2502.14120 (Preprint); Journalfassung in The Aeronautical Journal (Cambridge Core). DOI nicht gesehen. https://arxiv.org/abs/2502.14120 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur betrifft die Venue: Neben dem arXiv-Preprint gibt es laut Cambridge Core eine Fassung in The Aeronautical Journal (PII S0001924025100249 in der URL). Deren DOI und Jahrgang habe ich nicht gesehen.
- Gabriele Pannocchia, Marco Gabiccini, Alessio Artoni (2015): Offset-free MPC explained: novelties, subtleties, and applications. IFAC-PapersOnLine 48(23), S. 342-351 (5th IFAC Conference on Nonlinear Model Predictive Control NMPC 2015, Sevilla). DOI 10.1016/j.ifacol.2015.11.304. https://www.sciencedirect.com/science/article/pii/S2405896315025884 [nur Abstract] · Prüflauf: bestätigt.
- Patil, Theotokatos, Tsitsilonis (Vornamen nicht im Suchergebnis gesehen; Theotokatos vermutlich Gerasimos, prüfen) (2025 (Vol. 24, No. 1, erschienen Januar 2025; online 2024 laut DOI und Dateiname im Strathprints-Repositorium)): Data-driven model for marine engine fault diagnosis using in-cylinder pressure signals. Journal of Marine Engineering & Technology, Vol. 24, No. 1 (Taylor & Francis). DOI 10.1080/20464177.2024.2432777. https://www.tandfonline.com/doi/full/10.1080/20464177.2024.2432777 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Autoren fehlten beim Finder.
- Patton, Andrew J.; Politis, Dimitris N.; White, Halbert (2009): Correction to "Automatic Block-Length Selection for the Dependent Bootstrap" by D. Politis and H. White. Econometric Reviews 28(4), S. 372-375. DOI 10.1080/07474930802459016. https://www.tandfonline.com/doi/full/10.1080/07474930802459016 [nur Abstract] · Prüflauf: bestätigt.
- Peherstorfer, Benjamin; Willcox, Karen (2016): Data-driven operator inference for nonintrusive projection-based model reduction. Computer Methods in Applied Mechanics and Engineering 306, S. 196-215. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0045782516301104 [nur Abstract] · Prüflauf: bestätigt.
- Peretzki, Daniel; Isaksson, Alf J.; Bittencourt, André Carvalho; Forsman, Krister (2011): Data Mining of Historic Data for Process Identification. AIChE Annual Meeting 2011, Minneapolis, MN, USA, 16.-21. Oktober 2011 (Konferenzbeitrag). DOI nicht gesehen. https://people.isy.liu.se/rt/andrecb/files/Peretzki_AICHE11.pdf [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: vollständige Mitautoren (Isaksson, Bittencourt, Forsman) und Tagung AIChE Annual Meeting 2011, Minneapolis, 16.-21.10.2011, laut Suchergebnis (Zitierung u. a. im Umfeld von Processes 2015, doi 10.3390/pr3020357); Autorenliste …
- Piroddi, L.; Spinelli, W. (2003): An identification algorithm for polynomial NARX models based on simulation error minimization. International Journal of Control 76(17), S. 1767–1781. DOI 10.1080/00207170310001635419. https://www.tandfonline.com/doi/abs/10.1080/00207170310001635419 [nur Abstract] · Prüflauf: bestätigt.
- Politis, Dimitris N.; Romano, Joseph P. (1994): The Stationary Bootstrap. Journal of the American Statistical Association 89(428), S. 1303-1313. DOI 10.1080/01621459.1994.10476870. https://www.tandfonline.com/doi/abs/10.1080/01621459.1994.10476870 [nur Abstract] · Prüflauf: bestätigt.
- Politis, Dimitris N.; White, Halbert (2004): Automatic Block-Length Selection for the Dependent Bootstrap. Econometric Reviews 23(1), S. 53-70. DOI 10.1081/ETC-120028836. https://www.tandfonline.com/doi/abs/10.1081/ETC-120028836 [nur Abstract] · Prüflauf: bestätigt.
- S. Joe Qin, Thomas A. Badgwell (2003): A survey of industrial model predictive control technology. Control Engineering Practice 11(7), S. 733-764. DOI 10.1016/S0967-0661(02)00186-7. https://www.sciencedirect.com/science/article/abs/pii/S0967066102001867 [nur Abstract] · Prüflauf: bestätigt.
- Markus Quade, Markus Abel, J. Nathan Kutz, Steven L. Brunton (2018): Sparse identification of nonlinear dynamics for rapid model recovery. Chaos: An Interdisciplinary Journal of Nonlinear Science 28(6), 063116; Preprint arXiv:1803.00894. DOI 10.1063/1.5027470. https://pubs.aip.org/aip/cha/article/28/6/063116/1059339/Sparse-identification-of-nonlinear-dynamics-for [nur Abstract] · Prüflauf: bestätigt.
- Racine, Jeffrey S. (2000): Consistent cross-validatory model-selection for dependent data: hv-block cross-validation. Journal of Econometrics 99(1), S. 39-61. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0304407600000300 [nur Abstract] · Prüflauf: bestätigt.
- Ribeiro, Antônio H.; Aguirre, Luis A. (2018): "Parallel Training Considered Harmful?": Comparing series-parallel and parallel feedforward network training. Neurocomputing 316, S. 222–231. DOI 10.1016/j.neucom.2018.07.071. https://www.sciencedirect.com/science/article/abs/pii/S0925231218309068 [nur Abstract] · Prüflauf: bestätigt.
- Ripa, Francesco; Astolfi, Daniele; Hamroun, Boussad; Regruto, Diego (2025): Integral action for bilinear systems with application to counter current heat exchanger. arXiv-Preprint arXiv:2507.16553. DOI nicht gesehen. https://arxiv.org/abs/2507.16553 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Der Finder hatte die Autoren leer gelassen.
- Clarence W. Rowley, Scott T. M. Dawson (2017): Model Reduction for Flow Analysis and Control. Annual Review of Fluid Mechanics 49, S. 387-417. DOI 10.1146/annurev-fluid-010816-060042. https://www.annualreviews.org/content/journals/10.1146/annurev-fluid-010816-060042 [nur Abstract] · Prüflauf: bestätigt.
- Samuel Rudy, Alessandro Alla, Steven L. Brunton, J. Nathan Kutz (2019): Data-Driven Identification of Parametric Partial Differential Equations. SIAM Journal on Applied Dynamical Systems 18(2), S. 643-660; Preprint arXiv:1806.00732. DOI 10.1137/18M1191944. https://doi.org/10.1137/18m1191944 [nur Abstract] · Prüflauf: bestätigt.
- Trivikram Satharasi, Tochukwu E. Ogri, Muzaffar Qureshi, Kyle Volle, Rushikesh Kamalapurkar (2026): Adaptive Control with Sparse Identification of Nonlinear Dynamics. arXiv:2604.06338 (Preprint, eingereicht 07.04.2026). DOI nicht gesehen. https://arxiv.org/abs/2604.06338 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Autoren ergänzt (laut Suchzusammenfassung).
- Tim Sauer, James A. Yorke, Martin Casdagli (1991): Embedology. Journal of Statistical Physics 65, 579-616. DOI 10.1007/BF01053745. https://link.springer.com/article/10.1007/BF01053745 [nur Abstract] · Prüflauf: bestätigt.
- Irene Schimperna, Lea Bold, Johannes Köhler, Karl Worthmann, Lalo Magni (2025): Stability of data-driven Koopman MPC with terminal conditions. arXiv 2511.21248 (Preprint, eingereicht 26.11.2025, revidiert 10.04.2026); laut arXiv-Eintrag angenommen für die 24th European Control Conference (ECC) 2026. DOI nicht gesehen. https://arxiv.org/abs/2511.21248 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Autoren und arXiv-ID im Suchergebnis gesehen.
- Irene Schimperna, Karl Worthmann, Manuel Schaller, Lea Bold, Lalo Magni (2026): Data-driven model predictive control: Asymptotic stability despite approximation errors exemplified in the Koopman framework. Automatica (2026); Preprint arXiv 2505.05951. DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S0005109826003870 [nur Abstract] · Prüflauf: bestätigt.
- Schoukens, Maarten; Noël, Jean-Philippe (2017): Three Benchmarks Addressing Open Challenges in Nonlinear System Identification. IFAC-PapersOnLine 50(1), S. 446-451 (20. IFAC World Congress). DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896317300915 [nur Abstract] · Prüflauf: bestätigt.
- Schoukens, Johan; Ljung, Lennart (2019): Nonlinear System Identification: A User-Oriented Road Map. IEEE Control Systems Magazine 39(6), S. 28–99. DOI 10.1109/MCS.2019.2938121. https://research.tue.nl/en/publications/nonlinear-system-identification-a-user-oriented-road-map/ [nur Abstract] · Prüflauf: bestätigt.
- Shardt, Yuri A. W.; Huang, Biao (2011): Closed-loop identification condition for ARMAX models using routine operating data. Automatica 47(7), S. 1534-1537. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0005109811002263 [nur Abstract] · Prüflauf: bestätigt.
- Shardt, Yuri A. W.; Huang, Biao (2011): Closed-loop identification with routine operating data: Effect of time delay and sampling time. Journal of Process Control 21, S. 997-1010. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0959152411001259 [nur Abstract] · Prüflauf: bestätigt.
- Shardt, Yuri A. W.; Huang, Biao (2013): Data quality assessment of routine operating data for process identification. Computers & Chemical Engineering 55, S. 19-27. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S009813541300094X [nur Abstract] · Prüflauf: bestätigt.
- Shi, Yao; Zhang, Zhiming; Chen, Xiaoqiang; Xie, Lei; Liu, Xueqin; Su, Hongye (2023): Data-Driven model identification and efficient MPC via quasi-linear parameter varying representation for ORC waste heat recovery system. Energy, Bd. 271 (C) (Elsevier); PII S0360544223003535. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0360544223003535 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel exakt bestätigt (ScienceDirect-Treffer).
- Shook, D. S.; Mohtadi, C.; Shah, S. L. (1991): Identification for long-range predictive control. IEE Proceedings D (Control Theory and Applications) 138(1), S. 75-84. DOI nicht gesehen.  [nur bibliografisch] · Prüflauf: korrigiert. Korrektur: Metadaten (Shook/Mohtadi/Shah, 1991, IEE Proc.
- Shook, D. S.; Mohtadi, C.; Shah, S. L. (1992): A control-relevant identification strategy for GPC. IEEE Transactions on Automatic Control 37(7), S. 975-980. DOI nicht gesehen. https://ieeexplore.ieee.org/document/148352/ [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt/korrigiert: Autoren Shook/Mohtadi/Shah, Jahr 1992, IEEE Trans.
- Lim C. Siang; Shams Elnawawi; Lee D. Rippon; Daniel L. O'Connor; R. Bhushan Gopaluni (2023 (begutachtete Fassung); Preprint 2022): Data Quality Over Quantity: Pitfalls and Guidelines for Process Analytics. 22nd IFAC World Congress 2023, ScienceDirect PII S2405896323013046 (ISSN-Präfix 2405-8963 = IFAC-PapersOnLine, Band nicht gesehen); Preprint arXiv:2211.06440. DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896323013046 [nur Abstract] · Prüflauf: korrigiert. Korrektur: arXiv-Angabe des Finders stimmt, aber es gibt eine begutachtete Fassung (IFAC World Congress 2023 auf ScienceDirect, auch DAIS-Lab-Seite 2023C3_siang_ifac); diese statt des Preprints zitieren.
- Sirola, M.; McBreen, J.; Esfarjani, M.R. (nur aus dem Zusammenfassungstext der Suche, nicht aus einem Titel oder einer URL; prüfen) (2026): Charge Air System in an Experimental Combustion Engine—Combined Simulation Model: A Digital Twin Approach Including Advanced Control Concepts. Sensors 26(12), 3854 (MDPI), veröffentlicht 17.06.2026. DOI 10.3390/s26123854. https://doi.org/10.3390/s26123854 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur/Ergänzung: Die Vermutung des Finders (Sensors 26(12)) bestätigt sich, dazu Artikelnummer 3854 und Datum 17.06.2026.
- S. Sivaranjani; Yuanyuan Shi; Nikolay Atanasov; Thai Duong; Jie Feng; Tim Martin; Yuezhu Xu; Vijay Gupta; Frank Allgöwer (2025): Control-Oriented System Identification: Classical, Learning, and Physics-Informed Approaches. arXiv-Preprint arXiv:2512.06315 (eess.SY, v2 vorhanden). DOI nicht gesehen. https://arxiv.org/abs/2512.06315 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und arXiv-ID bestätigt.
- Skogestad, Sigurd; Postlethwaite, Ian (2005 (2. Aufl.)): Multivariable Feedback Control: Analysis and Design. John Wiley & Sons, 2. Aufl. 2005, 608 S.; ISBN 978-0-470-01168-3 (Softcover), 978-0-470-01167-6 (Hardcover). DOI nicht gesehen. https://www.wiley.com/en-us/multivariable-feedback-control-analysis-and-design-2nd-edition-p-9780470011683 [nur Abstract] · Prüflauf: bestätigt.
- Staiger, Douglas; Stock, James H. (1997): Instrumental Variables Regression with Weak Instruments. Econometrica 65(3), S. 557-586. DOI nicht gesehen. https://www.econometricsociety.org/publications/econometrica/1997/05/01/instrumental-variables-regression-weak-instruments [nur Abstract] · Prüflauf: bestätigt.
- J. Stark (1999): Delay Embeddings for Forced Systems. I. Deterministic Forcing. Journal of Nonlinear Science 9, 255-332. DOI 10.1007/s003329900072. https://link.springer.com/article/10.1007/s003329900072 [nur Abstract] · Prüflauf: bestätigt.
- J. Stark, D. S. Broomhead, M. E. Davies, J. Huke (2003): Delay Embeddings for Forced Systems. II. Stochastic Forcing. Journal of Nonlinear Science 13, 519-577. DOI 10.1007/s00332-003-0534-4. https://link.springer.com/article/10.1007/s00332-003-0534-4 [nur Abstract] · Prüflauf: bestätigt.
- Sokratis Stoumpos; Gerasimos Theotokatos; Christoforos Mavrelos; Evangelos Boulougouris (2020): Towards Marine Dual Fuel Engines Digital Twins—Integrated Modelling of Thermodynamic Processes and Control System Functions. Journal of Marine Science and Engineering 8(3), Art. 200 (MDPI). DOI nicht gesehen. https://www.mdpi.com/2077-1312/8/3/200 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Autoren (University of Strathclyde, Maritime Safety Research Centre).
- Sokratis Stoumpos, Gerasimos Theotokatos (2022): A novel methodology for marine dual fuel engines sensors diagnostics and health management. International Journal of Engine Research (SAGE). DOI 10.1177/1468087421998635. https://journals.sagepub.com/doi/full/10.1177/1468087421998635 [nur Abstract] · Prüflauf: bestätigt.
- Strässer, Robin; Worthmann, Karl; Mezić, Igor; Berberich, Julian; Schaller, Manuel; Allgöwer, Frank (2026): An overview of Koopman-based control: From error bounds to closed-loop guarantees. Annual Reviews in Control, Vol. 61, Art. 101035; Preprint arXiv:2509.02839. DOI 10.1016/j.arcontrol.2025.101035. https://www.sciencedirect.com/science/article/pii/S1367578825000495 [nur Abstract] · Prüflauf: bestätigt.
- Amit Surana, Andrzej Banaszuk (2016): Linear observer synthesis for nonlinear systems using Koopman Operator framework. IFAC-PapersOnLine 49(18), S. 716-723 (10th IFAC Symposium on Nonlinear Control Systems, NOLCOS 2016). DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896316318304 [nur Abstract] · Prüflauf: bestätigt.
- Söderström, Torsten; Stoica, Petre (1989): System Identification. Prentice Hall International (Prentice Hall International Series in Systems and Control Engineering), ISBN 0138812365 / 9780138812362. DOI nicht gesehen. https://www.cambridge.org/core/journals/econometric-theory/article/abs/system-identificationt-soderstrom-and-p-stoica-prentice-hall-international-1989/586555F5E831891F67178147691D3D11 [nur bibliografisch] · Prüflauf: bestätigt.
- Torsten Söderström (2007): Errors-in-variables methods in system identification. Automatica 43(6), S. 939-958. DOI 10.1016/j.automatica.2006.11.025. https://www.sciencedirect.com/science/article/abs/pii/S0005109807000714 [nur Abstract] · Prüflauf: bestätigt.
- Floris Takens (1981): Detecting strange attractors in turbulence. In: Dynamical Systems and Turbulence, Warwick 1980, Lecture Notes in Mathematics 898, Springer, ab S. 366. DOI 10.1007/BFb0091924. https://link.springer.com/chapter/10.1007/BFb0091924 [nur bibliografisch] · Prüflauf: bestätigt.
- Theiler, J.; Eubank, S.; Longtin, A.; Galdrikian, B.; (Farmer, J. D. als fünfter Autor in den Suchergebnissen nicht gesehen) (1992): Testing for nonlinearity in time series: the method of surrogate data. Physica D: Nonlinear Phenomena 58(1-4), S. 77-94. DOI 10.1016/0167-2789(92)90102-S. https://www.sciencedirect.com/science/article/abs/pii/016727899290102S [nur Abstract] · Prüflauf: bestätigt.
- Jonathan H. Tu, Clarence W. Rowley, Dirk M. Luchtenburg, Steven L. Brunton, J. Nathan Kutz (2014): On dynamic mode decomposition: Theory and applications. Journal of Computational Dynamics 1, S. 391-421. DOI nicht gesehen. https://arxiv.org/abs/1312.0041 [nur Abstract] · Prüflauf: bestätigt.
- Tufa, L. D.; Ka, C. Z. (2016): Effect of Model Plant Mismatch on MPC Performance and Mismatch Threshold Determination. Procedia Engineering, Bd. 148, S. 1008-1014. DOI 10.1016/j.proeng.2016.06.518. https://www.sciencedirect.com/science/article/pii/S1877705816309857 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt, kein Widerspruch: Der Finder hatte die Autoren leer gelassen und Jahr und Venue nur vermutet.
- Aurelio Raffa Ugolini; Valentina Breschi; Andrea Manzoni; Mara Tanelli (2024): SINDy vs Hard Nonlinearities and Hidden Dynamics: a Benchmarking Study. arXiv:2403.00578 (Preprint); Workshop on Nonlinear System Identification Benchmarks 2024; eine Verlagsfassung liegt auf ScienceDirect unter PII S2405896324012837. DOI nicht gesehen. https://arxiv.org/abs/2403.00578 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel, Jahr und arXiv-ID bestätigt.
- Mohamed Vall, O. M.; M'hiri, R. (Autoren im Suchergebnis nicht angezeigt, ungeprüft) (2008): An approach to polynomial NARX/NARMAX systems identification in a closed-loop with variable structure control. International Journal of Automation and Computing (heute Machine Intelligence Research), Springer. DOI 10.1007/s11633-008-0313-7. https://link.springer.com/article/10.1007/s11633-008-0313-7 [nur Abstract] · Prüflauf: bestätigt.
- Van den Hof, Paul M. J.; Schrama, Ruud J. P. (1993): An indirect method for transfer function estimation from closed loop data. Automatica 29, S. 1523–1527 (Heft 6 im Suchergebnis nicht gesehen). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/000510989390015L [nur Abstract] · Prüflauf: bestätigt.
- Verhoek, Abbas, Tóth, Haesaert (2021): Data-Driven Predictive Control for Linear Parameter-Varying Systems. IFAC-PapersOnLine 54(8), S. 101-108 (4th IFAC Workshop on Linear Parameter Varying Systems, LPVS 2021); Preprint arXiv:2103.16160. DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896321013641 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur/Ergänzung: Autoren Verhoek, Abbas, Tóth, Haesaert (nur Nachnamen gesehen); veröffentlicht in IFAC-PapersOnLine 54(8), 101-108, 2021, LPVS 2021 (Suchzusammenfassung, ScienceDirect-PII S2405896321013641, TU-Eindhoven-Portal).
- Yang Wang, Stephen P. Boyd (2010): Fast Model Predictive Control Using Online Optimization. IEEE Transactions on Control Systems Technology 18, S. 267-278. DOI nicht gesehen. https://www.researchgate.net/publication/224557816_Fast_Model_Predictive_Control_Using_Online_Optimization [nur Abstract] · Prüflauf: bestätigt.
- Wirgin, Armand (2004): The inverse crime. arXiv:math-ph/0401050 (Preprint). DOI nicht gesehen. https://arxiv.org/abs/math-ph/0401050 [nur Abstract] · Prüflauf: bestätigt.
- Yue Wu (Xi'an Jiaotong University; laut Suchzusammenfassung, Einzelautorschaft nicht sicher geprüft) (2026): Control-Channel Informativity for Koopman EDMDc under Behavior-Policy Data. arXiv:2605.17966 (Preprint, eingereicht 18.05.2026). DOI nicht gesehen. https://arxiv.org/abs/2605.17966 [nur Abstract] · Prüflauf: bestätigt.
- Yue Wu (School of Automation Science and Engineering, Xi'an Jiaotong University; laut Suchzusammenfassung) (2026): Diagnostic Certificates of Data Quality and Regression Identifiability for Koopman Identification. arXiv:2605.09545 (Preprint, eingereicht 12.05.2026). DOI nicht gesehen. https://arxiv.org/abs/2605.09545 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Autor ergänzt (Finder hatte keinen).
- Yahagi, S.; Seto, H.; Yonezawa, A. u. a. (vollständige Liste nicht gesehen) (2025): Sparse Identification and Nonlinear Model Predictive Control for Diesel Engine Air Path System. International Journal of Control, Automation, and Systems 23, S. 620-629. DOI 10.1007/s12555-024-0452-9. https://link.springer.com/article/10.1007/s12555-024-0452-9 [nur Abstract] · Prüflauf: bestätigt.
- Yahagi, Shuichi; Yonezawa, Ansei; Seto, Hiroki; Yonezawa, Heisei; Kajiwara, Itsuro (2025): Sparse Identification of Nonlinear Dynamics Enhanced by Ensemble Learning, Multi-Step Prediction Evaluation, Elite Strategy, and Classification Techniques for Applications to Industrial Systems. arXiv:2503.05154 (Preprint, März 2025). DOI nicht gesehen. https://arxiv.org/abs/2503.05154 [nur Abstract] · Prüflauf: bestätigt.
- Yahagi, Shuichi; Yonezawa, Ansei; Yonezawa, Heisei; Seto, Hiroki; Kajiwara, Itsuro (2026): Generalized bilinear Koopman realization from input-output data for multi-step prediction with metaheuristic optimization of lifting function and its application to real-world industrial system. arXiv:2602.15422 (Preprint, eingereicht 17.02.2026, eess.SY). DOI nicht gesehen. https://arxiv.org/abs/2602.15422 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Die Autorenliste des Finders („Yahagi, Shuichi u. a.“) war unvollständig.
- Ansei Yonezawa, Heisei Yonezawa, Shuichi Yahagi, Itsuro Kajiwara, Shinya Kijimoto, Hikaru Taniuchi, Kentaro Murakami (2026): Sparse Identification of Nonlinear Dynamics With Library Optimization Mechanism: Recursive Long-Term Prediction Perspective. IEEE Transactions on Cybernetics 56(5), 2475-2488 (Mai 2026); Preprint arXiv:2507.18220. DOI 10.1109/TCYB.2026.3652850. https://ieeexplore.ieee.org/document/11365958/ [nur Abstract] · Prüflauf: bestätigt.
- Yousefi, M.; Gopaluni, R. B.; Loewen, P. D.; Forbes, M. G.; Dumont, G. A.; Backstrom, J. (2015): Impact of model plant mismatch on performance of control systems: An application to paper machine control. Control Engineering Practice, Bd. 43, S. 59-68. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S096706611500132X [nur Abstract] · Prüflauf: korrigiert. Korrektur: Ergänzt: Der Finder hatte die Autoren leer gelassen, Jahr und Journal waren nur vermutet.
- Yu, Liuqian; Fennel, Katja; Wang, Bin; Laurent, Arnaud; Thompson, Keith R.; Shay, Lynn K. (2019): Evaluation of nonidentical versus identical twin approaches for observation impact assessments: an ensemble-Kalman-filter-based ocean assimilation application for the Gulf of Mexico. Ocean Science 15, S. 1801-1814. DOI 10.5194/os-15-1801-2019. https://os.copernicus.org/articles/15/1801/2019/ [nur Abstract] · Prüflauf: bestätigt.
- Linan Zhang, Hayden Schaeffer (2019): On the Convergence of the SINDy Algorithm. Multiscale Modeling & Simulation 17(3), 948-972. DOI nicht gesehen. https://arxiv.org/abs/1805.06445 [nur Abstract] · Prüflauf: bestätigt.
- Jiadi Zhang, Mohammad Reza Amini, Ilya Kolmanovsky, Munechika Tsutsumi, Hayato Nakada (2022): Development of a Model Predictive Airpath Controller for a Diesel Engine on a High-Fidelity Engine Model with Transient Thermal Dynamics. arXiv:2202.12803 [eess.SY], eingereicht 25.02.2022 (Preprint); PDF-Kopf nennt 2022 American Control Conference (ACC), 8.–10.06.2022, Atlanta, GA. DOI nicht gesehen. https://arxiv.org/abs/2202.12803 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur: Die Autorenliste war unvollständig („Zhang, Jiadi u. a.“). Die vollständige Liste stammt aus dem Suchergebnis (arXiv-Listing).
- Zhang, Qi u. a. (Mitautoren im Suchergebnis nicht sichtbar) (2024): Nonlinear sparse variational Bayesian learning based model predictive control with application to PEMFC temperature control. Control Engineering Practice (Elsevier); Preprint arXiv:2404.09519. DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0967066124001126 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Korrektur betrifft die Zeitschrift, die der Finder offengelassen hatte.
- Zhao, Peng; Yu, Bin (2006): On Model Selection Consistency of Lasso. Journal of Machine Learning Research 7, S. 2541-2563. DOI nicht gesehen. https://www.jmlr.org/papers/v7/zhao06a.html [nur Abstract] · Prüflauf: bestätigt.
- Zinage, S.; Jadhav, S.; Zhou, Y.; Bilionis, I.; Meckl, P. (nicht im Suchergebnis gesehen) (2022): Data Driven Modeling of Turbocharger Turbine using Koopman Operator. IFAC-PapersOnLine (ScienceDirect PII S2405896322028233); Preprint arXiv:2204.10421. DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896322028233 [nur Abstract] · Prüflauf: bestätigt.
- Autoren offen (2021 (Journal-Fassung, laut Suchtext September 2021); Konferenzfassung gleichen Titels 2020): MPC closed-loop identification without excitation. Journal of Process Control (PII S0959152421001438); gleichnamige Konferenzfassung IFAC World Congress 2020, IFAC-PapersOnLine (PII S2405896320311770). DOI 10.1016/j.jprocont.2021.08.018. https://www.sciencedirect.com/science/article/abs/pii/S0959152421001438 [nur Abstract] · Prüflauf: bestätigt.
- Autoren offen (2022): Nonlinear Model Identification and Observer Design for Thrust Estimation of Small-scale Turbojet Engines. 2022 IEEE International Conference on Robotics and Automation (ICRA), Philadelphia; IEEE Xplore Dokument 9812283; Preprint arXiv:2205.08330. DOI nicht gesehen. https://ieeexplore.ieee.org/document/9812283/ [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel, Jahr und arXiv-ID bestätigt.
- Autoren offen (2024): Model Discrepancy Learning for Heat Exchanger Networks. IFAC-PapersOnLine (laut Suchzusammenfassung; PII S2405896324011005 passt zur ISSN 2405-8963), online 05.09.2024; Band/Seiten nicht gesehen. DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S2405896324011005 [nur Abstract] · Prüflauf: bestätigt.
- Autoren offen (2025 (nur aus PII S0967066125… abgeleitet, nicht explizit gesehen)): Data-driven Koopman model predictive control for the integrated thermal management of electric vehicles. ScienceDirect, PII S0967066125000863 (ISSN-Präfix 0967-0661 = Control Engineering Practice; Zeitschriftenname im Ergebnis nicht explizit gesehen). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0967066125000863 [nur Abstract] · Prüflauf: bestätigt.
- Autoren offen (2026): An Assessment of the Operation Under Different Ambient Conditions of the Charge–Air Cooler for a Large Marine Diesel Engine. Journal of Marine Science and Engineering (MDPI), Band 14, Art. 845 (laut DOI). DOI 10.3390/jmse14090845. https://doi.org/10.3390/jmse14090845 [nur Abstract] · Prüflauf: korrigiert. Korrektur: Titel und DOI als Ergebnis-URL gesehen.
- Autoren offen (2026): Bilinear Koopman-Based Robust Model Predictive Control for Unknown Nonlinear Systems via Contraction Metrics. arXiv:2607.25658 (Preprint). DOI nicht gesehen. https://arxiv.org/abs/2607.25658 [nur Abstract] · Prüflauf: bestätigt.
- Autoren offen (2026 (arXiv-Einreichung 18.05.2026)): Data-Driven Dynamic Modeling of a Tendon-Actuated Continuum Robot. arXiv:2605.18720 (Preprint). DOI nicht gesehen. https://arxiv.org/abs/2605.18720 [nur Abstract] · Prüflauf: bestätigt.

### Nur einmal gesehen, nicht gegengeprüft (†, letzte Nachrecherche)

- † Patrik Valábek, Michaela Horváthová, Gabriele Pannocchia, Martin Klaučo (2026): Experimental validation of deep Koopman MPC for real-time pasteurization unit control. Control Engineering Practice (ScienceDirect PII S0967066125004253; Band/Seiten nicht sichtbar). Vorfassung als SSRN-Preprint (abstract_id 5339590), Datensatz auf Zenodo (Record 18169784). DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S0967066125004253 [nur Abstract]
- † Patrik Valábek, Michaela Horváthová, Martin Klaučo (2026): Performance Trade-Offs in Koopman-Based MPC for a Heat Exchanger. SSRN (Preprint/Working Paper, abstract_id 7493739). DOI nicht gesehen. https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7493739 [nur Abstract]
- † Autoren offen (2021): Dynamic mode decomposition for nonintrusive and robust model predictive control of residential heating systems. Energy and Buildings (ScienceDirect PII S0378778821007349; Band/Seiten nicht sichtbar). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0378778821007349 [nur Abstract]
- † Yue Wu u. a. (nur Erstautor aus Suchzusammenfassung, Autorenliste am arXiv-Eintrag prüfen) (2025): Mechanism-Guided Residual Lifting and Control Consistent Modeling for Pneumatic Drying Processes. arXiv 2510.24370. DOI nicht gesehen. https://arxiv.org/pdf/2510.24370 [nur Abstract]
- † Autoren offen (2025): Online Learning Control Strategies for Industrial Processes with Application for Loosening and Conditioning. arXiv 2506.08983. DOI nicht gesehen. https://arxiv.org/abs/2506.08983 [nur Abstract]
- † Autoren offen (2024 (aus PII abgeleitet, prüfen)): Real-time application of Koopman-based optimal control strategies for fuel cell stack thermal management. Control Engineering Practice (ScienceDirect PII S0967066124003848; Band/Seiten nicht sichtbar). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0967066124003848 [nur Abstract]
- † Ryo Miyashita, Yoshihiko Susuki, Atsushi Ishigame (2022): Koopman-Model Predictive Control with Signal Temporal Logic Specifications for Temperature Regulation of a Warm-Water Supply System. arXiv 2207.04184. DOI nicht gesehen. https://arxiv.org/abs/2207.04184 [nur Abstract]
- † Patrik Valábek, Michaela Horváthová, Martin Klaučo (2025): Deep Koopman Economic Model Predictive Control of a Pasteurisation Unit. arXiv 2511.04437. DOI nicht gesehen. https://arxiv.org/abs/2511.04437 [nur Abstract]
- † Autoren offen (2024): Multi-objective optimization of building HVAC operation: Advanced strategy using Koopman predictive control and deep learning. Building and Environment (ScienceDirect PII S0360132323011009; ADS-Bibcode 2024BuEnv.24811073S). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0360132323011009 [nur Abstract]
- † Autoren offen (2023 (aus PII abgeleitet, prüfen)): Data-driven identification and fast model predictive control of the ORC waste heat recovery system by using Koopman operator. Control Engineering Practice (ScienceDirect PII S0967066123002484; Band/Seiten nicht sichtbar). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0967066123002484 [nur Abstract]
- † Jeon, Tae-Youl; Jung, Byung-Gun (Namen aus der Suchzusammenfassung zum Preprints.org-Eintrag 202309.1594; gegen MDPI-Seite prüfen) (2023): A Study of PI Controller Tuning Methods Using the Internal Model Control Guide for a Ship Central Cooling System as a Multi-Input, Single-Output System. Journal of Marine Science and Engineering (MDPI), Bd. 11, H. 10, Art. 2025 (laut URL), Oktober 2023; Preprint: Preprints.org 202309.1594. DOI nicht gesehen. https://www.mdpi.com/2077-1312/11/10/2025 [nur Abstract]
- † Jeon u. a. (Suchzusammenfassung: "Jeon and Lee"; Vornamen und vollständige Autorenliste nicht sichtbar) (2025): Energy Saving in Ship Central Cooling Systems: IMC-Tuned PID with Feedforward Control. Journal of Marine Science and Engineering (MDPI), Bd. 13, H. 3, Art. 510 (laut DOI/URL), März 2025. DOI 10.3390/jmse13030510. https://doi.org/10.3390/jmse13030510 [nur Abstract]
- † Jeon u. a. (laut Suchzusammenfassung; vollständige Autorenliste nicht sichtbar) (2022): A Study on the Control Solution of Ship’s Central Fresh Water-Cooling System for Efficient Energy Control Based on Merchant Training Ship. Journal of Marine Science and Engineering (MDPI), Bd. 10, H. 5, Art. 679 (laut URL). DOI nicht gesehen. https://www.mdpi.com/2077-1312/10/5/679 [nur Abstract]
- † Lee, Chang-Min; Jeon, Tae-Youl; Jung, Byung-Gun; Lee, Young-Chan (aus der Suchzusammenfassung zum ResearchGate-Eintrag; prüfen) (2021): Design of Energy Saving Controllers for Central Cooling Water Systems. Journal of Marine Science and Engineering (MDPI), Bd. 9, H. 5, Art. 513 (laut URL), Mai 2021. DOI nicht gesehen. https://www.mdpi.com/2077-1312/9/5/513 [nur Abstract]
- † Autoren offen (2025): Modeling and Key Parameter Interaction Analysis for Ship Central Cooling Systems. Applied Sciences (MDPI), Bd. 15, H. 13, Art. 7241 (laut DOI/URL). DOI 10.3390/app15137241. https://doi.org/10.3390/app15137241 [nur Abstract]
- † Tavakoli, S.; Schramm, J.; Pedersen, E. (2021 (Papiernummer 2021-01-5062; Suchzusammenfassung nennt Erscheinungsdatum 1. Januar 2022, prüfen)): Strategies on Methane Slip Mitigation of Spark-Ignition Natural Gas Engine during Transient Motion. SAE Technical Paper 2021-01-5062, SAE International. DOI nicht gesehen. https://www.sae.org/publications/technical-papers/content/2021-01-5062/ [nur Abstract]
- † im Auszug nicht sichtbar (Treffer eines DTU-Orbit-Eintrags bei Suche nach Tavakoli/Pedersen/Schramm; Zuordnung prüfen) (2020): Modeling and analysis of performance and emissions of marine lean-burn natural gas engine propulsion in waves. Applied Energy (Elsevier). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0306261920313696 [nur Abstract]
- † Autoren offen (2024 (Bd. 19, H. 10; DOI-Kennung enthält 2023)): Temperature control characteristics of intelligent cooling system for high-speed marine diesel engine. Ships and Offshore Structures (Taylor & Francis), Bd. 19, H. 10. DOI 10.1080/17445302.2023.2249201. https://www.tandfonline.com/doi/abs/10.1080/17445302.2023.2249201 [nur Abstract]
- † Autoren offen (2025): Effects of Varying the Air-Fuel Equivalence Ratio at Different EGR-Rates on a Medium-Speed LNG-Diesel Dual-Fuel Engine. SAE Technical Paper 2025-24-0041, SAE International. DOI nicht gesehen. https://saemobilus.sae.org/papers/effects-varying-air-fuel-equivalence-ratio-different-egr-rates-a-medium-speed-lng-diesel-dual-fuel-engine-2025-24-0041 [nur Abstract]
- † Autoren offen (nicht im Auszug sichtbar (IEEE-Dokument 10804655, vermutlich 2024/2025, prüfen)): Data-Driven Predictive Control of Bilinear HVAC Dynamics—An Experimental Case Study. IEEE Journals & Magazine (Zeitschrift im Auszug nicht genannt). DOI nicht gesehen. https://ieeexplore.ieee.org/document/10804655/ [nur Abstract]
- † Autoren offen (2026 (arXiv-ID 2601.11901)): Least-Squares Multi-Step Koopman Operator Learning for Model Predictive Control (HTML-Version: A Least-Squares Multi-Step Koopman Operator for Model Predictive Control). arXiv 2601.11901. DOI nicht gesehen. https://arxiv.org/abs/2601.11901 [nur Abstract]
- † Autoren offen (2025 (arXiv-ID 2512.14510)): Closed-Loop Consistent, Causal Data-Driven Predictive Control via SSARX. arXiv 2512.14510. DOI nicht gesehen. https://arxiv.org/html/2512.14510 [nur Abstract]
- † Autoren offen (2021 (aus PII S0098135421000545 abgeleitet, prüfen)): Model predictive control using subspace model identification. ScienceDirect, PII S0098135421000545 (Zeitschrift im Auszug nicht genannt; ISSN-Präfix deutet auf Computers & Chemical Engineering, prüfen). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0098135421000545 [nur Abstract]
- † Saman Mostafavi u. a. (laut Auszug „Saman Mostafavi and 3 other authors“) (2022): Nonlinear Moving Horizon Estimation and Model Predictive Control for Buildings with Unknown HVAC Dynamics. arXiv 2211.10097. DOI nicht gesehen. https://arxiv.org/abs/2211.10097 [nur Abstract]
- † Autoren offen (2019 (arXiv-ID 1906.00352)): Linear Model-Predictive Controller (LMPC) for Building's Heating Ventilation and Air Conditioning (HVAC) System. arXiv 1906.00352. DOI nicht gesehen. https://arxiv.org/pdf/1906.00352 [nur bibliografisch]
- † Autoren offen (2022 (aus PII S1359431122006160 abgeleitet, prüfen)): Gain scheduling model predictive controller design for tankless gas water heaters with time-varying delay. ScienceDirect, PII S1359431122006160 (Zeitschrift im Auszug nicht genannt; ISSN-Präfix deutet auf Applied Thermal Engineering, prüfen). DOI nicht gesehen. https://www.sciencedirect.com/science/article/pii/S1359431122006160 [nur Abstract]
- † Autoren offen (nicht im Auszug sichtbar (ISBN-Präfix 978-3-032, vermutlich 2025/2026, prüfen)): Non-linear Control of HVAC Heat Exchangers with Gain Scheduling. Springer Nature Link, Buchkapitel (Buchtitel im Auszug nicht genannt). DOI 10.1007/978-3-032-10546-2_36. https://link.springer.com/chapter/10.1007/978-3-032-10546-2_36 [nur bibliografisch]
- † Autoren offen (2022 (arXiv-ID 2202.13291)): A Simple Discretization Scheme for Gain Matrix Conditioning. arXiv 2202.13291. DOI nicht gesehen. https://arxiv.org/pdf/2202.13291 [nur Abstract]
- † Max Rose u. a. (2024): Model Predictive Control of District Heating Grids Using Stabilizing Terminal Ingredients. arXiv 2404.01820. DOI nicht gesehen. https://arxiv.org/abs/2404.01820 [nur Abstract]
- † Autoren offen (2020): System identification of a hysteresis-controlled pump system using SINDy. arXiv:2003.07465 (Preprint); Konferenzfassung „Robust system identification for hysteresis-controlled devices using SINDy“, IEEE Xplore Dokument 9254626; Fraunhofer-Publica-Eintrag. DOI nicht gesehen. https://arxiv.org/abs/2003.07465 [nur Abstract]
- † Autoren offen (2024): Bias correction and instrumental variables for direct data-driven model-reference control. arXiv:2411.05740 (Preprint). DOI nicht gesehen. https://arxiv.org/pdf/2411.05740 [nur bibliografisch]
- † Do, Loi u. a. (Suchergebnis: „authors including Loi Do“, Erstautorschaft nicht gesichert) (2024): Practical Guidelines for Data-driven Identification of Lifted Linear Predictors for Control. arXiv:2408.01116 (Preprint, August 2024); Matlab-Code im GitHub-Repository aa4cc/Lifted-Linear-Predictors-Guidelines. DOI nicht gesehen. https://arxiv.org/abs/2408.01116 [nur Abstract]
- † Autoren offen (2021 (aus PII abgeleitet, prüfen)): Simultaneous identification of linear building dynamic model and disturbance using sparsity-promoting optimization. ScienceDirect PII S0005109821001515 (ISSN in der PII entspricht Automatica; im Auszug nicht ausgeschrieben). DOI nicht gesehen. https://www.sciencedirect.com/science/article/abs/pii/S0005109821001515 [nur Abstract]

### DOI-Importliste für Zotero (DOI stand selbst im Suchergebnis)

```text
10.1016/j.compchemeng.2021.107411  % abdullahSparseidentificationbasedModelPredictive2021
10.1007/s12239-020-0092-x  % aranDieselEngineAirpath2020
10.1016/j.jprocont.2009.04.007  % badweDetectionModelplantMismatch2009
10.1002/0471725153  % belsleyRegressionDiagnosticsIdentifying1980
10.1007/BFb0109870  % bemporadRobustModelPredictive1999
10.1016/S0005-1098(01)00174-1  % bemporadExplicitLinearQuadratic2002
10.1007/s41104-021-00087-0  % beranModelbasedApproachControl2021
10.1007/978-3-658-35588-3_19  % beranChargeAirCoolingHigh2021
10.1016/j.ins.2011.12.028  % bergmeirUseCrossvalidationTime2012
10.1016/j.csda.2017.11.003  % bergmeirNoteValidityCrossvalidation2018
10.1002/aic.16980  % bhadrirajuOperableAdaptiveSparse2020
10.1016/j.jprocont.2021.10.006  % bhadrirajuOASISPOperableAdaptive2021
10.1080/00207178608933593  % billingsCorrelationBasedModel1986
10.1080/00207179408921513  % billingsNonlinearModelValidation1994
10.1002/9781118535561  % billingsNonlinearSystemIdentification2013
10.1080/00401706.1974.10489208  % boxAnalysisClosedLoopDynamicStochastic1974
10.5555/1756006.1859921  % cawleyOverfittingModelSelection2010
10.1073/pnas.1906995116  % championDatadrivenDiscoveryCoordinates2019
10.1080/00207178908953472  % chenOrthogonalLeastSquares1989
10.1080/00207179008934126  % chenNonlinearSystemIdentification1990
10.1177/14680874261419158  % choiHybridModelingMarine2026
10.1080/17445302.2021.1920095  % coradduPhysicalDatadrivenHybrid2021
10.1088/2632-2153/ad45b0  % dahdahClosedloopKoopmanOperator2024
10.1080/07350015.1995.10524599  % dieboldComparingPredictiveAccuracy1995
10.1016/0005-1098(81)90070-4  % fortescueImplementationSelftuningRegulators1981
10.3390/machines11050557  % fuComparativeStudyHealth2023
10.1016/j.physd.2025.134893  % goyalGuaranteedStableQuadratic2025
10.1007/s11071-025-12070-7  % grasevKoopmanEigenfunctionbasedIdentification2026
10.2307/1913827  % hausmanSpecificationTestsEconometrics1978
10.1098/rsos.211823  % hirshSparsifyingPriorsBayesian2022
10.1016/j.arcontrol.2004.12.002  % isermannModelbasedFaultdetectionDiagnosis2005
10.1038/s41598-026-53715-w  % jagadeeshExperimentalEmulationCharge2026
10.1016/j.cam.2005.09.027  % kaipioStatisticalInverseProblems2007
10.1098/rspa.2018.0335  % kaiserSparseIdentificationNonlinear2018
10.1016/j.conengprac.2020.104424  % kaleliDevelopmentPredictiveBased2020
10.1137/18M1216572  % kambTimeDelayObservablesKoopman2020
10.1103/PhysRevFluids.6.094401  % kaptanogluPromotingGlobalStability2021
10.1007/s11071-023-08525-4  % kaptanogluBenchmarkingSparseSystem2023
10.1007/s00332-017-9423-0  % kordaConvergenceExtendedDynamic2018
10.1146/annurev-fluid-121021-025220  % kramerLearningNonlinearReduced2024
10.1214/aos/1176347265  % kunschJackknifeBootstrapGeneral1989
10.1093/biomet/65.2.297  % ljungMeasureLackFit1978
10.1007/s00162-020-00536-w  % loiseauDatadrivenModelingChaotic2020
10.3390/en12020259  % luNumericalCalculationMethod2019
10.1109/CCTA53793.2025.11151368  % lovlandClosedLoopIdentificationChallenge2025
10.1109/ACCESS.2023.3257109  % manzoorVehicularApplicationsKoopman2023
10.3390/modelling6040127  % mayarodriguezModelFreeIdentificationHeat2025
10.1111/j.1467-9868.2010.00740.x  % meinshausenStabilitySelection2010
10.1016/j.automatica.2012.06.038  % morariNonlinearOffsetfreeModel2012
10.1080/01621459.1960.10482064  % muthOptimalPropertiesExponentially1960
10.1080/00207179.2021.2013541  % narasingamDatadrivenFeedbackStabilisation2023
10.1007/978-3-662-04323-3  % nellesNonlinearSystemIdentification2000
10.1007/s00332-022-09862-1  % nuskeFiniteDataErrorBounds2023
10.1002/rnc.70272  % osmanAdaptiveSINDyLyapunovModel2026
10.1115/1.4062160  % panKoopmanModelPredictive2023
10.1016/j.conengprac.2024.105936  % panNonlinearModelPredictive2024
10.1016/j.ifacol.2015.11.304  % pannocchiaOffsetfreeMPCExplained2015
10.1080/20464177.2024.2432777  % patilDatadrivenModelMarine2025
10.1080/07474930802459016  % pattonCorrectionAutomaticBlockLength2009
10.1080/00207170310001635419  % piroddiIdentificationAlgorithmPolynomial2003
10.1080/01621459.1994.10476870  % politisStationaryBootstrap1994
10.1081/ETC-120028836  % politisAutomaticBlockLengthSelection2004
10.1016/S0967-0661(02)00186-7  % qinSurveyIndustrialModel2003
10.1063/1.5027470  % quadeSparseIdentificationNonlinear2018
10.1016/j.neucom.2018.07.071  % ribeiroParallelTrainingConsidered2018
10.1146/annurev-fluid-010816-060042  % rowleyModelReductionFlow2017
10.1137/18M1191944  % rudyDataDrivenIdentificationParametric2019
10.1007/BF01053745  % sauerEmbedology1991
10.1109/MCS.2019.2938121  % schoukensNonlinearSystemIdentification2019
10.3390/s26123854  % sirolaChargeAirSystem2026
10.1007/s003329900072  % starkDelayEmbeddingsForced1999
10.1007/s00332-003-0534-4  % starkDelayEmbeddingsForced2003
10.1177/1468087421998635  % stoumposNovelMethodologyMarine2022
10.1016/j.arcontrol.2025.101035  % strasserOverviewKoopmanbasedControl2026
10.1016/j.automatica.2006.11.025  % soderstromErrorsinvariablesMethodsSystem2007
10.1007/BFb0091924  % takensDetectingStrangeAttractors1981
10.1016/0167-2789(92)90102-S  % theilerTestingNonlinearityTime1992
10.1016/j.proeng.2016.06.518  % tufaEffectModelPlant2016
10.1007/s11633-008-0313-7  % vallApproachPolynomialNARX2008
10.1007/s12555-024-0452-9  % yahagiSparseIdentificationNonlinear2025
10.1109/TCYB.2026.3652850  % yonezawaSparseIdentificationNonlinear2026
10.5194/os-15-1801-2019  % yuEvaluationNonidenticalVersus2019
10.1016/j.jprocont.2021.08.018  % Key offen (Autoren fehlen)
10.3390/jmse14090845  % Key offen (Autoren fehlen)
```

## Offen / nicht belegt

**Quellen und Belege**
- Kein Volltext gelesen. Alle Aussagen über Quellen stehen auf Abstract-Ebene; Seitenangaben für `\cite[S. …]` fehlen durchgehend. Aussagen aus Abstracts nicht als Volltextbeleg übernehmen.
- DOIs nicht aufgelöst. 84 DOIs standen selbst in einem Suchergebnis (Importliste), weitere nur in Zusammenfassungen der Suchmaschine oder gar nicht.
- Autorenlisten teils nur aus Zusammenfassungen der Suchmaschine; wo die Suchanfrage die Namen schon enthielt, besteht Echo-Gefahr (in den Bemerkungen der Quellenliste markiert, z. B. Meda u. a. 2026, Badwe u. a. 2009, Douma u. a. 2008, Sirola u. a. 2026).
- 33 Quellen aus der letzten Nachrecherche (†) nicht gegengeprüft, darunter Valábek u. a. 2026 (E2.2) und die Schiffskühlkreis-Arbeiten von Jeon, Jung u. a.
- Key `wulffPhysicsinformedRegressionModels2025` nicht auffindbar; nächster Kandidat Nielsen u. a. 2025 (Preprint).
- Vermutete Zuordnungen von Keys, in Zotero klären: `zinageDataDrivenModeling2022` = arXiv 2204.10421; `medaKoopmanBasedMethodsEV2025` = arXiv 2504.03872; `boldDataDrivenMPCStability2025` = arXiv 2505.05951; `yahagiSparseIdentificationNonlinear` (ohne Jahr) = EMEC-SINDy arXiv 2503.05154; `yonezawa…2025` = SINDy-LOM, Journalfassung IEEE Trans. Cybern. 2026; JMSE 2026, Art. 845 = „Arava 2026“ aus ch2 Z. 954.
- Metadaten vorhandener Keys nur teilweise gesehen: Atam 2018 (Seiten, DOI), Beran u. a. 2021 (Band, Seiten), Zinage u. a. 2022 (Autoren), Meda, Stockar 2025 (Autoren, Konferenz), Yahagi u. a. 2025 IJCAS (vollständige Autorenliste).
- Für die Beiträge zentrale Abstract-Aussagen, im Volltext zu prüfen: Cisneros u. a. 2020 und Shi u. a. 2023 (Scheduling nur über exogene Größen möglich?), Pan, Li 2024 (Bilinearität über den Zustand), Wu 2026 (Kriterium der Stellkanal-Informativität), Løvland u. a. 2025 (`−K⁻¹`, Theorem 1), Yahagi u. a. 2026 (Serien-PID, Ausgänge), Korda & Mezić 2018 (L²(μ)-Projektion, nur autonome Systeme).
- Aussagen zu Rupprecht 2016, Vagapov 2022/2024 und Sui 2022 in E2.2 stammen aus ch3 und wurden nicht neu geprüft.

**Suchumfang**
- Nur Websuche mit Abstract-Auszügen, keine Datenbank (Scopus, Web of Science, Google Scholar). Leerbefunde (E2.3, E4.6) gelten nur für diesen Suchweg.
- Die ersten Läufe V3 und V4 sowie Teile von V5 und V6 brachen am gemeinsamen Suchbudget ab; die Wiederholungen V3n bis V6n liefen mit 25, 25, 23 und 12 Anfragen. Gezielte Suchen nach SINDYc-MPC an HVAC-Wärmeübertragern und deutsche Anfragen zur modellprädiktiven Ladelufttemperaturregelung blieben aus.
- CIMAC-Kongressbeiträge nicht durchsuchbar (Titel teils abgeschnitten); SAE- und ASME-ICEF-Beiträge nur stichprobenartig.
- Forschungsprofile von Prof. Henning und Prof. Merkel nicht recherchiert; Fragen in E1.4 aus den Schwerpunkten im Auftrag abgeleitet.

**Eigene Rechnungen (von Copilot nachzurechnen, sympy war nicht verfügbar)**
- Zellreduktion `ε_n = 1 − (1 + N/n)^{−n}` (F1); zweistufige Gewichte `w_1, w_2, w_3` und zweistufige Gain-Gleichung (E1.2); Mitteltemperatur-Ansatz `ε = 2N/(2+N)` (E1.2).
- QP-Gegenbeispiel und Bedingungen (a)–(d) (E1.1 K1, S2); Affinität von `T_{k+1} = a(d_k) T_k + c(d_k) + b(d_k) u_k` (E1.1 K3).
- map-Form gleich Vorwärtsdifferenz im LS-Sinn (E1.1 K3); Kennfeld-Schranke des Ventil-Gains (A6); R² gegen die Last als untere Schranke des multiplen R² (A2, nur wenn die Last im Spaltenraum liegt).
- Taupunkt nach Magnus: 3 bar absolut rund 51,5 °C, 4 bar absolut rund 57 °C. Nur Illustration; der Ladedruck am HP-Kühler des 49/60DF steht nicht in `kontext/`.
- Fall A in E4.3 (Verdampfungssenke vor der HT-Stufe).

**Daten und Firmenwissen, deren Verfügbarkeit offen ist**
- Kennfeld der Vorsteuerung (A6, B1), Reglerparameter von ChATCo (A13, B4), Felddaten einer zweiten Baureihe (D3), Wartungs- und Reinigungstermine (D4), Sensordatenblätter oder Kalibrierprotokolle (A16). Ohne diese Daten schrumpfen die Ideen auf den Diskussionsteil.
- Ob Hyperparameter bisher auf Testdaten gewählt wurden (S3), ist aus ch2/ch3 nicht erkennbar.

**Schätzungen**
- Nutzen und Stunden in E3 sind eigene Schätzungen ohne Kenntnis des Codes und des Datenbestands.
- Öffentliche Herstellerseiten in E4.5 sind keine Belege; der Wortlaut der Everllence-Retrofit-Seite ist ungeprüft.
