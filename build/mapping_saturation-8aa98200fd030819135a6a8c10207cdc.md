# Kartierungssättigung

Der Kartierungssättigung-Indikator liefert ein Maß für die Vollständigkeit.
Es wird analysiert, wie sich das Wachstum kartierter Objekte in OSM im Laufe der Zeit einem natürlichen Maximum annähert.

## Ergebnis

![mapping_sat](../../abbildungen/mapping_sat_ansbach.png)

## Methodik
`Intrinsischer Ansatz`

Die zentrale Annahme der Kartierungsättigung ist, dass jedes Objekt in der Realität eine endliche Ausdehnung hat. Mit zunehmender Kartierungsaktivität nimmt die Anzahl bzw. Länge neu hinzugefügter Objekte pro Zeitschritt ab, und die kumulative Wachstumskurve sättigt sich allmählich in Richtung des tatsächlichen Werts.
Um dieses Sättigungsniveau zu schätzen, nutzen wir die historische Entwicklung der OSM-Beiträge und passen nichtlineare Regressionsmodelle an die kumulative Wachstumskurve an. Der Workflow für den Kartierungssättigung-Indikator besteht aus vier Hauptschritten.

1) Die zeitliche Entwicklung der OSM-Daten wird für die ausgewählte Objektklasse extrahiert und ab 2008 in monatlichen Intervallen aggregiert.
2) Die kumulative Zeitreihe der kartierten Objekte wird mithilfe eines nichtlinearen Regressionsansatzes mit verschiedenen logistischen Wachstumsmodellen angepasst.
3) Das am besten passende Modell wird anhand statistischer Fehlerkriterien ausgewählt.
4) Die Asymptote des angepassten Modells wird verwendet, um die maximale Anzahl kartierbarer Objekte zu approximieren, und die Vollständigkeit wird als Integral der tatsächlichen OSM-Daten zur angepassten Sättigungskurve über die letzten 3 Jahre berechnet und auf einen Wertebereich von
0 bis 1 normalisiert.

:::{margin} Limitationen
Die Ergebniskurve der Mapping-Sättigung kann schwierig zu interpretieren sein. Wie aussagekräftig der Ergebniswert ist, hängt auch von der Form der Sättigungskurve ab.

Die Aussagekraft variiert je nach Thema: Sie funktioniert besser für kleine, diskrete Objekte (z. B. Häuser), aber schlechter für große Polygone (z. B. Landnutzung), bei denen ein einzelner abrupter Kartierungsschritt zu einer geringen Vollständigkeit führen kann.
:::

Daraus ergeben sich drei Qualitätsstufen: 

- Nicht gesättigt (<0.3)
- Laufende Kartierung (0.3 - 0.97)
- Hohe Sättigung (> 0.97)


## Beispiele

Ein gutes Beispiel für den erwarteten Kartierungsverlauf kann in diesem Beispiel gesehen werden. 
Hier wurden _Straßen (alle highways)_ in Ansbach untersucht.
Über die Jahre wurden immer mehr Daten hinzugefügt. Im Zeitraum von 2008 bis 2010 wurde in kurzer Zeit eine große Anzahl an
Straßenlänge kartiert. 
Danach wurde im Laufe der Zeit langsam weniger neue Straßenlänge hinzugefügt, 
jedoch ist weiterhin eine kontinuierliche Kartierung erkennbar, die sich aber einer Sättigung annähert. Es kann davon 
ausgegangen werden, dass die Kartierung von Straßen in Ansbach abgeschlossen ist und nur noch kleinere Korrekturen durchgeführt werden.

<div>
<img src="../../abbildungen/mapping_sat_ansbach.png" width="700"/>
</div>

In untenstehendem Beispiel wurde die Kartierungssättigung für _Straßen (Autos)_ für eine Region in Tunesien berechnet. 
Hier siehst du eine anders geformte Sättigungskurve. Die Daten wurden nicht kontinuierlich und allmählich bis zur Sättigung 
hinzugefügt, sondern in einzelnen Schüben, was zu einer treppenartigen Form führt. Diese Schübe können unterschiedliche 
Ursachen haben: Es könnte sich um tatsächliche Neubauten von Straßen handeln; wahrscheinlicher ist allerdings, dass es 
sich hierbei um einzelne Kartierungsevents handelt, die in einem kurzen Zeitraum große Mengen neuer Straßen kartiert haben.
Ob nun noch einige Straßen fehlen bis das Gebiet vollständig kartiert ist oder bereits alle Straßen durch diese Schübe 
abgedeckt wurden, lässt sich anhand der Daten nicht feststellen. Die Richtigkeit der Qualitätseinschätzung kann deshalb nicht 
eindeutig bestätigt werden.

<div>
<img src="../../abbildungen/mapping_sat_tunesia.png" width="700"/>
</div>

Dass die Qualitätseinschätzung als laufende Kartierung korrekt ist, kann anhand folgenden Beispiels erkannt werden. 
Untersucht wurden Bäume (_Nutzerdefiniertes Thema_) in Dossenheim. Auch hier lässt sich ein stufenweiser Datenanstieg
feststellen. Hier allerdings in deutlich kürzeren Abständen. Auch wurden erst kürzlich große Mengen neuer Bäume hinzugefügt.
Die von der Sättigungskurve angenommene maximale Anzahl an Bäumen wurde dadurch bereits erreicht. Es kann davon ausgegangen
werden, dass hier der Kartierungsprozess noch am Laufen ist und die Qualitätseinschätzung des Indikators nicht korrekt ist.

<div>
<img src="../../abbildungen/mapping_sat_dossenheim.png" width="700"/>
</div>


## Referenzen
- Gröchenig S et al. (2014): Digging into the history of VGI data-sets: results from a worldwide study on OpenStreetMap mapping activity [https://doi.org/10.1080/17489725.2014.978403](https://doi.org/10.1080/17489725.2014.978403)
- Barrington-Leigh C and Millard-Ball A (2017): The world’s user-generated road map is more than 80% complete [https://doi.org/10.1371/journal.pone.0180698](https://doi.org/10.1371/journal.pone.0180698)
- Josephine Brückner, Moritz Schott, Alexander Zipf, and Sven Lautenbach (2021): Assessing shop completeness in OpenStreetMap for two federal states in Germany [Brückner et al. (2021)](https://doi.org/10.5194/agile-giss-2-20-2021)
