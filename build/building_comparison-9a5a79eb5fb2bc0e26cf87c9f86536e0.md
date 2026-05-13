# Gebäudevergleich

Mit dem Gebäudevergleich können wir das Verhältnis der OSM-Gebäudefläche im Vergleich zu zwei Referenzdatensätzen überprüfen.

:::{attention}
Dieser Indikator ist nur für das Thema _Gebäude (Fläche)_ verfügbar.
:::

## Ergebnis
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Das grüne, gelbe oder rote Banner oben links zeigt den Attribut-Vollständigkeitsgrad an.

<img src="../../abbildungen/gebäudevergleich_las_palmas.png"/>

Die Grafik zeigt ein Balkendiagramm, in dem für jeden Referenzdatensatz, der sich im Untersuchungsgebiet befindet, zwei Balken zu sehen sind. Einmal jeweils die Gebäudefläche des entsprechenden Referenzdatensatzes im Untersuchungsgebiet und die Gebäudefläche von OSM in grau.

:::{attention}
Ist nicht das gesamte Untersuchungsgebiet von dem jeweiligen Referenzdatensatz abgedeckt wird auch nur die OSM-Gebäudefläche von dem Teil des Untersuchungsgebiet angegeben, der vom Referenzdatensatz abgedeckt ist. Es ist daher auch möglich, dass die Referenzdatensätze unterschiedliche Teile des Untersuchungsgebiet abdecken und somit auch unterschiedliche Werte für OSM in der Grafik zu sehen sind.
:::

## Methodik und Referenzdatensätze
`Extrinsischer Ansatz`

Das Ergebnis ist das Verhältnis der gesamten Gebäudefläche in OSM geteilt durch die gesamte Gebäudefläche im Referenzdatensatz.
Abhängig von der Verfügbarkeit der Referenzdatensätze in deinem Interessensgebiet liefert dir das Ergebnisprotokoll 1-2 Vergleichsdiagramme.
Der Gebäudevergleich ist eine extrinsische Methode, was bedeutet, dass OSM-Daten mit externen Referenzdatensätzen verglichen werden.
Dies liefert einen Hinweis auf die Vollständigkeit der OSM-Daten.
Allerdings dürfen die Referenzdatensätze nicht als vollständig korrekt oder aktuell angesehen werden.

Referenzdatensätze:
- [EUBUCCO](https://docs.eubucco.com/): EUBUCCO ist ein europaweiter Datensatz für Gebäudegrundrisse, der aus administrativen Datensätzen abgeleitet wurde. Über 300 Millionen Gebäudegrundrisse in Europa sind enthalten. Dieser Datensatz ist der vollständigste Datensatz für Gebäudegrundrisse. Allerdings ist er älter, kann veraltet sein und deckt nur Gebiete innerhalb Europas ab.
- [Microsoft Buildings](https://planetarycomputer.microsoft.com/dataset/ms-buildings): Der Microsoft Buildings Datensatz ist ein weltweiter Datensatz für Gebäudegrundrisse. Ein Machine-Learning-Ansatz wurde verwendet, um Gebäudegrundrisse aus Satellitenbildern abzuleiten. Neben unvermeidbaren Fehlern, die bei der Elementerkennung durch Machine Learning auftreten, ist der große Vorteil dieses Datensatzes die weltweite Abdeckung.

Im Bereich für die Auswahl des Interessensgebiets im Dashboard kannst du weiße, hellgraue und dunkelgraue Regionen sehen, wenn der Gebäudevergleich-Indikator aktiviert ist. Dies zeigt die Verfügbarkeit der Referenzdatensätze an.

<div>
<img src="../../abbildungen/gebäudevergleich_map.png" width="500"/>
</div>

- In weißen Bereichen sind beide Referenzdatensätze verfügbar.
- Hellgraue Bereiche zeigen an, dass nur einer der beiden möglichen Referenzdatensätze verfügbar ist.
- Dunkelgraue Bereiche sind Gebiete ohne Referenzdatensätze.

Ein Ergebnis wird berechnet, wenn mindestens 50 % deines ausgewählten Gebiets durch einen Referenzdatensatz abgedeckt sind.

:::{margin} Limitationen
1. Da OpenStreetMap sich kontinuierlich aktualisiert und die Referenzdatensätze zu einem bestimmten Zeitpunkt herausgegeben wurden, sind diese relative zu OpenStreetMap zum Zeitpunkt des Vergleichs nicht mehr aktuell.
2. Der Vergleich basiert nur auf dem Verhältnis der gesamten Flächen und nicht auf der Verschneidung beziehungsweise Überlappung der einzelnen Gebäude.
:::

## Beispiele

Die folgende Abbildung zeigt den Gebäudevergleich-Indikator für Las Palmas, wo EUBUCCO einen größeren Teil der Inseln abdeckt als Microsoft Buildings. Für den Vergleich werden nur OSM-Gebäudegrundrisse berücksichtigt, die sich innerhalb des durch den Referenzdatensatz abgedeckten Bereichs befinden. Dadurch wird die gesamte OSM-Gebäudefläche im Vergleich mit Microsoft Buildings kleiner dargestellt als im Vergleich mit EUBUCCO.

<img src="../../abbildungen/gebäudevergleich_las_palmas.png" width="700"/>
