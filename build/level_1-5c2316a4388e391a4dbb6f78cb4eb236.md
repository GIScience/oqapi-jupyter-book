# Level 1 - Straßennetzwerk

In dieser Aufgaben werden wir die Qualität von OSM Daten bezüglich der Straßenverkehrsinfrastruktur untersuchen.
Wählt hierfür im ohsome Dashboard zunächst eine beliebige Region in Deutschland aus, für die ihr die Analyse durchführen wollt.

Nun müsst ihr herausfinden, welche *Themen* im ohsome Dashboard OSM-Daten für Straßeninfrastruktur beinhalten.
Schaut hierfür durch die [Themendefinitionen](../topics.md).
Relevante Themen sind z.B.: Straßen (alle highways), Straßen (Autos), Brücken (alle Wege), Brücken (Autos) und Brücken (Anzahl)

Für die meisten Anwendungsfälle sind die vordefinierten Themen ausreichend und ihre Benennung ist klar.
Dennoch ist es wichtig bei der Themenauswahl zu verstehen, welche Objektarten bzw. in unserem Fall welche
Straßentypen durch die vorgegebene Definition ausgewählt werden.
Gegegenenfalls muss die Definition dann für die eigenen Anforderungen angepasst werden.

## Thema: Straßen (Autos)

Zunächst wollen wir nun ein generelles Verständnis über die OSM-Tags erlangen, die beim Kartieren von Straßenverkehrsinfrastruktur genutzt werden.
Hierfür kann z.B. die [OSM Map Features Wikiseite](https://wiki.openstreetmap.org/) genutzt werden.
Die *Map Features* beschreiben alle grundlegenden OSM-Objektarten und welche zusätzlichen Attribute in der Regel genutzt werden.

:::{admonition} Aufgabe
:class: tip
Nutze das OSM Wiki und beschreibe, welche Straßentypen durch das Thema *Straßen (Autos)* im ohsome Dashboard abgedeckt werden.
:::

:::{dropdown} Lösung
Für Straßen wird in OSM der Schlüssel *highway* genutzt. Mehr Informationen findest du [hier](https://wiki.openstreetmap.org/wiki/Key:highway).
Eine genauere Auswahl von entsprechenden Werten, die für den Straßenverkehr genutzt werden, können [hier](https://wiki.openstreetmap.org/wiki/Highways#Roads_and_tracks) gefunden werden.
Das Thema *Straßen (Autos)* umfasst Autobahnen, Bundesstraßen, Landes- und Kreisstraßen und Straßen in Wohngebieten sowie die zugehörigen Anschlussstraßen bzw. Zubringer.
:::

Für die Verteilung von OSM-Werten zu den OSM-Schlüsseln ist [Taginfo](https://taginfo.openstreetmap.org/) eine sehr hilfreiche Quelle.
Taginfo gibt eine gute Übersicht, welche OSM-Tags tatsächlich wie häufig genutzt werden.

:::{admonition} Aufgabe
:class: tip
Nutze Taginfo und finde Beispiele, welche weiteren häufigen Straßentypen nicht im Thema *Straßen (Autos)* inbegriffen sind.
:::

:::{dropdown} Lösung
Wie die einzelnen Highway-Tags in OSM verteilt sind, kann über [Taginfo](https://taginfo.openstreetmap.org/keys/highway#overview) untersucht werden.
Die Auflistung der häufigsten Tag-Values in Taginfo zeigt, dass z.B. Erschließungsstraßen (`highway=service`) und Wirtschafts- und Feldwege (`highway=track`)nicht von unserem Thema *Straßen (Autos)* betrachtet werden.
:::

## Thema: Brücken (Autos)

Des Weiteren sind Brücken relevant für den Straßenverkehr.
Wie diese in OSM gemappt werden, kann [hier](https://wiki.openstreetmap.org/wiki/Key:bridge) nachgelesen werden.
Auch hier können mehr Informationen über die Verteilung in OSM auf [Taginfo](https://taginfo.openstreetmap.org/keys/bridge) untersucht werden.

Diesmal interessieren wir uns für die zusätzlichen Attribute, die genutzt werden um Brücken im Detail zu beschreiben.
Auch diese Informationen zu sinnvollen OSM-Tag Kombinationen finden sich im OSM Wiki und in Taginfo.

:::{admonition} Aufgabe
:class: tip
Nenne die vier häufigsten OSM-Tags, welche zur Beschreibung von Brückeneigenschaften genutzt werden.
Nutze Taginfo für deine Recherche.
:::

:::{dropdown} Lösung
In Taginfo werden die [sinnvollen Kombinationen](https://taginfo.openstreetmap.org/keys/bridge#combinations) der Häufigkeit nach aufgelistet.
Brücken (insgesamt 7,2 Millionen Elemente) werden in OSM häufig mit diesen weiteren Tags beschrieben:
* `layer`: ~6,7 Millionen Elemente
* `highway`: ~6,5 Millionen Elemente
* `name`: ~2,5 Millionen Elemente
* `surface`: ~2,2 Millionen Elemente
:::

## Auswahl der Qualitätsindikatoren

Für die verschiedenen Themen stehen unterschiedliche Indikatoren zur Auswahl.
Diese können entweder in den [Themendefinitionen](../topics.md)
oder im Dashboard im Themenkatalog.

:::{admonition} Aufgabe
:class: tip
Finde heraus, welche Datenqualitätsindikatoren für die Themen *Straßen (Autos)* und *Brücken (Autos)* verfügbar sind.
:::

:::{dropdown} Lösung
**Straßen (Autos)**
  - Kartierungssättigung
  - Attributvollständigkeit
  - Aktualität
  - Nutzeraktivität
  - Thematische Genauigkeit (Straßen) 

**Brücken (Autos)**
  - Kartierungssättigung
  - Attributvollständigkeit
  - Aktualität
  - Nutzeraktivität
:::

:::{note}
In dieser Aufgabe fokussieren wir uns auf die Indikatoren *Kartierungssättigung*, *Aktualität* und *Attributvollständigkeit*.
:::

## Durchführung der Analyse im ohsome Dashboard

Berechne zunächst für das Thema *Straßen (Autos)* die Kartierungssättigung und die Aktualität für deine anfangs gewählte Region.
Im zweiten Schritt kannst du für die gleiche Region das Thema anpassen zu *Radwege* und die gleichen Indikatoren verwenden.

Im nächsten Schritt weiten wir die Analyse auf die Attributvollständigkeit aus.
Wir wollen die Attribute *Straßenname* und *Oberfläche* untersuchen.

:::{admonition} Aufgabe
:class: tip
Vergleiche die Ergebnisse der Berechnungen.
Wie können die Unterschiede erklärt werden?
:::

:::{dropdown} Lösung

Straßen und Radwege:
* [Ergebnisse für Straßen in Heidelberg](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=roads&adminids=-285864&indicators=mapping-saturation%2Ccurrentness): hohe Aktualität und gleichzeitig hohe Vollständigkeit
* [Ergebnisse für Radwege in Heidelberg](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=cycleway&adminids=-285864&indicators=mapping-saturation%2Ccurrentness): hohe Aktualität aber momentan noch nicht vollständig in OSM kartiert.
* Erklärung: Der Fokus der OSM Community hat sich anfangs auf Kartieren von Straßen gelegt, erst später wurden zunehmend Radwege eingetragen. Dieser Prozess hält bis heute an.

Straßenname und Oberfläche:
* Ergebnisse für Straßen in Heidelberg: [67% Straßenname](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=roads&attribute-completeness--attributes=name&adminids=-285864&indicators=attribute-completeness) und [83% Oberfläche](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=roads&attribute-completeness--attributes=surface&adminids=-285864&indicators=attribute-completeness) 
* Ergebnisse für Radwege in Heidelberg: [46% Straßenname](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=cycleway&attribute-completeness--attribute-title=Name&attribute-completeness--attribute-filter=name%3D*&adminids=-285864&indicators=attribute-completeness) und [99% Oberfläche](https://next.ohsome-dashboard.heigit.org/de/#backend=oqtApi&topic=cycleway&attribute-completeness--attribute-title=Oberfl%C3%A4che&attribute-completeness--attribute-filter=surface%3D*&adminids=-285864&indicators=attribute-completeness)
* Erklärung: Erwarungsgemäß haben die meisten Radwege keinen Namen. Gleichzeitig sind die Radwege in Heidelberg hinsichtlich des Oberflächenbelags nahezu perfekt kartiert.
:::

:::{note}
Wenn du für deine Analyse flexibler mit OSM-Filtern arbeiten möchtest, schaue dir die Aufgabe in [Level 2](level_2.md) an.
:::
