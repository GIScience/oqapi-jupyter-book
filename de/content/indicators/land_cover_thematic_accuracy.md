# Thematische Genauigkeit (Landbedeckung)

Dieser Indikator bewertet die Übereinstimmung zwischen OSM-Landbedeckungsdaten und dem CORINE Land Cover (CLC) Datensatz.
Er kann entweder für alle CLC-Klassen oder für ausgewählte Klassen einzeln angewendet werden.



Für das definierte Interessensgebiet werden die aus der Verschneidung von OSM- und CLC-Daten resultierenden Polygone in einer Wahrheitsmatrix aggregiert. Daraus berechnen wir klassenbezogene und Gesamtgenauigkeitsmetriken, einschließlich Präzision, Sensivität und dem F1-Score. Alle Metriken sind flächengewichtet, sodass die räumliche Ausdehnung der Polygone berücksichtigt wird, anstatt Elemente als gleich gewichtete Einheiten zu behandeln. Dieser Ansatz ermöglicht eine systematische Bewertung der thematischen Konsistenz von OSM-Landbedeckungsdaten im Vergleich zu den referenzierten CLC-Daten.

:::{note}
Bei diesem Indikator muss zusätzlich zum Thema auch ein Attribut gewählt werden, das untersucht werden soll. Dafür erscheint unter der Auswahl des Indikators ein Feld für die Attributauswahl (siehe Abbildung). Der Indikator kann entweder für ein einzelnes Attribut oder alle Attribute auf einmal berechnet werden. Für letzteres muss das Feld leer gelassen werden.

<div>
<img src="../../abbildungen/landbedeck_thematisch_dropdown.png" width="300"/>
</div>
:::

Der Ergebniswert wird als flächengewichteter F1-Score berechnet, normalisiert auf einen Bereich von 0 bis 1. Werte unter 0.6 gelten als geringe thematische Übereinstimmung, Werte zwischen 0.6 und 0.85 als mittlere Übereinstimmung und Werte über 0.85 als hohe Übereinstimmung zwischen OSM und CLC.

:::{attention}
Dieser Indikator ist nur für das Thema _Landnutzung und Landbedeckung_ verfügbar.
:::

### Methodik und Daten

`Extrinsischer Ansatz`

Die OSM-Elemente werden basierend auf ihren landuse=* und natural=* Tags den CLC Level 2 Klassen zugeordnet, wie in der folgenden Tabelle dargestellt. Die räumliche Verschneidung von OSM-Polygonen mit CLC-Polygonen erzeugt kombinierte Geometrien, die sowohl die OSM- als auch die CLC-Klassenlabels enthalten. Dieser Schritt stellt sicher, dass Unterschiede in den Klassendefinitionen direkt auf Polygonebene analysiert werden können. Bereiche, in denen einer der Datensätze nicht verfügbar ist, werden ignoriert. Für das definierte Interessensgebiet werden die aus der Verschneidung von OSM- und CLC-Daten resultierenden Polygone in einer Wahrheitsmatrix aggregiert. Daraus berechnen wir klassenbezogene und Gesamtgenauigkeitsmetriken, einschließlich Precision, Recall und dem F1-Score. Alle Metriken sind flächengewichtet, sodass die räumliche Ausdehnung der Polygone berücksichtigt wird, anstatt Features als gleich gewichtete Einheiten zu behandeln. Dieser Ansatz ermöglicht eine systematische Bewertung der thematischen Konsistenz von OSM-Landbedeckung im Vergleich zu den referenzierten CLC-Daten. Der Ergebniswert wird als flächengewichteter F1-Score berechnet, normalisiert auf einen Bereich von 0 bis 1.

- Geringe thematische Genauigkeit (< 0.6)
- Mittlere thematische Genauigkeit (0.6 - 0.85)
- Hohe thematische Genauigkeit (> 0.85)


#### CORINE Landbedeckungsdaten
In seiner aktuellen Form bietet das [CORINE Land Cover (CLC)](https://land.copernicus.eu/en/products/corine-land-cover) Produkt ein europaweites Inventar von Landbedeckung und Landnutzung mit 44 thematischen Klassen, die von großflächigen Waldgebieten bis hin zu einzelnen Weinbergen reichen. CORINE verwendet eine dreistufige Nomenklatur für Land-Cover-Klassen.
Hier verwenden wir das „CORINE Land Cover 5 ha, Stand 2021 (CLC5-2021)“, bereitgestellt durch das Bundesamt für Kartographie und Geodäsie, sowie Level 2 der Nomenklatur (z. B. 1.1 Urban Fabric, 1.2 Industrial, commercial and transport units).

### Aufbereitung der Daten

OSM-Objekten werden basierend auf ihrer Kennzeichnung eine CLC-Klasse zugewiesen. Dazu wurde die unten angegebene Tabellle benutzt.
Wir berechnen die Verschneidung von OSM-Landbedeckung-Polygonen und CORINE-Landbedeckung-Polygonen.
Die resultierenden Polygone enthalten sowohl die OSM-CLC-Klasse als auch die CORINE-Klasse.

| CLC (level 2)                                        | OSM tags                                                                                                                                                                                |
|------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.1 Städtische geprägte Flächen                                    | `landuse in (residential, retail)`                                                                                                                                                      |
| 1.2 	Industrie-, Gewerbe- und Verkehrsflächen      | `landuse in (industrial, commercial, port, railway, lock) or leisure in (marina)`                                                                                                       |
| 1.3 	Abbauflächen, Deponien und Baustellen               | `landuse in (quarry, construction, landfill, brownfield)`                                                                                                                               |
| 1.4 	Grünflächen    | `landuse in (recreation_ground, allotments, village_green, cemetery, grass) or leisure in (park, garden, pitch, golf_course, playground, stadium, recreation_ground, common, dog_park)` |
| 2.1 	Ackerland                                     | `landuse in (greenhouse_horticulture, greenhouse, farmland, farmyard)`                                                                                                                  |
| 2.2 	Dauerkulturen                                 | `landuse in (vineyard, orchard)`                                                                                                                                                        |
| 2.3 	Grünland                                        | `landuse in (meadow)`                                                                                                                                                                   |
| 2.4 	Heterogene landwirtschaftliche Fläche                | *For class 2.4 many of the OSM tags from 2.1 apply. Therefore class 2.4 is never assigned.*                                                                                             |
| 3.1 	Wälder                                         | `landuse in (forest) or natural in (wood)`                                                                                                                                              |
| 3.2 	Strauch- und Krautvegetation | `landuse in (greenfield) or natural in (grassland, scrub, heath, fell)`                                                                                                                 |
| 3.3 	Offene Flächen ohne/ mit geringer Vegetation        | `natural in (beach, scree, shingle, bare_rock, sand, glacier, mud, glacier, rock, cliff, fill)`                                                                                         |
| 4.1 	Feuchtflächen im Landesinneren                               | `natural in (wetland)`                                                                                                                                                                  |
| 4.2 	Feuchtflächen an der Küste                               | `landuse in (salt_pond)`                                                                                                                                                                |
| 5.1 	Wasserflächen im Landesinneren                                   | `natural in (water, pond) or landuse in (basin, reservoir)`                                                                                                                             |
| 5.2 	Meeresgewässer                                   | *Marine waters are not mapped in OSM. Therefore class 5.2 is never assigned.*                                                                                                           |

## Ergebnisgrafik
Die Ergebnisse der Abfrage findest du im Ergebnisprotokoll unten.
Ergebnisprotokoll unten.
Das grüne, gelbe oder rote Banner oben links zeigt den Attribut-Vollständigkeitsgrad an.



## Beispiel

In Bonn hat die thematische Genauigkeit aller Landbedeckungsklassen gemeinsam eine mittlere Genauigkeit von 85,16%. Auf der Abbildung sehen wir wie sich diese Genauigkeit zusammensetzt und dass beispielsweise städtisch geprägte Fläche (Urban Fabric) eine weit höhere Übereinstimmung mit der Corine Klassifikation erreicht als Grünflächen (Shrubs and/or herbaceous vegetation associations).

<div>
<img src="../../abbildungen/landbedeck_thematisch_bonn.png" width="700"/>
</div>

Wenn wir in dem Dropdown-Menü eine spezielle Landbedeckungsklasse auswählen die uns besonders interessiert, sieht das Ergebnis wie folgt aus. Hier sehen wir die thematische Genauigkeit für Grünflächen in Bonn. Falsch-Negativ, Richtig-Positiv und Falsch-Positiv sind hier jeweils zu etwa einem Drittel vorhanden. Dies zeigt uns eine geringe Übereinstimmung des OSM mit dem Corine Datensatzes im Bereich Grünflächen in Bonn.

<div>
<img src="../../abbildungen/landbedeck_thematisch_bonn_grünflächen.png" width="700"/>
</div>

Eine höhere Übereinstimmung finden wir im Kreis Euskirchen mit der Klasse Ackerland.

<div>
<img src="../../abbildungen/landbedeck_thematisch_euskirchen_ackerland.png" width="700"/>
</div>

### Für diesen Indikator genutzte Literatur

- Schultz, Michael, Janek Voss, Michael Auer, Sarah Carter und Alexander Zipf. 2017. „Open Land Cover from OpenStreetMap and Remote Sensing.“ International Journal of Applied Earth Observation and Geoinformation 63 (Mai): 206–13. https://doi.org/10.1016/j.jag.2017.07.014.


```python

```
