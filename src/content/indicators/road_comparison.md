# Road Comparison

The Road Comparison indicator estimates the completeness of OSM road data using a reference
dataset. The result is a ratio of the length of reference roads covered by OSM roads to the total
length of the reference dataset.

:::{attention}
This indicator is only available for the topic _Roads (all highways)_.
:::

## Methods and Data
`Extrinsic method`

The indicator identifies matching road geometries in OSM and in the reference dataset in order to
calculate the ratio of matching road length in km.
The Microsoft Roads dataset is used as the reference. However, the reference dataset shouldn't be
regarded as fully correct or up to date.
The Road Comparison indicator is only available for the *topic* "Roads (all highways)".

Reference dataset:
- [Microsoft Roads](https://github.com/microsoft/RoadDetections): the Microsoft Roads dataset is a
  worldwide road dataset. A machine learning approach was used to derive roads from satellite
  imagery.

:::{margin} Limitations
Since OpenStreetMap is continuously updated while the reference dataset was released at a specific
point in time, it's no longer as current as OpenStreetMap at the time of comparison.
:::

## Result

You'll find the results of the query in the result log below.
The green, yellow or red banner in the top left shows the attribute completeness level.

The chart shows a bar chart of completeness. The grey fill indicates what percentage of the
reference roads are covered by OSM roads.

## Example

<div>
<img src="../../abbildungen/Straßenvergleich_Heidelberg.png" width="600"/>
</div>

The agreement between Microsoft Roads and OSM in Heidelberg is 96%, so we can assume a high level
of completeness for the OSM data here.

In a region of Turkey, agreement is only around two thirds. Here completeness is only medium, and
some data gaps can be assumed, although the OSM data may still be usable depending on the use case.

<div>
<img src="../../abbildungen/Straßenvergleich_Türkei.png" width="600"/>
</div>
