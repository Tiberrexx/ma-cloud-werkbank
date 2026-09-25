# Auftrag A — Literaturlücken: Ergebnis (Cloud-Sitzung, 25.09.2026)

Grundlage: `auftraege/A_literaturluecken.md`, `kontext/ch2.tex` und `kontext/ch3.tex` (Kopie vom 25.09.2026).
Kandidatenliste zur Prüfung durch Copilot gegen Zotero und die Originale. Keine Kapiteländerung.

## Vorbemerkung: Werkzeuglage und Lesart

- In dieser Sitzung war nur die Websuche verfügbar. Verlagsseiten, arXiv, doi.org, Crossref,
  OpenAlex, Semantic Scholar, DiVA und dblp waren für den Abruf gesperrt. GitHub war lesbar.
- Folge: **Keine Quelle ist im Volltext gelesen.** Keine Seiten- oder Gleichungsangabe aus den
  Kapiteln konnte am Original geprüft werden. Einzige Ausnahme: das JOSS-Manuskript von PySINDy
  im GitHub-Repo (A2, Kaptanoglu u. a. 2022).
- Die Rechercheagenten dieser Sitzung haben ihr Suchkontingent aufgebraucht. Einzelne Punkte
  sind deshalb nur teilweise durchsucht; das steht jeweils dabei und unter „Offen / nicht belegt“.
- Status je Quelle, streng ausgelegt:
  - `[Volltext gelesen]` nur beim genannten Repo-Manuskript.
  - `[nur bibliografisch]` überall sonst, auch wenn Abstract-Inhalt über eine
    Suchzusammenfassung sichtbar war. Den Abstract selbst hat niemand am Verlag gelesen.
- Herkunftskennung je Angabe:
  - **(T)** wörtlich in einem Treffertitel oder einer Treffer-URL; belastbar.
  - **(G)** direkt gelesen in einer GitHub-Datei (z. B. `docs/JOSS2/paper.bib` und
    `docs/academic.rst` im Repo dynamicslab/pysindy, README eines Autoren-Repos).
  - **(S)** nur aus der modellgeschriebenen Zusammenfassung der Suchmaschine; kein Primärbeleg.
- „Aussage“ heißt: Die im Kapitel zugeschriebene Aussage passt zu Titel und Abstract-Inhalt
  (so weit sichtbar). Das ist nie ein Volltextbeleg.
- BibTeX-Einträge enthalten nur (T)- und (G)-Felder. Alles andere steht als
  `% ungeprüft:`-Zeile über dem Eintrag. Keys sind Vorschläge im Stil der vorhandenen Keys;
  endgültig erzeugt sie Better-BibTeX in Zotero.

## Kurzbefund (wichtigste Korrekturen)

- „Tschöke/Pucher 2018“: Autor ist Pucher, Tschöke ist Mitherausgeber des Handbuchs
  Dieselmotoren (4. Aufl.). Gleiches gilt für „Tschöke/Pantow“.
- „Llamas 2019“: Die Dissertation ist von 2018. Für 2019 kommt ein Artikel Llamas & Eriksson
  in Frage (Jahr nur aus Suchzusammenfassung).
- ch3 „Hansen 1989“: Früheste Veröffentlichung ist ACC 1988 (Hansen & Franklin). Den Begriff
  „dual-Youla“ verwendet erst die spätere Literatur; Hansen spricht von „fractional representation“.
- ch3 „Chiuso 2007, Erstdefinition PBSID“: nicht haltbar. Verfahren geht auf Chiuso & Picci 2005
  zurück, 2007 bringt Bezeichnung und optimierte Variante.
- ch3 „Schrama 1993“: Erstautor ist Van den Hof (Van den Hof & Schrama 1993, Automatica);
  Konferenzfassung CDC 1992.
- Druckverlust-Beleg: Hauptkandidat Eriksson & Nielsen 2014, Kap. 7 (Ladeluftkühler als
  inkompressible Drossel); schon in der Bib.
- A2 Champion u. a. 2020: belegt keine **Ungleichungs**nebenbedingungen, nur Gleichungen.
  Ersatz: Kaptanoglu u. a. 2022 (JOSS, PySINDy).
- A2 Farina & Piroddi 2010: Zeitschrift ist Int. J. Control.
- A2 Sheikh u. a. 2024: Anwendung Li-Ionen-Batterie (J. Energy Storage), nur methodische Analogie.
- A2 Kaptanoglu 2021 (Trapping): Das Trapping-Theorem selbst geht laut Autoren-Notebook auf
  Schlegel & Noack 2015 zurück.
- Nebenbefund: ch2 zitiert `erikssonMODELINGTURBOCHARGEDSI` mit „S. 132“. Der OGST-Artikel
  Eriksson 2007 hat S. 523–538; Ziel des Keys prüfen.

---

## Teil A1 — fehlende Keys in Kap. 2 und 3

| Nr. | Quelle (Kapitelangabe, Zeile) | Bibliografie | DOI / ISBN / URL | Status | Aussage | Stelle / Befund |
|---|---|---|---|---|---|---|
| 1 | „Tschöke/Pucher 2018, S. 68, Gl. 41, Rekuperationsgrad“ (ch2 Z. 536) | Pucher, H.: Ladungswechsel und Aufladung beim Dieselmotor. In: Tschöke, H.; Mollenhauer, K.; Maier, R. (Hrsg.): Handbuch Dieselmotoren, 4. Aufl., Reihe Springer Reference Technik (T). Springer Vieweg, 2018, Kapitel S. 43–87 (S) | Kapitel 10.1007/978-3-658-07697-9_4 (T); Buch 10.1007/978-3-658-07697-9 (T); ISBN Druck 978-3-658-07696-2 (T); Living-Reference-Fassung 10.1007/978-3-658-07997-0_4-1 (T, eigene Seitenzählung) | [nur bibliografisch] | nicht prüfbar | S. 68 liegt im Seitenbereich (S). Gl. 41 und der Begriff „Rekuperationsgrad“ nicht gesehen. Kurzform im Kapitel falsch (s. Kurzbefund). Nicht mit `pucherLadeluftkuehlungUndLadeluftkuehler2012` verwechseln |
| 1b | „Tschöke/Pantow 2018, S. 696, Gl. 8 und 9“ (ch2 Z. 740–741; laut Kommentar in BIB-Nachtrag) | Pantow, E. (S): Externe Kühlung von Dieselmotoren (T). Im selben Handbuch, S. 679–716 (S) | Living Reference 10.1007/978-3-658-07997-0_47-1 (T); Druckkapitel 10.1007/978-3-658-07697-9_47 (S) | [nur bibliografisch] | nicht prüfbar | S. 696 liegt im Seitenbereich (S). Nicht mit „Interne Kühlung von Dieselmotoren“ verwechseln (10.1007/978-3-658-07997-0_46-1, T) |
| 2 | „Holmgren 2005, Gl. 3.26, Druckfehler Plus statt Minus“ (ch2 Z. 563–565) | Holmgren, A. (Vorname Anders, S) (2005, S): Mean Value Modelling of the intake manifold temperature (T). Master's thesis (T), Vehicular Systems, Linköping University, LiTH-ISY-EX-3648-2005 (S) | https://www.diva-portal.org/smash/get/diva2:21637/FULLTEXT01.pdf (T) | [nur bibliografisch] | nicht prüfbar | Titel ermittelt. Gl. 3.26 und der Vorzeichenfehler nicht gesehen |
| 3 | „Llamas 2019, S. 18: Luftmassenstrom am Großmotor nicht gemessen“ (ch2 Z. 620–621) | Llamas, X. (T) (2018, T über Dateinamen): Modeling and Control of EGR on Marine Two-Stroke Diesel Engines (T). Dissertation, Linköping Studies in Science and Technology, Dissertations No. 1904 (T), Linköping University | DiVA diva2:1178537 (T); ISBN 978-91-7685-368-9 (S); DOI 10.3384/diss.diva-144596 (S) | [nur bibliografisch] | nicht prüfbar | **Jahr weicht ab.** Kandidat für „2019“: Llamas, X.; Eriksson, L.: Control-oriented modeling of two-stroke diesel engines with exhaust gas recirculation for marine applications, DOI 10.1177/1475090218768992 (T, journals.sagepub.com); Zeitschrift, Band, Seiten nicht gesehen. Welche Quelle S. 18 trägt, offen |
| 4 | „Heywood, S. 54, Gl. 2.27a, Liefergrad, Auflage klären“ (ch2 Z. 622) | 1. Aufl.: Heywood, J. B. (1988): Internal Combustion Engine Fundamentals. New York: McGraw-Hill (T). 2. Aufl.: Heywood, J. B. (2018): Internal Combustion Engine Fundamentals, 2nd ed. McGraw Hill (T) | 1. Aufl. ISBN 978-0-07-028637-5 (T); 2. Aufl. ISBN 978-1-260-11610-6 (T) | [nur bibliografisch] | nicht prüfbar | Auflage mit Gl. 2.27a auf S. 54 nicht feststellbar. Abschn. 2.10 „Volumetric Efficiency“ in der 1. Aufl. nur (S). Seite 54 passt eher zur 1. Aufl.; das ist eine Vermutung |
| 5 | Beleg für `Δp ∝ ṁ²/ρ` bzw. `ṁ ∝ sqrt(Δp·p/T)` (ch2 Z. 622–625; Prüfpunkt Z. 1010–1011) | siehe Nr. 5a–5e unten | – | – | – | Empfehlung: 5a als Hauptbeleg, 5b oder 5c für die Wärmeübertrager-Seite. MathWorks-Doku (`mathworksHeatExchangerInterfaceG`) nicht als einzigen Beleg stehen lassen |
| 5a | dto., Motorliteratur | Eriksson, L.; Nielsen, L. (2014): Modeling and Control of Engines and Drivelines. Wiley, Automotive Series (T); Kap. 7 „Mean Value Engine Modeling“ (T) | ISBN 978-1-118-47999-5 (T); Buch 10.1002/9781118536186 (T); Kap. 7 10.1002/9781118536186.ch7 (T) | [nur bibliografisch] | teilweise | Zwei LiU-Abschlussarbeiten modellieren Luftfilter, Ladeluftkühler und Abgasanlage als inkompressible Drosseln „nach Eriksson & Nielsen (2014)“ (S, zweimal). Gleichung und Nummer nicht gesehen. Schon als `erikssonModelingControlEngines2014` in der Bib |
| 5b | dto., Wärmeübertrager-Lehrbuch | Shah, R. K.; Sekulić, D. P. (2003): Fundamentals of Heat Exchanger Design. Hoboken: Wiley (T). Kap. 6 „Heat Exchanger Pressure Drop Analysis“ (S) | Buch 10.1002/9780470172605 (T); ISBN 978-0-471-32171-2 (T) | [nur bibliografisch] | nicht prüfbar | Kern-Druckverlust in Kap. 6 laut (S); Formel und Re-Abhängigkeit des Reibungsbeiwerts nicht gesehen |
| 5c | dto., Nachschlagewerk | Kast, W.; Nirschl, H.; Gaddis, E. S.; Wirth, K.-E.; Stichlmair, J. (S): L1 Pressure Drop in Single Phase Flow (T). In: VDI Heat Atlas, 2. Aufl. (T), Springer, 2010 (S) | Kapitel 10.1007/978-3-540-77877-6_70 (T); Werk 10.1007/978-3-540-77877-6 (T) | [nur bibliografisch] | nicht prüfbar | Kapitelthema passt. Deutsche Ausgabe (VDI-Wärmeatlas, Kap. L1) nicht gesucht |
| 5d | dto., Motorliteratur | Eriksson, L. (2007): Modeling and Control of Turbocharged SI and DI Engines. Oil & Gas Science and Technology – Rev. IFP 62(4), 523–538 (G, README nkymark/TCSISimTestbed) | 10.2516/ogst:2007042 (T) | [nur bibliografisch] | nicht prüfbar | Ein Simulationsmodell mit Luftfilter und Ladeluftkühler beruht laut README (G) auf dieser Arbeit; Drosselgleichung nicht gesehen. Nebenbefund zum Key `erikssonMODELINGTURBOCHARGEDSI` s. Kurzbefund |
| 5e | dto., Motorliteratur | Guzzella, L.; Onder, C. H.: Introduction to Modeling and Control of Internal Combustion Engine Systems. Springer (T); 2. Aufl. 2010 (S) | 10.1007/978-3-642-10775-7 (T); ISBN 978-3-642-10774-0 (T) | [nur bibliografisch] | nicht prüfbar | Schon als `guzzellaIntroductionModelingControl2010` in der Bib. Lokal prüfen, ob die in ch2 zitierte S. 31, Gl. 2.7 oder Abschn. 2.3 eine inkompressible Drosselgleichung enthält |
| 6a | ch3 Z. 688: „Hansen 1989, Erstquelle der dual-Youla-Parametrierung“ | Hansen, F. R. (1989): A fractional representation approach to closed loop system identification and experiment design (T). Ph.D. Thesis, Stanford University (Autor, Hochschule, Jahr S) | ProQuest https://www.proquest.com/openview/55f54a694983344bfedabd824074ef4a/1 (T) | [nur bibliografisch] | teilweise | Spätere Arbeiten schreiben Hansen (1989) die „dual Youla“-Parametrierung zu (S). Früher: Hansen, F. R.; Franklin, G. F. (S): On a Fractional Representation Approach to Closed-Loop Experiment Design (T), ACC 1988, S. 1319–1320 (S); IEEE Xplore 4789924, NTRS 19880067329 (T). Dazu Hansen, Franklin, Kosut (S): Closed-Loop Identification via the Fractional Representation: Experiment Design (T), ACC 1989, S. 1422–1427 (S); IEEE Xplore 4790411 (T) |
| 6b | ch3 Z. 692: „Chiuso 2007, Erstdefinition PBSID“ | Chiuso, A. (G) (2007): The role of vector autoregressive modeling in predictor-based subspace identification (T). Automatica 43(6), 1034–1048 (G). Chiuso, A. (2007): On the Relation Between CCA and Predictor-Based Subspace Identification (T). IEEE Trans. Autom. Control (T, dblp), 52(10), 1795–1812 (S) | Automatica: PII S000510980700057X (T); DOI 10.1016/j.automatica.2006.12.009 nur über Suche zugeordnet. TAC: IEEE Xplore 4349185 (T) | [nur bibliografisch] | nein | Das TAC-Abstract nennt PBSID laut (S) bereits „recently proposed“. Ursprung: Chiuso, A.; Picci, G. (G) (2005): Consistency analysis of some closed-loop subspace identification methods (T). Automatica 41(3), 377–391 (T, PDF-Titel; G). Die PBSID-Toolbox (TU Delft, G) nennt für PBSIDopt Chiuso & Picci 2005 und Chiuso 2007 Automatica. Welche Arbeit das Kürzel „PBSID“ zuerst verwendet, offen |
| 6c | ch3 Z. 702: „Schrama 1993, Erstquelle des Zwei-Stufen-Verfahrens“ | Van den Hof, P. M. J.; Schrama, R. J. P. (S, mehrfach; Dateiname der Autoren-PDF) (1993): An indirect method for transfer function estimation from closed loop data (T). Automatica 29(6), 1523–1527 (T, PDF-Titel) | PII 000510989390015L (T); DOI 10.1016/0005-1098(93)90015-L (S, Suche nach der DOI führt auf den Artikel) | [nur bibliografisch] | teilweise | Schrama ist **Zweitautor**. Abstract laut (S): konsistente Schätzung der Strecke aus Closed-Loop-Daten auch bei ungenauem Rauschmodell, einstellbare Biasverteilung. Frühere Fassung gleichen Titels: Van den Hof, Schrama, Bosgra, 31st IEEE CDC 1992 (Autoren aus Dateiname der Autoren-URL; IEEE Xplore iel5/1040/8509/00371136, T) |
| 7a | „Stanivuk 2021, S. 117, Gl. 9“, τ = C_eff/(ṁ_L c_p + U_eff A) (ch2 Z. 835–836) | Stanivuk, T. (T) u. a. (Lalić, B.; Žanić Mikuličić, J.; Šundov, M., S) (2021, S): Simulation Modelling of Marine Diesel Engine Cooling System (T). Transactions on Maritime Science (T) 10(1), 112–125 (S) | https://www.toms.com.hr/index.php/toms/article/view/398 (T); DOI 10.7225/toms.v10.n01.008 (S, zwei Suchen gleich) | [nur bibliografisch] | nicht prüfbar | S. 117 liegt im Seitenbereich (S). Arbeit behandelt das Kühlsystem des Schiffsdiesels, laut (S) mit seewassergekühltem Spülluftkühler; Form von Gl. 9 offen |
| 7b | „Arava 2026“, mariner Kühler ohne latenten Term (ch2 Z. 954–955) | Arava, T.; Ionescu, R.; Miron, L.; Chiriac, R. (S, zwei Suchen gleich) (2026): An Assessment of the Operation Under Different Ambient Conditions of the Charge–Air Cooler for a Large Marine Diesel Engine (T). J. Mar. Sci. Eng. 14(9), 845, online 30.04.2026 (S) | 10.3390/jmse14090845 (T) | [nur bibliografisch] | nicht prüfbar, Zweifel | Laut (S) Simulation (AVL CRUISE) eines Großdiesels mit Rohr-Lamellen-Ladeluftkühler; Thema ist der Einfluss der Ansaugluftfeuchte. Ob die Kondensationsenthalpie fehlt, am Original prüfen; die Feuchte ist dort Untersuchungsgegenstand |
| 7c | „Taler 2017, Gl. 20“, Stoffwertterm über Temperaturniveau (ch2 Z. 969–970) | nicht eindeutig identifiziert | Kandidaten (alle T): K1 „Simple heat transfer correlations for turbulent tube flow“, E3S Web Conf. 2017 (URL e3sconf_wtiue2017_02008); K2 „Simple power-type heat transfer correlations for turbulent pipe flow in tubes“, J. Thermal Science, 10.1007/s11630-017-0947-2; K3 „Mathematical modeling of unsteady response of plate and fin heat exchanger to sudden change in liquid flow rate“, E3S Web Conf. 2017 (URL e3sconf_ef2017_01023) | – | nicht prüfbar | Kein BibTeX. Mit dem Taler-2017-Eintrag in `BIB_NACHTRAG_0709.bib` abgleichen. K3 passt thematisch am ehesten (instationäres Lamellenrohr-Modell, S) |
| 7d | „Wahlström 2009, S. 7“, Gegenposition: Ladeluftkühler mit Temperaturzustand (ch2 Z. 977) | Wahlström, J. (2009, T über Dateinamen): Control of EGR and VGT for Emission Control and Pumping Work Minimization in Diesel Engines (T). Dissertation, Linköping Studies in Science and Technology, Dissertations No. 1256 (T) | https://www.diva-portal.org/smash/get/diva2:219874/FULLTEXT02.pdf (T); ISBN nicht gefunden | [nur bibliografisch] | nicht prüfbar, Zweifel | Lizentiatsarbeit 2006 mit gleichem Titel existiert (diva2:22523, T). Das zugehörige Modell (Wahlström, J.; Eriksson, L. (2011): Modelling diesel engines with a variable-geometry turbocharger and exhaust gas recirculation by optimization of model parameters for capturing non-linear system dynamics. Proc. IMechE D 225, 960–986, DOI 10.1177/0954407011398177, T) hat laut (S) acht Zustände, ein Kühler-Temperaturzustand wird dort nicht genannt. Gegenposition am Original prüfen |
| 7e | „Ekberg 2018“ (ch2 Z. 1015, nur in der Liste fehlender Keys) | zwei Kandidaten; Autoren jeweils Ekberg, K.; Leek, V.; Eriksson, L. (S) | K1: Validation of an Open-Source Mean-Value Heavy-Duty Diesel Engine Model (T). Proc. SIMS 59, Linköping Electronic Conference Proceedings 153 (T), DOI 10.3384/ecp18153290 (T). K2: Modeling and Validation of an Open-Source Mean Value Heavy-Duty Diesel Engine Model (T). SNE Simulation Notes Europe 28(4) (T), DOI 10.11128/sne.28.tn.10451 (T) | [nur bibliografisch] | – | Keine Textstelle im Kapitel. Auswahl K1 oder K2 durch Thomas |
| 7f | PG 51/60DF-M, S. 117, Tab. 74, Band 40–70 °C (ch2 Z. 125–126) | MAN/Everllence: 51/60DF Project Guide – Marine (Titel im Link abgeschnitten, T) | https://www.everllence.com/applications/projectguides/4stroke/Propulsion/PG_P-II_5160DF.pdf (T); Übersicht https://www.everllence.com/marine/products/planning-tools-and-downloads/project-guides (T) | [nur bibliografisch] | nicht prüfbar | Ausgabe und Jahr nicht ermittelbar. Seite und Tabelle hängen von der Ausgabe ab; Ausgabedatum ins Zitat. Kein BibTeX vor Einsicht ins Titelblatt |

Anmerkungen A1:

- Nr. 7 des Auftrags („weitere Stellen mit Key fehlt“): per Suche in ch2 gefunden und als 7a–7f
  aufgenommen (Z. 126, 836, 954, 969, 977, 1015). Vagapov 2024 (Z. 739, 863) hat laut Kommentar
  schon den Key `vagapovModellierungIdentifikationUnd2024` und ist nicht aufgenommen.
- ch3 hat außer den drei `\anno`-Stellen (6a–6c) keine weiteren „Key fehlt“-Marken.
- Heywood: Die Arbeit sollte die Auflage nennen, deren Exemplar vorliegt. Gl.-Nummer und Seite
  an diesem Exemplar prüfen.
- Llamas: Für „am Großmotor nicht gemessen“ ist die Dissertation (Zweitakt-Schiffsdiesel mit AGR)
  der naheliegende Kandidat. Aussage gilt dort für einen Zweitakter; Übertragung auf den
  Viertakt-49/60DF im Text als Übertragung kennzeichnen.
- Hansen: Wenn „Erstquelle“ im Text bleibt, ACC 1988 nennen. Sonst „Hansen 1989 (Diss.)“ plus
  Hansen, Franklin, Kosut 1989 als zugängliche Fassung.
- Van den Hof & Schrama: Die Einordnung „Joint-Input-Output-Familie bei Forssell & Ljung“ in
  ch3 Z. 706–707 ist hier nicht geprüft.
- Übersicht Closed-Loop-Subspace (für PBSID-Herkunft lokal nachlesen): van der Veen, G.;
  van Wingerden, J.-W.; Bergamasco, M.; Lovera, M.; Verhaegen, M. (S) (2013): Closed-loop
  subspace identification methods: an overview. IET Control Theory & Applications (T),
  DOI 10.1049/iet-cta.2012.0653 (T).

---

## Teil A2 — Quellen der SINDYc-Methodenleiter

| Quelle (Kapitelangabe) | Bibliografie | DOI / URL | Status | Aussage | Stelle / Befund |
|---|---|---|---|---|---|
| Bakarji, Callaham, Brunton, Kutz 2022, Nat. Comput. Sci. 2:834–844 | Bakarji, J.; Callaham, J.; Brunton, S. L.; Kutz, J. N. (S) (2022): Dimensionally consistent learning with Buckingham Pi (T). Nature Computational Science (T) 2(12), 834–844 (S, mehrere Suchen gleich) | 10.1038/s43588-022-00355-5 (Suffix in nature.com-URL, T); arXiv:2202.04643 (T) | [nur bibliografisch] | ja | Drei Verfahren mit Buckingham-Pi als Nebenbedingung, eines auf SINDy-Basis (S) |
| Schaeffer & McCalla 2017, Phys. Rev. E | Schaeffer, H.; McCalla, S. G. (2017): Sparse model selection via integral terms. Phys. Rev. E 96(2), 023302 (G) | 10.1103/PhysRevE.96.023302 (T, G) | [nur bibliografisch] | ja | Integralterme im Titel; Fit an die Trajektorie statt an Ableitungen (S) |
| Messenger & Bortz 2021, Weak SINDy ODE, MMS 19(3) | Messenger, D. A.; Bortz, D. M. (S) (2021): Weak SINDy: Galerkin-Based Data-Driven Model Selection (T). Multiscale Model. Simul. 19(3) (T), 1474–1497 (S) | 10.1137/20M1343166 (T); arXiv:2005.04339 (T) | [nur bibliografisch] | teilweise | Schwache Form belegt (S); ODE-Bezug nur über die Abgrenzung zur PDE-Arbeit. ch3 zitiert `messengerWeakSINDyPartial2021`, das ist die PDE-Fassung (J. Comput. Phys., 110525, DOI 10.1016/j.jcp.2021.110525, G) |
| Zhang & Schaeffer 2019, MMS 17(3), Konvergenz STLSQ | Zhang, L.; Schaeffer, H. (2019): On the Convergence of the SINDy Algorithm. Multiscale Model. Simul. 17(3), 948–972 (G, Autoren-Repo) | 10.1137/18M1189828 (T) | [nur bibliografisch] | ja | Wechsel aus LS-Fit und Schwellwertschritt nähert lokale Minimierer eines ℓ0-bestraften LS-Problems an; Konvergenzbedingungen und -rate (S). Arbeit sagt „SINDy algorithm“, nicht „STLSQ“ |
| Rudy u. a. 2017, Sci. Adv., STRidge | Rudy, S. H.; Brunton, S. L.; Proctor, J. L.; Kutz, J. N. (2017): Data-driven discovery of partial differential equations. Science Advances 3, e1602614 (G); Heft 4 (S) | 10.1126/sciadv.1602614 (T, G) | [nur bibliografisch] | teilweise | Abstract nennt laut (S) nur „sparsity-promoting techniques“. STRidge belegt über das offizielle Code-Repo (Funktion `STRidge`; README verweist auf das Supplement, G). Supplement nicht gelesen |
| Zheng u. a. 2019, IEEE Access, SR3 | Zheng, P.; Askham, T.; Brunton, S. L.; Kutz, J. N.; Aravkin, A. Y.: A Unified Framework for Sparse Relaxed Regularized Regression: SR3. IEEE Access 7, 1404–1423 (G) | 10.1109/ACCESS.2018.2886528 (G); IEEE Xplore 8573778 (T); arXiv:1807.05411 (T) | [nur bibliografisch] | ja | **Jahr uneinheitlich:** PySINDy nennt 2018 (Online-Erscheinen), Band 7 ist 2019 (S). Jahr in Zotero über die DOI festlegen; der Key hängt daran |
| Kaptanoglu u. a. 2023, Nonlinear Dyn., Solver-Benchmark | Kaptanoglu, A. A.; Zhang, L.; Nicolaou, Z. G.; Fasel, U.; Brunton, S. L. (S) (2023): Benchmarking sparse system identification with low-dimensional chaos (T). Nonlinear Dynamics (T) 111(14), 13143–13164 (S) | 10.1007/s11071-023-08525-4 (T); arXiv:2302.10787 (T) | [nur bibliografisch] | ja | Vergleich von vier Sparse-Regression-Verfahren plus schwacher Form an rund 70 chaotischen Systemen (Begleit-Notebook, G; S) |
| Champion u. a. 2020, IEEE Access, Ungleichungsnebenbedingungen | Champion, K.; Zheng, P.; Aravkin, A. Y.; Brunton, S. L.; Kutz, J. N. (2020): A unified sparse optimization framework to learn parsimonious physics-informed models from data. IEEE Access 8, 169259–169271 (G) | 10.1109/ACCESS.2020.3023625 (G); arXiv:1906.10612 | [nur bibliografisch] | nein | Abstract laut (S) nur allgemein „physical constraints“. Code-Repo zum Paper (kpchamp/SINDySR3, G) kennt nur lineare Gleichungsnebenbedingungen |
| Ersatz für Ungleichungen | Kaptanoglu, A. A.; de Silva, B. M.; Fasel, U.; Kaheman, K.; Goldschmidt, A. J.; Callaham, J.; Delahunt, C. B.; Nicolaou, Z. G.; Champion, K.; Loiseau, J.-C.; Kutz, J. N.; Brunton, S. L. (2022): PySINDy: A comprehensive Python package for robust sparse system identification. J. Open Source Softw. 7(69), 3994 (G) | 10.21105/joss.03994 (G) | [Volltext gelesen] am Manuskript `docs/JOSS2/paper.md` im PySINDy-Repo, nicht am Verlags-PDF | ja | Summary des Manuskripts: Algorithmen, die Ungleichungsnebenbedingungen und Stabilität erzwingen bzw. fördern. Umsetzung `ConstrainedSR3(inequality_constraints=True)` für `C·w ≤ d` über CVXPY, nur mit konvexem Regularisierer (G) |
| Kaptanoglu u. a. 2021, Phys. Rev. Fluids, Trapping | Kaptanoglu, A. A.; Callaham, J. L.; Aravkin, A.; Hansen, C. J.; Brunton, S. L. (2021): Promoting global stability in data-driven models of quadratic nonlinear dynamics. Phys. Rev. Fluids 6(9), 094401 (G) | 10.1103/PhysRevFluids.6.094401 (G); arXiv:2105.01843 | [nur bibliografisch] | ja | Trapping-SINDy für energieerhaltende quadratische Nichtlinearitäten (Autoren-Notebook, G). Theorem selbst laut Notebook: Schlegel, M.; Noack, B. R. (2015): On long-term boundedness of Galerkin models. J. Fluid Mech. 765, 325–352 (nur G, ungeprüft) |
| Schaeffer, Tran, Ward 2018, SIAM J. Appl. Math., Monom vs. Legendre | Schaeffer, H.; Tran, G.; Ward, R. (2018): Extracting sparse high-dimensional dynamics from limited data. SIAM J. Appl. Math. 78(6), 3279–3295 (G) | 10.1137/18M116798X (G); arXiv:1707.08528 (T) | [nur bibliografisch] | nicht prüfbar | Abstract laut (S): exakte Rekonstruktion aus weniger Abtastwerten als Unbekannten über Zufallsabtastung, drei Abtaststrategien. Legendre-Basis dort nicht erwähnt; nur ein anderer Suchlauf nennt (S) eine Legendre-transformierte Messmatrix für die Garantien. Aussage „Sparsamkeit basisabhängig“ nicht belegt |
| Hastie, Tibshirani, Tibshirani 2020, Stat. Sci. | Hastie, T.; Tibshirani, R.; Tibshirani, R. (2020): Best Subset, Forward Stepwise or Lasso? Analysis and Recommendations Based on Extensive Comparisons (T). Statistical Science 35(4), 579–592 (T) | 10.1214/19-STS733 (T) | [nur bibliografisch] | ja | Vergleich der drei Verfahren, relaxed lasso insgesamt am besten, Best Subset nur bei hohem SNR vorn (S). Diskussionspapier; Rejoinder 35(4), 625–626, DOI 10.1214/20-STS733REJ (T) |
| Piroddi & Spinelli 2003, Int. J. Control | Piroddi, L.; Spinelli, W. (2003): An identification algorithm for polynomial NARX models based on simulation error minimization (T). Int. J. Control 76(17) (T), 1767–1781 (S) | 10.1080/00207170310001635419 (T) | [nur bibliografisch] | ja | Simulationsfehler als Kriterium der Regressorauswahl, dazu Pruning (S). Vorname Spinelli ungeklärt |
| Farina & Piroddi 2010 | Farina, M.; Piroddi, L. (2010): An iterative algorithm for simulation error based identification of polynomial input–output models using multi-step prediction (T). Int. J. Control 83(7) (T), 1442–1456 (S) | 10.1080/00207171003793262 (T) | [nur bibliografisch] | ja | Iterativ geschätzte Prädiktoren wachsenden Horizonts senken den Aufwand der Simulationsfehler-Schätzung (S). Verwechslungsgefahr: Farina & Piroddi, Int. J. Syst. Sci. 43(2), 319–333 (Jahr 2011/2012 ungeklärt) und Int. J. Adapt. Control Signal Process. 2011, DOI 10.1002/acs.1203 (T) |
| Machado & Jones 2024, ACC, SINDy-SI | Machado, G. F.; Jones, M. (2024): Sparse Identification of Nonlinear Dynamics with Side Information (SINDy-SI) (T). 2024 American Control Conference (ACC) (T), 2879–2884 (S). Preprint arXiv:2310.04227 (T) | IEEE Xplore 10644812 (T); DOI 10.23919/ACC60939.2024.10644812 (S) | [nur bibliografisch] | teilweise | Sum-of-Squares-Programmierung, Nebeninformation garantiert eingehalten (S). Monotonie-Nebenbedingungen, invariante Mengen und bekannte Gleichgewichte nur (S); Positivität nicht gesehen. Modell rein polynomial (wegen SOS) |
| Tulleken 1993, Automatica | Tulleken, H. J. A. F. (1993): Grey-box modelling and identification using physical knowledge and bayesian techniques (T). Automatica 29(2), 285–308 (T) | PII 000510989390124C (T); DOI 10.1016/0005-1098(93)90124-C (über Suche zugeordnet) | [nur bibliografisch] | teilweise | Linear beschränkte Grey-Box-Modellklasse, Bayes-Schätzung (S). „Vorzeichen stationärer Verstärkungen“ nur über eine Sekundärquelle in einer Suchzusammenfassung; im Original nicht bestätigt |
| Aguirre, Barroso, Saldanha, Mendes 2004, IEE Proc. CTA | Aguirre, L. A.; Barroso, M. F. S.; Saldanha, R. R.; Mendes, E. M. A. M. (2004): Imposing steady-state performance on identified nonlinear polynomial models by means of constrained parameter estimation (T). IEE Proc. Control Theory Appl. 151(2), 174–179 (T) | 10.1049/ip-cta:20040102 (T) | [nur bibliografisch] | ja | Statik des Polynommodells als Gleichungsnebenbedingung, beschränkte kleinste Quadrate (S) |
| Aguirre, arXiv 1907.06803, Abschn. 7.1/7.2 | Aguirre, L. A. (2019, aus arXiv-ID): A Bird's Eye View **of** Nonlinear System Identification (T). arXiv:1907.06803, Preprint | https://arxiv.org/abs/1907.06803 (T) | [nur bibliografisch] | teilweise | Grey-Box mit Zusatzinformation (Statik, Symmetrie, Bifurkation) laut (S); Abschn. 7 zu Fixpunkten und Statik als Strukturhinweis (S). Inhalt von 7.1/7.2 nicht gesehen. Keine Journal-Fassung gefunden |
| Cisneros, Voss, Werner 2016, CDC | Cisneros, P. S. G.; Voss, S.; Werner, H. (2016): Efficient Nonlinear Model Predictive Control via quasi-LPV representation (T). 2016 IEEE 55th CDC (T), 3216–3221 (S) | IEEE Xplore 7798752 (T); DOI 10.1109/CDC.2016.7798752 (S) | [nur bibliografisch] | ja | NMPC über quasi-LPV als Folge von QPs/SOCPs je Zeitschritt, Stabilität offline über LMIs (S) |
| Meinshausen & Bühlmann 2010, JRSS B | Meinshausen, N.; Bühlmann, P. (2010): Stability selection (T). J. R. Stat. Soc. B 72(4) (T), 417–473 (Anfang T, Ende S; vermutlich mit Diskussion) | 10.1111/j.1467-9868.2010.00740.x (T) | [nur bibliografisch] | ja | Subsampling plus Auswahlverfahren, Fehlerkontrolle für falsch ausgewählte Variablen in endlichen Stichproben (S) |
| Hirsh, Barajas-Solano, Kutz 2022, R. Soc. Open Sci. | Hirsh, S. M.; Barajas-Solano, D. A.; Kutz, J. N. (G, arXiv-Fassung) (2022): Sparsifying priors for Bayesian uncertainty quantification in model discovery (T). R. Soc. Open Sci. (T) 9(2), 211823 (S) | 10.1098/rsos.211823 (T); arXiv:2107.02107 (T) | [nur bibliografisch] | ja | UQ-SINDy: Koeffizienten per MCMC, Spike-and-Slab- und regularisierter Horseshoe-Prior, Inklusionswahrscheinlichkeit je Kandidat (S); beide Priors auch im Autoren-Code (G) |
| Sheikh u. a. 2024, LPV + Lasso | Sheikh, A. M. A.; Donkers, M. C. F.; Bergveld, H. J. (2024): A comprehensive approach to sparse identification of linear parameter-varying models for lithium-ion batteries using improved experimental design (T). Journal of Energy Storage (T) 95, 112581 (S) | 10.1016/j.est.2024.112581 (G, README PyBatteryID) | [nur bibliografisch] | ja | LPV in Ein-/Ausgangsform, Parameter über „physikalisch motivierte“ Basisfunktionen von SOC und Strom, Termauswahl mit LASSO, Schätzung mit Ridge (S). Anwendung Li-Ionen-Batterie. Gleiche Autoren, ACC 2024: „Investigating Identification Input Designs for Modelling Lithium-ion Batteries with Hysteresis using LPV Framework“, DOI 10.23919/ACC60939.2024.10644893 (G); Beschreibung im Auftrag passt zum Journal-Artikel |
| Somalwar u. a. 2025, arXiv:2504.01766, Mehrschritt-Kriterium | Somalwar, A.; Lee, B. D.; Pappas, G. J.; Matni, N. (S) (2025, aus arXiv-ID): Learning with Imperfect Models: When Multi-step Prediction Mitigates Compounding Error (T). arXiv:2504.01766, Preprint | https://arxiv.org/abs/2504.01766 (T) | [nur bibliografisch] | ja | Lineare Systeme: Bei korrekt spezifizierter Modellklasse hat das Einschrittmodell den kleineren asymptotischen Vorhersagefehler; bei Fehlspezifikation (partielle Beobachtbarkeit) senkt ein direkter Mehrschritt-Prädiktor den Bias (S) |

Anmerkungen A2:

- Alle 22 genannten Quellen existieren (Somalwar mit Titel und Autoren wie oben).
- Aussage „nein“ nur bei Champion u. a. 2020 (Ungleichungen). Dort Kaptanoglu u. a. 2022 als Beleg
  vorschlagen; Champion 2020 kann für Gleichungsnebenbedingungen und Trimming stehen bleiben.
- Aussage mit Einschränkung: Tulleken (Vorzeichen stationärer Verstärkung), Machado & Jones
  (Positivität), Schaeffer/Tran/Ward (Basisabhängigkeit), Aguirre arXiv (Abschnittsinhalt),
  Rudy (STRidge nur im Supplement bzw. Code).
- Für den Text: Somalwar u. a. stützen das Mehrschritt-Kriterium als Mittel gegen Bias bei
  Fehlspezifikation, nicht als allgemein überlegenes Kriterium.

---

## Teil A3 — Negativbefunde

Belastbarkeit gilt jeweils nur für den genannten Suchweg (Websuche, keine Volltexte, kein Scopus/WoS,
keine Zitationsverfolgung). Kein Ergebnis ist ein Nachweis der Nichtexistenz.

### A3.1 Freier Eigenterm bricht Verschiebungsinvarianz; Bibliothek nur aus Temperaturdifferenzen

- Ergebnis: **teilweise.** Allgemeine Rahmen zum Erzwingen von Symmetrien in SINDy gefunden.
  Nicht gefunden: eine Arbeit, die die Invarianz gegenüber dem Temperaturnullpunkt behandelt,
  den freien Koeffizienten auf x(k) als Bruch dieser Invarianz benennt oder eine Bibliothek nur
  aus Temperaturdifferenzen vorschlägt.
- Nächste Treffer (alle [nur bibliografisch]):
  - Otto, S. E.; Zolman, N.; Kutz, J. N.; Brunton, S. L. (S): A Unified Framework to Enforce,
    Discover, and Promote Symmetry in Machine Learning. arXiv:2311.00212 (T), Preprint 2023;
    Zeitschriftenfassung JMLR 26(248), 1–83, 2025 (S).
    Symmetrien als lineare Nebenbedingungen an SINDy-Koeffizienten über die Lie-Ableitung (S).
    Eine Translation T → T + c wäre formal darstellbar; ein Temperaturbeispiel ist nicht belegt.
    Nähe: methodisch am nächsten.
  - Ahmadi, A. A.; El Khadir, B. (2020): Learning Dynamical Systems with Side Information.
    L4DC, PMLR 120 (T, proceedings.mlr.press/v120/ahmadi20a); arXiv:2008.10135 (T). Langfassung
    laut (S) SIAM Review 65(1), 183–223, 2023. Vorwissen als konvexe SDP-Nebenbedingungen (S).
    Ob Translationsinvarianz dazugehört, nicht geprüft.
  - Yang, J. u. a. (2024): Symmetry-Informed Governing Equation Discovery. NeurIPS 2024;
    arXiv:2405.16756 (T). Bibliothek auf bekannte Symmetriegruppe beschränkt (S). Weitere Autoren
    nicht geprüft.
  - Chen, C.; Jin, X.; Li, H. (2022): Discovering Governing Equations by Machine Learning
    implemented with Invariance. arXiv:2203.15586 (T), Preprint. Galilei-Invarianz als
    Bauregel der Kandidatenterme bei PDE (S).
  - Zar, J. H. (1968): The Effect of the Choice of Temperature Scale on Simple Linear Regression
    Equations. Ecology 49(6), 1161 (S); DOI 10.2307/1934501 (T). Umrechnung einer
    Regressionsgleichung bei Wechsel der Temperaturskala; kein Dynamikmodell. Einziger Treffer
    mit ausdrücklichem Bezug zur Skalenwahl.
  - Randtreffer: Bakarji u. a. 2022 (Skaleninvarianz über Buckingham Pi, nicht Offset);
    Di Natale, L. u. a. (2022): Physically Consistent Neural Networks for building thermal
    modeling, Applied Energy 325 (S), arXiv:2112.03212 (T); neuronales Netz, nicht SINDy.
- Suchweg (20 Anfragen): SINDy symmetry constraints translation invariance library; Otto
  Unified framework symmetry; Ahmadi El Khadir side information (+ SIAM Review); Symmetry-Informed
  Governing Equation Discovery; sparse identification temperature offset invariance Celsius
  Kelvin temperature differences library; sparse regression „translation invariance“ affine
  coordinate change (Filter arxiv, sciencedirect, ieeexplore, springer, royalsocietypublishing,
  epubs.siam, pnas, journals.aps); SINDy invariance under shift of state variable; Galilean
  invariance SINDy library; dimensionally consistent SINDy Buckingham Pi; SINDy thermal model
  library temperature differences only; equivariant sparse regression Lie derivative (Filter
  arxiv, jmlr, neurips, pmlr); „choice of temperature scale“ regression coefficients; SINDy
  data centering deviation variables operating point sparsity; deutsch: Temperaturdifferenzen
  Bibliothek sparse Identifikation Verschiebungsinvarianz Temperaturnullpunkt; sparse
  identification heat transfer „temperature difference“ library (Filter arxiv, sciencedirect,
  mdpi, ieeexplore, springer, tandfonline).
- Belastbarkeit: mittel für „nicht gefunden“. Offen, ob Otto u. a. oder Ahmadi & El Khadir im
  Volltext ein Translations- bzw. Offset-Beispiel führen.

### A3.2 Sparsamkeit ist basisabhängig (Monom / verschoben / orthogonal)

- Ergebnis: **teilweise.** Allgemeine Basis- und Koordinatenabhängigkeit der SINDy-Sparsamkeit
  ist belegbar. Nicht gefunden: eine Arbeit, die den Verlust der Sparsamkeit durch Verschiebung
  oder Zentrierung der Monome (Nullpunktwechsel) ausdrücklich zeigt.
- Treffer:
  - Brunton, S. L.; Proctor, J. L.; Kutz, J. N. (2016), PNAS, DOI 10.1073/pnas.1517384113 (T);
    schon als `bruntonDiscoveringGoverningEquations2016` in der Bib. Laut (S) nennt die
    Diskussion die Abhängigkeit von Messgrößen und „sparsifying function basis“. Nicht im Text
    geprüft.
  - Champion, K.; Lusch, B.; Kutz, J. N.; Brunton, S. L. (2019): Data-driven discovery of
    coordinates and governing equations. PNAS 116(45), 22445–22451 (S); DOI
    10.1073/pnas.1906995116 (T). Sucht Koordinaten, in denen ein sparsames Modell existiert;
    Sparsamkeit also koordinatenabhängig (S). Nähe: direkt verwandt (nichtlineare Koordinaten,
    nicht Verschiebung).
  - PySINDy-Dokumentation `docs/tips.rst` (G, wörtlich): „If one has reason to believe the
    dynamics can be sparsely represented in terms of Chebyshev polynomials rather than monomials,
    then the library should include Chebyshev polynomials.“ Dort ebenfalls (G): Mit
    Polynombibliothek findet SINDy die ersten Terme der um null entwickelten Taylorreihe. Zitierbar
    ist dazu das Softwarepapier `desilvaPySINDyPythonPackage2020` (schon in der Bib) oder
    Kaptanoglu u. a. 2022 (A2); ob die Aussage dort im Papier steht, nicht geprüft.
  - Schaeffer, Tran, Ward 2018 (s. A2): Legendre-Bezug nicht bestätigt.
  - Feng, Y.; Mangan, N. M.; Jayadharan, M. (2026): Ill-Conditioning in Dictionary-Based
    Dynamic-Equation Learning: A Systems Biology Case Study. arXiv:2603.11330 (T), Preprint.
    Vergleich Monom-, Legendre-, Chebyshev-Bibliotheken; orthogonale Basen verbessern die
    Konditionierung nicht durchgängig (S). Nähe: direkt zur Basiswahl, aber Konditionierung statt
    Sparsamkeit.
  - Randtreffer (verwandt): Wu, K.; Xiu, D. (2019), J. Comput. Phys., arXiv:1809.09170 (T);
    Roman, S.; Todorovski, L.; Džeroski, S. (2026), arXiv:2608.13504 (T); Racioppo, P. (2026),
    AC-SINDy, arXiv:2604.18889 (T); Ba, F. A.; Melnyk, O.; Wald, C.; Steidl, G. (2024),
    Foundations of Data Science, DOI 10.3934/fods.2024025 (T).
- Suchweg (21 Anfragen): Schaeffer Tran Ward Legendre; Champion PNAS 2019; SINDy orthogonal
  polynomial library Legendre versus monomials sparsity (Filter arxiv, sciencedirect, siam,
  springer, royalsociety, aimsciences); Titelsuchen Feng, SORT, AC-SINDy; sparsity depends on
  choice of basis „not invariant“ change of variables; Wu Xiu; sparse identification shifted
  monomials centered polynomial library expansion point (Filter arxiv, sciencedirect, siam,
  pnas, royalsociety, aip); SINDy library Chebyshev Legendre conditioning (Filter arxiv,
  sciencedirect, springer, mdpi, ieee); PySINDy JOSS; data-scale independent regulariser;
  Brunton 2016 Diskussion; polynomial vector field sparsity not preserved under affine change of
  coordinates; SINDy Chebyshev monomial parsimony; GitHub `pysindy/docs/tips.rst`.
- Belastbarkeit: mittel für „keine Arbeit zur Offset-/Zentrierungsabhängigkeit gefunden“.
  Algebraisch ist der Befund elementar (Verschiebung eines Monoms erzeugt alle niedrigeren
  Potenzen); das ist eigene Überlegung, kein Literaturbeleg.

### A3.3 SINDy mit ε-NTU- oder Wärmeübertrager-Spalten

- Ergebnis: **nicht gefunden** für ε-NTU- oder LMTD-Spalten in einer SINDy-Bibliothek.
  **Teilweise** für SINDYc an Wärmeübertragern überhaupt (nur als Diskrepanzmodell).
- Treffer (alle [nur bibliografisch]):
  - Akan, M. T.; Portilla, C.; Özkan, L. (S) (2024): Model Discrepancy Learning for Heat Exchanger
    Networks (T). IFAC-PapersOnLine 58(14), 271–276 (S);
    https://www.sciencedirect.com/science/article/pii/S2405896324011005 (T). SINDYc und
    kleinste Quadrate lernen die Abweichung zwischen Messdaten und physikalischem
    Simulationsmodell, z. B. durch Fouling (S). Hybrides Diskrepanzmodell, keine
    Wärmeübertrager-Termformen in der Bibliothek bekannt. Nähe: direkt verwandt, keine Überdeckung.
  - Loiseau, J.-C. (S) (2020): Data-driven modeling of the chaotic thermal convection in an
    annular thermosyphon (T). Theor. Comput. Fluid Dyn. (T); DOI 10.1007/s00162-020-00536-w (T);
    arXiv:1911.07920 (T). DMD-Reduktion, dann SINDy, Lorenz-ähnliches Polynommodell (S). Keine
    Wärmeübertrager-Terme erkennbar. Die Thermosiphon-Fallstudie im Tutorial arXiv:2607.15077
    (T) ist nach Trefferlage dieselbe Anwendung; Bibliothek dort nicht gesehen.
  - Ito, Y.; Hato, T.; Kano, A. u. a. (S) (2023): Physics-Informed Machine Learning for Surrogate
    Modeling of Heat Transfer Phenomena (T). J. Comput. Nonlinear Dynam. 18(11), 111001 (S).
    SINDy mit nichtnegativem STLSQ für die Temperatur eines Leistungsmoduls, Simulationsdaten (S).
    Nähe: verwandt, kein Wärmeübertrager.
  - Ohne Belegwert: arXiv:2003.07465 (SINDy an einer zweipunktgeregelten Pumpe/Kühlanlage, T);
    ein US-Patent zu SINDy in HVAC-Ventilregelung (Patent, kein Beleg).
- Suchweg (10 Anfragen; Filter in Klammern): sparse identification nonlinear dynamics heat
  exchanger (arxiv, sciencedirect, ieeexplore, springer, mdpi, tandfonline); „Model Discrepancy
  Learning for Heat Exchanger Networks“ SINDYc (zweimal, mit und ohne Filter); SINDy candidate
  library effectiveness-NTU OR LMTD heat exchanger physics-informed sparse regression (arxiv,
  sciencedirect, ieeexplore, springer, mdpi, asme); SINDy sparse regression dynamic model heat
  exchanger outlet temperature experimental data; SINDy HVAC chiller heat pump heat exchanger;
  sparse identification district heating substation OR plate heat exchanger OR cooling coil;
  „annular thermosyphon“ sparse identification Loiseau; SINDYc thermal system library bilinear
  mass flow times temperature difference terms; „Physics-Informed Machine Learning for Surrogate
  Modeling of Heat Transfer Phenomena“. Vorher im ersten Durchlauf: GitHub-Suche
  „SINDy heat exchanger“ ohne Treffer.
- Belastbarkeit: mittel für „keine ε-NTU-/LMTD-Spalten in einer SINDy-Bibliothek gefunden“.
  Die Bibliothek bei Akan u. a. ist nur im Volltext klärbar.

### A3.4 SINDy ausdrücklich als LPV-Identifikation gedeutet

- Ergebnis: **nicht gefunden.** Keine Arbeit gefunden, die sagt, dass SINDy(c) mit Produkttermen
  Scheduling-Variable × Zustand ein LPV-Modell ist. Namensvarianten „LPV-SINDy“, „SINDy-LPV“,
  „parameter-varying SINDy“ ohne Fachtreffer. Die Gegenrichtung (sparse LPV-Identifikation,
  Koopman als LPV) gibt es.
- Treffer (alle [nur bibliografisch]):
  - Koelewijn, P. J. W.; Singh, R.; Seiler, P.; Tóth, R. (S) (2024): Learning Reduced-Order Linear
    Parameter-Varying Models of Nonlinear Systems (T). IFAC-PapersOnLine (aus PII abgeleitet);
    https://www.sciencedirect.com/science/article/pii/S2405896324013193 (T); arXiv:2312.06217 (T).
    Laut Snippet (S) nennen sie SINDy als Reduktionsverfahren mit „generally still nonlinear“
    Struktur. Zuordnung des Snippets wahrscheinlich, ungeprüft. Nähe: direkt, aber
    **Gegenposition** (SINDy dort nicht als LPV eingeordnet).
  - Iacob, L. C.; Tóth, R.; Schoukens, M. (S) (2024): Koopman form of nonlinear systems with inputs
    (T). Automatica 162, 111525 (S);
    https://www.sciencedirect.com/science/article/pii/S0005109824000177 (T); arXiv:2207.12132 (T).
    Lineare Zustandsmatrix, zustandsabhängige Eingangsmatrix, also ein speziell strukturiertes
    LPV-Modell; bilinear, wenn die Eingangsmatrix im Span der Observablen liegt (S).
    Strukturargument für Koopman/EDMDc, nicht für SINDy. Nähe: nächstliegend.
  - Jordanou, J. P.; Camponogara, E.; Gildin, E. (S) (2025): Identifying large-scale linear
    parameter varying systems with dynamic mode decomposition methods (T). J. Comput. Phys.
    (aus PII abgeleitet); arXiv:2502.02336 (T). DMD-Varianten zur LPV-Identifikation, auch mit
    Lasso/Ridge (S). Nähe: verwandt.
  - Sparse LPV-Identifikation (Gegenrichtung, Autoren nicht gesehen): „Identification of linear
    parameter-varying systems: A reweighted ℓ2,1-norm regularization approach“ (T), Mech. Syst.
    Signal Process., PII S0888327017304247; „Sparse RKHS estimation via globally convex
    optimization and its application in LPV-IO identification“ (T), Automatica 115, 108914 (S),
    PII S0005109820301126. Sheikh u. a. 2024 (A2) gehört ebenfalls hierher.
  - Koopman → quasi-LPV für MPC an einer ORC-Abwärmenutzung: „Data-Driven model identification and
    efficient MPC via quasi-linear parameter varying representation for ORC waste heat recovery
    system“ (T), Energy 2023 (aus PII abgeleitet), PII S0360544223003535; Autoren nicht gesehen.
- Suchweg (12 Anfragen): sparse identification nonlinear dynamics linear parameter-varying LPV
  scheduling variable (arxiv, sciencedirect, ieeexplore, springer, tandfonline); SINDy „LPV“
  quasi-LPV interpreted as linear parameter-varying; Tóth LPV identification sparse basis
  function selection Lasso; „LPV-ARX“ sparse estimation non-negative garrote Tóth Hjalmarsson;
  Sparse RKHS LPV-IO Automatica; „LPV-SINDy“ OR „SINDy-LPV“ OR „parameter-varying SINDy“ OR
  „SINDy with scheduling“ (ohne Filter); sparse dictionary learning LPV representation SINDy
  Koopman embedding; „Control-Oriented System Identification: Classical, Learning, and
  Physics-Informed Approaches“ LPV SINDy (Übersicht arXiv:2512.06315, keine SINDy-LPV-Aussage
  sichtbar); Koopman form inputs LPV Iacob Tóth Schoukens; SINDy quasi-LPV model predictive
  control; zwei Titel-/Autorensuchen (Jordanou, Koelewijn). Vorher: GitHub-Suche „SINDy LPV“
  ohne Treffer.
- Belastbarkeit: mittel bis gut auf Suchmaschinenebene. Nicht abgedeckt: Volltexte von
  Iacob u. a. und Koelewijn u. a. (könnten SINDy erwähnen), Tóth-Monografie 2010, Dissertationen.
- Anschluss an A2: Cisneros, Voss, Werner 2016 (quasi-LPV-MPC) und Sheikh u. a. 2024
  (sparse LPV mit physikalisch motivierter Basis) sind die nächsten Belege für die beiden
  Hälften der Deutung; die Verbindung „SINDy = LPV“ wäre eigene Einordnung.

### A3.5 SINDYc/EDMDc an Ladeluftkühlern, Motor-Luftpfaden oder Wärmeübertragern mit Messdaten (2020–2026)

- Ergebnis: **teilweise.** Außerhalb der schon zitierten Yahagi-/Yonezawa-Gruppe keine Arbeit mit
  bestätigten Messdaten an Ladeluftkühler, Motorluftpfad, Schiffs- oder Gasmotor gefunden.
  Mehrere Koopman-MPC-Arbeiten an thermischen Anlagen mit Wärmeübertragern; deren Datenstatus
  (Messung oder Simulation) ist durchweg ungeklärt.
- Bekannte Arbeiten (schon in ch3), hier nur eingeordnet:
  - Yonezawa u. a. (S), SINDy mit Bibliotheksoptimierung, rekursive Langzeitprognose;
    arXiv:2507.18220 (T), IEEE Xplore 11365958 (T). Diesel-Luftpfad (Saugrohrdruck, AGR-Rate;
    Eingänge Drehzahl, Einspritzmenge, AGR-Ventil, VGT) (S). Prüfstandsdaten unklar.
  - arXiv:2503.05154 (T), SINDy „for Applications to Industrial Systems“: vermutlich
    `yahagiSparseIdentificationNonlinear2025`, nicht geprüft.
  - arXiv:2602.15422 (T), generalisiertes bilineares Koopman: `yahagiGeneralizedBilinearKoopman2026`;
    laut (S) Intercooler im Motorsystem erwähnt.
- Neue Treffer (alle [nur bibliografisch], Angaben zu Anlage und Daten aus S):

  | Arbeit | Anlage | Messdaten | Methode | MPC |
  |---|---|---|---|---|
  | „Data-driven identification and fast model predictive control of the ORC waste heat recovery system by using Koopman operator“ (T), Control Eng. Pract. (aus PII), PII S0967066123002484 | ORC-Abwärmenutzung mit Verdampfer | unklar | Koopman | ja |
  | „Neural Koopman operator-assisted model predictive control of an Organic Rankine Cycle“ (T), Appl. Therm. Eng. (aus PII), PII S1359431123007251 | ORC | unklar | neuronaler Koopman | ja |
  | „Koopman-Model Predictive Control with Signal Temporal Logic Specifications for Temperature Regulation of a Warm-Water Supply System“ (T), arXiv:2207.04184 | Warmwasserversorgung | laut S experimentell validiert, ungeprüft | Koopman | ja |
  | „Deep Koopman Economic Model Predictive Control of a Pasteurisation Unit“ (T), arXiv:2511.04437 | Pasteurisieranlage, Labormaßstab | unklar | Deep Koopman | ja (EMPC) |
  | „Nonlinear model predictive control of chiller plant demand response with Koopman bilinear model and Krylov-subspace model reduction“ (T), Control Eng. Pract. (aus PII), PII S0967066124000960 | Kältezentrale | unklar | bilineares Koopman-Modell | ja (NMPC) |
  | „Explainable fault detection and diagnosis in HVAC systems using a Koopman operator with normal data“ (T), Energy Build. (aus PII), PII S0378778825013106 | RLT-Anlage, Kühlregister-Ventilfehler | unklar | Koopman-VAE | nein |
  | „Koopman Model Predictive Control of an Integrated Thermal Management System for Electric Vehicles“ (T), J. Dyn. Syst. Meas. Control 145(5), 051005 (S) | Thermomanagement E-Fahrzeug | laut S High-Fidelity-Simulation | Koopman, Grey-Box | ja |

  - Weitere Koopman-Arbeiten zum Thermomanagement von E-Fahrzeugen und zu Gasturbinen
    (arXiv:2604.01730, 2505.10438, 2205.08330) nach Trefferlage mit Simulationsdaten oder
    ungeklärtem Datenstatus; kein Kolbenmotor-Luftpfad.
  - Möglicher Einstieg für eine Nachsuche: „Vehicular Applications of Koopman Operator Theory –
    A Survey“, arXiv:2303.10471 (T), nicht ausgewertet.
- Kein Treffer für SINDy/Koopman an: Ladeluftkühler, Schiffs- oder Gasmotor,
  Fernwärme-Übergabestation, Wärmepumpen- oder Kältekreis (SINDy), Batteriekühlung (SINDy).
- Suchweg (13 Anfragen): SINDy diesel engine air path experimental test bench data boost
  pressure EGR (arxiv, sciencedirect, ieeexplore, sae, sagepub, mdpi, springer); „Sparse
  identification of nonlinear dynamics with library optimization mechanism“ diesel airpath;
  Koopman OR DMDc engine air path boost pressure MPC experimental test bench; marine engine OR
  ship engine OR gas engine Koopman OR SINDy measured data charge air; Koopman OR DMDc OR SINDy
  heat exchanger experimental measurements MPC temperature (mit asme); „ORC waste heat recovery
  system by using Koopman operator“; intercooler OR „charge air cooler“ data-driven dynamic model
  SINDy OR Koopman OR „dynamic mode decomposition“ (mit sae, sagepub); Koopman OR SINDy district
  heating OR air handling unit OR cooling coil real operational data; Koopman thermal management
  electric vehicles experimental data; Koopman OR SINDy internal combustion engine experimental
  validation dynamometer 2023–2025; SINDy OR Koopman vapor compression OR heat pump OR
  refrigeration experimental MPC; Koopman MPC warm-water supply real plant; SINDy battery
  thermal management coolant loop experimental.
- Belastbarkeit: gut für „kein Ladeluftkühler oder Motorluftpfad mit echten Daten außerhalb der
  Yahagi-/Yonezawa-Gruppe“ auf Suchmaschinenebene. Schwach für Wärmeübertrager, HVAC und
  Prozessanlagen allgemein (Datenstatus ungeklärt).
- Folge für ch3 Z. 1018–1029: Der dort formulierte Leerbefund (Stand 02.09.2026) bleibt nach
  dieser Suche bestehen. Die gefundene SINDYc-Anwendung an einem Wärmeübertrager-Netz
  (Akan u. a. 2024, A3.3) wäre als nächstliegende Arbeit zu prüfen.

---

## BibTeX-Entwürfe

Nur (T)- und (G)-Felder im Eintrag. `% ungeprüft:` über dem Eintrag nennt Felder aus (S) oder
Ableitungen. Keys: Stil der vorhandenen Keys (deutsche Wörter wie „und“ bleiben stehen, wie in
`pucherLadeluftkuehlungUndLadeluftkuehler2012`; Bindestrichwörter zusammengezogen, wie in
`dahdahClosedloopKoopmanOperator2024`). Endgültige Keys erzeugt Better-BibTeX.

### A1

```bibtex
% ungeprüft: year = {2018}; publisher = {Springer Vieweg}; address = {Wiesbaden}
% Key: Umlaut-Umschrift (tschoeke/tschoke) hängt an der Better-BibTeX-Spracheinstellung
@book{tschoekeHandbuchDieselmotoren2018,
  editor    = {Tschöke, Helmut and Mollenhauer, Klaus and Maier, Rudolf},
  title     = {Handbuch Dieselmotoren},
  edition   = {4},
  series    = {Springer Reference Technik},
  isbn      = {978-3-658-07696-2},
  doi       = {10.1007/978-3-658-07697-9}
}

% ungeprüft: Vorname Helmut; year = {2018}; pages = {43--87}; publisher = {Springer Vieweg}
% offen: S. 68, Gl. 41 ("Rekuperationsgrad") am Druckexemplar prüfen
@incollection{pucherLadungswechselUndAufladung2018,
  author    = {Pucher, H.},
  title     = {Ladungswechsel und Aufladung beim Dieselmotor},
  booktitle = {Handbuch Dieselmotoren},
  editor    = {Tschöke, Helmut and Mollenhauer, Klaus and Maier, Rudolf},
  edition   = {4},
  series    = {Springer Reference Technik},
  doi       = {10.1007/978-3-658-07697-9_4}
}

% ungeprüft: author = {Pantow, Eberhard}; year = {2018}; pages = {679--716};
%            doi Druckkapitel = {10.1007/978-3-658-07697-9_47}
% belegt (T) nur die Living-Reference-Fassung: 10.1007/978-3-658-07997-0_47-1
% Key ohne Autor nicht sinnvoll erzeugbar; Vorschlag nach Prüfung: pantowExterneKuehlungDieselmotoren2018
@incollection{pantowExterneKuehlungDieselmotoren2018,
  title     = {Externe Kühlung von Dieselmotoren},
  booktitle = {Handbuch Dieselmotoren},
  editor    = {Tschöke, Helmut and Mollenhauer, Klaus and Maier, Rudolf},
  edition   = {4},
  series    = {Springer Reference Technik}
}

% ungeprüft: Vorname Anders; year = {2005}; school = {Linköping University};
%            number = {LiTH-ISY-EX-3648-2005}
@mastersthesis{holmgrenMeanValueModelling2005,
  author    = {Holmgren, A.},
  title     = {Mean Value Modelling of the Intake Manifold Temperature},
  type      = {Master's thesis},
  url       = {https://www.diva-portal.org/smash/get/diva2:21637/FULLTEXT01.pdf}
}

% ungeprüft: isbn = {978-91-7685-368-9}; doi = {10.3384/diss.diva-144596}
@phdthesis{llamasModelingControlEGR2018,
  author    = {Llamas, Xavier},
  title     = {Modeling and Control of {EGR} on Marine Two-Stroke Diesel Engines},
  school    = {Linköping University},
  series    = {Linköping Studies in Science and Technology. Dissertations},
  number    = {1904},
  year      = {2018},
  url       = {https://liu.diva-portal.org/smash/record.jsf?pid=diva2:1178537}
}

% ungeprüft: year = {2019}; journal (vermutlich Proc. IMechE Part M, nur aus DOI-Präfix);
%            volume, number, pages
@article{llamasControlorientedModelingTwostroke2019,
  author    = {Llamas, Xavier and Eriksson, Lars},
  title     = {Control-oriented modeling of two-stroke diesel engines with exhaust gas recirculation for marine applications},
  doi       = {10.1177/1475090218768992}
}

@book{heywoodInternalCombustionEngine1988,
  author    = {Heywood, John B.},
  title     = {Internal Combustion Engine Fundamentals},
  publisher = {McGraw-Hill},
  address   = {New York},
  year      = {1988},
  isbn      = {978-0-07-028637-5}
}

% ungeprüft: genaues Impressum der 2. Auflage (McGraw Hill Education, Ort)
@book{heywoodInternalCombustionEngine2018,
  author    = {Heywood, John B.},
  title     = {Internal Combustion Engine Fundamentals},
  edition   = {2},
  publisher = {McGraw Hill},
  year      = {2018},
  isbn      = {978-1-260-11610-6}
}

% ungeprüft: author = {Stanivuk, Tatjana and Lalić, Branko and Žanić Mikuličić, Jelena and Šundov, Marko};
%            year = {2021}; volume = {10}; number = {1}; pages = {112--125};
%            doi = {10.7225/toms.v10.n01.008}
@article{stanivukSimulationModellingMarine2021,
  title     = {Simulation Modelling of Marine Diesel Engine Cooling System},
  journal   = {Transactions on Maritime Science},
  url       = {https://www.toms.com.hr/index.php/toms/article/view/398}
}

% ungeprüft: author = {Arava, Tanase and Ionescu, Radu and Miron, Lucian and Chiriac, Radu};
%            journal = {Journal of Marine Science and Engineering}; year = {2026};
%            volume = {14}; number = {9}; pages = {845}
@article{aravaAssessmentOperationDifferent2026,
  title     = {An Assessment of the Operation Under Different Ambient Conditions of the Charge--Air Cooler for a Large Marine Diesel Engine},
  doi       = {10.3390/jmse14090845}
}

% ungeprüft: Vorname Johan; isbn. Key-Umschrift ö hängt an der Better-BibTeX-Einstellung
@phdthesis{wahlstromControlEGRVGT2009,
  author    = {Wahlström, J.},
  title     = {Control of {EGR} and {VGT} for Emission Control and Pumping Work Minimization in Diesel Engines},
  school    = {Linköping University},
  series    = {Linköping Studies in Science and Technology. Dissertations},
  number    = {1256},
  year      = {2009},
  url       = {https://www.diva-portal.org/smash/get/diva2:219874/FULLTEXT02.pdf}
}

% ungeprüft: number = {7}
@article{wahlstromModellingDieselEngines2011,
  author    = {Wahlström, J. and Eriksson, L.},
  title     = {Modelling diesel engines with a variable-geometry turbocharger and exhaust gas recirculation by optimization of model parameters for capturing non-linear system dynamics},
  journal   = {Proceedings of the Institution of Mechanical Engineers, Part D: Journal of Automobile Engineering},
  volume    = {225},
  pages     = {960--986},
  year      = {2011},
  doi       = {10.1177/0954407011398177}
}

% Ekberg 2018: K1 oder K2 wählen
% ungeprüft (beide): author = {Ekberg, Kristoffer and Leek, Viktor and Eriksson, Lars}; pages
@inproceedings{ekbergValidationOpenSourceMeanValue2018,
  title     = {Validation of an Open-Source Mean-Value Heavy-Duty Diesel Engine Model},
  booktitle = {Proceedings of The 59th Conference on Simulation and Modelling (SIMS 59)},
  series    = {Linköping Electronic Conference Proceedings},
  number    = {153},
  year      = {2018},
  doi       = {10.3384/ecp18153290}
}

% ungeprüft: journal = {SNE Simulation Notes Europe}; year = {2018}; pages = {197--204}
@article{ekbergModelingValidationOpenSource2018,
  title     = {Modeling and Validation of an Open-Source Mean Value Heavy-Duty Diesel Engine Model},
  volume    = {28},
  number    = {4},
  doi       = {10.11128/sne.28.tn.10451}
}

% Druckverlust-Beleg (Nr. 5). Eriksson & Nielsen 2014 und Guzzella & Onder 2010 sind schon in der Bib.
% Abgleich: Eriksson/Nielsen ISBN 978-1-118-47999-5, doi 10.1002/9781118536186 (Kap. 7: .ch7);
%           Guzzella/Onder ISBN 978-3-642-10774-0, doi 10.1007/978-3-642-10775-7
% ungeprüft: Kapitel 6 "Heat Exchanger Pressure Drop Analysis" (Titel nur S)
@book{shahFundamentalsHeatExchanger2003,
  author    = {Shah, Ramesh K. and Sekulić, Dušan P.},
  title     = {Fundamentals of Heat Exchanger Design},
  publisher = {John Wiley \& Sons},
  address   = {Hoboken, NJ},
  year      = {2003},
  isbn      = {978-0-471-32171-2},
  doi       = {10.1002/9780470172605}
}

% ungeprüft: author = {Kast, W. and Nirschl, H. and Gaddis, E. S. and Wirth, K.-E. and Stichlmair, J.};
%            year = {2010}; publisher = {Springer}; address = {Berlin, Heidelberg}
% Key ohne geprüften Autor vorläufig
@incollection{kastL1PressureDrop2010,
  title     = {L1 Pressure Drop in Single Phase Flow},
  booktitle = {VDI Heat Atlas},
  edition   = {2},
  doi       = {10.1007/978-3-540-77877-6_70}
}

% Hinweis: prüfen, ob erikssonMODELINGTURBOCHARGEDSI dieselbe Arbeit meint ("S. 132" passt nicht)
@article{erikssonModelingControlTurbocharged2007,
  author    = {Eriksson, Lars},
  title     = {Modeling and Control of Turbocharged {SI} and {DI} Engines},
  journal   = {Oil \& Gas Science and Technology -- Rev. IFP},
  volume    = {62},
  number    = {4},
  pages     = {523--538},
  year      = {2007},
  doi       = {10.2516/ogst:2007042}
}

% ch3 \anno Hansen
% ungeprüft: author = {Hansen, F. R.}; school = {Stanford University}; year = {1989}; ProQuest-Nr. 8919429
@phdthesis{hansenFractionalRepresentationApproach1989,
  title     = {A fractional representation approach to closed loop system identification and experiment design},
  url       = {https://www.proquest.com/openview/55f54a694983344bfedabd824074ef4a/1}
}

% ungeprüft: author = {Hansen, F. R. and Franklin, G. F.}; booktitle = {Proc. American Control Conference};
%            year = {1988}; pages = {1319--1320}
@inproceedings{hansenFractionalRepresentationApproach1988,
  title     = {On a Fractional Representation Approach to Closed-Loop Experiment Design},
  url       = {https://ieeexplore.ieee.org/document/4789924}
}

% ungeprüft: author = {Hansen, F. R. and Franklin, G. F. and Kosut, R. L.};
%            booktitle = {Proc. American Control Conference}; address = {Pittsburgh}; year = {1989};
%            pages = {1422--1427}; doi nicht gefunden
@inproceedings{hansenClosedLoopIdentificationFractional1989,
  title     = {Closed-Loop Identification via the Fractional Representation: Experiment Design},
  url       = {https://ieeexplore.ieee.org/document/4790411}
}

% ch3 \anno Chiuso
% ungeprüft: doi = {10.1016/j.automatica.2004.10.015} (S); Vornamen
@article{chiusoConsistencyAnalysisClosedloop2005,
  author    = {Chiuso, A. and Picci, G.},
  title     = {Consistency analysis of some closed-loop subspace identification methods},
  journal   = {Automatica},
  volume    = {41},
  number    = {3},
  pages     = {377--391},
  year      = {2005}
}

% ungeprüft: doi = {10.1016/j.automatica.2006.12.009} (über Suche zugeordnet)
@article{chiusoRoleVectorAutoregressive2007,
  author    = {Chiuso, A.},
  title     = {The role of vector autoregressive modeling in predictor-based subspace identification},
  journal   = {Automatica},
  volume    = {43},
  number    = {6},
  pages     = {1034--1048},
  year      = {2007}
}

% ungeprüft: volume = {52}; number = {10}; pages = {1795--1812}; doi = {10.1109/TAC.2007.906159}
@article{chiusoRelationCCAPredictorBased2007,
  author    = {Chiuso, A.},
  title     = {On the Relation Between {CCA} and Predictor-Based Subspace Identification},
  journal   = {IEEE Transactions on Automatic Control},
  year      = {2007},
  url       = {https://ieeexplore.ieee.org/document/4349185/}
}

% ch3 \anno Schrama
% ungeprüft: author = {Van den Hof, P. M. J. and Schrama, R. J. P.} (mehrere S, Dateiname);
%            doi = {10.1016/0005-1098(93)90015-L} (S)
@article{vandenhofIndirectMethodTransfer1993,
  title     = {An indirect method for transfer function estimation from closed loop data},
  journal   = {Automatica},
  volume    = {29},
  number    = {6},
  pages     = {1523--1527},
  year      = {1993},
  url       = {https://www.sciencedirect.com/science/article/abs/pii/000510989390015L}
}

% ungeprüft: author = {Van den Hof, P. M. J. and Schrama, R. J. P. and Bosgra, O. H.} (Dateiname);
%            booktitle = {Proc. 31st IEEE Conference on Decision and Control}; address = {Tucson};
%            year = {1992}; pages = {1702--1706}
@inproceedings{vandenhofIndirectMethodTransfer1992,
  title     = {An indirect method for transfer function estimation from closed loop data},
  url       = {https://ieeexplore.ieee.org/iel5/1040/8509/00371136.pdf}
}
```

### A2

```bibtex
% ungeprüft: author = {Bakarji, Joseph and Callaham, Jared and Brunton, Steven L. and Kutz, J. Nathan};
%            volume = {2}; number = {12}; pages = {834--844}
@article{bakarjiDimensionallyConsistentLearning2022,
  title     = {Dimensionally consistent learning with {Buckingham Pi}},
  journal   = {Nature Computational Science},
  year      = {2022},
  doi       = {10.1038/s43588-022-00355-5}
}

@article{schaefferSparseModelSelection2017,
  author    = {Schaeffer, Hayden and McCalla, Scott G.},
  title     = {Sparse model selection via integral terms},
  journal   = {Physical Review E},
  volume    = {96},
  number    = {2},
  pages     = {023302},
  year      = {2017},
  doi       = {10.1103/PhysRevE.96.023302}
}

% ungeprüft: author = {Messenger, Daniel A. and Bortz, David M.}; year = {2021}; pages = {1474--1497}
@article{messengerWeakSINDyGalerkinBased2021,
  title     = {Weak {SINDy}: Galerkin-Based Data-Driven Model Selection},
  journal   = {Multiscale Modeling \& Simulation},
  volume    = {19},
  number    = {3},
  doi       = {10.1137/20M1343166}
}

@article{zhangConvergenceSINDyAlgorithm2019,
  author    = {Zhang, Linan and Schaeffer, Hayden},
  title     = {On the Convergence of the {SINDy} Algorithm},
  journal   = {Multiscale Modeling \& Simulation},
  volume    = {17},
  number    = {3},
  pages     = {948--972},
  year      = {2019},
  doi       = {10.1137/18M1189828}
}

% ungeprüft: number = {4}
@article{rudyDatadrivenDiscoveryPartial2017,
  author    = {Rudy, Samuel H. and Brunton, Steven L. and Proctor, Joshua L. and Kutz, J. Nathan},
  title     = {Data-driven discovery of partial differential equations},
  journal   = {Science Advances},
  volume    = {3},
  pages     = {e1602614},
  year      = {2017},
  doi       = {10.1126/sciadv.1602614}
}

% ungeprüft: year (2018 lt. PySINDy, 2019 lt. S); bei 2018 Key zhengUnifiedFrameworkSparse2018
@article{zhengUnifiedFrameworkSparse2019,
  author    = {Zheng, Peng and Askham, Travis and Brunton, Steven L. and Kutz, J. Nathan and Aravkin, Aleksandr Y.},
  title     = {A Unified Framework for Sparse Relaxed Regularized Regression: {SR3}},
  journal   = {IEEE Access},
  volume    = {7},
  pages     = {1404--1423},
  doi       = {10.1109/ACCESS.2018.2886528}
}

% ungeprüft: author = {Kaptanoglu, Alan A. and Zhang, Lanyue and Nicolaou, Zachary G. and Fasel, Urban and Brunton, Steven L.};
%            year = {2023}; volume = {111}; number = {14}; pages = {13143--13164}
@article{kaptanogluBenchmarkingSparseSystem2023,
  title     = {Benchmarking sparse system identification with low-dimensional chaos},
  journal   = {Nonlinear Dynamics},
  doi       = {10.1007/s11071-023-08525-4}
}

% Beleg nur für Gleichungsnebenbedingungen und Trimming, nicht für Ungleichungen
@article{championUnifiedSparseOptimization2020,
  author    = {Champion, Kathleen and Zheng, Peng and Aravkin, Aleksandr Y. and Brunton, Steven L. and Kutz, J. Nathan},
  title     = {A unified sparse optimization framework to learn parsimonious physics-informed models from data},
  journal   = {IEEE Access},
  volume    = {8},
  pages     = {169259--169271},
  year      = {2020},
  doi       = {10.1109/ACCESS.2020.3023625}
}

% Beleg für Ungleichungsnebenbedingungen (Manuskript im Repo gelesen)
@article{kaptanogluPySINDyComprehensivePython2022,
  author    = {Kaptanoglu, Alan A. and de Silva, Brian M. and Fasel, Urban and Kaheman, Kadierdan and Goldschmidt, Andy J. and Callaham, Jared and Delahunt, Charles B. and Nicolaou, Zachary G. and Champion, Kathleen and Loiseau, Jean-Christophe and Kutz, J. Nathan and Brunton, Steven L.},
  title     = {{PySINDy}: A comprehensive {Python} package for robust sparse system identification},
  journal   = {Journal of Open Source Software},
  volume    = {7},
  number    = {69},
  pages     = {3994},
  year      = {2022},
  doi       = {10.21105/joss.03994}
}

@article{kaptanogluPromotingGlobalStability2021,
  author    = {Kaptanoglu, Alan A. and Callaham, Jared L. and Aravkin, Aleksandr and Hansen, Christopher J. and Brunton, Steven L.},
  title     = {Promoting global stability in data-driven models of quadratic nonlinear dynamics},
  journal   = {Physical Review Fluids},
  volume    = {6},
  number    = {9},
  pages     = {094401},
  year      = {2021},
  doi       = {10.1103/PhysRevFluids.6.094401}
}

@article{schaefferExtractingSparseHighdimensional2018,
  author    = {Schaeffer, Hayden and Tran, Giang and Ward, Rachel},
  title     = {Extracting sparse high-dimensional dynamics from limited data},
  journal   = {SIAM Journal on Applied Mathematics},
  volume    = {78},
  number    = {6},
  pages     = {3279--3295},
  year      = {2018},
  doi       = {10.1137/18M116798X}
}

% ungeprüft: volume = {9}; number = {2}; pages = {211823}
% Autoren aus der arXiv-Fassung (G, PySINDy)
@article{hirshSparsifyingPriorsBayesian2022,
  author    = {Hirsh, Seth M. and Barajas-Solano, David A. and Kutz, J. Nathan},
  title     = {Sparsifying priors for Bayesian uncertainty quantification in model discovery},
  journal   = {Royal Society Open Science},
  year      = {2022},
  doi       = {10.1098/rsos.211823}
}

% ungeprüft: author = {Somalwar, Anne and Lee, Bruce D. and Pappas, George J. and Matni, Nikolai}
% year aus arXiv-ID (2504 = April 2025)
@misc{somalwarLearningImperfectModels2025,
  title         = {Learning with Imperfect Models: When Multi-step Prediction Mitigates Compounding Error},
  year          = {2025},
  eprint        = {2504.01766},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

@article{hastieBestSubsetForward2020,
  author    = {Hastie, Trevor and Tibshirani, Robert and Tibshirani, Ryan},
  title     = {Best Subset, Forward Stepwise or Lasso? Analysis and Recommendations Based on Extensive Comparisons},
  journal   = {Statistical Science},
  volume    = {35},
  number    = {4},
  pages     = {579--592},
  year      = {2020},
  doi       = {10.1214/19-STS733}
}

% ungeprüft: pages = {1767--1781}; Vorname Spinelli
@article{piroddiIdentificationAlgorithmPolynomial2003,
  author    = {Piroddi, L. and Spinelli, W.},
  title     = {An identification algorithm for polynomial {NARX} models based on simulation error minimization},
  journal   = {International Journal of Control},
  volume    = {76},
  number    = {17},
  year      = {2003},
  doi       = {10.1080/00207170310001635419}
}

% ungeprüft: pages = {1442--1456}
@article{farinaIterativeAlgorithmSimulation2010,
  author    = {Farina, Marcello and Piroddi, Luigi},
  title     = {An iterative algorithm for simulation error based identification of polynomial input--output models using multi-step prediction},
  journal   = {International Journal of Control},
  volume    = {83},
  number    = {7},
  year      = {2010},
  doi       = {10.1080/00207171003793262}
}

% ungeprüft: pages = {2879--2884}; doi = {10.23919/ACC60939.2024.10644812}
@inproceedings{machadoSparseIdentificationNonlinear2024,
  author    = {Machado, Gabriel F. and Jones, Morgan},
  title     = {Sparse Identification of Nonlinear Dynamics with Side Information ({SINDy-SI})},
  booktitle = {2024 American Control Conference (ACC)},
  year      = {2024},
  url       = {https://ieeexplore.ieee.org/document/10644812/}
}

% ungeprüft: doi = {10.1016/0005-1098(93)90124-C} (über Suche zugeordnet); Vornamen
@article{tullekenGreyboxModellingIdentification1993,
  author    = {Tulleken, H. J. A. F.},
  title     = {Grey-box modelling and identification using physical knowledge and bayesian techniques},
  journal   = {Automatica},
  volume    = {29},
  number    = {2},
  pages     = {285--308},
  year      = {1993}
}

@article{aguirreImposingSteadystatePerformance2004,
  author    = {Aguirre, L. A. and Barroso, M. F. S. and Saldanha, R. R. and Mendes, E. M. A. M.},
  title     = {Imposing steady-state performance on identified nonlinear polynomial models by means of constrained parameter estimation},
  journal   = {IEE Proceedings - Control Theory and Applications},
  volume    = {151},
  number    = {2},
  pages     = {174--179},
  year      = {2004},
  doi       = {10.1049/ip-cta:20040102}
}

% year aus arXiv-ID (1907 = Juli 2019)
@misc{aguirreBirdsEyeView2019,
  author        = {Aguirre, Luis A.},
  title         = {A Bird's Eye View of Nonlinear System Identification},
  year          = {2019},
  eprint        = {1907.06803},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% ungeprüft: pages = {3216--3221}; doi = {10.1109/CDC.2016.7798752}
@inproceedings{cisnerosEfficientNonlinearModel2016,
  author    = {Cisneros, Pablo S. G. and Voss, Sophia and Werner, Herbert},
  title     = {Efficient Nonlinear Model Predictive Control via quasi-{LPV} representation},
  booktitle = {2016 IEEE 55th Conference on Decision and Control (CDC)},
  year      = {2016},
  url       = {https://ieeexplore.ieee.org/document/7798752/}
}

% ungeprüft: Endseite 473 (vermutlich mit Diskussion)
@article{meinshausenStabilitySelection2010,
  author    = {Meinshausen, Nicolai and B{\"u}hlmann, Peter},
  title     = {Stability selection},
  journal   = {Journal of the Royal Statistical Society: Series B (Statistical Methodology)},
  volume    = {72},
  number    = {4},
  year      = {2010},
  doi       = {10.1111/j.1467-9868.2010.00740.x}
}

% ungeprüft: volume = {95}; pages = {112581}; ausgeschriebene Vornamen
@article{sheikhComprehensiveApproachSparse2024,
  author    = {Sheikh, A. M. A. and Donkers, M. C. F. and Bergveld, H. J.},
  title     = {A comprehensive approach to sparse identification of linear parameter-varying models for lithium-ion batteries using improved experimental design},
  journal   = {Journal of Energy Storage},
  year      = {2024},
  doi       = {10.1016/j.est.2024.112581}
}
```

### A3

Nur direkt relevante Treffer. `bruntonDiscoveringGoverningEquations2016` und
`desilvaPySINDyPythonPackage2020` sind schon in der Bib.

```bibtex
% ungeprüft: author = {Champion, Kathleen and Lusch, Bethany and Kutz, J. Nathan and Brunton, Steven L.};
%            volume = {116}; number = {45}; pages = {22445--22451}
@article{championDatadrivenDiscoveryCoordinates2019,
  title     = {Data-driven discovery of coordinates and governing equations},
  journal   = {Proceedings of the National Academy of Sciences},
  year      = {2019},
  doi       = {10.1073/pnas.1906995116}
}

% ungeprüft: Zeitschriftenfassung journal = {Journal of Machine Learning Research}; year = {2025};
%            volume = {26}; number = {248}; pages = {1--83}
% ungeprüft: author = {Otto, Samuel E. and Zolman, Nicholas and Kutz, J. Nathan and Brunton, Steven L.}
@misc{ottoUnifiedFrameworkEnforce2023,
  title         = {A Unified Framework to Enforce, Discover, and Promote Symmetry in Machine Learning},
  eprint        = {2311.00212},
  archivePrefix = {arXiv},
  note          = {Preprint; Jahr aus arXiv-ID (2311 = November 2023)},
  year          = {2023}
}

% ungeprüft: author = {Ahmadi, Amir Ali and El Khadir, Bachir}; Langfassung SIAM Review 65(1), 183--223, 2023
@inproceedings{ahmadiLearningDynamicalSystems2020,
  title     = {Learning Dynamical Systems with Side Information},
  booktitle = {Proceedings of the 2nd Conference on Learning for Dynamics and Control (L4DC)},
  series    = {Proceedings of Machine Learning Research},
  volume    = {120},
  year      = {2020},
  url       = {https://proceedings.mlr.press/v120/ahmadi20a.html}
}

% ungeprüft: author = {Zar, Jerrold H.}; volume = {49}; number = {6}; pages = {1161}
@article{zarEffectChoiceTemperature1968,
  title     = {The Effect of the Choice of Temperature Scale on Simple Linear Regression Equations},
  journal   = {Ecology},
  year      = {1968},
  doi       = {10.2307/1934501}
}

% ungeprüft: author = {Feng, Yuxiang and Mangan, Niall M. and Jayadharan, Manu}
@misc{fengIllConditioningDictionaryBased2026,
  title         = {Ill-Conditioning in Dictionary-Based Dynamic-Equation Learning: A Systems Biology Case Study},
  year          = {2026},
  eprint        = {2603.11330},
  archivePrefix = {arXiv},
  note          = {Preprint}
}

% ungeprüft: author = {Akan, M. Tolga and Portilla, Christian and Özkan, Leyla};
%            journal = {IFAC-PapersOnLine}; year = {2024}; volume = {58}; number = {14}; pages = {271--276}
@article{akanModelDiscrepancyLearning2024,
  title     = {Model Discrepancy Learning for Heat Exchanger Networks},
  url       = {https://www.sciencedirect.com/science/article/pii/S2405896324011005}
}

% ungeprüft: author = {Loiseau, Jean-Christophe}; year = {2020}; volume, pages
@article{loiseauDatadrivenModelingChaotic2020,
  title     = {Data-driven modeling of the chaotic thermal convection in an annular thermosyphon},
  journal   = {Theoretical and Computational Fluid Dynamics},
  doi       = {10.1007/s00162-020-00536-w}
}

% ungeprüft: author = {Iacob, Lucian C. and T{\'o}th, Roland and Schoukens, Maarten};
%            journal = {Automatica}; year = {2024}; volume = {162}; pages = {111525}
@article{iacobKoopmanFormNonlinear2024,
  title     = {Koopman form of nonlinear systems with inputs},
  url       = {https://www.sciencedirect.com/science/article/pii/S0005109824000177}
}

% ungeprüft: author = {Koelewijn, Patrick J. W. and Singh, Rajiv and Seiler, Peter and T{\'o}th, Roland};
%            journal = {IFAC-PapersOnLine}; year = {2024}
@article{koelewijnLearningReducedOrderLinear2024,
  title     = {Learning Reduced-Order Linear Parameter-Varying Models of Nonlinear Systems},
  url       = {https://www.sciencedirect.com/science/article/pii/S2405896324013193}
}
```

---

## Offen / nicht belegt

Allgemein:

- Kein Volltext gelesen (Ausnahme: PySINDy-JOSS-Manuskript im Repo). Alle Seiten- und
  Gleichungsangaben der Kapitel sind ungeprüft.
- Alle mit (S) markierten Angaben (Autoren, Bände, Seiten, DOIs, Inhaltsangaben) stammen aus
  Suchzusammenfassungen und sind in Zotero bzw. am Original zu prüfen.
- Keys sind Vorschläge; Umlaut-Umschrift (tschoeke/tschoke, wahlstrom/wahlstroem) und
  Bindestrichwörter von Better-BibTeX erzeugen lassen.

A1 (Stellen am Original prüfen):

- Pucher 2018, S. 68, Gl. 41 („Rekuperationsgrad“); Seitenbereich 43–87 nur (S).
- Pantow 2018, S. 696, Gl. 8 und 9; Autor, Seiten 679–716 und Druckkapitel-DOI nur (S).
- Holmgren 2005, Gl. 3.26 (Plus statt Minus); Jahr, Berichtsnummer, Vorname nur (S).
- Llamas: Dissertation 2018 oder Artikel 2019? S. 18 in welcher Quelle? Zeitschrift, Band, Seiten
  des Artikels fehlen; ISBN und DOI der Dissertation nur (S).
- Heywood: Auflage mit S. 54, Gl. 2.27a.
- Druckverlust-Beleg: Gleichung in Eriksson & Nielsen 2014, Kap. 7 (inkompressible Drossel) nicht
  gesehen; Shah & Sekulić Kap. 6 und VDI Heat Atlas L1 nur bibliografisch; deutsche Ausgabe des
  VDI-Wärmeatlas, Kays & London und Hendricks nicht gesucht.
- Ziel des Keys `erikssonMODELINGTURBOCHARGEDSI` („S. 132“ passt nicht zu Eriksson 2007, S. 523–538).
- Hansen 1989: Autor, Hochschule, Jahr nur (S); Vorname nicht gesehen; keine DOI für ACC 1988/1989.
- Chiuso: welche Arbeit das Kürzel „PBSID“ zuerst verwendet (2005, CDC 2006, 2007); DOIs der
  Automatica-Artikel nur (S) bzw. über Suche zugeordnet; TAC-Band/Seiten nur (S).
- Van den Hof & Schrama 1993: Autorenreihenfolge und DOI nur (S) bzw. Dateiname; CDC-1992-Fassung
  nur über Dateiname; Einordnung bei Forssell & Ljung (ch3 Z. 706–707) nicht geprüft.
- Stanivuk 2021: Autoren 2–4, Band, Seiten, DOI nur (S); Form von Gl. 9 auf S. 117.
- Arava 2026: Autoren, Band, Heft, Artikelnummer nur (S); ob ein latenter Term fehlt.
- Taler 2017: nicht identifiziert; Abgleich mit `BIB_NACHTRAG_0709.bib`.
- Wahlström 2009: S. 7 und die „Gegenposition“ (Temperaturzustand des Kühlers) ungeprüft; nach (S)
  eher fraglich.
- Ekberg 2018: K1 oder K2.
- PG 51/60DF-M: Ausgabe, Jahr, S. 117, Tab. 74. Öffentlicher Projektguide zum 49/60DF nicht gefunden.

A2:

- Tulleken 1993: Vorzeichen stationärer Verstärkungen im Original.
- Machado & Jones 2024: Positivität/Monotonie im Original; Seiten und DOI nur (S).
- Aguirre arXiv 1907.06803: Inhalt Abschn. 7.1/7.2.
- Schaeffer, Tran, Ward 2018: Monom- vs. Legendre-Basis und Sparsamkeit.
- Rudy u. a. 2017: STRidge im Supplement.
- Messenger & Bortz 2021: ODE-Fokus am Abstract; Seiten nur (S).
- Zheng u. a.: Jahr 2018 oder 2019 in Zotero festlegen.
- Kaptanoglu 2021: Metadaten Schlegel & Noack 2015 (nur aus Notebook).
- Seiten nur (S): Piroddi & Spinelli, Farina & Piroddi, Machado & Jones, Cisneros u. a.,
  Meinshausen & Bühlmann (Endseite). Band/Artikelnummer nur (S): Sheikh u. a., Hirsh u. a.,
  Bakarji u. a., Kaptanoglu u. a. 2023.
- Vornamen offen: Spinelli, Tulleken, Aguirre u. a. 2004, Sheikh.
- Farina & Piroddi, Int. J. Syst. Sci. 43(2): Jahr 2011 oder 2012, DOI nicht gefunden (nur
  Verwechslungshinweis).

A3:

- Otto u. a. und Ahmadi & El Khadir: ob Translations- bzw. Offsetinvarianz im Volltext als
  Beispiel vorkommt.
- Akan u. a. 2024: Bibliothek (ε-NTU/LMTD?) und ob echte Messdaten verwendet werden.
- Koelewijn u. a. 2024 und Iacob u. a. 2024: Erwähnung von SINDy im Volltext; Zuordnung des
  Koelewijn-Snippets.
- Datenstatus (Messung/Simulation) der Koopman-MPC-Arbeiten in A3.5, vor allem arXiv:2207.04184,
  arXiv:2511.04437 und ORC (Control Eng. Pract. 2023).
- Nicht abgedeckt: Scopus/Web of Science, Google Scholar, Zitationsverfolgung, Tóth-Monografie,
  Survey arXiv:2303.10471. Vorschlag für die lokale Nachsuche:
  - Thema 3: „SINDy“ AND („heat exchanger“ OR „effectiveness-NTU“ OR NTU OR LMTD)
  - Thema 4: „SINDy“ AND („linear parameter-varying“ OR LPV OR „quasi-LPV“ OR scheduling)
  - Thema 5: (SINDYc OR SINDy OR DMDc OR EDMDc OR Koopman) AND (intercooler OR „charge air
    cooler“ OR „air path“ OR „boost pressure“ OR EGR), 2020–2026, Filter Messdaten
