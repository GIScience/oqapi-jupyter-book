# ohsome Dashboard

Auf dieser Seite findest du eine einfache Übersicht darüber, wie du dich im [ohsome Dashboard](https://dashboard.ohsome.org/en/#backend=ohsomeApi&groupBy=none&time=%2F2026-02-19T12%3A00Z%2FP1M&key=natural&value=tree&types=node&measure=count) zurechtfindest.
Im oberen linken Reiter kannst du zwischen den *OSM-Zeitreihen* und den *OSM-Qualitätsanalysen* wählen.
Die *Zeitreihen* geben dir Einblicke in die Entwicklung der OSM-Daten für jede Region und jeden Zeitraum.
Die *Qualitätsanalysen* bieten viele verschiedene Indikatoren, mit denen du OSM-Daten für dein Interessensgebiet validieren kannst.

Klicke oben links auf den Reiter *OSM-Qualitätsanalysen* um das Dashboard umzustellen.
Das Dashboard ist in verschiedene Bereiche aufgeteilt, die unterschiedliche Schritte der Analyse beeinflussen:
1. [Thema](#thema)
2. [Untersuchungsgebiet](#Untersuchungsgebiet)
3. [Qualitätsindikatoren](#qualit-tsindikatoren)
4. [Ergebnisse](#Ergebnisse)

![ohsome Dashboard Overview](../abbildungen/ohsome_dashboard_overview_de.png)

## Thema

Im ersten Schritt, wählst du aus dem Dropdown-Menü das *Thema* aus, das du untersuchen möchtest.
Klickst du in das Eingabefeld, kannst du auch nach weiteren vordefinierten Themen suchen.

*Themen* (auch Topics genannt) werden durch eine Menge von OSM Tags definiert, die eine bestimmte Objektart beschreiben.
Das OSM-Dashboard erstellt automatisch den passenden OSM-Filter basierend auf dem ausgewählten *Thema*.

:::{margin} **Beispiel**
Das Thema *Schulen* ist beispielsweise durch diesen OSM-Tagfilter definiert: ```amenity=school and (type:way or type:node)```
:::

<img src="../abbildungen/topics_deutsch.png" width="300"/>

:::{admonition} Custom Topics
:class: seealso
Du kannst *Themen* auch komplett frei definieren, z.B. wenn du nur bestimmte Straßentypen in deiner Analyse betrachten möchtest.
Wir haben dafür eine eigene Tutorialseite angelegt → [Custom Topics](custom_topics.md)
:::


## Untersuchungsgebiet

Wähle dein Untersuchungsgebiet auf der Karte im rechten Fenster aus. Du kannst entlang von Verwaltungsgrenzen oder mit selbst definierten Rahmen auswählen. Zoome hinein, um eine genauere Abgrenzung deines Untersuchungsgebiet zu erhalten.

::::{tab-set}
::: {tab-item} Verwaltungsgrenzen
Klicke einfach auf ein Gebiet und wähle es so für die Analyse aus.
Du kannst auch mehrere Regionen gleichzeitig wählen und eine gemeinsame Abfrage für die gesamte Region ausführen. 
Du kannst Gebiete entfernen, wenn du erneut auf sie klickst oder die blaue Box unter der Karte entfernst.

![area_of_interest](../abbildungen/Untersuchungsgebiet_Auswahlkarte_de.png)
:::

::: {tab-item} Bounding Box
Ziehe mit der Maus ein Rechteck auf und definiere eine *Bounding Box*.
Du kannst diese Bounding Box anschließend auch wieder anpassen oder löschen.

![area_of_interest](../abbildungen/Untersuchungsgebiet_Auswahlkarte_de_bbox.png)
:::
::::


## Qualitätsindikatoren

Abhängig von deinem gewählten *Thema* findest du die verfügbaren Qualitätsindikatoren zur Auswahl.
Jeder Indikator wird direkt im ohsome Dashboard kurz beschrieben.
Eine detaillierte Erläuterung zur Methodik und möglichen Limitationen findest du im nächsten Kapitel.

Du kannst OSM-Daten anhand mehrerer Qualitätsdimensionen analysieren:

:::{dropdown} Vollständigkeit
- Kartensättigung
- Attributvollständigkeit
- Gebäudevergleich
- Landbedeckungsvollständigkeit
- Straßenvergleich
:::

:::{dropdown} Zeitliche Genauigkeit
- Aktualität
:::

:::{dropdown} Thematische Genauigkeit
- Thematische Genauigkeit - Landbedeckung
- Thematische Genauigkeit - Straßen
:::

:::{dropdown} Sonstige
- Nutzeraktivität
:::



Wähle die aus, die dich interessieren und klicke auf *Abfrage starten*, um die Berechnung deiner Ergebnisse anzustoßen.

<img src="../abbildungen/indikatoren_auswahl_de.png" width="300"/>

## Ergebnisse

Die berechneten Ergebnissen werden nach einigen Sekunden im unteren Fenster als Abbildung geladen.
Das Ergebnis jedes Indikators wird farblich in drei Kategorien eingestuft: in der Regel grün (gut), gelb (mittel) und rot (schlecht). Die Einstufung wird anhand von wenigen Sätzen erläutert.

![ergebnisse](../abbildungen/ohsome_dashboard_ergebnisse_de.png)


:::{margin} **Ergebnisse teilen**
Du kannst deine Ergebnisse mit anderen Menschen über einen Link teilen. Diese URL verlinkt zur Berechnung der nebenstehenden Abbildung.

https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=cycleway&adminids=-285864&indicators=currentness
:::

Auf den nächsten Seiten beschreiben wir die Ergebnisse für jeden Qualitätsindikator und diskutieren verschiedene Interpretationen.