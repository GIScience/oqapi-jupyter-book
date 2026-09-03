# Level 2 - Custom Attributes and Topics

In this exercise, we'll investigate the quality of OSM data using self-defined topics and
attributes.
Start by choosing any region in Germany in the ohsome Dashboard for which you want to run the
analysis.

## Attribute Completeness: Road Width

The Attribute Completeness indicator lets you freely define attributes, or adapt the definition of
existing attributes.
This means any attribute you like can be checked.

:::{admonition} Task
:class: tip
For the topic *Roads (cars)*, try to find out how many roads have information about their width.
Use a custom attribute you've created yourself for the Attribute Completeness indicator.
:::

:::{dropdown} Solution
Select the topic *Roads (cars)*. When selecting the Attribute Completeness indicator, choose any
attribute, then click the blue field next to the attributes. In this window, remove the existing
filter and enter `width=*` instead. Then calculate the indicator for the desired region.
:::

## Custom Topics

If the predefined topics aren't sufficient for an analysis, you can also define a topic of your
own.

:::{admonition} Task
:class: tip
Create your own topic for all motorways.
First, research the relevant filter in the [OSM wiki](https://wiki.openstreetmap.org/).
:::

:::{dropdown} Solution
German motorways are mapped in OSM with the key-value pair *highway=motorway* (see [here](https://wiki.openstreetmap.org/wiki/DE:Germany/Autobahn)).
To restrict ourselves to linear features, we also add *geometry:line*.
Together, this gives us the filter *highway=motorway and geometry:line*.
:::

Now you can calculate the various OSM quality indicators for your custom topic.
[Here's an example](https://next.ohsome-dashboard.heigit.org/en/#backend=oqtApi&topic=custom-topic&topic-title=Stra%C3%9Fen+%28Autos%29&topic-filter=highway+in+%28motorway%2C+motorway_link%29+and+geometry%3Aline&adminids=-62611&indicators=mapping-saturation%2Ccurrentness%2Cuser-activity)
of Mapping Saturation, Currentness and User Activity for the custom topic *Motorways* in
Baden-Württemberg.
