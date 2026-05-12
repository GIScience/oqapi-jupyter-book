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
Für das BKG LaVerDi Projekt nutzen wir OSM Daten um Änderungen der Landnutzung in Deutschland besser zu verstehen.
Änderungen in OSM können dabei einen ersten Hinweis geben, an welchen Orten in der "realen" Welt Landnutzungsänderungen aufgetreten sind.
Dennoch sind OSM Änderungen immer zeitlich verzögert, da es schlicht eine gewisse Zeit braucht bis Mapper eine Änderung erkennen und eintragen.


<img src="../abbildungen/landcover_quality_overview_maps.png" width="600"/>

:::{margin} Aktualität
Wir haben unterschiedliche Dimensionen der Datenqualität gemessen.
Unter anderen messen wir die Aktualität, die angibt wie gut sind aktuelle Änderungen der Landnutzung in OSM erfasst sind.
:::


## Übersichtskarten
In vielen Anwendungen wird OSM als Hintergrundkarte oder für Übersichtskarten genutzt.
Bei diesen Darstellungen sind oft mehrere Layer relevant, z.B. das Straßennetz, Gewässer und die größten Städte.
Für diese Anwendungen ist es sinnvoll schnell einen großflächigen Überblick zu bekommen über Vollständigkeit oder Aktuatlität.

<img src="../abbildungen/hdx_country_report.png"/>

:::{margin} Straßenvergleich
Wenn externe Straßdendaten verfügbar sind, dann können wir beide Datensätze vergleichen.
Für den Road Comparison Indikator vergleichen wir OSM-Daten und Microsoft Roads.
:::


## Weitere Anwendungsbeispiele:
* [Weitere Blogbeiträge zu OQAPI](https://heigit.org/tag/ohsome-quality-api-de/)