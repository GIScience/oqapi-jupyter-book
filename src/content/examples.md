# Application Examples


## Routing and Navigation
OSM data underpins many routing applications, such as [openrouteservice](https://maps.openrouteservice.org/#/).
The course of a calculated route and its estimated travel time also depend on the availability and
quality of the road data.
OSM tags such as `highway` or `maxspeed` determine whether a road is "usable" for cars, cyclists or
pedestrians, and what speed can be assumed.
With data quality indicators such as *Road Comparison* or *Attribute Completeness*, we can find out
more about how reliable the OSM data is.

:::{margin} Talk at the FOSSGIS conference 2026
[OpenStreetMap data as a basis for routing – how well does it really work?](https://media.ccc.de/v/fossgis2026-84139-openstreetmap-daten-als-grundlage-fur-routing-wie-gut-funktioniert-das-wirklich/playlist)
:::

<img src="../abbildungen/beispiel_ors_indien.png"/>

:::{margin} Attribute Completeness
For most of the route between Mumbai and Hyderabad, the road surface isn't mapped in OSM.
This affects the estimated travel time.
:::

## Disaster Response
In disaster response, OSM data can be a source of up-to-date situational information.
Combined with other data layers, such as flood masks from [Copernicus
EMS](https://emergency.copernicus.eu/), it's possible to quickly produce an initial estimate of the
number of buildings or people affected.

After the flood in the Ahr valley in July 2021, we combined OSM buildings with flood extent data
and census data to produce an initial situational picture for the German Red Cross.
We also used land use information from OSM to distinguish between residential and non-residential
buildings.


<img src="../abbildungen/beispiel_ahrtal.png" width="400"/>

:::{margin} Completeness
For this analysis it was important to take the completeness of the OSM data into account.
In the study area, the measured completeness of buildings in OSM was very high.
:::


## Land Use
For the BKG LaVerDi project, we use OSM data to better understand land use change in Germany.
Changes in OSM can give us an early indication of where land use changes have occurred in the
"real" world.
That said, OSM changes are always somewhat delayed, since it simply takes time for mappers to
notice a change and record it.


<img src="../abbildungen/landcover_quality_overview_maps.png" width="600"/>

:::{margin} Currentness
We measured several dimensions of data quality.
Among others, we measure currentness, which indicates how well recent land use changes are
captured in OSM.
:::


## Overview Maps
Many applications use OSM as a background map or for overview maps.
These often rely on several relevant layers, such as the road network, water bodies and the
largest cities.
For these applications, it's useful to quickly get a broad overview of completeness or currentness.

<img src="../abbildungen/hdx_country_report.png"/>

:::{margin} Road Comparison
When external road data is available, we can compare both datasets.
For the Road Comparison indicator, we compare OSM data and Microsoft Roads.
:::


## Further Application Examples:
* [More blog posts on OQAPI](https://heigit.org/tag/ohsome-quality-api/)
