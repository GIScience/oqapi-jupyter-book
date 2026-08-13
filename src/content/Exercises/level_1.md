# Level 1 - Road Network

In this exercise, we'll investigate the quality of OSM data relating to road transport
infrastructure.
Start by choosing any region in Germany in the ohsome Dashboard for which you want to run the
analysis.

Now you need to work out which *topics* in the ohsome Dashboard cover OSM data for road
infrastructure.
Take a look through the [Topic Definitions](../topics.md) to find out.
Relevant topics include, for example: Roads (all highways), Roads (cars), Bridges (all ways),
Bridges (cars) and Bridges (count)

For most use cases, the predefined topics are sufficient, and their naming is clear.
Still, when choosing a topic it's important to understand which feature types - in our case, which
road types - are selected by the given definition.
If necessary, the definition then needs to be adapted to your own requirements.

## Topic: Roads (cars)

First, let's build a general understanding of the OSM tags used when mapping road transport
infrastructure.
The [OSM Map Features wiki page](https://wiki.openstreetmap.org/) is a good place to start.
*Map Features* describes all the basic OSM feature types and which additional attributes are
typically used.

:::{admonition} Task
:class: tip
Use the OSM wiki to describe which road types are covered by the topic *Roads (cars)* in the
ohsome Dashboard.
:::

:::{dropdown} Solution
OSM uses the key *highway* for roads. You can find more information [here](https://wiki.openstreetmap.org/wiki/Key:highway).
A more precise selection of the values used for road traffic can be found [here](https://wiki.openstreetmap.org/wiki/Highways#Roads_and_tracks).
The topic *Roads (cars)* covers motorways, federal roads, state and county roads, and residential
roads, along with their associated slip roads and link roads.
:::

[Taginfo](https://taginfo.openstreetmap.org/) is a very helpful resource for seeing how OSM values
are distributed across OSM keys.
Taginfo gives a good overview of which OSM tags are actually used, and how often.

:::{admonition} Task
:class: tip
Use Taginfo to find examples of other common road types that aren't included in the topic *Roads
(cars)*.
:::

:::{dropdown} Solution
How the individual highway tags are distributed in OSM can be examined via [Taginfo](https://taginfo.openstreetmap.org/keys/highway#overview).
The list of the most common tag values in Taginfo shows that, for example, service roads
(`highway=service`) and tracks (`highway=track`) aren't covered by our topic *Roads (cars)*.
:::

## Topic: Bridges (cars)

Bridges are also relevant to road traffic.
You can read up on how they're mapped in OSM [here](https://wiki.openstreetmap.org/wiki/Key:bridge).
Here too, you can investigate more information about their distribution in OSM on [Taginfo](https://taginfo.openstreetmap.org/keys/bridge).

This time we're interested in the additional attributes used to describe bridges in detail.
This information on useful OSM tag combinations can also be found in the OSM wiki and on Taginfo.

:::{admonition} Task
:class: tip
Name the four most common OSM tags used to describe bridge properties.
Use Taginfo for your research.
:::

:::{dropdown} Solution
Taginfo lists the [useful combinations](https://taginfo.openstreetmap.org/keys/bridge#combinations) in order of frequency.
Bridges (7.2 million features in total) are frequently described in OSM with these further tags:
* `layer`: ~6.7 million features
* `highway`: ~6.5 million features
* `name`: ~2.5 million features
* `surface`: ~2.2 million features
:::

## Choosing quality indicators

Different indicators are available for different topics.
You can find these either in the [Topic Definitions](../topics.md), or in the topic catalogue in
the Dashboard.

:::{admonition} Task
:class: tip
Find out which data quality indicators are available for the topics *Roads (cars)* and *Bridges
(cars)*.
:::

:::{dropdown} Solution
**Roads (cars)**
  - Mapping Saturation
  - Attribute Completeness
  - Currentness
  - User Activity
  - Road Thematic Accuracy

**Bridges (cars)**
  - Mapping Saturation
  - Attribute Completeness
  - Currentness
  - User Activity
:::

:::{note}
In this exercise, we'll focus on the *Mapping Saturation*, *Currentness* and *Attribute
Completeness* indicators.
:::

## Running the analysis in the ohsome Dashboard

First, calculate the Mapping Saturation and Currentness for the topic *Roads (cars)* for the
region you chose at the start.
In the second step, you can change the topic to *Cycleway* for the same region and use the same
indicators.

Next, we'll extend the analysis to Attribute Completeness.
We want to look at the attributes *street name* and *surface*.

:::{admonition} Task
:class: tip
Compare the results of the calculations.
How can the differences be explained?
:::

:::{dropdown} Solution

Roads and cycleways:
* [Results for roads in Heidelberg](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=roads&adminids=-285864&indicators=mapping-saturation%2Ccurrentness): high currentness and high completeness at the same time
* [Results for cycleways in Heidelberg](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=cycleway&adminids=-285864&indicators=mapping-saturation%2Ccurrentness): high currentness, but not yet fully mapped in OSM
* Explanation: the OSM community initially focused on mapping roads, and only later increasingly
  added cycleways. This process continues to this day.

Street name and surface:
* Results for roads in Heidelberg: [67% street name](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=roads&attribute-completeness--attributes=name&adminids=-285864&indicators=attribute-completeness) and [83% surface](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=roads&attribute-completeness--attributes=surface&adminids=-285864&indicators=attribute-completeness)
* Results for cycleways in Heidelberg: [46% street name](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=cycleway&attribute-completeness--attribute-title=Name&attribute-completeness--attribute-filter=name%3D*&adminids=-285864&indicators=attribute-completeness) and [99% surface](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=cycleway&attribute-completeness--attribute-title=Oberfl%C3%A4che&attribute-completeness--attribute-filter=surface%3D*&adminids=-285864&indicators=attribute-completeness)
* Explanation: as expected, most cycleways don't have a name. At the same time, cycleways in
  Heidelberg are mapped almost perfectly with regard to their surface.
:::

:::{note}
If you'd like to work more flexibly with OSM filters for your analysis, take a look at the
exercise in [Level 2](level_2.md).
:::
