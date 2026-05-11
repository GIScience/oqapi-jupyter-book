# Aktualität

Der Aktualität-Indikator misst wie aktuell OSM-Elemente sind, indem die Verteilung ihrer neuesten Beiträge analysiert wird.

## Methodik
`Intrinsischer Ansatz`

Der Aktualität-Indikator berücksichtigt alle Änderungen an Geometrien und Attributen (ohne Löschungen) seit 2008, aggregiert in monatlichen Intervallen. Der Ergebniswert wird als Prozentsatz der Elemente berechnet, die in den letzten 36 Monaten zuletzt bearbeitet wurden, normalisiert auf einen Bereich von 0 bis 1. Jeder Beitrag wird einer von drei Qualitätsstufen zugeordnet:

- Veraltet (< 0.5): Elemente, die über einen längeren Zeitraum (über 8 Jahre) nicht aktualisiert wurden, werden als veraltet eingestuft. Diese Schwellenwerte werden in Monaten seit dem aktuellen Datum ausgedrückt. Für jede Qualitätsstufe wird der relative Anteil der Beiträge berechnet, die in diese Kategorien fallen.
- Mittel (0.5 - 0.75): Beiträge, die zuletzt innerhalb eines Zeitraums von 4 bis 8 Jahren bearbeitet wurden, werden als mittel eingestuft.
- Aktuell (> 0.75): Elemente gelten als aktuell, wenn ihre letzte Bearbeitung in ein vordefiniertes kurzes Zeitfenster von unter 4 Jahren fällt.
Generell ist anzumerken, dass je nach Thema Daten auch noch akkurat sind, selbst wenn sie veraltet sind. Natürliche Landbedeckungsflächen wie Wälder können beispielsweise trotz eines Alters von über 8 Jahren noch korrekt sein.

## Ergebnisgrafik
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Ergebnisprotokoll unten.
Das grüne, gelbe oder rote Banner oben links zeigt den Attribut-Vollständigkeitsgrad an.

In der Grafik wird für jeden Monat auf der X-Achse ein Balken dargestellt. Die Höhe des Balken gibt an, wie viel Prozent der aktuell/heute vorhandenen OSM-Objekte des gewählten Themas in diesem Monat zuletzt bearbeitet wurden. Die Farbe gibt an, zu welcher der oben genannten Qualitätsstufen dieser Monat gerechnet wird. In der Legende sind die summierten Prozente für jede Qualitätsstufe. Die Y-Achse auf der linken Seite stellt die Prozentwerte dar, während die rechte Seite die absoluten Werte der entsprechenden Aggregation zeigen.
## Beispiel

Sehen wir uns im Folgenden einige Ergebnisse des Aktualität-Indikators an. 
Die erste Abbildung zeigt Änderungen an Objekten des Themas _Feuerwachen_ in Erding in ihrer zeitlichen Verteilung. So kann ein Ergebnis aussehen, wenn es nur sehr wenige Elemente des abgefragten Themas in dem Untersuchungsgebiet gibt, die nur selten bearbeitet werden. Wenn wir mit dem Cursor über die farbigen Linien fahren, öffnet sich ein Fenster das weitere Informationen erhält. Hier erfahren wir, dass an jedem Änderungszeitpunkt genau ein Objekt bearbeitet wurde.

<div>
<img src="../../abbildungen/aktualität_feuerwachen_erding.png" width="700"/>
</div>

In der nächsten Abbildung sehen wir die Aktualität von ÖPNV-Haltestellen in Karlsruhe. Wir haben hier ein Thema mit vielen einzelnen Objekten, die sich aufgrund von Baustellen oder Änderung von Fahrplänen häufiger ändern können.

<div>
<img src="../../abbildungen/aktualität_öpnv.png" width="700"/>
</div>


```python

```
