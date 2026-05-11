# Thematische Genauigkeit (Straßen)

Die thematische Genauigkeit von Straßen zeigt die Übereinstimmung straßenspezifischer Attribute zwischen OSM-Daten und Daten aus dem Basis-DLM.

:::{note}
Bei diesem Indikator muss zusätzlich zum Thema auch ein Attribut gewählt werden, das untersucht werden soll. Dafür erscheint unter der Auswahl des Indikators ein Feld für die Attributauswahl (siehe Abbildung). Der Indikator kann entweder für ein einzelnes Attribut oder alle Attribute auf einmal berechnet werden. Für letzteres muss das Feld leer gelassen werden.

<div>
<img src="../../abbildungen/attributauswahl_thematisch_straßen.png" width="300"/>
</div>
:::


:::{attention}
Dies ist kein Qualitätsindikator. Eine Abschätzung der Qualität erfolgt hier nicht, daher wird auch kein Qualitätslabel gegeben. Die Informationen können dennoch nützlich sein, allerdings hängt die Aussagekraft vom Anwendungsfall ab.
:::

:::{attention}
Dieser Indikator ist nur für das Thema _Straßen (Autos)_ verfügbar.
:::

## Methoden und Daten
`Extrinsischer Ansatz`

Dieser Indikator ist nicht dafür gedacht, die Qualität der OSM-Daten zu bewerten. Er zeigt die Übereinstimmung zwischen OSM und einem Referenzdatensatz, ohne davon auszugehen, dass einer der Datensätze dem anderen überlegen ist.

Der Indikator ist nur für das Thema Straßen(Autos) und innerhalb der Grenzen Deutschlands verfügbar. 

Du kannst pro Abfrage ein Attribut auswählen.

OSM-Straßen und DLM-Straßen werden mithilfe von [map-matching-2](https://github.com/addy90/map-matching-2) unter Verwendung eines auf einem Markov-Entscheidungsprozess basierenden Modells abgeglichen.
Dadurch wird jedem DLM-Straßensegment keine, eine oder mehrere OSM-Straßensegmente zugeordnet. Falls kein OSM-Straßensegment zugewiesen werden konnte, wird das DLM-Straßensegment nicht weiter in der Kalkulation berücksichtigt. In der Ergebnisbeschreibung wird angegeben, wie viel Prozent der gesamten DLM-Straßenlänge zugwiesen werden konnte. Konnte genau ein OSM-Straßensegment dem DLM-Straßensegment zugewiesen werden, wird die gesamte Länge des DLM-Straßensegment entsprechend des untenstehenden Attributvergleichs in das Ergebnis übernommen. Wird einem DLM-Straßensegment mehrere OSM-Straßensegmente zugewiesen, wird die Länge des DLM-Straßensegment durch die Anzahl an zugewiesenen OSM-Straßensegmenten geteilt. Die so entstehende Länge wird dann entsprechend des untenstehenden Attributvergleichs für jedes OSM-Straßensegment in das Ergebnis übernommen.
Für die abgeglichenen Straßen wird zunächst überprüft, ob jedes Attribut in beiden Datensätzen vorhanden ist. Falls dies der Fall ist,
werden die Werte verglichen. Standardmäßig erfolgt der Vergleich direkt, es gibt jedoch einige Ausnahmen:

#### Name

Für den Namen wurde die [Lhevenstein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) berechnet, womit die Ähnlichkeit der beiden Namen abgeglichen werden kann. Die Namen
wurden als übereinstimmend gezählt, wenn ihr Levenshtein-Verhältnis über 0,85 lag.

#### Oberflächenmaterial

Für die Oberfläche werden OSM-Tags (Kennzeichnungen) und DLM-Tags abgeglichen. Alle OSM-Tags, die nicht in der folgenden Tabelle enthalten sind, werden als nicht übereinstimmend gewertet.

| DLM-Wert             | OSM-Wert                                                 |
|----------------------|-----------------------------------------------------------|
| Beton                | concrete                                                  |
| Bitumen, Asphalt     | asphalt                                                   |
| Pflaster             | paving_stones, sett, brick, cobblestone, unhewn_cobblestone |
| Gestein, zerkleinert | fine_gravel, gravel, sand, compacted, pebblestone         |

#### Fahrbahnbreite

Für die Breite wurde eine Toleranz von 1 m angewendet.

#### Einbahnstraße

Zur Überprüfung der Fahrtrichtung wird der Vektor beider Geometrien berechnet. Haben beide das gleiche Vorzeichen, wird dies als Übereinstimmung gewertet.


### Referenzdatensatz

Das Basis-DLM wird vom Bundesamt für Kartographie und Geodäsie veröffentlicht und beschreibt die topographischen
Objekte der Landschaft sowie das Relief der Erdoberfläche im Vektorformat. Die Objekte werden durch ihre räumliche
Lage, ihren geometrischen Typ, beschreibende Attribute und Beziehungen zu anderen Objekten definiert. Jedes Objekt besitzt eine eindeutige 
Identifikationsnummer innerhalb Deutschlands. Die Straßen aus diesem Datensatz werden für diesen Indikator verwendet.

| Attribut | OSM tags(Kennzeichnungen)  | DLM attribute | Description                                      | 
|-----------|-----------|---------------|--------------------------------------------------|
 | name      | name, ref | NAM           | Der Name oder die Referenz einer Straße.         |
 | surface   | surface   | OFM           | Das Material, aus dem die Straßenoberfläche besteht. |
 | lanes     | lanes     | FSZ           | Die Anzahl der Fahrspuren auf diesem Straßenabschnitt. |
 | width     | width     | BRF           | Die Breite der Straße.                           |
 | oneway    | oneway    | FAR           | Die Fahrtrichtung von Einbahnstraßen.            |

## Ergebnisgrafik

Die Abbildung besteht aus ein oder zwei Balkendiagrammen. Die linke Abbildung zeigt an, wie viel Straßenlänge aller Straßen des DLMs, die mit OSM-Straßen gematchten werden konnten, das gewählte Attribut vorweisen. Dabei wird unterschieden, ob das Attribut nur im DLM, nur in OSM, in beiden oder keinem von beiden vorhanden ist. Sofern es Straßen gibt, bei denen das Attribut in beiden Datensätzen vorkommt, wird zusätzlich ein weiteres Balkendiagramm auf der rechten Seite angezeigt. Dieses zeigt, bei wie viel dieser Straßenlänge, in der das Attribut in beiden Datensätzen vorkommt, dieses Attribut übereinstimmt bzw. nicht übereinstimmt. Sofern für keine Straße das Attribut in beiden Datensätzen vorhanden ist, bleibt die rechte Seite der Abbildung leer.

## Beispiel

In dieser Beispielabbildung wurde die Übereinstimmung des Straßenattributs _Name_ überprüft. 
Die blauen Balken zeigen das Vorhandensein des Attributs in jedem Datensatz (OSM und Basis-DLM).
Die violetten Balken zeigen die Übereinstimmung zwischen den beiden Datensätzen und visualisieren die ähnlichen und unterschiedlichen Attribute in Anzahl und Prozent.
In der gewählten Region existiert das Attribut _Name_ sowohl in OSM- als auch in DLM-Daten größtenteils, wobei es in OSM etwas kompletter scheint. Außerdem wird deutlich, dass das Attribut zwischen den Datensätzen eine hohe Übereinstimmung aufweist. Generell lassen sich anhand der Übereinstimmung nicht direkt Rückschlüsse auf die Datenqualität schließen. Häufige Unterschiede im Attribut _Straßenspuren_ sind beispielsweise stark durch unterschiedliche Kartierungsregeln geprägt.

<div>
<img src="../../abbildungen/Road_accuracy_name_HD.png" width="600"/>
</div>

In dieser Beispielabbildung wurde die Übereinstimmung aller Attribut überprüft.
Es ist zu sehen, dass bei fast allen Straßen nicht alle Attribute gesetzt sind. Einige Straßen aus OSM weisen alle Attribute auf. Da es keine Straßen gibt, in denen alle Attribute in beiden Datensätzen vorhanden sind, wird das rechte Balkendiagramm mit der Übereinstimmung der Attribute nicht angezeigt.
In jedem Bundesland wird mindestens ein Attribut in der Regel nicht erfasst, daher gibt es im DLM kaum bis keine Straßen, die alle Attribute aufweist, daher kann mit dieser Auswahl hauptsächlich überprüft werden, wie viele OSM-Straßen alle Attribute aufweisen.

<div>
<img src="../../abbildungen/straßen_thematisch_nicht_in_beiden.png" width="600"/>
</div>

## Limitierungen

Bekannte Limitierung sind:
* Fußgängerstraßen wurden nicht zugewiesen
* Autobahnen werden in den beiden Datensätzen unterschiedlich dargestellt. Im DLM wird jede Spur als eigene Fahrbahnachse eingetragen und die Mittellinie des gesamten Abschnitt ebenfalls als eine Fahrbahnachse. In OSM wird dies oft als eine Straße pro Fahrtrichtung kartiert. Die Anzahl an Spuren wird als Attribut hinzugefügt
* ebenfalls kann es vorkommen, dass DLm-Straßensegmente fälschlicherweise Bahntrassen zugewiesen werden, wenn sich diese zwischen zwei Fahrbahnen befindet
* durch die oben beschriebene Annahme bei mehreren zugewiesenen OSM-Straßensegmente auf ein DLM-Straßensegment wird ein Teil der Straßenlänge einer anderen OSM-Straße zugewiesen


### Referenzen

- A. Wöltche, "Open source map matching with Markov decision processes: A new method and a detailed benchmark with existing approaches", Transactions in GIS, vol. 27, no. 7, pp. 1959–1991, Oct. 2023, doi: [10.1111/tgis.13107](https://onlinelibrary.wiley.com/doi/full/10.1111/tgis.13107).



```python

```
