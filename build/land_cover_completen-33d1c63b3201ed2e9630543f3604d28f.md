# Landbedeckungsvollständigkeit

Der Landbedeckungsvollständigkeits-Indikator berechnet den Prozentsatz der Gesamtfläche, die durch OSM-Landbedeckungsdaten abgedeckt ist.

:::{attention}
Dieser Indikator ist nur für das Thema _Landnutzung und Landbedeckung_ verfügbar.
:::

## Ergebnis
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Die Grafik zeigt den Prozentwert der gewählten Fläche, die von OSm-Landbedeckungsdaten abgedeckt ist.
Das grüne, gelbe oder rote Banner oben links zeigt den Landbedeckungsvollständigkeit an.

<img src="../../abbildungen/landbedeck_vollständigkeit_bonn.png"/>

## Methodik
`Intrinsischer Ansatz`

Der Landbedeckungsvollständigkeit-Indikator quantifiziert den Anteil eines Interessensgebiets (AOI), der durch OSM-Landbedeckungsdaten abgedeckt ist.
Er wird intrinsisch als Verhältnis der aufsummierten Fläche von OSM-Landbedeckungspolygonen zur Gesamtfläche des Untersuchungsgebiets berechnet, normalisiert auf einen Bereich von 0 bis 1.

:::{margin} Limitationen
Sich überlappende OSM-Landbedeckungspolygone werden mehrfach gezählt und können das Landbedeckungsvollständigkeitsverhältnis fälschlicherweise erhöhen.
:::

Es gibt drei Qualitätskategorien:
- niedrige Vollständigkeit < 50%
- mittlere Vollständigkeit 50% - 85%
- hohe Vollständigkeit > 85%

Dieser Indikator ist nur für das Thema _land-cover_ verfügbar. Dieser umfasst alle OSM-Tags, die Landbedeckung und Landnutzung definieren, wie bebaute Flächen, Wald oder Binnengewässer. Eine detaillierte Liste der Filter für alle genutzten OSM-Tags findest du in den [Themadefinitionen](../topics.md).

## Beispiele

Hier sehen wir die Landbedeckungsvollständigkeit von Bonn. Mit 94% hat Bonn eine hohe Vollständigkeit.

<img src="../../abbildungen/landbedeck_vollständigkeit_bonn.png" width="700"/>

Diese Abbildung zeigt die Landbedeckungsvollständigkeit aus einem ländlichen Raum nahe Hannover. Mit 77% wird die Vollständigkeit als mittelmäßig eingestuft.

<img src="../../abbildungen/landbedeck_vollständigkeit_hannover.png" width="700"/>


```python

```
