# ohsome quality API

An indicator estimates data quality for OpenStreetMap (OSM). It takes an area of interest in form of a GeoJSON Feature and a Topic object describing the set of OSM features as input.

- Qualitätsdimensionen erklären
- Einführung ins Dashboard
- Screenshots
- Eingabeparameter erklären
- Indikatoren und Topics erklären
- Bilder ausm Dashboard für die indikatoren diagramme mit erklärung
- 



## Limitations
- Timeout=600
- Too many queries can lead to timeout error -> reduce max workers
- The speed of the query depends on the number of total users in the moment. If a query does not work, sometimes it helps to try to a later point in time.