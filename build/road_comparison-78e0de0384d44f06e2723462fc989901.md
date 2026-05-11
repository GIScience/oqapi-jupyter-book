# Straßenvergleich

Der Straßenvergleich-Indikator schätzt die Vollständigkeit der OSM-Straßendaten anhand eines Referenzdatensatzes. Das Ergebnis ist ein Verhältnis der Länge der Referenzstraßen, die durch OSM-Straßen abgedeckt sind, zur Gesamtlänge des Referenzdatensatzes.

:::{attention}
Dieser Indikator ist nur für das Thema _Straßen (alle highways)_ verfügbar.
:::

## Methoden und Daten
`Extrinsische Methode`

Der Indikator identifiziert entsprechende Straßengeometrien in OSM und im Referenzdatensatz, um das Verhältnis der übereinstimmenden Straßenlänge in km zu berechnen.
Der Microsoft Roads Datensatz wird als Referenz verwendet. Allerdings sollte der Referenzdatensatz nicht als vollständig korrekt und aktuell betrachtet werden.
Der Road Comparison Indicator ist nur für das *Thema* „Straßen (alle highways)“ verfügbar.

Referenzdatensatz: 
- [Microsoft Roads](https://github.com/microsoft/RoadDetections): Der Microsoft Roads Datensatz ist ein weltweiter Straßendatensatz. Ein Machine-Learning-Ansatz wurde verwendet, um Straßen aus Satellitenbildern abzuleiten.

## Ergebnisgrafik
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Ergebnisprotokoll unten.
Das grüne, gelbe oder rote Banner oben links zeigt den Attribut-Vollständigkeitsgrad an.

Die Grafik zeigt ein Balkendiagramm der Vollständigkeit. Die graue Füllung zeigt an, wie viel Prozent der Referenzstraßen von OSM-Straßen abgedeckt werden.

## Beispiel

<div>
<img src="../../abbildungen/Straßenvergleich_Heidelberg.png" width="600"/>
</div>

Die Übereinstimmung zwischen Microsoft Roads und OSM beträgt in Heidelberg 96%, weshalb hier von einer hohe Vollständigkeit der OSM-Daten auszugehen ist.

In einer Region der Türkei liegt die Übereinstimmung nur bei etwa zwei Dritteln. Hier ist die Vollständigkeit nur mittelmäßig und es ist von einigen Datenlücken auszugehen, wobei die OSM-Daten je nach Anwendungsfall durchaus noch nutzbar sind.

<div>
<img src="../../abbildungen/Straßenvergleich_Türkei.png" width="600"/>
</div>



```python

```
