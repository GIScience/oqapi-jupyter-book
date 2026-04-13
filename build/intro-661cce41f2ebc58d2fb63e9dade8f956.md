# OQAPI Jupyter Book

Welcome to the ohsome Dashboard tutorial. Here you find explanations and user guidlines for all of our quality indicators for OSM data.

OpenStreetMap is a rich source of user-generated, freely available geospatial data for many applications. However, varying data quality and a lack of standardization can make it challenging to use. We developed the ohsome Dashboard for you to assess OSM data quality globally or for specific areas and helping you determine if it meets your project needs.

The ohsome dashboard enables analysis of OpenStreetMap data with full version history, no programming required. It generates statistics and visualizes them directly, with customizable filters and groupings by tags, types, region, and time. The ohsome Quality API (OQAPI) provides access to OSM data quality information for specific regions and use cases.

## Quality Dimensions
Here is a list of all our available quality indicators. Each indicator and its usage is explained 
accuracy

## Dashboard Usage
To navigate the ohsome Dashboard, you need to be familiar with three simple expressions:

### Topic

Topics are defined by a set of OSM Tags and Keys that match a certain object. 
At the left window, navigate to *OSM Quality Analysis*.
Under "Topic" you find a drop down menu. Open it and get familiar with all the topics you can chose from.
Select the topic you want to explore.
The OSM dashboard will automatically create the appropriate OSM filter regarding on the selected topic.
![topic](images/topic.png)

### Area of Interest

Choose your area of interest on the map on the right window. You can choose along governmental boundaries or self defined bounding boxes.

![area_of_interest](images/area_of_interest.png)

### Quality Indicators
Depending on the Topic you chose, you will find the available Quality Indicators to select. Select the once you are interested in and hit the "run query" button to load your figures. 
If you are running the Attribute Completeness or Road Thematic Accuracy Indicator, you can select certain attributes. For taking advantage of that, activate the indicator and open the drop-down menu to find the set of attributes you can choose from at your Topic. If you choose multiple attributes in one query, it will be presented as one result.
![quality_indicators](images/quality_indicators.png)

