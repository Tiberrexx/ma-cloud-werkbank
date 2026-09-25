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
| `eq.k.zusammensetzung` (Z. 752–757) | Reihenschaltung der drei Widerstände korrekt. Nicht genannt: Verschmutzungswiderstände vernachlässigt, $\eta_f$ (Oberflächenwirkungsgrad, Z. 601) und $R_{\mathrm{Wand}}$ als konstant angesetzt | Annahmen nennen; Folgerung Z. 734–735 algebraisch gedeckt: für $\alpha_W A_W\to\infty$ strebt $kA$ gegen $1/(1/(\eta_f\alpha_L A_L)+R_{\mathrm{Wand}})$ |
| `eq.grundlagen.basic.stufen` (Z. 366–374) und `eq.grundlagen.basic.ltspanne` (Z. 387–391) | Umformung korrekt | Zusätzlich die geschlossene Form angeben (unten G1): $\Tstat$ ist eine konvexe Kombination von $\Tin$, $\THT$, $\TLT$ mit Gewichten $(1-\varepsilon_{HT})(1-\varepsilon_{LT})$, $\varepsilon_{HT}(1-\varepsilon_{LT})$, $\varepsilon_{LT}$; Summe 1 |
| Kommentar EB21 (Z. 315–320): `Tstat = T_col_in - PH*dH - P3*d3`, `d3 = (T_HTCW-T_LTCW)+cFix*dH` | Koeffizientenvergleich (sympy, solve nach $P_H$, $P_3$): exakt für $P_3=\varepsilon_{LT}$ und $P_H=\varepsilon_{HT}+\varepsilon_{LT}(1-\varepsilon_{HT}-c)$ bei beliebigem $c$ (= `cFix`). Bei konstanten Koeffizienten ist die EB21-Form damit für jedes feste `cFix` exakt; $P_H=\varepsilon_{HT}$ folgt nur mit $c=1-\varepsilon_{HT}$. $P_H$ und $c$ sind nicht getrennt bestimmbar (passt zu Z. 319–320: unabhängige Fitkoeffizienten) | $P_H$ nicht als $\varepsilon_{HT}$ und `cFix` nicht als $1-\varepsilon_{HT}$ deuten. Mit festem `cFix` bleibt die Form exakt, $P_H$ trägt dann aber den ventilabhängigen Anteil $\varepsilon_{LT}(1-\varepsilon_{HT}-c_{\mathrm{Fix}})$. Näherung erst, wenn $\varepsilon_{LT}$ (bzw. $P_3$) mit $\mrel$ oder $\valveCA$ variiert und $P_H$, `cFix` konstant bleiben; exakt dann nur bei konstantem $\varepsilon_{HT}$ und $c_{\mathrm{Fix}}=1-\varepsilon_{HT}$ |
| `eq.grundlagen.basic.produkte` (Z. 404–413) | Ausmultiplizieren korrekt | Für den QP festhalten: $a_2 g(\valveCA)\Delta T$ ist linear in $\valveCA$ nur, wenn $g$ affin ist oder im QP um den aktuellen Hub linearisiert wird ($g(u)\approx g(u_0)+g'(u_0)(u-u_0)$), und nur, solange $\Delta T$ aus exogenen Größen besteht ($\Tin$, $\THT$, $\TLT$), nicht aus $\Tout$. Wird $v=g(\valveCA)$ mit monotonem $g$ als Stellgröße genommen, bleiben die Box-Schranken linear, Ratenschranke und $\Delta u$-Gewicht in $\valveCA$ sind in $v$ aber nicht mehr linear |
| `eq.grundlagen.basic.dynamik` (Z. 436–440) | Form korrekt. $\lambda(\mrel,\valveCA)$ mit Ventilabhängigkeit ergibt ein Produkt $\valveCA\cdot\Tout$: bilinear, **nicht QP-tauglich** ohne Einfrieren | Satz ergänzen (Z. 447–448 nennt es nur Modellvereinfachung): Ventil nur im Zielwert (mit affinem bzw. linearisiertem $g$) ist eine hinreichende Form für den linearen QP, keine notwendige; ein Ventilterm in der Rate ist nach Einfrieren oder Linearisieren ebenfalls QP-fähig, dann nur genähert |
| Z. 446: $\lambda=c_\lambda\mrel$ | Aus `eq.energiebilanz.dyn` folgt $\lambda=(\dot m_L c_{p,L}+U_{\mathrm{eff}}A)/C_{\mathrm{eff}}$ (sympy). Nach Z. 921 hängt auch $U_{\mathrm{eff}}A/C_{\mathrm{eff}}$ von $\dot m_L$ ab; ist der Leitwert luftseitig begrenzt (analog Z. 611–612), geht $\lambda$ für $\dot m_L\to0$ gegen null | Proportionale und affine Rate sind beide lokale Näherungen im Betriebsband; die affine $\lambda=c_0+c_1\mrel$ hat einen freien Achsenabschnitt (bei $U_{\mathrm{eff}}A=\kappa\dot m_L^p$: $\kappa(1-p)\dot m_0^p/C_{\mathrm{eff}}$), die proportionale setzt ihn null (Zusatzannahme) |
| `eq.energiebilanz` (Z. 524–529) | Vorzeichen korrekt (Wasser erwärmt sich) | Einstufige Ersatzbeschreibung ist schon im Copilot-Punkt Z. 497–503 benannt |
| Kennzahlen Z. 533–538 | $\varepsilon=(C_{\min}/C_L)\,\varepsilon_Q$ korrekt (sympy) | – |
| Gegenstrom-Formel Z. 539–541 | Korrekt. Grenzfall $C_r\to0$ ergibt $1-e^{-\mathrm{NTU}}$ (sympy). Bei $C_r=1$ ist der Ausdruck 0/0, Grenzwert $\mathrm{NTU}/(1+\mathrm{NTU})$ | Gültigkeit „$C_r<1$“ an die Formel schreiben |
| `eq.Tout.stat` und unnummerierte Zweistufenform (Z. 568–577) | Korrekt; Exponentialform = Stufenform mit $\varepsilon=1-e^{-\mathrm{NTU}}$ (sympy) | Unnummerierte Gleichung nummerieren; Z. 994–995 greift sie als „serielle ε-NTU-Beziehung“ auf |
| Räumliche Bilanz Z. 584–585 | $C_L\,\mathrm dT/\mathrm da=-k(T-T_W)$ ergibt $T(A)=T_W+(T_0-T_W)e^{-kA/C_L}$ (sympy); $k$ ist hier flächenbezogen | Einheit von $k$ (W/(m²K)) nennen, sonst Verwechslung mit $kA$ |
| Z. 555–556: „Zielwert liegt zwischen $\Tin$, $\THT$ und $\TLT$“ | Stimmt, präziser als konvexe Kombination (s. oben), gilt für $0\le\varepsilon\le1$ | Gewichte angeben; sie zeigen, dass $\THT$ nur über $\varepsilon_{HT}(1-\varepsilon_{LT})$ eingeht |
| `eq.grundlagen.gain.epsntu` (Z. 796–802) | Kettenregel korrekt (sympy). Mit totalen Ableitungen exakt; $\mathrm d\varepsilon/\mathrm d\valveCA$ enthält dann $\partial\varepsilon/\partial\dot m_L\cdot\mathrm d\dot m_L/\mathrm d\valveCA$ | Festlegen, welche Ableitung gemeint ist. Wird $\mathrm d\varepsilon/\mathrm d\valveCA$ als Kennlinienableitung $\partial\varepsilon/\partial\valveCA$ gelesen (wie Z. 787), den Term $-(\Tin-\TLT)\,\partial\varepsilon/\partial\dot m_L\cdot\mathrm d\dot m_L/\mathrm d\valveCA$ ergänzen oder $\dot m_L$ ausdrücklich festhalten |
| Z. 781–783: „Vorzeichen negativ … bei mit dem Hub wachsendem $\varepsilon$“ | Zusätzlich nötig: Kühlerspanne $\Tin-\TLT>0$ | Bedingung ergänzen (für die LT-Stufe genauer $T_{zw}-\TLT>0$, vgl. Z. 807–811) |
| Gain-Gleichung vs. Zweistufenform | `eq.grundlagen.gain.epsntu` nutzt die einstufige Spanne $\Tin-\TLT$; die Zweistufenform (Z. 807–811) die LT-Spanne $T_{zw}-\TLT$ | Kennzeichnen, dass die erste Gleichung die einstufige Ersatzform ist; für die Arbeit gilt die zweite |
| Stationärer Grenzwert Z. 848–850 | $\varepsilon=N/(1+N)$, $N=U_{\mathrm{eff}}A/(\dot m_L c_{p,L})$ korrekt (sympy) | – |
| Zeitkonstante Z. 835–840 | $\tau=C_{\mathrm{eff}}/(\dot m_L c_{p,L}+U_{\mathrm{eff}}A)$ korrekt; mit Mitteltemperatur $\tau=C/(\dot m_L c_p+kA/2)$ korrekt (sympy) | – |
| Lokale Form Z. 911–920 | $a=(\dot m_L c_{p,L}+U_{\mathrm{eff}}A)/C_{\mathrm{eff}}$, $b=U_{\mathrm{eff}}A/C_{\mathrm{eff}}$ korrekt (sympy) | – |
| Massenstromexponent Z. 611–613 | $\mathrm{d}\ln\mathrm{NTU}/\mathrm{d}\ln\dot m_L=p-1$ korrekt, wenn $C_{\min}=C_L$ | Bedingung $C_{\min}=C_L$ an dieser Stelle wiederholen (steht Z. 543–546 und Z. 764–765, fehlt bei Z. 611–613) |
| `eq.luftproxy.druckverlust`, `.dichte`, `.relativ` (Z. 653–691) | Umstellung korrekt: $\dot m_L=A_{\mathrm{Str}}\sqrt{2\,\dpHP\,\rho_L/\zeta_L}$; mit $\rho=p/(RT)$ folgt $\dot m_L\propto\sqrt{\dpHP\,p/T}$; $\mrel=\dot m_L/\dot m_{L,\mathrm{ref}}$ unter denselben Annahmen (sympy) | – |
| $q_{\mathrm{rel}}$ (Z. 706–712) | $q_{\mathrm{rel}}=\mrel\sqrt{T/T_{\mathrm{ref}}}$ korrekt (sympy) | – |
| MPC-Satz Z. 1080–1082: „Ist das Modell linear in der Stellgröße, ist (mpc) ein konvexes QP“ | **Unvollständig.** Die Prädiktion ist affin in $u$, wenn das Modell gemeinsam affin in $u$ und in den von $u$ beeinflussten Zuständen ist; die Koeffizienten dürfen von exogenen Größen und von Zuständen abhängen, die $u$ nicht erreicht (z. B. $\Tin$ als eigener Zustand, Z. 490–491, solange das Modell keinen Ventilpfad auf $\Tin$ enthält; nach Z. 777–780 bewegt sich $\Tin$ mit dem Hub mit, Nachweis in `sec.erg.ol`). Gegenbeispiel (sympy): $x^+=x-\theta x^2+u$ ergibt $\partial^2x_2/\partial u_0^2=-2\theta\neq0$. Bilinear $u\cdot x$: gemischte Ableitung $\neq0$. LPV mit exogenem Scheduling ($\mrel$ als Messgröße): beide Ableitungen null | Formulieren: Modell gemeinsam affin in Stellgröße und den von ihr beeinflussten Zuständen bei gegebenem Verlauf der exogenen Größen (LPV mit gemessener Scheduling-Größe); dann quadratische Kosten plus lineare Beschränkungen = konvexes QP |

### Annahmen, die fehlen oder nur verstreut stehen

- **Ventilschaltung (Z. 249–265):**
  - Z. 249–250 nennt ein Dreiwegeventil, das den Wasserdurchsatz durch die LT-Stufe einstellt;
    Z. 253 nennt Mischventile. Die Ventilbauart legt die hydraulische Schaltung nicht fest; ein
    Widerspruch zwischen Z. 250 und Z. 253 ist damit nicht belegt.
  - Umlenk- bzw. Verteilschaltung mit Bypass (auch mit Mischventil im Rücklauf möglich): Das
    Ventil stellt den Durchsatz durch die LT-Stufe, die Wassereintrittstemperatur der Stufe ist
    $\TLT$. Beimisch- oder Einspritzschaltung (eigene Pumpe im Stufenkreis): Eintritt mit
    Mischtemperatur, $\varepsilon_{LT}$ dann nicht auf $\TLT$ bezogen. Diese Einordnung ist
    ohne Literaturbeleg (s. Offen).
  - Z. 263–265 (Rohrstrecke zwischen Mischventil und Kühlereintritt totzeitkritisch) legt das
    Ventil vor den Kühlereintritt; das kann auf eine veränderliche Wassereintrittstemperatur
    hindeuten, belegt die Schaltung aber nicht.
  - Schaltung und Einbauort an der Anlage bzw. aus der Anlagendokumentation klären und als
    Annahme führen.
- **Messort von $\THT$, $\TLT$:** Eintritt der jeweiligen Stufe oder Kreisvorlauf? Die
  Stufengleichungen setzen die Wassereintrittstemperatur der Stufe voraus
  (vgl. Z. 557–558: Sensorlage nicht verifiziert). Z. 261–262: Temperatursensor stromab des
  Ventils, Messgröße dort nicht angegeben; für den Messort von $\TLT$ daraus nichts ableiten.
- **Quasistationäres $\varepsilon$:** Die Stufengleichungen nehmen $\varepsilon$ als momentane
  Funktion von Durchsätzen; Wand- und Wasserdynamik stecken dann allein in $\lambda$. Einmal
  ausdrücklich nennen (steht implizit in Z. 848–859).
- **$\varepsilon$-NTU-Voraussetzungen** (verstreut): stationär, adiabat, konstante Stoffwerte
  Z. 507–509 (zu Gl. `eq.energiebilanz`), Stromführung Z. 512–516, konstantes $T_W$ und
  $C_W\gg C_L$ Z. 584–588. Es fehlen konstantes $k$ über der Fläche und vernachlässigte
  Längswärmeleitung. Gebündelt an der Gegenstrom-Formel nennen.
- **Kapazitätsstrom bei kleinem Hub:** Z. 543–546 setzt $C_{\min}=C_L$ „über den ganzen
  Ventilhub“; Z. 738–741 nennt als Hypothese den Wechsel von $C_{\min}$ auf die Wasserseite bei
  kleinen Hüben. Dann gilt $\varepsilon=1-e^{-\mathrm{NTU}}$ für die Luftseite nicht mehr.
  Beide Stellen gegenseitig verweisen und den Gültigkeitsbereich der Grenzfallformel eingrenzen.
- **Einzustandsbilanz:** eine konzentrierte Kapazität; $\Tout$ als Zustand steht für eine
  Mitteltemperatur; Sensor- und Transportdynamik getrennt (Z. 866–874 nennt sie).
- **Proxy:** Annahmen sind vollständig genannt (Z. 643–650, 717–726); nichts zu ergänzen.

### Zitierte Lehrbuchstellen

- Alle Stellen in diesem Abschnitt (ch2 Z. 304–1032) **nicht prüfbar** in dieser Sitzung
  (kein Volltextzugang). Lokal zu prüfen: Almbauer 2019 (S. 821–840, Gl. 31.x), Pucher 2012
  (S. 256–257, Gl. 12.3–12.8; Abschn. 12.4, S. 265–268), Isermann 2014 (S. 147, Gl. 4.1.48;
  Gl. 4.6.x, 4.7.x), Eriksson & Nielsen 2014 (Gl. 7.x, Tab. 7.6),
  `erikssonMODELINGTURBOCHARGEDSI` S. 132, Guzzella & Onder 2010, Sui u. a. 2022 Anhang B,
  Yin & Jensen 2003, Vagapov u. a. 2022, Rupprecht 2016, Mrosek 2009, Theotokatos 2010,
  Baldi 2015, Baar 2019 (S. 769–780), Pettersson 2000 (S. 11, Gl. 2.16), Arici 1999
  (Gl. 2, 27, 34), Merker 2019 (Gl. 20.26).
- Inhaltliche Plausibilität (nicht Stelle): Die Gleichungsformen passen zu den genannten
  Gleichungstypen (Bilanz, Serienwiderstand, $\varepsilon$-NTU, Behälterbilanz). Das ist keine
  Prüfung der Seitenzahl.
- Formale Auffälligkeiten:
  - Z. 739 und Z. 863 nennen „Vagapov 2024“ im Klartext, obwohl der Key
    `vagapovModellierungIdentifikationUnd2024` existiert (ch3 Z. 1081). Durch `\cite` ersetzen.
  - Weitere Klartextverweise ohne `\cite`: Tschöke/Pucher 2018, S. 68, Gl. 41 (Z. 536),
    Holmgren 2005, Gl. 3.26 (Z. 563–565), Llamas 2019, S. 18 (Z. 620), Heywood, S. 54,
    Gl. 2.27a (Z. 622), Tschöke/Pantow 2018, S. 696, Gl. 8 und 9 (Z. 740–741), Stanivuk 2021,
    S. 117, Gl. 9 (Z. 835–836), Arava 2026 (Z. 954), Taler 2017, Gl. 20 (Z. 969–970),
    Wahlström 2009, S. 7 (Z. 977). Keys laut ch2 Z. 1014–1017 in BIB_NACHTRAG_0709.bib
    (Holmgren, Stanivuk, Tschöke/Pucher mit Pantow, Arava, Taler), bei Heywood, Llamas und
    Wahlström „Key pruefen“; nach Übernahme durch `\cite` ersetzen.
  - Z. 650: Quadratischer Druckverlust nur mit MathWorks-Doku belegt; Kandidaten aus Auftrag A
    (Eriksson & Nielsen 2014 Kap. 7, Shah & Sekulić 2003 Kap. 6, VDI Heat Atlas L1) ergänzen.
  - Z. 209, 217 (`everllencese4960DFProject2025`) und Z. 251
    (`everllenceseTemperaturregelventilMitAnbau2025`) ohne Seitenangabe; übrige Werkszitate mit Seiten.

### Stufenreihenfolge (HT zuerst, dann LT)

- Richtung konsistent in: Z. 178–181 (Anlagenbeschreibung), Z. 362–372
  (Grundherleitung), Z. 551–553 (Stichpunkte), Z. 574–577 (Exponentialform), Z. 807–811
  (partielle Stellwirkung), Z. 892 (Einzustandsgrenze), Z. 905–907 (Ersatzschaltbild:
  „HT-Bündel als vorgeschalteter Block“).
- Status uneinheitlich: Z. 178–181 stellt HT vor LT ohne Beleg als Tatsache dar, Z. 395–396 als
  Systemvereinfachung, Z. 557–558 als nicht verifizierte Geometrie. In der Anlagenbeschreibung
  als Annahme kennzeichnen oder mit Quelle belegen.
- Einstufige Ersatzformen ohne HT-Stufe: `eq.energiebilanz` (Z. 524–529),
  `eq.energiebilanz.dyn` (Z. 877–884), `eq.grundlagen.gain.epsntu` (Z. 796–802) sowie
  `eq.Tout.stat` (Z. 568–572), die Z. 547 und Z. 857 als Zielwert verwenden, während Z. 371
  und Z. 456 den zweistufigen Zielwert festlegen. Z. 857 auf
  Gl. (`eq.grundlagen.basic.stufen`) umstellen oder `eq.Tout.stat` dort ausdrücklich als
  einstufige Ersatzform bzw. als Baustein je Stufe (Z. 551) kennzeichnen. Die
  Copilot-Punkte Z. 497–503 und 888–896 kennzeichnen die Einstufigkeit für die Bilanzen. Die
  Gain-Gleichung ist noch nicht gekennzeichnet (s. Tabelle).
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
nicht in der Bib stehen, sind mit `% neu:` markiert. Einträge unter „BibTeX-Entwürfe B2“; Piroddi,
Farina und Somalwar stammen aus Auftrag A, `pannocchiaOffsetfreeTrackingMPC2015` steht in den
BibTeX-Entwürfen von Auftrag D.
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
  \item Map-Form von \sindyc{} und \edmdc{} schätzt den diskreten Koeffizienten $a$ (bei
    konstantem $\lambda$ und ZOH $a=e^{-\lambda\Delta t}$). Exakte Rückrechnung
    $\lambda=-\ln a/\Delta t$; die Euler-Lesart $\lambda\approx(1-a)/\Delta t$ (bzw. der
    Koeffizient in $\mathbf x_{k+1}=\mathbf x_k+\Delta t\,\boldsymbol\Theta\boldsymbol\Xi$)
    unterschätzt $\lambda$ um den Faktor $\approx1-\lambda\Delta t/2$. Bei geändertem Takt neu
    schätzen oder über $\ln a$ umrechnen.
  \item Hängt $\lambda$ von $\mrel$ ab, ist \eqref{eq.grundlagen.zoh} nichtlinear in $\mrel$,
    die Euler-Form \eqref{eq.grundlagen.euler} affin. Ein Bibliotheksterm $\mrel\,\Tout$ entspricht
    damit der Euler-Näherung; Abweichung klein, solange $\lambda\Delta t\ll1$.
  \item Die kontinuierliche Standardform braucht eine numerische Ableitung
    (ch.~\ref{ch.standderTechnik}, Abschnitt~\ref{ssec.sot.sindy.discrete}); die Map-Form nicht.
  \item Takt im Verhältnis zur Prozessdynamik und zum Reglertakt ($500\,$ms,
    Abschnitt~\ref{ChATCo}) wählen; Faustregel zur Abtastzeit aus
    \cite{astromComputerControlledSystemsTheory1997} mit Stelle belegen.
  % neu: astromComputerControlledSystemsTheory1997, franklinDigitalControlDynamic1998
  \item Anker: \cite{astromComputerControlledSystemsTheory1997} (Abtastung mit Halteglied,
    Kap.~2, Abschnittsname nur aus Suchzusammenfassung),
    \cite{franklinDigitalControlDynamic1998} (Euler gegenüber Halteglied-Äquivalent).
    % franklinDigitalControlDynamic1998: Stelle offen
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
  % neu: astromComputerControlledSystemsTheory1997, normeyricoControlDeadtimeProcesses2007,
  %      maciejowskiPredictiveControlConstraints2002, camachoModelPredictiveControl2007
  \item Anker: \cite{normeyricoControlDeadtimeProcesses2007} (Kap.~2 Totzeitprozesse,
    Kap.~9 MPC für Totzeitprozesse); \cite{maciejowskiPredictiveControlConstraints2002},
    \cite{camachoModelPredictiveControl2007} (Kap.~7 beschränktes MPC; Stellen für
    $\Delta u$-Schranken lokal nachschlagen).
    % maciejowskiPredictiveControlConstraints2002: Stelle offen
  \item Anschluss: In ein lineares QP passen alle drei Totzeitdarstellungen: verschobener
    Eingang mit Zustandserweiterung (bei ganzzahligem $n_d$ exakt), PT$_n$-Kette und Padé (nach
    Diskretisierung linear, mehr Zustände, nur genähert; Padé mit Nullstelle rechts, im
    zeitdiskreten MPC entbehrlich). Die Ratenschranke \eqref{eq.grundlagen.rate} ist linear.
    Nicht exakt darstellbar ist nur die Totzeit bei Richtungswechsel (Umkehrspanne).
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
  \item Bedingung für das QP ist die gemeinsame Affinität in Stellgröße und den von ihr
    beeinflussten Zuständen. Produkte zweier von $\mathbf u$ beeinflusster Größen
    (Zustand$\times$Zustand, Stellgröße$\times$Zustand) machen die Prädiktion nicht affin in
    $\mathbf u$ (B1, sympy-Beispiel); Produkte mit exogenen oder von $\mathbf u$ unbeeinflussten
    Größen sind zulässig, wenn deren Verlauf über den Horizont vorgegeben oder eingefroren wird
    (LPV-Form).
  \item Weiche Schranke: Mit rein quadratischer Strafe $\mu s^2$ wird die Schranke verletzt,
    sobald sie im harten Problem aktiv wäre, obwohl eine zulässige Lösung existiert; ein
    zusätzlicher linearer Term
    $\mu_1 s$ mit ausreichend großem $\mu_1$ macht die Strafe exakt (\cite{kerriganSoftConstraintsExact2000}; Voraussetzung laut Suchzusammenfassung:
    Strafgewicht über einer unteren Schranke; Zulässigkeitsfragen
    \cite{scokaertFeasibilityIssuesLinear1999}).
  \item Offsetfreiheit: Störmodell $d^{\mathrm{off}}_{k+1}=d^{\mathrm{off}}_k$ am Ausgang,
    $y_k=Cx_k+d^{\mathrm{off}}_k$; Beobachter schätzt $\hat x$ und $\hat d^{\mathrm{off}}$;
    Zielwertberechnung löst die Ruhelage $(x_s,u_s)$ zum Sollwert.
    Bedingungen: erweitertes System detektierbar (beim reinen Ausgangsstörmodell: $(A,C)$
    detektierbar und $A$ ohne Eigenwert 1), Zahl der Störzustände gleich Zahl der gemessenen
    Ausgänge, Zielwertberechnung lösbar, geschlossener Kreis stabil, Beschränkungen stationär
    nicht aktiv \cite{muskeDisturbanceModelingOffsetfree2002,
    pannocchiaDisturbanceModelsOffsetfree2003, maederLinearOffsetfreeModel2009}
    (Stellen lokal nachschlagen).
  \item Gemessene Störgrößen ($\TLT$, Last) als Vorsteuerung über ihren Verlauf im Horizont;
    ohne Prognose konstant fortschreiben. (Greift den Merker ch2 Z.~1111 auf:
    Störgrößenprädiktion erwähnen.)
  % neu: kerriganSoftConstraintsExact2000, scokaertFeasibilityIssuesLinear1999,
  %      maciejowskiPredictiveControlConstraints2002, pannocchiaOffsetfreeTrackingMPC2015
  \item Anker: \cite{rawlingsModelPredictiveControl20202020}; \cite{maciejowskiPredictiveControlConstraints2002};
    \cite{pannocchiaOffsetfreeTrackingMPC2015} (Vergleich offsetfreier Formulierungen:
    Störmodell mit Beobachter, Zustandsstörbeobachter, Geschwindigkeitsform).
    % rawlingsModelPredictiveControl20202020, maciejowskiPredictiveControlConstraints2002,
    % pannocchiaOffsetfreeTrackingMPC2015: Stelle offen
    % pannocchiaOffsetfreeTrackingMPC2015: [nur bibliografisch]; Aufzählung der Formulierungen
    % nicht aus dem Titel, ungeprüft (S)
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
  % neu: khalilNonlinearSystems2002, skogestadMultivariableFeedbackControl2005
  \item Anker: \cite{khalilNonlinearSystems2002} (Ruhelage, Linearisierung; Stelle lokal);
    \cite{skogestadMultivariableFeedbackControl2005} (Modellunsicherheit, Kap.~7 laut
    Suchzusammenfassung); \cite{rawlingsModelPredictiveControl20202020} (Zielwertberechnung).
    % rawlingsModelPredictiveControl20202020: Stelle offen
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
    % piroddiIdentificationAlgorithmPolynomial2003, farinaIterativeAlgorithmSimulation2010:
    % [nur bibliografisch]; Aussage durch Titel gedeckt (T)
  \item Konsistenz: Gleichungsfehler passt zu weißem Gleichungsrauschen (ARX-Struktur),
    Simulationsfehler zu Ausgangsrauschen (OE-Struktur)
    \cite{ljungSystemIdentificationTheory1999} (Kapitel lokal nachschlagen).
  \item Die Konsistenzaussage gilt im offenen Kreis. Bei Daten aus geregeltem Betrieb
    (Abschnitt~\ref{ChATCo}) ist $u$ mit dem Rauschen korreliert; die direkte Schätzung ist dann
    nur konsistent, wenn das wahre Störmodell im Modellsatz liegt
    (Abschnitt~\ref{closed_loop_identifkation}). Simulationsfehler bzw. OE-Struktur mit festem
    Rauschmodell ergibt dann eine verzerrte Strecke, auch in der Verstärkung.
  \item Träge Strecke, $a\to1$: Schon das Persistenzmodell $\hat y_{k+1|k}=y_k$ hat einen
    kleinen Einschrittfehler. Einschrittgüte daher immer gegen diese Referenz angeben.
  \item Das MPC nutzt $N$-Schritt-Prädiktionen. Maßgeblich ist der Fehler über dem Horizont,
    $e(h)$ für $h=1,\dots,N$. Für lineare Systeme mit fehlspezifizierter Modellklasse
    (Teilbeobachtbarkeit) senken direkt trainierte Mehrschritt-Prädiktoren den Bias gegenüber
    dem Freilauf eines Einschrittmodells; ein Einschrittmodell mit Mehrschritt-Verlust ist dort
    nur empirisch untersucht \cite{somalwarLearningImperfectModels2025}.
    % somalwarLearningImperfectModels2025: arXiv:2504.01766, Preprint; [nur bibliografisch],
    % Inhalt und Bias-Aussage nur aus Suchzusammenfassung (S); CDC-2025-Fassung nur laut
    % Suchzusammenfassung, lokal prüfen
  \item Freilauf auf aufgezeichneter Stellgröße aus geregeltem Betrieb ist eine
    Open-Loop-Simulation mit Closed-Loop-Eingang; eine Closed-Loop-Simulation braucht
    zusätzlich den Regler.
  % neu: piroddiIdentificationAlgorithmPolynomial2003, farinaIterativeAlgorithmSimulation2010,
  %      somalwarLearningImperfectModels2025, nellesNonlinearSystemIdentification2020,
  %      ribeiroParallelTrainingConsidered2018
  \item Anker: \cite{ljungSystemIdentificationTheory1999}; \cite{nellesNonlinearSystemIdentification2020} (Kap.~19, Gleichungs- gegenüber
    Ausgangsfehler); \cite{ribeiroParallelTrainingConsidered2018} (serie-parallele gegenüber
    paralleler Schätzung).
    % ljungSystemIdentificationTheory1999, ribeiroParallelTrainingConsidered2018: Stelle offen
  \item Anschluss: Die Arbeit bewertet offene und geschlossene Kette; pro Modell angeben, welches
    Kriterium für den Fit, welches für die Auswahl und welches für die Bewertung gilt.
\end{itemize}
% COPILOT-STICHPUNKTE END B2-Simulationsfehler
```

### BibTeX-Entwürfe B2

Herkunft (T/G/S) je Feld ist für die Einträge B2 nicht dokumentiert. Alle Felder gelten bis zum
Abgleich mit Zotero/Original als ungeprüft; Felder, die schon beim Erstellen als unsicher galten,
stehen zusätzlich als `% ungeprüft:` über dem Eintrag. Status aller Einträge:
[nur bibliografisch]. Schon in der Bib: `rawlingsModelPredictiveControl20202020`,
`muskeDisturbanceModelingOffsetfree2002`, `pannocchiaDisturbanceModelsOffsetfree2003`,
`maederLinearOffsetfreeModel2009`, `ljungSystemIdentificationTheory1999`,
`kaiserSparseIdentificationNonlinear2018`. Aus Auftrag A (noch nicht in der Bib):
`piroddiIdentificationAlgorithmPolynomial2003`, `farinaIterativeAlgorithmSimulation2010`,
`somalwarLearningImperfectModels2025`. Status in dieser Sitzung für alle genannten Keys, auch
die schon vorhandenen und die aus Auftrag A: [nur bibliografisch];
`somalwarLearningImperfectModels2025` ist arXiv-Preprint. `pannocchiaOffsetfreeTrackingMPC2015`:
Eintrag in den BibTeX-Entwürfen von Auftrag D.

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

% ungeprüft: author = {Kerrigan, E. C. and Maciejowski, J. M.} (Nachnamen in Treffer-URL gesehen,
%            Initialen nur aus Suchzusammenfassung);
%            booktitle = {Proc. UKACC International Conference (Control 2000)};
%            address = {Cambridge, UK}; year = {2000}; pages = {2319--2327}; keine DOI gefunden
@inproceedings{kerriganSoftConstraintsExact2000,
  title     = {Soft Constraints and Exact Penalty Functions in Model Predictive Control},
  url       = {https://spiral.imperial.ac.uk/entities/publication/b1d59b69-3901-41f5-bb9f-f619319fa9dc}
}

% ungeprüft: Vornamen (Pierre, Rawlings); number = {8}; pages = {1649--1659} (Startseite 1649 aus ADS-Bibcode, T)
@article{scokaertFeasibilityIssuesLinear1999,
  author    = {Scokaert, P. O. M. and Rawlings, J. B.},
  title     = {Feasibility issues in linear model predictive control},
  journal   = {AIChE Journal},
  volume    = {45},
  year      = {1999},
  doi       = {10.1002/aic.690450805}
}

% pannocchiaOffsetfreeTrackingMPC2015: hier nicht übernehmen, Eintrag siehe BibTeX-Entwürfe D (Metadaten G).

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
# Koeffizientenvergleich nach Tin, THT, TLT: alle (PH, P3) bei beliebigem c
diff3 = sp.expand(Tstat - eb21)
sol3 = sp.solve([diff3.coeff(vv) for vv in (Tin, THT, TLT)], [PH, P3], dict=True)
print("EB21 Koeffizientenvergleich:", sol3)
check("PH = eHT + eLT(1-eHT-c)", sol3[0][PH] - (eHT + eLT*(1 - eHT - c)))

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

Ausgabe: alle Prüfungen „OK“; EB21-Koeffizientenvergleich: $P_3=\varepsilon_{LT}$, $P_H=\varepsilon_{HT}+\varepsilon_{LT}(1-\varepsilon_{HT}-c)$; Mehrschritt-Beispiel: $\partial^2x_2/\partial u_0^2=-2\theta$ (nicht affin), bilinear $\theta^2(x_0-T_{LT})$, LPV exogen 0; $K=b/(1-a)$ mit relativer Empfindlichkeit $a/(1-a)$.

---

## Offen / nicht belegt

- Keine Lehrbuchstelle am Original geprüft; das gilt für alle in ch2 zitierten Seiten und
  Gleichungsnummern des Abschnitts Wärmeübertragung und für alle Kapitelangaben in B2.
- B2-Anker nur bibliografisch; Kapitelnamen bei Åström & Wittenmark, Franklin u. a., Skogestad &
  Postlethwaite nur aus Suchzusammenfassung. Lokal nachschlagen: Euler/Näherung (Åström),
  Padé und verschobener Eingang (Normey-Rico), $\Delta u$-Schranken und weiche Schranken
  (Maciejowski, Camacho Kap. 7), Linearisierung (Khalil), Verstärkungsunsicherheit (Skogestad),
  Kapitel zu Prädiktions- und Simulationsfehler (Ljung), Bedingungen der Offsetfreiheit
  (Muske 2002, Pannocchia 2003, Maeder 2009).
- Anker ohne Stelle: B2.1 Franklin; B2.2 Maciejowski; B2.3 alle drei (Rawlings, Maciejowski,
  Pannocchia 2015); B2.4 Rawlings; B2.5 Ljung (Kapitel), Ribeiro (Abschnitt).
- Somalwar u. a. 2025: CDC-2025-Fassung nur laut Suchzusammenfassung; Preprint-Vermerk lokal
  prüfen.
- BibTeX B2: Herkunft der Felder (ISBN, DOI, Reihe, Ort, Vornamen) nicht je Feld belegt.
- Kaiser u. a. 2018: Befund „kontinuierliches Modell, nichtlineares MPC mit SQP“ stammt aus dem
  Autoren-Code (GitHub eurika-kaiser/SINDY-MPC), nicht aus dem Papertext.
- Kein belastbarer Primäranker für „Gain-Fehler identifizierter Modelle verschlechtert MPC“.
  Kandidaten nur mit (S)-Metadaten: Yousefi u. a. 2015 (Control Eng. Pract. 43, 59–68,
  Model-Plant-Mismatch an Papiermaschinen), Wang, Hägglund, Song 2012 (Ind. Eng. Chem. Res.,
  DOI 10.1021/ie300834y aus URL). Ein Lehrbuchanker zur integralen Regelbarkeit bei
  Gain-Fehlern (z. B. Morari & Zafiriou) wurde nicht gesucht.
- Ventilschaltung (Stufe mit $\TLT$ oder mit Mischtemperatur angeströmt, vgl. ch2 Z. 263–265)
  und Messort von $\THT$, $\TLT$: nur aus der Anlage klärbar, nicht aus der Literatur.
- Hydraulische Einordnung unter „Ventilschaltung“ (Umlenk- bzw. Verteilschaltung mit
  Eintritt $\TLT$, Beimisch- oder Einspritzschaltung mit Mischtemperatur): Fachwissen ohne
  geprüfte Quelle; Webseiten aus der Suche nicht übernommen. Lehrbuchstelle zur Anlagenhydraulik
  lokal ergänzen oder Aussage auf die Anlagendokumentation stützen.
- Stufenreihenfolge HT vor LT und Sensorlage: laut ch2 Z. 557–558 nicht verifiziert; nur aus
  Anlage oder Zeichnung klärbar.
- Faustregel zur Abtastzeit: Stelle bei Åström & Wittenmark nicht gesehen.
- Gleichungslabels in B2 (`eq.grundlagen.zoh` usw.) sind Vorschläge; auf Kollision mit
  bestehenden Labels in Kap. 5 prüfen.
