# Attribute Completeness

The Attribute Completeness indicator shows how detailed and completely additional attributes,
e.g. street name or speed limit, are mapped in your area of interest. For this indicator, you
choose an attribute to investigate from the dropdown menu.

:::{margin}
<img src="../../abbildungen/attributvollständigkeit.png" width="250"/>
</div>
:::

Depending on the *topic*, you can choose from a different set of attributes. If you select more
than one attribute in a single query, the results are combined, and the result figure shows the
percentage of all features that have all the selected attributes.

:::{dropdown} **Defining custom attributes**
You can also define several attributes, or attributes of your own.
:::

## Result
You'll find the results of the query in the result log below.
The green, yellow or red banner in the top left shows the attribute completeness level.

<img src="../../abbildungen/attributvollständigkeit_frankfurt.png" width="700"/>

## Methods and Data
`Intrinsic approach`

Calculates the percentage of features that hold a given attribute.
For point geometries, the total number of features is compared with the number of features that
have the selected attributes.
If the OSM feature under investigation is a line, the ratio is calculated based on length in km.
For polygons, we use the area in km².

There are three quality categories:
- low completeness < 25%
- medium completeness 25% - 75%
- high completeness > 75%

The thresholds for the quality categories were set by looking at many areas and attributes, and
shouldn't be understood as an objective metric.

:::{margin} Limitations
1. Some attributes in OpenStreetMap are implied by the presence of other attributes. For example,
   the speed limit within a living street is typically not explicitly mapped, since it can be
   derived from the road type. These implicit attributes aren't currently taken into account.
2. The threshold used to assess completeness is the same for every attribute, even though the
   appropriate threshold really depends on the use case.
:::

## Examples

In the following example, we can see how important it is to choose the right topic. We want to
find out the attribute completeness of street names for Frankfurt city centre.

In this figure, we see the result for the topic _Roads (all highways)_. Just under 40% is a medium
level of completeness, and a surprising result for a large German city. At this point we should
notice that something might not be quite right. The topic _Roads (all highways)_ doesn't just
include roads usable by cars, but every path used for motorised traffic as well as cycleways and
footways. Since many cycleways and footways don't have an explicit name, the query result comes
out at just under 40%.

<div>
<img src="../../abbildungen/attributvollständigkeit_frankfurt.png"/>
</div>

If we're only interested in the street names of roads used by motorised traffic, we should choose
the topic _Roads (cars)_ instead. In the next figure, we see that for the same area of interest we
now get a high level of completeness.

<div>
<img src="../../abbildungen/attributvollständigkeit_frankfurt_autos.png" width="700"/>
</div>
