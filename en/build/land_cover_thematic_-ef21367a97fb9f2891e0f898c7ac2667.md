# Land Cover Thematic Accuracy

This indicator assesses the agreement between OSM land cover data and the CORINE Land Cover (CLC)
dataset.
It can be applied either to all CLC classes together, or to individual selected classes.

For the defined area of interest, the polygons resulting from the intersection of OSM and CLC data
are aggregated in a confusion matrix. From this, we calculate class-level and overall accuracy
metrics, including precision, recall and the F1 score. All metrics are area-weighted, so that the
spatial extent of the polygons is taken into account rather than treating features as equally
weighted units. This approach allows for a systematic assessment of the thematic consistency of
OSM land cover data compared with the referenced CLC data.

:::{note}
For this indicator, an attribute must be chosen in addition to the topic. A field for selecting
the attribute appears below the indicator selection (see figure). The indicator can be calculated
either for a single attribute or for all attributes at once. For the latter, leave the field empty.

<div>
<img src="../../abbildungen/landbedeck_thematisch_dropdown.png" width="300"/>
</div>
:::

The result value is calculated as an area-weighted F1 score, normalised to a range of 0 to 1.
Values below 0.6 are considered low thematic agreement, values between 0.6 and 0.85 medium
agreement, and values above 0.85 high agreement between OSM and CLC.

:::{attention}
This indicator is only available for the topic _Land Use and Land Cover_.
:::

### Methods and Data

`Extrinsic approach`

OSM features are assigned to CLC Level 2 classes based on their `landuse=*` and `natural=*` tags,
as shown in the table below. The spatial intersection of OSM polygons with CLC polygons produces
combined geometries that hold both the OSM and the CLC class labels. This step ensures that
differences between the class definitions can be analysed directly at polygon level. Areas where
one of the two datasets isn't available are ignored. For the defined area of interest, the
polygons resulting from the intersection of OSM and CLC data are aggregated in a confusion matrix.
From this, we calculate class-level and overall accuracy metrics, including precision, recall and
the F1 score. All metrics are area-weighted, so that the spatial extent of the polygons is taken
into account rather than treating features as equally weighted units. This approach allows for a
systematic assessment of the thematic consistency of OSM land cover compared with the referenced
CLC data. The result value is calculated as an area-weighted F1 score, normalised to a range of 0
to 1.

- Low thematic accuracy (< 0.6)
- Medium thematic accuracy (0.6 - 0.85)
- High thematic accuracy (> 0.85)

:::{margin} Limitations
Since OpenStreetMap is continuously updated while the reference dataset was released at a specific
point in time, the reference dataset is no longer as current as OpenStreetMap at the time of
comparison.
:::

#### CORINE Land Cover

In its current form, the [CORINE Land Cover (CLC)](https://land.copernicus.eu/en/products/corine-land-cover)
product provides a Europe-wide inventory of land cover and land use with 44 thematic classes,
ranging from large forest areas down to individual vineyards. CORINE uses a three-level
nomenclature for land cover classes.
Here we use "CORINE Land Cover 5 ha, as of 2021 (CLC5-2021)", provided by the Bundesamt für
Kartographie und Geodäsie (Federal Agency for Cartography and Geodesy), together with Level 2 of
the nomenclature (e.g. 1.1 Urban Fabric, 1.2 Industrial, commercial and transport units).

### Data Preparation

OSM features are assigned a CLC class based on their tags, using the table given below.
We calculate the intersection of OSM land cover polygons and CORINE land cover polygons.
The resulting polygons hold both the OSM-derived CLC class and the CORINE class.

| CLC (level 2) | OSM tags |
|----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.1 Urban Fabric | `landuse in (residential, retail)` |
| 1.2 Industrial, commercial and transport units | `landuse in (industrial, commercial, port, railway, lock) or leisure in (marina)` |
| 1.3 Mine, dump and construction sites | `landuse in (quarry, construction, landfill, brownfield)` |
| 1.4 Artificial, non-agricultural vegetated areas | `landuse in (recreation_ground, allotments, village_green, cemetery, grass) or leisure in (park, garden, pitch, golf_course, playground, stadium, recreation_ground, common, dog_park)` |
| 2.1 Arable land | `landuse in (greenhouse_horticulture, greenhouse, farmland, farmyard)` |
| 2.2 Permanent crops | `landuse in (vineyard, orchard)` |
| 2.3 Pastures | `landuse in (meadow)` |
| 2.4 Heterogeneous agricultural areas | *Many OSM values for class 2.4 overlap with those of class 2.1. Class 2.4 is therefore never assigned.* |
| 3.1 Forests | `landuse in (forest) or natural in (wood)` |
| 3.2 Scrub and/or herbaceous vegetation associations | `landuse in (greenfield) or natural in (grassland, scrub, heath, fell)` |
| 3.3 Open spaces with little or no vegetation | `natural in (beach, scree, shingle, bare_rock, sand, glacier, mud, glacier, rock, cliff, fill)` |
| 4.1 Inland wetlands | `natural in (wetland)` |
| 4.2 Maritime wetlands | `landuse in (salt_pond)` |
| 5.1 Inland waters | `natural in (water, pond) or landuse in (basin, reservoir)` |
| 5.2 Marine waters | *Marine waters aren't mapped in OSM. Class 5.2 is therefore never assigned.* |

:::{margin} Limitations
Since OpenStreetMap is continuously updated while the reference dataset was released at a specific
point in time, it's no longer as current as OpenStreetMap at the time of comparison.
:::

## Result

You'll find the results of the query in the result log below.
The green, yellow or red banner in the top left shows the attribute completeness level.

## Example

In Bonn, the thematic accuracy across all land cover classes combined is a medium 85.16%. The
figure shows how this accuracy breaks down, and that, for example, Urban Fabric achieves far higher
agreement with the CORINE classification than Shrubs and/or herbaceous vegetation associations.

<div>
<img src="../../abbildungen/landbedeck_thematisch_bonn.png" width="700"/>
</div>

If we select a particular land cover class of interest from the dropdown menu, the result looks
like this. Here we see the thematic accuracy for shrubs and/or herbaceous vegetation in Bonn.
False negative, true positive and false positive are each present in roughly equal thirds. This
shows us low agreement between OSM and the CORINE dataset in the area of shrub and herbaceous
vegetation in Bonn.

<div>
<img src="../../abbildungen/landbedeck_thematisch_bonn_grünflächen.png" width="700"/>
</div>

We find higher agreement in the Euskirchen district for the arable land class.

<div>
<img src="../../abbildungen/landbedeck_thematisch_euskirchen_ackerland.png" width="700"/>
</div>

### References Used for this Indicator

- Schultz, Michael, Janek Voss, Michael Auer, Sarah Carter and Alexander Zipf. 2017. "Open Land
  Cover from OpenStreetMap and Remote Sensing." International Journal of Applied Earth Observation
  and Geoinformation 63 (May): 206–13. https://doi.org/10.1016/j.jag.2017.07.014.
