# Dashboard Usage
On this page, you find a simple overview on how to navigate the [ohsome Dashboard](https://dashboard.ohsome.org/en/#backend=ohsomeApi&groupBy=none&time=%2F2026-02-19T12%3A00Z%2FP1M&key=natural&value=tree&types=node&measure=count). 

## Let's start with the Basics!
On the upper left tab, you can choose between the OSM History Stats and OSM Quality Analyses.
The History Stats gives you an insight into the eventful history of OSM data for any region and time period you are interested in.
The Quality Analyses offer many different qualitiy indicators you can use to validate OSM data for your area of interes.
![tabs](content/images/tabs.png)

## OSM Quality Analyses

### Topic

Topics are defined by a set of OSM Tags and Keys that match a certain object. 
At the left window, navigate to *OSM Quality Analysis*.
Under "Topic" you find a drop down menu. Open it and get familiar with all the topics you can chose from.
Select the topic you want to explore.
The OSM dashboard will automatically create the appropriate OSM filter regarding on the selected topic.
![topic](content/images/topic.png)

### Area of Interest

Choose your area of interest on the map on the right window. You can choose along governmental boundaries or self defined bounding boxes. Zoom in to catch a more precice border for your area of interest.
You can run queries for multiple regions at a time. Just click at multiple areas and remove them with another click, or close the blue box under the map.

![area_of_interest](content/images/area_of_interest.png)

### Quality Indicators
Here you can analyse OSM data along multiple Quality Dimensions:
**Quality Dimensions**
Completeness
- Mapping Saturation
- Attribute Completeness
- Building Comparison
- Land Cover Completeness
- Road Comparison
Currentness
- Currentness
Thematic Accuracy
- Land Cover Thematic Accuracy
- Road Thematic Accuracy
Others
- User Activity


Depending on the Topic you chose, you will find the available Quality Indicators to select. Select the once you are interested in and hit the "run query" button to load your figures. 
If you are running the Attribute Completeness or Road Thematic Accuracy Indicator, you can select certain attributes. For taking advantage of that, activate the indicator and open the drop-down menu to find the set of attributes you can choose from at your Topic. If you choose multiple attributes in one query, it will be presented as one result.
![quality_indicators](content/images/quality_indicators.png)
