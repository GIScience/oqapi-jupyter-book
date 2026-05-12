#%% md
# Level 1 - Nutzung der vordefinierten Themen

In dieser Aufgaben wollen wir Infrastruktur für den Straßenverkehr untersuchen. Wählt hierfür zunächst eine Region, für die ihr die Analyse durchführen wollt. 

### Recherche der relevanten OSM-Tags

Zunächst sollte ein generelles Verständnis über die OSM-Schlüssel, die relevant für Straßeninfrastruktur sind. Hierfür kann 
z.B. die offizielle [Wikiseite von OSM](https://wiki.openstreetmap.org/) genutzt werden. Für die Verteilung von OSM-Werten
zu den OSM-Schlüsseln ist [Taginfo](https://taginfo.openstreetmap.org/) eine sehr hilfreiche Quelle. Versuche nun
sinnvolle OSM-Schlüssel-Wert-Paare zu finden, die für den Straßenverkehr genutzt werden.

:::{info}
Für die meisten Anwendungsfälle sind die vordefinierten Themen ausreichend und ihre Benennung ist klar. Daher kann dieser
Schritt in der Regel übersprungen werden und direkt mit der *Themenauswahl* gestartet werden.
:::


:::{dropdown} Lösung

Für Straßen wird in OSM der Schlüssel *highway* genutzt. Mehr Informationen findest du [hier](https://wiki.openstreetmap.org/wiki/Key:highway).
Eine genauere Auswahl von entsprechenden Werten, die für den Straßenverkehr genutzt werden, können [hier](https://wiki.openstreetmap.org/wiki/Highways#Roads_and_tracks)
gefunden werden. Wie die einzelnen Schlüssel in OSM verteilt sind, kann über [Taginfo](https://taginfo.openstreetmap.org/keys/highway#overview) untersucht werden.

Des Weiteren sind Brücken relevant für den Straßenverkehr. Wie diese in OSM gemappt werden, kann [hier](https://wiki.openstreetmap.org/wiki/Key:bridge)
nachgelesen werden. Auch hier können mehr Informationen über die Verteilung in OSM auf [Taginfo](https://taginfo.openstreetmap.org/keys/bridge)
untersucht werden.


:::

### Themenauswahl

Nun müsst ihr herausfinden, welche Themen OSM-Daten für Straßeninfrastruktur beinhalten. Schaut hierfür durch die [Themendefinitionen](../topics.md).

:::{dropdown} Lösung
Relevante Themen sind z.B.: Straßen (alle highways), Straßen (Autos), Brücken (alle Wege), Brücken (Autos) und Brücken (Anzahl)
:::

### Indikatorenauswahl

Für die verschiedenen Themen stehen unterschiedliche Indikatoren zur Auswahl. Diese können entweder in den [Themendefinitionen](../topics.md)
oder im Dashboard im Themenkatalog. Finde heraus, welche Indikatoren für die von dir ausgewählten Themen verfügbar sind. 

:::{dropdown} Lösung
**Straßen (alle highways)**
  - Kartierungssättigung
  - Straßenvergleich
  - Attributvollständigkeit
  - Aktualität
  - Nutzeraktivität 

**Straßen (Autos)**
  - Kartierungssättigung
  - Attributvollständigkeit
  - Aktualität
  - Nutzeraktivität
  - Thematische Genauigkeit (Straßen) 

**Brücken (alle Wege)**
  - Kartierungssättigung
  - Aktualität
  - Nutzeraktivität  

**Brücken (Autos)**
  - Kartierungssättigung
  - Aktualität
  - Nutzeraktivität  

**Brücken (Anzahl)**
  - Kartierungssättigung
  - Aktualität
  - Nutzeraktivität
:::

:::{info}
In dieser Aufgabe fokussieren wir uns auf die Indikatoren *Kartierungssättigung*, *Aktualität* und *Attributvollständigkeit*.
:::

### Durchführung der Analyse

Berechne sowohl für das Thema Straßen (alle highways) als auch für Straßen (Autos) die Kartierungssättigung und die Aktualität.
Was sind hier die Unterschiede? Für die Attributvollständigkeit versuche verschiedene Attribute aus und kombiniere diese auch mal.
Was kann festgestellt werden? Probiere auch die Themen für Brücken aus. Beachte, dass hier keine Attributvollständigkeit
berechnet werden kann.

:::{info}
Wenn du für deine Analyse flexibler mit OSM-Filtern arbeiten möchtest, schaue dir die Aufgabe in [Level 2](level_2.md) an 
:::
