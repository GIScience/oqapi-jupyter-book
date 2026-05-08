# Landbedeckungsvollständigkeit

Der Landbedeckungsvollständigkeits-Indikator berechnet den Prozentsatz der Gesamtfläche, die durch OSM-Landbedeckungsdaten abgedeckt ist.

:::{attention}
Dieser Indikator ist nur für das Thema _Landnutzung und Landbedeckung_ verfügbar.
:::

### Methodik und Daten
`Intrinsischer Ansatz`

Der Landbedeckungsvollständigkeit-Indikator quantifiziert den Anteil eines Interessensgebiets (AOI), der durch OSM-Landbedeckungsdaten abgedeckt ist. Er wird intrinsisch als Verhältnis der aufsummierten Fläche von OSM-Landbedeckungspolygonen zur Gesamtfläche der AOI berechnet, normalisiert auf einen Bereich von 0 bis 1:

- Niedrige Vollständigkeit (< 0.5)
- Mittlere Vollständigkeit (0.5 - 0.85)
- Hohe Vollständigkeit (> 0.85)

Dieser Indikator ist nur für das Thema _land-cover_ verfügbar. Dieser umfasst alle OSM-Tags (Kennzeichnungen), die Landbedeckung und Landnutzung definieren, wie bebaute Flächen, Wald oder Binnengewässer. Eine detaillierte Liste der Filter für alle genutzten OSM-Tags findest du in den [Themadefinitionen](../topics.md).


### Limitationen

Sich überlappende OSM-Landbedeckungspolygone werden mehrfach gezählt und können das Landbedeckungsvollständigkeitsverhältnis fälschlicherweise erhöhen.

## Ergebnisgrafik
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Ergebnisprotokoll unten.
Das grüne, gelbe oder rote Banner oben links zeigt den Attribut-Vollständigkeitsgrad an.

Es gibt drei Qualitätskategorien:
- niedrige Completeness < 50%
- mittlere Completeness 50% - 85%
- hohe Completeness > 85%

Die Grafik zeigt den Prozentwert der gewählten Fläche, die von OSm-Landbedeckungsdaten abgedeckt ist.


## Beispiel

Hier sehen wir die Landbedeckungsvollständigkeit von Bonn. Mit 94% hat Bonn eine hohe Vollständigkeit.

<div>
<img src="../abbildungen/landbedeck_vollständigkeit_bonn.png" width="700"/>
</div>

Diese Abbildung zeigt die Landbedeckungsvollständigkeit aus einem ländlichen Raum nahe Hannover. Mit 77% wird die Vollständigkeit als mittelmäßig eingestuft.

<div>
<img src="../abbildungen/landbedeck_vollständigkeit_hannover.png" width="700"/>
</div>



```python

```
