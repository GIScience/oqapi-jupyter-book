# Road Thematic Accuracy

Road Thematic Accuracy shows the agreement of road-specific attributes between OSM data and data
from the Basis-DLM.

:::{note}
For this indicator, an attribute must be chosen in addition to the topic. A field for selecting
the attribute appears below the indicator selection (see figure). The indicator can be calculated
either for a single attribute or for all attributes at once. For the latter, leave the field empty.

<div>
<img src="../../abbildungen/attributauswahl_thematisch_straßen.png" width="300"/>
</div>
:::


:::{attention}
This isn't a quality indicator. No quality assessment is performed here, so no quality label is
given either. The information can still be useful, although how meaningful it is depends on the
use case.
:::

:::{attention}
This indicator is only available for the topic _Roads (cars)_.
:::

## Methods and Data
`Extrinsic approach`

This indicator isn't intended to assess the quality of the OSM data. It shows the agreement
between OSM and a reference dataset, without assuming that either dataset is superior to the
other.

The indicator is only available for the topic Roads (cars), and only within the borders of
Germany.

You can select one attribute per query.

:::{margin} Limitations
Since OpenStreetMap is continuously updated while the reference datasets are released at a
specific point in time, they're no longer as current as OpenStreetMap at the time of comparison.
:::

OSM roads and DLM roads are matched using [map-matching-2](https://github.com/addy90/map-matching-2),
using a model based on a Markov decision process.
This assigns each DLM road segment none, one, or several OSM road segments. If no OSM road segment
could be assigned, the DLM road segment is excluded from the calculation. The result description
states what percentage of the total DLM road length could be assigned. If exactly one OSM road
segment could be assigned to the DLM road segment, the entire length of the DLM road segment is
carried over into the result according to the attribute comparison described below. If several OSM
road segments are assigned to a DLM road segment, the length of the DLM road segment is divided by
the number of assigned OSM road segments. The resulting length is then carried over into the
result for each OSM road segment, according to the attribute comparison described below.
For matched roads, we first check whether each attribute is present in both datasets. If it is,
the values are compared. By default, the comparison is direct, though there are a few exceptions:

#### Name

For the name, the [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) was
calculated, which lets us compare how similar the two names are. Names were counted as matching if
their Levenshtein ratio was above 0.85.

#### Surface

For surface, OSM tags and DLM tags are matched against each other. All OSM tags not included in
the following table are counted as non-matching.

| DLM value | OSM value |
|----------------------|-----------------------------------------------------------|
| Beton                | concrete                                                  |
| Bitumen, Asphalt     | asphalt                                                   |
| Pflaster             | paving_stones, sett, brick, cobblestone, unhewn_cobblestone |
| Gestein, zerkleinert | fine_gravel, gravel, sand, compacted, pebblestone         |

#### Width

For width, a tolerance of 1 m was applied.

#### Oneway

To check the direction of travel, the vector of both geometries is calculated. If both have the
same sign, this is counted as a match.


### Reference dataset

The Basis-DLM is published by the Bundesamt für Kartographie und Geodäsie (Federal Agency for
Cartography and Geodesy) and describes the topographic features of the landscape as well as the
relief of the Earth's surface in vector format. Features are defined by their spatial location,
their geometry type, descriptive attributes, and relationships to other features. Every feature has
a unique identification number within Germany. The roads from this dataset are used for this
indicator.

| Attribute | OSM tags  | DLM attribute | Description |
|-----------|-----------|---------------|--------------------------------------------------|
| name      | name, ref | NAM           | The name or reference of a road. |
| surface   | surface   | OFM           | The material the road surface is made of. |
| lanes     | lanes     | FSZ           | The number of lanes on this road segment. |
| width     | width     | BRF           | The width of the road. |
| oneway    | oneway    | FAR           | The direction of travel for one-way roads. |

## Result

The figure consists of one or two bar charts. The chart on the left shows what proportion of the
total length of all DLM roads that could be matched to OSM roads have the selected attribute. This
distinguishes between the attribute being present only in the DLM, only in OSM, in both, or in
neither. Where there are roads for which the attribute is present in both datasets, a further bar
chart is shown on the right. This shows, for that road length where the attribute is present in
both datasets, how much of it matches or doesn't match. If the attribute isn't present in both
datasets for any road, the right-hand side of the figure remains empty.

## Example

In this example figure, agreement for the road attribute _Name_ was checked.
The blue bars show the presence of the attribute in each dataset (OSM and Basis-DLM).
The purple bars show the agreement between the two datasets, visualising the similar and differing
attributes in count and percentage.
In the selected region, the attribute _Name_ exists in both OSM and DLM data for the most part,
though it appears slightly more complete in OSM. It's also clear that the attribute shows high
agreement between the datasets. In general, agreement doesn't allow direct conclusions to be drawn
about data quality. Frequent differences in the _lanes_ attribute, for example, are strongly
shaped by differing mapping conventions.

<div>
<img src="../../abbildungen/Road_accuracy_name_HD.png" width="600"/>
</div>

In this example figure, agreement across all attributes was checked.
It's clear that for almost all roads, not all attributes are set. Some roads from OSM have all
attributes. Since there are no roads for which all attributes are present in both datasets, the
right-hand bar chart showing attribute agreement isn't displayed.
In every federal state, at least one attribute is generally not captured, so there are few to no
roads in the DLM with all attributes present. This selection can therefore mainly be used to check
how many OSM roads have all attributes.

<div>
<img src="../../abbildungen/straßen_thematisch_nicht_in_beiden.png" width="600"/>
</div>

## Limitations

Known limitations include:
* Pedestrian roads weren't assigned
* Motorways are represented differently in the two datasets. In the DLM, every lane is recorded as
  its own carriageway axis, and the centre line of the entire section is also recorded as a
  carriageway axis. In OSM, this is often mapped as one road per direction of travel, with the
  number of lanes added as an attribute.
* it can also happen that DLM road segments are incorrectly assigned to railway tracks, if these
  are located between two carriageways
* because of the assumption described above for DLM road segments with several assigned OSM road
  segments, part of the road length gets assigned to a different OSM road


### References

- A. Wöltche, "Open source map matching with Markov decision processes: A new method and a detailed benchmark with existing approaches", Transactions in GIS, vol. 27, no. 7, pp. 1959–1991, Oct. 2023, doi: [10.1111/tgis.13107](https://onlinelibrary.wiley.com/doi/full/10.1111/tgis.13107).
