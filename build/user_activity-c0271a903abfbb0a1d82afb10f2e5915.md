# Nutzeraktivität

Dieser Indikator berechnet, wie viele einzigartige Nutzer zu einem bestimmten Thema beigetragen haben, gruppiert nach Monaten.

:::{attention}
Dies ist kein Qualitätsindikator. Eine Abschätzung der Qualität erfolgt hier nicht, daher wird auch kein Qualitätslabel gegeben. Die Informationen können dennoch nützlich sein, allerdings hängt die Aussagekraft vom Anwendungsfall ab.
:::

### Methoden und Daten
`Intrinsische Methode`

Die monatliche Anzahl einzigartiger Nutzer, die ein bestimmtes Thema im Interessensgebiet bearbeitet haben, wird für den gesamten Zeitraum von OSM ermittelt.
Zusätzlich wird der Median für die letzten 3 Jahre berechnet sowie eine Regressionslinie erstellt, um die aktuelle Entwicklung der Nutzeraktivität zu erkennen.

Die Nutzeraktivität bewertet das Engagement der Beitragenden innerhalb des Untersuchungsgebiets und liefert keine direkten Informationen zur Datenqualität.
In Kombination mit anderen Indikatoren sowie durch die Betrachtung absoluter Werte und von Regressionstrends lassen sich jedoch Rückschlüsse auf die Nachhaltigkeit der OSM-Community ziehen.

## Beispiel
Dieser Indikator liefert zwar keine direkte Auskunft über die Datenqualität von OSM-Daten, aber man kann mit ihm dennoch Rückschlüsse auf die OSM-Daten schließen.

<div>
<img src="../abbildungen/Nutzeraktivität_Heidelberg.png" width="600"/>
</div>

Die obere Grafik der Nutzeraktivität in Heidelberg zum Thema _Straßen(Autos)_ zeigt beispielsweise, dass die Nutzeraktivität der letzten Jahre recht Stabil bei ca. 20 liegt und in den letzten 10 Jahren leicht gestiegen ist.

Bei einer ähnlich großen Region im Odenwald (untere Grafik) liegt die Nutzeraktivität deutlich niedriger bei nur ca. 3 monatlichen Nutzern. Auch hier ist diese Zahl kein deutliches Zeichen für die Datenqualität. Bei geringeren Nutzerzahlen werden allerdings die Kartierungspräferenzen einzelner Nutzer deutlich relevanter, also beispielsweise wie viele semantische Attribute hinzugefügt werden.
Außerdem kann dieser Indikator genutzt werden, um Kartierungs-Aktivitäten verschiedener Regionen und Themen zu vergleichen.

<div>
<img src="../abbildungen/Nutzeraktivität_ländliche_Region.png" width="600"/>
</div>



```python

```
