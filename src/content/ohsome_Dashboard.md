# ohsome Dashboard

On this page you'll find a quick overview of how to find your way around the [ohsome
Dashboard](https://dashboard.ohsome.org/en/#backend=ohsomeApi&groupBy=none&time=%2F2026-02-19T12%3A00Z%2FP1M&key=natural&value=tree&types=node&measure=count).
In the top-left tab you can switch between *OSM History Stats* and *OSM Quality Analyses*.
The *History Stats* give you insight into how OSM data has developed for any region and any
period.
The *Quality Analyses* offer many different indicators you can use to validate OSM data for your
area of interest.

Click the *OSM Quality Analyses* tab in the top left to switch the dashboard over.
The dashboard is split into different sections, each affecting a different step of the analysis:
1. [Topic](#topic)
2. [Area of Interest](#area-of-interest)
3. [Quality Indicators](#quality-indicators)
4. [Results](#results)

![ohsome Dashboard Overview](../abbildungen/ohsome_dashboard_overview_de.png)

## Topic

In the first step, choose the *topic* you want to investigate from the dropdown menu.
Clicking into the input field also lets you search for other predefined topics.

*Topics* are defined by a set of OSM tags that describe a particular
feature type.
The ohsome Dashboard automatically builds the matching OSM filter based on the selected *topic*.

:::{margin} **Example**
The topic *Schools* is defined, for example, by this OSM tag filter:
```amenity=school and (type:way or type:node)```
:::

<img src="../abbildungen/topics_deutsch.png" width="300"/>

:::{admonition} Custom Topics
:class: seealso
You can also define *topics* completely freely, for example if you only want to look at certain
road types in your analysis.
We've created a dedicated tutorial page for this → [Custom Topics](custom_topics.md)
:::


## Area of Interest

Choose your area of interest on the map in the right-hand pane. You can select along
administrative boundaries or with a freely drawn frame. Zoom in to get a more precise outline of
your area of interest.

::::{tab-set}
::: {tab-item} Administrative boundaries
Simply click on an area to select it for the analysis.
You can also select several regions at once and run a combined query for the whole region.
You can remove areas by clicking on them again or by removing the blue box under the map.

![area_of_interest](../abbildungen/Untersuchungsgebiet_Auswahlkarte_de.png)
:::

::: {tab-item} Bounding Box
Drag out a rectangle with the mouse to define a *bounding box*.
You can also adjust or delete this bounding box afterwards.

![area_of_interest](../abbildungen/Untersuchungsgebiet_Auswahlkarte_de_bbox.png)
:::
::::


## Quality Indicators

Depending on the *topic* you've chosen, you'll find the available quality indicators to select
from.
Each indicator is briefly described directly in the ohsome Dashboard.
A detailed explanation of the methodology and possible limitations can be found in the next
chapter.

You can analyse OSM data across several quality dimensions:

:::{dropdown} Completeness
- Mapping Saturation
- Attribute Completeness
- Building Comparison
- Land Cover Completeness
- Road Comparison
:::

:::{dropdown} Currentness
- Currentness
:::

:::{dropdown} Thematic Accuracy
- Land Cover Thematic Accuracy
- Road Thematic Accuracy
:::

:::{dropdown} Others
- User Activity
:::



Choose the ones you're interested in and click *run query* to start calculating your results.

<img src="../abbildungen/indikatoren_auswahl_de.png" width="300"/>

## Results

After a few seconds, the calculated results load as a figure in the lower pane.
Each indicator's result is colour-coded into three categories: usually green (good), yellow
(medium) and red (poor). A few sentences explain the classification.

![results](../abbildungen/ohsome_dashboard_ergebnisse_de.png)


:::{margin} **Sharing results**
You can share your results with other people via a link. This URL links to the calculation shown
in the adjacent figure.

https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=cycleway&adminids=-285864&indicators=currentness
:::

On the following pages, we describe the results for each quality indicator and discuss various
interpretations.
