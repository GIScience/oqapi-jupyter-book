# Anwendungsbeispiele


## Routing und Navigation
OSM-Daten sind die Grundlage für viele Routinganwendungen, z.B. für den [openrouteservice](https://maps.openrouteservice.org/#/).
Der Verlauf der berechneten Routen und die angegebene Fahrzeit hängt auch von der Verfügbarkeit und Qualität der Straßendaten ab.
OSM-Tags wie `highway` oder `maxspeed`, bestimmen dabei ob eine Straße für Autos, Radfahrer oder Fußgänger "befahrbar" ist und welche Geschwindigkeit angenommen werden kann.
Mit Datenqualitätsindikatoren, z.B. *Straßenvergleich* oder *Attributvollständigkeit*, können wir mehr über die Zuverlässigkeit der OSM-Daten herausfinden.

:::{margin} Vortrag auf der FOSSGIS-Konferenz 2026
[OpenStreetMap-Daten als Grundlage für Routing – wie gut funktioniert das wirklich?](https://media.ccc.de/v/fossgis2026-84139-openstreetmap-daten-als-grundlage-fur-routing-wie-gut-funktioniert-das-wirklich/playlist)
:::

<img src="../abbildungen/beispiel_ors_indien.png"/>

:::{margin} Attributvollständigkeit
Für den Großteil der Strecke zwischen Mumbai und Hyderabat ist der Oberflächenbelag der Straße in OSM nicht kartiert.
Dies beeinflusst die angegebene Fahrzeit.
:::

## Katastropenschutz
Im Katastrophenschutz können OSM-Daten eine Quelle für aktuelle Lageinformationen sein.
In Kombination mit weiteren Daten-Layern, z.B. Hochwassermasken von [Copernicus EMS](https://emergency.copernicus.eu/), ist es möglich schnell eine erste Abschätzung zur Anzahl von betroffenen Gebäuden oder Menschen zu erstellen.

Nach der Flut im Ahrtal im Juli 2021 haben wir OSM Gebäude mit Hochwasserflächen und Zensusdaten kombiniert um ein erstes Lagebild für das Deutsche Rote Kreuz zu erstellen. 
Zusätzlich haben wir Landnutzungsinformationen aus OSM genutzt, um Wohngebäude und Nicht-Wohngebäude zu unterscheiden.


<img src="../abbildungen/beispiel_ahrtal.png" width="400"/>

:::{margin} Vollständigkeit
Für die Analyse war es wichtig, die Vollständigkeit der OSM-Daten zu berücksichtigen.
Im Untersuchungsgebiet war die gemessene Vollständigkeit der Gebäude in OSM sehr hoch.
:::


## Landnutzung


* Beispiel aus LaVerDi
* OSM Daten als Grundlage um Änderungen der Landnutzung in Deutschland zu verstehen


:::{margin} Aktualität
Wie gut sind aktuelle Änderungen der Landnutzung in OSM erfasst?
:::


## Übersichtskarten
* große Straßen und POIs sind hier relevant


Anwendungsbeispiele:

* [Weitere Blogbeiträge zu OQAPI](https://heigit.org/tag/ohsome-quality-api-de/)