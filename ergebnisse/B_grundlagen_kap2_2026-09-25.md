# Auftrag B — Grundlagen Kap. 2: Herleitung geprüft und ergänzt (Cloud-Sitzung, 25.09.2026)

Grundlage: `auftraege/B_grundlagen_kap2.md`, `kontext/ch2.tex` (Kopie vom 25.09.2026).
Zeilenangaben beziehen sich auf diese Kopie. Stichpunkt-Zuarbeit, kein Fließtext.

## Vorbemerkung

- Algebra mit sympy 1.14 nachgerechnet; Skript im Anhang, alle Prüfungen reproduzierbar.
- Lehrbuchstellen konnten nicht am Original geprüft werden: In dieser Sitzung waren Verlagsseiten,
  arXiv und doi.org gesperrt, nur die Websuche lief. Jede zitierte Stelle ist deshalb
  „nicht prüfbar“, sofern nicht anders vermerkt.
- Begriffe: HT und LT heißen hier **Stufe** des Ladeluftkühlers (Vorgabe `CLAUDE.md`).
  ch2 Z. 178–185 verwendet noch „Bündel“ und belegt „Stufe“ mit LP/HP (s. Befund T1).
- Herkunftskennung der Literaturangaben wie in Auftrag A: (T) wörtlich in Treffertitel/URL,
  (G) aus GitHub-Datei gelesen, (S) nur aus Suchzusammenfassung.

---

## Teil B1 — Gegenprüfung der vorhandenen Herleitung

### Algebra

| Gleichung (Label, Zeile) | Befund | Vorschlag |
|---|---|---|
| `eq.grundlagen.basic.luftleistung` (Z. 330–333) | Definition, nichts umzuformen | – |
| `eq.grundlagen.basic.waermedurchgang` (Z. 346–349) | Definition, nichts umzuformen | – |
| `eq.grundlagen.basic.stufen` (Z. 366–374) und `eq.grundlagen.basic.ltspanne` (Z. 387–391) | Umformung korrekt | Zusätzlich die geschlossene Form angeben (unten G1): $\Tstat$ ist eine konvexe Kombination von $\Tin$, $\THT$, $\TLT$ mit Gewichten $(1-\varepsilon_{HT})(1-\varepsilon_{LT})$, $\varepsilon_{HT}(1-\varepsilon_{LT})$, $\varepsilon_{LT}$; Summe 1 |
| Kommentar EB21 (Z. 315–320): `Tstat = T_col_in - PH*dH - P3*d3`, `d3 = (T_HTCW-T_LTCW)+cFix*dH` | Exakte Serienidentität gilt genau für $P_H=\varepsilon_{HT}$, $P_3=\varepsilon_{LT}$, $c=1-\varepsilon_{HT}$ (sympy). Kommentar „cFix ist nicht exakt 1-PH“ ist damit richtig eingeordnet | Im Text: mit festem `cFix` ist die EB21-Form eine Näherung der Serienform; sie wird exakt, wenn `cFix = 1 - PH` |
| `eq.grundlagen.basic.produkte` (Z. 404–413) | Ausmultiplizieren korrekt | Für den QP festhalten: $a_2 g(\valveCA)\Delta T$ ist linear in $g(\valveCA)$, solange $\Delta T$ aus exogenen Größen besteht ($\Tin$, $\THT$, $\TLT$) und nicht aus $\Tout$ |
| `eq.grundlagen.basic.dynamik` (Z. 436–440) | Form korrekt. $\lambda(\mrel,\valveCA)$ mit Ventilabhängigkeit ergibt ein Produkt $\valveCA\cdot\Tout$: bilinear, **nicht QP-tauglich** ohne Einfrieren | Satz ergänzen: Ventil nur im Zielwert führen ist die Bedingung für den linearen QP (Z. 447–448 nennt es nur Modellvereinfachung) |
| Z. 446: $\lambda=c_\lambda\mrel$ | Aus `eq.energiebilanz.dyn` folgt $\lambda=(\dot m_L c_{p,L}+U_{\mathrm{eff}}A)/C_{\mathrm{eff}}$ (sympy). Der Anteil $U_{\mathrm{eff}}A/C_{\mathrm{eff}}$ verschwindet bei $\dot m_L\to0$ nicht | Affine Rate $\lambda=c_0+c_1\mrel$ als physikalisch näherliegende Variante nennen; reine Proportionalität ist eine zusätzliche Annahme |
| `eq.energiebilanz` (Z. 524–529) | Vorzeichen korrekt (Wasser erwärmt sich) | Einstufige Ersatzbeschreibung ist schon im Copilot-Punkt Z. 497–503 benannt |
| Kennzahlen Z. 533–538 | $\varepsilon=(C_{\min}/C_L)\,\varepsilon_Q$ korrekt (sympy) | – |
| Gegenstrom-Formel Z. 539–541 | Korrekt. Grenzfall $C_r\to0$ ergibt $1-e^{-\mathrm{NTU}}$ (sympy). Bei $C_r=1$ ist der Ausdruck 0/0, Grenzwert $\mathrm{NTU}/(1+\mathrm{NTU})$ | Gültigkeit „$C_r<1$“ an die Formel schreiben |
| `eq.Tout.stat` und unnummerierte Zweistufenform (Z. 568–577) | Korrekt; Exponentialform = Stufenform mit $\varepsilon=1-e^{-\mathrm{NTU}}$ (sympy) | Unnummerierte Gleichung nummerieren; Z. 994–995 greift sie als „serielle ε-NTU-Beziehung“ auf |
| Räumliche Bilanz Z. 584–585 | $C_L\,\mathrm dT/\mathrm da=-k(T-T_W)$ ergibt $T(A)=T_W+(T_0-T_W)e^{-kA/C_L}$ (sympy); $k$ ist hier flächenbezogen | Einheit von $k$ (W/(m²K)) nennen, sonst Verwechslung mit $kA$ |
| Z. 555–556: „Zielwert liegt zwischen $\Tin$, $\THT$ und $\TLT$“ | Stimmt, präziser als konvexe Kombination (s. oben), gilt für $0\le\varepsilon\le1$ | Gewichte angeben; sie zeigen, dass $\THT$ nur über $\varepsilon_{HT}(1-\varepsilon_{LT})$ eingeht |
| `eq.grundlagen.gain.epsntu` (Z. 796–802) | Kettenregel korrekt (sympy). Voraussetzung: $\dot m_L$ fest; hängt $\varepsilon$ von $\dot m_L$ ab und bewegt sich $\dot m_L$ mit, fehlt ein Term | Festhaltebedingung „$\dot m_L$ konstant“ in die Gleichung schreiben |
| Z. 781–783: „Vorzeichen negativ … bei mit dem Hub wachsendem $\varepsilon$“ | Zusätzlich nötig: Kühlerspanne $\Tin-\TLT>0$ | Bedingung ergänzen (für die LT-Stufe genauer $T_{zw}-\TLT>0$, vgl. Z. 807–811) |
| Gain-Gleichung vs. Zweistufenform | `eq.grundlagen.gain.epsntu` nutzt die einstufige Spanne $\Tin-\TLT$; die Zweistufenform (Z. 807–811) die LT-Spanne $T_{zw}-\TLT$ | Kennzeichnen, dass die erste Gleichung die einstufige Ersatzform ist; für die Arbeit gilt die zweite |
| Stationärer Grenzwert Z. 848–850 | $\varepsilon=N/(1+N)$, $N=U_{\mathrm{eff}}A/(\dot m_L c_{p,L})$ korrekt (sympy) | – |
| Zeitkonstante Z. 835–840 | $\tau=C_{\mathrm{eff}}/(\dot m_L c_{p,L}+U_{\mathrm{eff}}A)$ korrekt; mit Mitteltemperatur $\tau=C/(\dot m_L c_p+kA/2)$ korrekt (sympy) | – |
| Lokale Form Z. 911–920 | $a=(\dot m_L c_{p,L}+U_{\mathrm{eff}}A)/C_{\mathrm{eff}}$, $b=U_{\mathrm{eff}}A/C_{\mathrm{eff}}$ korrekt (sympy) | – |
| Massenstromexponent Z. 611–613 | $\mathrm{d}\ln\mathrm{NTU}/\mathrm{d}\ln\dot m_L=p-1$ korrekt, wenn $C_{\min}=C_L$ | Bedingung $C_{\min}=C_L$ an dieser Stelle wiederholen (steht erst Z. 764–765) |
| `eq.luftproxy.druckverlust`, `.dichte`, `.relativ` (Z. 653–691) | Umstellung korrekt: $\dot m_L=A_{\mathrm{Str}}\sqrt{2\,\dpHP\,\rho_L/\zeta_L}$; mit $\rho=p/(RT)$ folgt $\dot m_L\propto\sqrt{\dpHP\,p/T}$; $\mrel=\dot m_L/\dot m_{L,\mathrm{ref}}$ unter denselben Annahmen (sympy) | – |
| $q_{\mathrm{rel}}$ (Z. 706–712) | $q_{\mathrm{rel}}=\mrel\sqrt{T/T_{\mathrm{ref}}}$ korrekt (sympy) | – |
| MPC-Satz Z. 1080–1082: „Ist das Modell linear in der Stellgröße, ist (mpc) ein konvexes QP“ | **Unvollständig.** Über mehrere Schritte ist die Prädiktion nur affin in $u$, wenn das Modell auch im Zustand affin ist. Gegenbeispiel (sympy): $x^+=x-\theta x^2+u$ ergibt $\partial^2x_2/\partial u_0^2=-2\theta\neq0$. Bilinear $u\cdot x$: gemischte Ableitung $\neq0$. LPV mit exogenem Scheduling ($\mrel$ als Messgröße): beide Ableitungen null | Formulieren: Modell affin in Zustand und Stellgröße bei gegebenem Verlauf der exogenen Größen (LPV mit gemessener Scheduling-Größe); dann quadratische Kosten plus lineare Beschränkungen = konvexes QP |

### Annahmen, die fehlen oder nur verstreut stehen

- **Ventilschaltung (Z. 249–256):** Z. 250 „Dreiwegeventil stellt den Wasserdurchsatz“ (Verteilen),
  Z. 253 „Mischventile“ (Mischen). Für $\varepsilon_{LT}$ mit Bezug $\TLT$ muss die
  LT-Stufe mit Wasser der Temperatur $\TLT$ angeströmt werden, also Verteilschaltung mit Bypass.
  Bei Mischschaltung wäre die Wassereintrittstemperatur eine Mischtemperatur. Schaltung nennen
  und als Annahme führen.
- **Messort von $\THT$, $\TLT$:** Eintritt der jeweiligen Stufe oder Kreisvorlauf? Die
  Stufengleichungen setzen die Wassereintrittstemperatur der Stufe voraus.
- **Quasistationäres $\varepsilon$:** Die Stufengleichungen nehmen $\varepsilon$ als momentane
  Funktion von Durchsätzen; Wand- und Wasserdynamik stecken dann allein in $\lambda$. Einmal
  ausdrücklich nennen (steht implizit in Z. 848–859).
- **$\varepsilon$-NTU-Voraussetzungen:** konstante Stoffwerte, konstantes $k$ über der Fläche,
  keine Längswärmeleitung, feste Stromführung. Z. 512–516 nennt nur die Stromführung.
- **Kapazitätsstrom bei kleinem Hub:** Z. 543–546 setzt $C_{\min}=C_L$ „über den ganzen
  Ventilhub“; Z. 738–741 nennt als Hypothese den Wechsel von $C_{\min}$ auf die Wasserseite bei
  kleinen Hüben. Dann gilt $\varepsilon=1-e^{-\mathrm{NTU}}$ für die Luftseite nicht mehr.
  Beide Stellen gegenseitig verweisen und den Gültigkeitsbereich der Grenzfallformel eingrenzen.
- **Einzustandsbilanz:** eine konzentrierte Kapazität; $\Tout$ als Zustand steht für eine
  Mitteltemperatur; Sensor- und Transportdynamik getrennt (Z. 866–874 nennt sie).
- **Proxy:** Annahmen sind vollständig genannt (Z. 643–650, 717–726); nichts zu ergänzen.

### Zitierte Lehrbuchstellen

- Alle Stellen in diesem Abschnitt (Almbauer 2019 Gl. 31.x, Pucher 2012 Gl. 12.6–12.8,
  Isermann 2014 Gl. 4.6.x/4.7.x, Eriksson & Nielsen 2014 Gl. 7.x, Guzzella & Onder 2010,
  Sui u. a. 2022 Anhang B, Yin & Jensen 2003, Vagapov u. a. 2022, Rupprecht 2016, Mrosek 2009,
  Theotokatos 2010, Baldi 2015): **nicht prüfbar** in dieser Sitzung (kein Volltextzugang).
- Inhaltliche Plausibilität (nicht Stelle): Die Gleichungsformen passen zu den genannten
  Gleichungstypen (Bilanz, Serienwiderstand, $\varepsilon$-NTU, Behälterbilanz). Das ist keine
  Prüfung der Seitenzahl.
- Formale Auffälligkeiten:
  - Z. 739 und Z. 863 nennen „Vagapov 2024“ im Klartext, obwohl der Key
    `vagapovModellierungIdentifikationUnd2024` existiert (ch3 Z. 1081). Durch `\cite` ersetzen.
  - Z. 650: Quadratischer Druckverlust nur mit MathWorks-Doku belegt; Kandidaten aus Auftrag A
    (Eriksson & Nielsen 2014 Kap. 7, Shah & Sekulić 2003 Kap. 6, VDI Heat Atlas L1) ergänzen.
  - Z. 209, 217: `\cite{everllencese4960DFProject2025}` ohne Seitenangabe, andere Werkszitate haben Seiten.

### Stufenreihenfolge (HT zuerst, dann LT)

- Konsistent in: Z. 178–181 (Anlagenbeschreibung), Z. 204–208 (HT-Kreis), Z. 362–372
  (Grundherleitung), Z. 551–553 (Stichpunkte), Z. 574–577 (Exponentialform), Z. 807–811
  (partielle Stellwirkung), Z. 892 (Einzustandsgrenze).
- Einstufige Ersatzformen ohne HT-Stufe: `eq.energiebilanz` (Z. 524–529),
  `eq.energiebilanz.dyn` (Z. 877–884), `eq.grundlagen.gain.epsntu` (Z. 796–802). Die
  Copilot-Punkte Z. 497–503 und 888–896 kennzeichnen das. Die Gain-Gleichung ist noch nicht
  gekennzeichnet (s. Tabelle).
- **T1 Begriff:** Z. 184–185 definiert „Stufe“ = LP/HP und „Bündel“ = HT/LT. Nach `CLAUDE.md`
  heißt HT/LT „Stufe“. Vorschlag: „Aufladestufe (LP/HP)“ und „Kühlerstufe (HT/LT)“; „Bündel“
  steht in Z. 179, 180, 185, 204, 207, 220, 249, 485, 519, 551–554, 557, 733, 907.
- **T2 Symbol:** $\lambda$ steht für die Relaxationsrate (Z. 438), das MPC-Gewicht (Z. 1068)
  und in ch3 für den STLSQ-Schwellwert. Ein Symbol umbenennen (z. B. MPC-Gewicht $\rho_{\Delta u}$).

### G1 Geschlossene Form des stationären Zielwerts (sympy-geprüft, direkt einfügbar)

```latex
% COPILOT-STICHPUNKTE BEGIN B1-Zielwert-konvex
\begin{itemize}
  \item Einsetzen von $T_{\mathrm{zw}}$ in die LT-Stufe ergibt den Zielwert als gewichtete
    Summe der drei Eintrittstemperaturen (eigene Algebra):
    \begin{equation}
      \label{eq.grundlagen.basic.konvex}
      \Tstat = (1-\varepsilon_{\mathrm{HT}})(1-\varepsilon_{\mathrm{LT}})\,\Tin
             + \varepsilon_{\mathrm{HT}}(1-\varepsilon_{\mathrm{LT}})\,\THT
             + \varepsilon_{\mathrm{LT}}\,\TLT .
    \end{equation}
  \item Die Gewichte summieren sich zu eins und sind für
    $0\le\varepsilon_{\mathrm{HT}},\varepsilon_{\mathrm{LT}}\le1$ nicht negativ; der Zielwert
    liegt damit im Intervall der drei Temperaturen.
  \item Äquivalente Differenzform, Anschluss an die Bibliothek:
    $\Tstat=\Tin-\varepsilon_{\mathrm{HT}}(\Tin-\THT)
      -\varepsilon_{\mathrm{LT}}\bigl[(\THT-\TLT)+(1-\varepsilon_{\mathrm{HT}})(\Tin-\THT)\bigr]$.
  \item Eine Verschiebung aller drei Temperaturen um denselben Betrag verschiebt $\Tstat$ um
    genau diesen Betrag. Die Differenzform hat diese Eigenschaft für beliebige Koeffizienten,
    eine Form mit freiem Absolutterm in $\Tin$ nur bei passenden Koeffizienten.
\end{itemize}
% COPILOT-STICHPUNKTE END B1-Zielwert-konvex
```

---

## Teil B2 — fehlende Grundlagenbausteine als Stichpunktgerüst

Je Baustein ein Block im Stil `% COPILOT-STICHPUNKTE`, direkt in LaTeX einfügbar. Keys, die noch
nicht in der Bib stehen, sind mit `% neu:` markiert und unten unter „BibTeX-Entwürfe B2“ aufgeführt.
Gleichungen sind eigene Standardherleitungen (sympy-geprüft, wo angegeben); die Anker belegen die
Methode, nicht die konkrete Formulierung.

### B2.1 Zeitdiskretisierung

```latex
% COPILOT-STICHPUNKTE BEGIN B2-Zeitdiskretisierung
\begin{itemize}
  \item Ausgangspunkt ist die Relaxationsform Gl.~(\ref{eq.grundlagen.basic.dynamik}),
    $\mathrm d\Tout/\mathrm dt=\lambda(\Tstat-\Tout)$. Gemessen wird im Abtasttakt
    $\Delta t$; Stell- und Störgrößen gelten zwischen zwei Abtastpunkten als konstant
    (Halteglied nullter Ordnung, ZOH).
  \item Exakte Lösung über ein Intervall bei konstantem $\lambda$ und $\Tstat$ (sympy-geprüft):
    \begin{equation}
      \label{eq.grundlagen.zoh}
      T_{\mathrm{eng,in},k+1}=e^{-\lambda\Delta t}\,T_{\mathrm{eng,in},k}
        +\bigl(1-e^{-\lambda\Delta t}\bigr)\,T_{\mathrm{stat},k}.
    \end{equation}
  \item Explizites Euler-Verfahren ersetzt $e^{-\lambda\Delta t}$ durch $1-\lambda\Delta t$:
    \begin{equation}
      \label{eq.grundlagen.euler}
      T_{\mathrm{eng,in},k+1}=(1-\lambda\Delta t)\,T_{\mathrm{eng,in},k}+\lambda\Delta t\,T_{\mathrm{stat},k}.
    \end{equation}
    Fehler je Schritt von der Ordnung $(\lambda\Delta t)^2/2$; stabil nur für $\lambda\Delta t<2$.
  \item Pol der diskreten Form $z=e^{-\lambda\Delta t}$; Rückrechnung auf die Zeitkonstante
    $\tau=1/\lambda=-\Delta t/\ln z$. Ein identifizierter Koeffizient nahe eins ist deshalb
    kein Mangel, sondern Folge von $\Delta t\ll\tau$.
  \item Map-Form von \sindyc{} und \edmdc{} schätzt direkt $e^{-\lambda\Delta t}$ bzw.
    $1-\lambda\Delta t$ als Koeffizienten; bei geändertem Takt neu schätzen oder umrechnen.
  \item Hängt $\lambda$ von $\mrel$ ab, ist \eqref{eq.grundlagen.zoh} nichtlinear in $\mrel$,
    die Euler-Form \eqref{eq.grundlagen.euler} affin. Ein Bibliotheksterm $\mrel\,\Tout$ entspricht
    damit der Euler-Näherung; Abweichung klein, solange $\lambda\Delta t\ll1$.
  \item Die kontinuierliche Standardform braucht eine numerische Ableitung
    (ch.~\ref{ch.standderTechnik}, Abschnitt~\ref{ssec.sot.sindy.discrete}); die Map-Form nicht.
  \item Takt im Verhältnis zur Prozessdynamik und zum Reglertakt ($500\,$ms,
    Abschnitt~\ref{ChATCo}) wählen; Faustregel zur Abtastzeit aus
    \cite{astromComputerControlledSystemsTheory1997} mit Stelle belegen.
  \item Anker: \cite{astromComputerControlledSystemsTheory1997} (Abtastung mit Halteglied,
    Kap.~2, Abschnittsname nur aus Suchzusammenfassung),
    \cite{franklinDigitalControlDynamic1998} (Euler gegenüber Halteglied-Äquivalent).
    \cite{kaiserSparseIdentificationNonlinear2018} verwendet laut Autoren-Code ein
    kontinuierliches \sindyc-Modell mit Runge-Kutta-Schritt in einem nichtlinearen MPC (SQP),
    kein QP; als Beleg für die diskrete QP-Form daher nicht geeignet.
  \item Anschluss: Die Arbeit identifiziert in Map-Form; Gl.~\eqref{eq.grundlagen.zoh} erklärt,
    wie der geschätzte Eigenkoeffizient mit Takt und Zeitkonstante zusammenhängt.
\end{itemize}
% COPILOT-STICHPUNKTE END B2-Zeitdiskretisierung
```

### B2.2 Totzeit und Ratenbegrenzung eines Stellantriebs

```latex
% COPILOT-STICHPUNKTE BEGIN B2-Totzeit-Rate
\begin{itemize}
  \item Totzeit $\theta$ als ganzzahliges Vielfaches des Takts, $\theta=n_d\Delta t$:
    verschobener Eingang $u_{k-n_d}$ im Modell.
  \item Zustandserweiterung für MPC: $n_d$ Verzögerungszustände
    $\xi_k=[u_{k-1},\dots,u_{k-n_d}]^{\top}$ mit Schiebematrix; das Modell bleibt linear,
    die Zustandsdimension wächst um $n_d$:
    \begin{equation}
      \label{eq.grundlagen.totzeit}
      \xi_{k+1}=S\,\xi_k+e_1\,u_k,\qquad u^{\mathrm{wirk}}_k=e_{n_d}^{\top}\xi_k .
    \end{equation}
  \item Nicht ganzzahliger Anteil: Runden auf den Takt oder modifizierte z-Transformation
    (\cite{astromComputerControlledSystemsTheory1997}, Stelle nachschlagen).
  \item Padé-Näherung erster Ordnung
    $e^{-\theta s}\approx(1-\theta s/2)/(1+\theta s/2)$: kontinuierlich, erzeugt eine
    Nullstelle rechts; für ein zeitdiskretes MPC entbehrlich.
  \item Verzögerungskette (PT$_n$): nähert Totzeit plus Glättung; $n$ Zustände, nur näherungsweise.
  \item Ratenbegrenzung des Antriebs als lineare Ungleichung im QP:
    \begin{equation}
      \label{eq.grundlagen.rate}
      |u_k-u_{k-1}|\le\dot u_{\max}\,\Delta t .
    \end{equation}
  \item Totzeit nur bei Richtungswechsel (Umkehrspanne, Abschnitt~\ref{ChATCo}) ist
    hysteresebehaftet und im linearen QP nicht exakt darstellbar; als Modellfehler dem
    Störgrößenbeobachter überlassen oder konservativ über kleinere Ratenschranken abfangen.
  \item Anker: \cite{normeyricoControlDeadtimeProcesses2007} (Kap.~2 Totzeitprozesse,
    Kap.~9 MPC für Totzeitprozesse); \cite{maciejowskiPredictiveControlConstraints2002},
    \cite{camachoModelPredictiveControl2007} (Kap.~7 beschränktes MPC; Stellen für
    $\Delta u$-Schranken lokal nachschlagen);
    \cite{rawlingsModelPredictiveControl20202020}.
  \item Anschluss: In ein lineares QP passen verschobener Eingang mit Zustandserweiterung und die
    Ratenschranke \eqref{eq.grundlagen.rate}; Padé und Umkehrspanne nicht.
\end{itemize}
% COPILOT-STICHPUNKTE END B2-Totzeit-Rate
```

### B2.3 Lineares MPC als QP

```latex
% COPILOT-STICHPUNKTE BEGIN B2-MPC-QP
\begin{itemize}
  \item Modell affin in Zustand und Stellgröße bei gegebenem Verlauf der exogenen Größen
    $d_k$ (z.\,B. $\Tin$, $\TLT$, $\mrel$):
    $x_{k+1}=A(d_k)\,x_k+B(d_k)\,u_k+E(d_k)$, $y_k=C\,x_k$.
  \item Gestapelte Prädiktion über $N$ Schritte, affin in den Stellschritten:
    \begin{equation}
      \label{eq.grundlagen.praediktion}
      \mathbf y=\Phi\,x_0+\Gamma\,\mathbf u+\Psi .
    \end{equation}
  \item Mit Gl.~(\ref{eq.grundlagen.mpc}) ergibt sich eine quadratische Zielfunktion in
    $(\Delta\mathbf u,\mathbf s)$ mit positiv definiter Hesse-Matrix für $\lambda>0$, $\mu>0$;
    Stell-, Raten- und weiche Ausgangsschranken sind linear: konvexes QP.
  \item Bedingung für das QP ist die Affinität im Zustand, nicht nur in der Stellgröße.
    Produkte Zustand$\times$Zustand oder Stellgröße$\times$Zustand machen die Prädiktion nicht
    affin in $\mathbf u$ (B1, sympy-Beispiel). Produkte mit exogenen Größen sind zulässig, wenn
    deren Verlauf über den Horizont vorgegeben oder eingefroren wird (LPV-Form).
  \item Weiche Schranke: Mit rein quadratischer Strafe $\mu s^2$ wird die Schranke auch dann
    leicht verletzt, wenn eine zulässige Lösung existiert; ein zusätzlicher linearer Term
    $\mu_1 s$ mit ausreichend großem $\mu_1$ macht die Strafe exakt (\cite{kerriganSoftConstraintsExact2000}; Voraussetzung laut Suchzusammenfassung:
    Strafgewicht über einer unteren Schranke; Zulässigkeitsfragen
    \cite{scokaertFeasibilityIssuesLinear1999}).
  \item Offsetfreiheit: Störmodell $d^{\mathrm{off}}_{k+1}=d^{\mathrm{off}}_k$ am Ausgang,
    $y_k=Cx_k+d^{\mathrm{off}}_k$; Beobachter schätzt $\hat x$ und $\hat d^{\mathrm{off}}$;
    Zielwertberechnung löst die Ruhelage $(x_s,u_s)$ zum Sollwert.
    Bedingung: Detektierbarkeit des erweiterten Systems, Zahl der Störzustände gleich Zahl der
    Ausgänge \cite{muskeDisturbanceModelingOffsetfree2002,
    pannocchiaDisturbanceModelsOffsetfree2003, maederLinearOffsetfreeModel2009}.
  \item Gemessene Störgrößen ($\TLT$, Last) als Vorsteuerung über ihren Verlauf im Horizont;
    ohne Prognose konstant fortschreiben (Kommentar ch2 Z.~1111).
  \item Anker: \cite{rawlingsModelPredictiveControl20202020}; \cite{maciejowskiPredictiveControlConstraints2002};
    \cite{pannocchiaOffsetfreeTrackingMPC2015} (Vergleich offsetfreier Formulierungen:
    Störmodell mit Beobachter, Zustandsstörbeobachter, Geschwindigkeitsform).
  \item Anschluss: Kapitel~\ref{ch.methodik} kann die Modellklassen daran messen, ob sie die
    Affinitätsbedingung erfüllen; \arx{} und \edmdc{} tun es per Konstruktion, \sindyc{} nur mit
    passender Bibliothek.
\end{itemize}
% COPILOT-STICHPUNKTE END B2-MPC-QP
```

### B2.4 Stationäre Verstärkung eines nichtlinearen Modells

```latex
% COPILOT-STICHPUNKTE BEGIN B2-Verstaerkung
\begin{itemize}
  \item Ruhelage des zeitdiskreten Modells $x_{k+1}=f(x_k,u_k,d_k)$ bei festen Eingängen:
    $x_s=f(x_s,u_s,d_s)$; stationäre Kennlinie $y_s(u,d)$.
  \item Stationäre Verstärkung als lokale Steigung der Kennlinie; über die Linearisierung
    $A=\partial f/\partial x$, $B=\partial f/\partial u$ in der Ruhelage:
    \begin{equation}
      \label{eq.grundlagen.gain.stat}
      K=\frac{\partial y_s}{\partial u}\Big|_{(u_s,d_s)}=C\,(I-A)^{-1}B .
    \end{equation}
  \item Für die Relaxationsform ist $y_s=\Tstat$ und damit
    $K=\partial\Tstat/\partial\valveCA$ (Abschnitt~\ref{ssec.grundlagen.luftpfad.waermeuebertragung});
    die Rate $\lambda$ geht nicht ein. Ein Modell mit richtiger Dynamik und falschem
    $\varepsilon(\valveCA)$ hat eine falsche Verstärkung.
  \item Skalares Map-Modell $y_{k+1}=a\,y_k+b\,u_k+c$: $K=b/(1-a)$. Relative Empfindlichkeit
    gegenüber $a$ ist $a/(1-a)$ (sympy); sie wächst ohne Grenze für $a\to1$. Kleine Fehler im
    Eigenkoeffizienten träger Strecken verfälschen die Verstärkung stark.
  \item Bedeutung für MPC: $K$ bestimmt die Ruhelage-Stellgröße in der Zielwertberechnung und die
    Kreisverstärkung. Betragsfehler verändern das Regelverhalten; ein Vorzeichenfehler
    destabilisiert. Offset gleicht der Störgrößenbeobachter aus, die Dynamik nicht.
  \item Arbeitspunktabhängigkeit: Die S-förmige Streckenkennlinie
    (Abschnitt~\ref{ssec.erg.ol.kennlinie}) macht $K$ vom Hub abhängig; für den linearen QP
    Arbeitspunktwahl oder LPV-Form angeben.
  \item Konvention: Sekante über ein Hubband oder lokale Steigung, Band und Arbeitspunkt
    nennen (Z.~790--793 in ch2).
  \item Anker: \cite{khalilNonlinearSystems2002} (Ruhelage, Linearisierung; Stelle lokal);
    \cite{skogestadMultivariableFeedbackControl2005} (Modellunsicherheit, Kap.~7 laut
    Suchzusammenfassung); \cite{rawlingsModelPredictiveControl20202020} (Zielwertberechnung).
  \item Anschluss: Der Ventil-Gain ist eine der vier Bewertungsgrößen der Arbeit;
    Gl.~\eqref{eq.grundlagen.gain.stat} definiert ihn modellklassenübergreifend.
\end{itemize}
% COPILOT-STICHPUNKTE END B2-Verstaerkung
```

### B2.5 Simulationsfehler und Einschritt-Prädiktionsfehler

```latex
% COPILOT-STICHPUNKTE BEGIN B2-Simulationsfehler
\begin{itemize}
  \item Einschritt-Prädiktion nutzt den gemessenen Ausgang,
    $\hat y_{k+1|k}=f(y_k,u_k,d_k)$; Freilauf (Simulation) den eigenen Schätzwert,
    $\hat y_{k+1}=f(\hat y_k,u_k,d_k)$ mit $\hat y_0=y_0$.
    \begin{equation}
      \label{eq.grundlagen.fehlerarten}
      J_{\mathrm{1S}}=\sum_k\bigl(y_{k+1}-\hat y_{k+1|k}\bigr)^2,\qquad
      J_{\mathrm{sim}}=\sum_k\bigl(y_{k}-\hat y_{k}\bigr)^2 .
    \end{equation}
  \item Kleinste Quadrate nach Gl.~(\ref{eq.lsq}) minimieren $J_{\mathrm{1S}}$
    (Gleichungsfehler). $J_{\mathrm{sim}}$ ist nichtlinear in den Parametern und wird iterativ
    minimiert \cite{piroddiIdentificationAlgorithmPolynomial2003,
    farinaIterativeAlgorithmSimulation2010} (Keys aus Auftrag A).
  \item Konsistenz: Gleichungsfehler passt zu weißem Gleichungsrauschen (ARX-Struktur),
    Simulationsfehler zu Ausgangsrauschen (OE-Struktur)
    \cite{ljungSystemIdentificationTheory1999} (Kapitel lokal nachschlagen).
  \item Träge Strecke, $a\to1$: Schon das Persistenzmodell $\hat y_{k+1|k}=y_k$ hat einen
    kleinen Einschrittfehler. Einschrittgüte daher immer gegen diese Referenz angeben.
  \item Das MPC nutzt $N$-Schritt-Prädiktionen. Maßgeblich ist der Fehler über dem Horizont,
    $e(h)$ für $h=1,\dots,N$; Mehrschritt-Kriterium als Schätzziel senkt den Bias bei
    fehlspezifizierter Modellklasse \cite{somalwarLearningImperfectModels2025}.
  \item Freilauf auf aufgezeichneter Stellgröße aus geregeltem Betrieb ist eine
    Open-Loop-Simulation mit Closed-Loop-Eingang; eine Closed-Loop-Simulation braucht
    zusätzlich den Regler.
  \item Anker: \cite{ljungSystemIdentificationTheory1999}; \cite{nellesNonlinearSystemIdentification2020} (Kap.~19, Gleichungs- gegenüber
    Ausgangsfehler); \cite{ribeiroParallelTrainingConsidered2018} (serie-parallele gegenüber
    paralleler Schätzung).
  \item Anschluss: Die Arbeit bewertet offene und geschlossene Kette; pro Modell angeben, welches
    Kriterium für den Fit, welches für die Auswahl und welches für die Bewertung gilt.
\end{itemize}
% COPILOT-STICHPUNKTE END B2-Simulationsfehler
```

### BibTeX-Entwürfe B2

Nur (T)- und (G)-Felder im Eintrag, (S)-Felder als `% ungeprüft:` darüber. Status aller Einträge:
[nur bibliografisch]. Schon in der Bib: `rawlingsModelPredictiveControl20202020`,
`muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003`,
`maederLinearOffsetfreeModel2009`, `ljungSystemIdentificationTheory1999`,
`kaiserSparseIdentificationNonlinear2018`. Aus Auftrag A (noch nicht in der Bib):
`piroddiIdentificationAlgorithmPolynomial2003`, `farinaIterativeAlgorithmSimulation2010`,
`somalwarLearningImperfectModels2025`.

```bibtex
% ungeprüft: year = {1997}
% Dover-Nachdruck: ISBN 978-0-486-48613-0 (Jahr 2011/2012 unklar)
@book{astromComputerControlledSystemsTheory1997,
  author    = {{\AA}str{\"o}m, Karl J. and Wittenmark, Bj{\"o}rn},
  title     = {Computer-Controlled Systems: Theory and Design},
  edition   = {3},
  publisher = {Prentice Hall},
  isbn      = {978-0-13-314899-2}
}

@book{franklinDigitalControlDynamic1998,
  author    = {Franklin, Gene F. and Powell, J. David and Workman, Michael L.},
  title     = {Digital Control of Dynamic Systems},
  edition   = {3},
  publisher = {Addison-Wesley},
  year      = {1998},
  isbn      = {978-0-201-82054-6}
}

% ungeprüft: address = {London}. Key bei Bindestrich-Nachnamen von Better-BibTeX erzeugen lassen
@book{normeyricoControlDeadtimeProcesses2007,
  author    = {Normey-Rico, Julio E. and Camacho, Eduardo F.},
  title     = {Control of Dead-time Processes},
  series    = {Advanced Textbooks in Control and Signal Processing},
  publisher = {Springer},
  year      = {2007},
  isbn      = {978-1-84628-828-9},
  doi       = {10.1007/978-1-84628-829-6}
}

@book{maciejowskiPredictiveControlConstraints2002,
  author    = {Maciejowski, Jan M.},
  title     = {Predictive Control with Constraints},
  publisher = {Prentice Hall},
  address   = {Harlow, UK},
  year      = {2002},
  isbn      = {0-201-39823-0}
}

% ungeprüft: address = {London}
@book{camachoModelPredictiveControl2007,
  author    = {Camacho, Eduardo F. and Bordons, Carlos},
  title     = {Model Predictive Control},
  edition   = {2},
  series    = {Advanced Textbooks in Control and Signal Processing},
  publisher = {Springer},
  year      = {2007},
  isbn      = {978-1-85233-694-3},
  doi       = {10.1007/978-0-85729-398-5}
}

% ungeprüft: Initialen E. C.; booktitle = {Proc. UKACC International Conference (Control 2000)};
%            address = {Cambridge, UK}; year = {2000}; pages = {2319--2327}; keine DOI gefunden
@inproceedings{kerriganSoftConstraintsExact2000,
  author    = {Kerrigan, E. C. and Maciejowski, J. M.},
  title     = {Soft Constraints and Exact Penalty Functions in Model Predictive Control},
  url       = {https://spiral.imperial.ac.uk/entities/publication/b1d59b69-3901-41f5-bb9f-f619319fa9dc}
}

% ungeprüft: Vorname Rawlings; number = {8}; pages = {1649--1659} (Startseite 1649 aus ADS-Bibcode, T)
@article{scokaertFeasibilityIssuesLinear1999,
  author    = {Scokaert, Pierre O. M. and Rawlings, J. B.},
  title     = {Feasibility issues in linear model predictive control},
  journal   = {AIChE Journal},
  volume    = {45},
  year      = {1999},
  doi       = {10.1002/aic.690450805}
}

% ungeprüft: author = {Pannocchia, G.}; booktitle = {2015 European Control Conference (ECC)};
%            address = {Linz}; year = {2015}; pages = {527--532}; doi = {10.1109/ECC.2015.7330597}
@inproceedings{pannocchiaOffsetfreeTrackingMPC2015,
  title     = {Offset-free tracking {MPC}: A tutorial review and comparison of different formulations},
  url       = {https://ieeexplore.ieee.org/document/7330597/}
}

@book{khalilNonlinearSystems2002,
  author    = {Khalil, Hassan K.},
  title     = {Nonlinear Systems},
  edition   = {3},
  publisher = {Prentice Hall},
  address   = {Upper Saddle River},
  year      = {2002},
  isbn      = {978-0-13-067389-3}
}

% ungeprüft: address = {Chichester}. Hardcover-ISBN 978-0-470-01167-6
@book{skogestadMultivariableFeedbackControl2005,
  author    = {Skogestad, Sigurd and Postlethwaite, Ian},
  title     = {Multivariable Feedback Control: Analysis and Design},
  edition   = {2},
  publisher = {Wiley},
  year      = {2005},
  isbn      = {978-0-470-01168-3}
}

% ungeprüft: address = {Cham}; year = {2020}
@book{nellesNonlinearSystemIdentification2020,
  author    = {Nelles, Oliver},
  title     = {Nonlinear System Identification: From Classical Approaches to Neural Networks, Fuzzy Models, and Gaussian Processes},
  edition   = {2},
  publisher = {Springer},
  isbn      = {978-3-030-47438-6},
  doi       = {10.1007/978-3-030-47439-3}
}

% ungeprüft: journal = {Neurocomputing}; volume = {316}; pages = {222--231}; year = {2018};
%            doi = {10.1016/j.neucom.2018.07.071}
@article{ribeiroParallelTrainingConsidered2018,
  author        = {Ribeiro, Ant{\^o}nio H. and Aguirre, Luis A.},
  title         = {``Parallel Training Considered Harmful?'': Comparing series-parallel and parallel feedforward network training},
  url           = {https://www.sciencedirect.com/science/article/abs/pii/S0925231218309068},
  eprint        = {1706.07119},
  archivePrefix = {arXiv}
}
```


---

## Offen / nicht belegt

- Keine Lehrbuchstelle am Original geprüft; das gilt für alle in ch2 zitierten Seiten und
  Gleichungsnummern des Abschnitts Wärmeübertragung und für alle Kapitelangaben in B2.
- B2-Anker nur bibliografisch; Kapitelnamen bei Åström & Wittenmark, Franklin u. a., Skogestad &
  Postlethwaite nur aus Suchzusammenfassung. Lokal nachschlagen: Euler/Näherung (Åström),
  Padé und verschobener Eingang (Normey-Rico), $\Delta u$-Schranken und weiche Schranken
  (Maciejowski, Camacho Kap. 7), Linearisierung (Khalil), Verstärkungsunsicherheit (Skogestad),
  Kapitel zu Prädiktions- und Simulationsfehler (Ljung).
- Kaiser u. a. 2018: Befund „kontinuierliches Modell, nichtlineares MPC mit SQP“ stammt aus dem
  Autoren-Code (GitHub eurika-kaiser/SINDY-MPC), nicht aus dem Papertext.
- Kein belastbarer Primäranker für „Gain-Fehler identifizierter Modelle verschlechtert MPC“.
  Kandidaten nur mit (S)-Metadaten: Yousefi u. a. 2015 (Control Eng. Pract. 43, 59–68,
  Model-Plant-Mismatch an Papiermaschinen), Wang, Hägglund, Song 2012 (Ind. Eng. Chem. Res.,
  DOI 10.1021/ie300834y aus URL). Ein Lehrbuchanker zur integralen Regelbarkeit bei
  Gain-Fehlern (z. B. Morari & Zafiriou) wurde nicht gesucht.
- Ventilschaltung (Verteilen/Mischen) und Messort von $\THT$, $\TLT$: nur aus der Anlage
  klärbar, nicht aus der Literatur.
- Faustregel zur Abtastzeit: Stelle bei Åström & Wittenmark nicht gesehen.
- Gleichungslabels in B2 (`eq.grundlagen.zoh` usw.) sind Vorschläge; auf Kollision mit
  bestehenden Labels in Kap. 5 prüfen.


---

## Anhang: sympy-Skript (B1)

```python
# Nachrechnung der Umformungen aus kontext/ch2.tex (Abschnitt Wärmeübertragung im Ladeluftkühler)
# Jede Prüfung druckt "OK" oder den Rest, der nicht verschwindet.
import sympy as sp

Tin, Tout, TLT, THT, Tzw = sp.symbols('T_in T_out T_LT T_HT T_zw', real=True)
eHT, eLT, eps = sp.symbols('epsilon_HT epsilon_LT epsilon', real=True)
m, cp, UA, C, kA = sp.symbols('mdot c_p UA C kA', positive=True)
NTU, Cr = sp.symbols('NTU C_r', positive=True)

def check(name, expr):
    r = sp.simplify(expr)
    print(f"{name:55s}", "OK" if r == 0 else f"REST: {r}")

# 1) Stufengleichungen (eq.grundlagen.basic.stufen) und LT-Spanne (eq.grundlagen.basic.ltspanne)
Tzw_def = Tin - eHT*(Tin - THT)
Tstat = Tzw_def - eLT*(Tzw_def - TLT)
check("LT-Spanne Gl. ltspanne", (Tzw_def - TLT) - ((THT - TLT) + (1 - eHT)*(Tin - THT)))

# 2) Zielwert als konvexe Kombination von Tin, THT, TLT
w_in, w_ht, w_lt = (1-eHT)*(1-eLT), eHT*(1-eLT), eLT
check("Tstat = w_in*Tin + w_ht*THT + w_lt*TLT", Tstat - (w_in*Tin + w_ht*THT + w_lt*TLT))
check("Summe der Gewichte = 1", w_in + w_ht + w_lt - 1)

# 3) Serienidentität aus dem Kommentar (EB21): Tstat = Tin - PH*dH - P3*d3, d3 = (THT-TLT) + c*dH
PH, P3, c = sp.symbols('P_H P_3 c', real=True)
dH = Tin - THT
eb21 = Tin - PH*dH - P3*((THT - TLT) + c*dH)
exact = eb21.subs({PH: eHT, P3: eLT, c: 1 - eHT})
check("EB21-Form exakt mit PH=eHT, P3=eLT, c=1-eHT", Tstat - exact)

# 4) Effektivität / Temperaturänderungsgrad: eps = (Cmin/C_L)*eps_Q
Q, Cmin, CL = sp.symbols('Qdot C_min C_L', positive=True)
eps_air = (Q/CL)/(Tin - TLT)          # Q = C_L (Tin - Tout)
eps_Q = Q/(Cmin*(Tin - TLT))
check("eps = (Cmin/C_L)*eps_Q", eps_air - (Cmin/CL)*eps_Q)

# 5) Gegenstrom-Formel, Grenzfall Cr -> 0 und Cr -> 1
eps_cf = (1 - sp.exp(-NTU*(1 - Cr)))/(1 - Cr*sp.exp(-NTU*(1 - Cr)))
check("Gegenstrom, Cr->0 ergibt 1-exp(-NTU)", sp.limit(eps_cf, Cr, 0) - (1 - sp.exp(-NTU)))
check("Gegenstrom, Cr->1 ergibt NTU/(1+NTU)", sp.limit(eps_cf, Cr, 1) - NTU/(1 + NTU))

# 6) Räumliche Bilanz C_L dT/da = -k (T - T_W), T_W konstant -> Exponentialform
a, k, TW, T0 = sp.symbols('a k T_W T_0', positive=True)
T = sp.Function('T')
sol = sp.dsolve(sp.Eq(CL*T(a).diff(a), -k*(T(a) - TW)), T(a), ics={T(0): T0}).rhs
Aw = sp.symbols('A', positive=True)
check("Austritt T(A) = T_W + (T_0-T_W) exp(-kA/C_L)", sol.subs(a, Aw) - (TW + (T0 - TW)*sp.exp(-k*Aw/CL)))

# 7) Zwei Stufen in Exponentialform = Stufengleichungen mit eps = 1-exp(-NTU)
NH, NL = sp.symbols('NTU_HT NTU_LT', positive=True)
Tzw_exp = THT + (Tin - THT)*sp.exp(-NH)
check("T_zw Exponentialform = Stufenform", Tzw_exp - Tzw_def.subs(eHT, 1 - sp.exp(-NH)))

# 8) Stellverstärkung (eq.grundlagen.gain.epsntu), Kettenregel
u = sp.symbols('u')
E, Ti, Tl = sp.Function('eps')(u), sp.Function('T_in')(u), sp.Function('T_LT')(u)
Tout_u = Ti - E*(Ti - Tl)
rhs = -(Ti - Tl)*E.diff(u) + (1 - E)*Ti.diff(u) + E*Tl.diff(u)
check("dTout/du nach Gl. gain.epsntu", Tout_u.diff(u) - rhs)

# 9) Einzustandsbilanz (eq.energiebilanz.dyn): Stationär eps = N/(1+N), Zeitkonstante
rhs_dyn = (m*cp*(Tin - Tout) - UA*(Tout - TLT))/C
Tout_ss = sp.solve(sp.Eq(rhs_dyn, 0), Tout)[0]
N = UA/(m*cp)
check("stationär eps = N/(1+N)", (Tin - Tout_ss)/(Tin - TLT) - N/(1 + N))
check("tau = C/(mdot cp + UA)", -1/sp.diff(rhs_dyn, Tout) - C/(m*cp + UA))
# Mitteltemperatur als Treiber: kA/2 im Nenner
rhs_mean = (m*cp*(Tin - Tout) - kA*((Tin + Tout)/2 - TLT))/C
check("tau (Mitteltemperatur) = C/(mdot cp + kA/2)", -1/sp.diff(rhs_mean, Tout) - C/(m*cp + kA/2))

# 10) Lokale Form dTout/dt = a*d - b*(Tin - TLT), d = Tin - Tout
d = Tin - Tout
aa, bb = (m*cp + UA)/C, UA/C
check("dTout/dt = a d - b (Tin - TLT)", rhs_dyn - (aa*d - bb*(Tin - TLT)))

# 11) Relaxationsrate der Einzustandsbilanz: lambda = (mdot cp + UA)/C, Zielwert Tss
lam = (m*cp + UA)/C
check("rhs_dyn = lambda*(Tout_ss - Tout)", rhs_dyn - lam*(Tout_ss - Tout))

# 12) Druckverlust-Proxy (eq.luftproxy.druckverlust / dichte / relativ)
zeta, rho, Astr, v, dp, p, R, TK = sp.symbols('zeta rho A_Str v Delta_p p R T_K', positive=True)
v_of_m = m/(rho*Astr)
dp_expr = zeta/2*rho*v_of_m**2
m_sol = sp.solve(sp.Eq(dp, dp_expr), m)
m_pos = [s for s in m_sol if s.is_positive is not False][0]
check("mdot = A_Str sqrt(2 dp rho / zeta)", m_pos - Astr*sp.sqrt(2*dp*rho/zeta))
m_ideal = m_pos.subs(rho, p/(R*TK))
check("mdot ∝ sqrt(dp p / T)", sp.simplify(m_ideal/sp.sqrt(dp*p/TK)).has(dp, p, TK) * 1)
dpr, pr, Tr = sp.symbols('Delta_p_ref p_ref T_ref', positive=True)
mrel = sp.sqrt(dp/dpr * p/pr * Tr/TK)
qrel = sp.sqrt(dp/dpr * p/pr)
check("q_rel = m_rel*sqrt(T/T_ref)", qrel - mrel*sp.sqrt(TK/Tr))
check("m_rel = mdot/mdot_ref (gleiche Annahmen)", sp.simplify(m_ideal/m_ideal.subs({dp: dpr, p: pr, TK: Tr})) - mrel)

# 13) NTU-Exponent: kA ∝ mdot^p, Cmin = mdot cp -> NTU ∝ mdot^(p-1)
pexp, c0 = sp.symbols('p_e c_0', positive=True)
NTU_m = c0*m**pexp/(m*cp)
check("d ln NTU / d ln mdot = p-1", sp.simplify(sp.diff(sp.log(NTU_m), m)*m) - (pexp - 1))

# 14) Mehrschrittprädiktion: Modell linear in u, nichtlinear in x -> Prädiktion nicht affin in u
x0, u0, u1, th = sp.symbols('x_0 u_0 u_1 theta', real=True)
f = lambda x: x - th*x**2           # Beispiel: Zustandsterm quadratisch
x1 = f(x0) + u0
x2 = f(x1) + u1
print("x2 nach u0 zweimal abgeleitet (≠0 -> nicht affin):", sp.simplify(sp.diff(x2, u0, 2)))
# Bilinearer Term u*x (Rate hängt vom Ventil ab)
g = lambda x, uu: x + th*uu*(TLT - x)
x2b = g(g(x0, u0), u1)
print("bilinear: d2 x2/(du0 du1) =", sp.simplify(sp.diff(x2b, u0, u1)))
# LPV mit exogenem Scheduling s_k (mrel), linear in x und u -> affin
s0, s1, b = sp.symbols('s_0 s_1 b', real=True)
h = lambda x, uu, s: (1 - th*s)*x + b*uu
x2c = h(h(x0, u0, s0), u1, s1)
print("LPV exogen: d2 x2/du0^2 =", sp.diff(x2c, u0, 2), ", d2/(du0 du1) =", sp.diff(x2c, u0, u1))

# 15) Exakte ZOH-Diskretisierung von dT/dt = lambda (Tss - T) bei konstanten Eingängen
t, dt, lam_s, Tss = sp.symbols('t Delta_t lambda T_ss', positive=True)
Tf = sp.Function('T')
solz = sp.dsolve(sp.Eq(Tf(t).diff(t), lam_s*(Tss - Tf(t))), Tf(t), ics={Tf(0): T0}).rhs
check("ZOH: T(dt) = exp(-l dt) T0 + (1-exp(-l dt)) Tss", solz.subs(t, dt) - (sp.exp(-lam_s*dt)*T0 + (1 - sp.exp(-lam_s*dt))*Tss))
# Euler-Näherung: 1 - lambda*dt; Fehler zweiter Ordnung
print("Reihe exp(-l dt):", sp.series(sp.exp(-lam_s*dt), dt, 0, 3))

# 16) Stationäre Verstärkung eines diskreten Einzustandsmodells y+ = a*y + b*u + c
aK, bK = sp.symbols('a b', real=True)
K = bK/(1 - aK)
print("K = b/(1-a); relative Empfindlichkeit (dK/K)/(da/a) =", sp.simplify(sp.diff(K, aK)*aK/K))

# 17) Einschrittfehler eines trägen Modells: Persistenzmodell y+ = y hat Einschrittfehler y+ - y
#     (keine Rechnung nötig; nur Hinweis, dass bei a -> 1 der Einschrittfehler klein bleibt)
```

Ausgabe: alle Prüfungen „OK“; Mehrschritt-Beispiel: $\partial^2x_2/\partial u_0^2=-2\theta$ (nicht affin), bilinear $\theta^2(x_0-T_{LT})$, LPV exogen 0; $K=b/(1-a)$ mit relativer Empfindlichkeit $a/(1-a)$.

