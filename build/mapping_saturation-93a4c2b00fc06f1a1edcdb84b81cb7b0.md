# Kartierungssättigung

Der Kartierungssättigung-Indikator liefert (zusammen mit den Vollständigkeitsindikatoren) ein Maß für die Vollständigkeit. Es wird alysiert, wie sich das Wachstum kartierter Objekte in OSM im Laufe der Zeit einem natürlichen Maximum annähert. 


## Methoden und Daten
`Intrinsischer Ansatz`

Die zentrale Annahme der Mapping-Sättigung ist, dass jedes Objekt in der Realität eine endliche Ausdehnung hat. Mit zunehmender Kartierungsaktivität nimmt die Anzahl bzw. Länge neu hinzugefügter Objekte pro Zeitschritt ab, und die kumulative Wachstumskurve sättigt sich allmählich in Richtung des tatsächlichen Werts.
Um dieses Sättigungsniveau zu schätzen, nutzen wir die historische Entwicklung der OSM-Beiträge und passen nichtlineare Regressionsmodelle an die kumulative Wachstumskurve an. Der Workflow für den Kartierungssättigung-Indikator besteht aus vier Hauptschritten. 

1) Die zeitliche Entwicklung der OSM-Daten wird für die ausgewählte Objektklasse extrahiert und ab 2008 in monatlichen Intervallen aggregiert.
2) Die kumulative Zeitreihe der kartierten Objekte wird mithilfe eines nichtlinearen Regressionsansatzes mit verschiedenen logistischen Wachstumsmodellen angepasst.
3) Das am besten passende Modell wird anhand statistischer Fehlerkriterien ausgewählt.
4) Die Asymptote des angepassten Modells wird verwendet, um die maximale Anzahl kartierbarer Objekte zu approximieren, und die Vollständigkeit wird als Integral der tatsächlichen OSM-Daten zur angepassten Sättigungskurve über die letzten 3 Jahre berechnet und auf einen Wertebereich von
0 bis 1 normalisiert.

Daraus ergeben sich drei Qualitätsstufen: 

- Nicht gesättigt (<0.3)
- Laufende Kartierung (0.3 - 0.97)
- Hohe Sättigung (> 0.97)

Die Ergebnis-Kurve der Mapping-Sättigung kann schwierig zu interpretieren sein. Wie aussagekräftig der Ergebniswert ist, hängt auch von der Form der Sättigungskurve ab.

## Beispiel

Hier siehst du ein Beispiel für eine klassische „gute“ Sättigungskurve. Über die Jahre wurden immer mehr Daten hinzugefügt. Im Zeitraum von 2008 bis 2010 wurde in kurzer Zeit die größte Länge kartiert. Danach wurde im Laufe der Zeit langsam weniger Länge hinzugefügt, jedoch ist weiterhin eine kontinuierliche Kartierung erkennbar.

![mapping_sat](../../../images/mapping_sat_ansbach.png)


In diesem Beispiel siehst du eine anders geformte Sättigungskurve. Die Daten wurden nicht kontinuierlich und allmählich bis zur Sättigung hinzugefügt, sondern in wiederkehrenden Schüben, was zu dieser treppenartigen Form führt.
![mapping_sat](../../../images/mapping_sat_tunesien.png)

## Einschränkungen
Die Aussagekraft variiert je nach Thema: Sie funktioniert besser für kleine, diskrete Objekte (z. B. Häuser), aber schlechter für große Polygone (z. B. Landnutzung), bei denen ein einzelner abrupter Kartierungsschritt zu einer geringen Vollständigkeit führen kann.

## Referenzen

- Gröchenig S et al. (2014): Digging into the history of VGI data-sets: results from a worldwide study on OpenStreetMap mapping activity (https://doi.org/10.1080/17489725.2014.978403)
- Barrington-Leigh C and Millard-Ball A (2017): The world’s user-generated road map is more than 80% complete (https://doi.org/10.1371/journal.pone.0180698 pmid:28797037)
- Josephine Brückner, Moritz Schott, Alexander Zipf, and Sven Lautenbach (2021): Assessing shop completeness in OpenStreetMap for two federal states in Germany (https://doi.org/10.5194/agile-giss-2-20-2021)


```python

```
