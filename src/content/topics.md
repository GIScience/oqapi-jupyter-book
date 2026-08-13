# Topics

A topic describes the request that will be sent to the [ohsome API](https://api.ohsome.org).
Each topic represents a particular set of features, aggregated information, or user statistics
derived from the OpenStreetMap database. Each topic is defined by the ohsome API _endpoint_, an
_aggregation_type_, and the _filter_ parameter. In addition, every topic has a key, a name, a
description, a list of valid indicators, and a list of projects it belongs to.

When you select a topic in the Dashboard, all available indicators for it appear automatically
below it.

You'll also find a table showing indicator availability for each topic if you click the "Browse
topic catalogue" button right next to the topic field.

### Aggregation

OSM data is summarised using an aggregation type. Each topic has exactly one assigned aggregation
type. The *Count* aggregation type counts each individual feature, *Length* adds up the geographic
length of all features, and *Area* adds up the geographic area of the features accordingly.
Currently, only the Currentness, Mapping Saturation and Attribute Completeness indicators take the
aggregation type into account.

:::{dropdown} Buildings (count)

- **Description:** All buildings, defined by all features tagged `building=*`.
- **Filter:** `building=* and building!=no and geometry:polygon`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Buildings (area)

- **Description:** All buildings, defined by all features tagged `building=*`.
- **Filter:** `building=* and building!=no and geometry:polygon`
- **Aggregation:** Area
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Building Comparison
  - User Activity
  :::

---

:::{dropdown} Roads (all highways)

- **Description:** All linear OSM features holding the principal tag `highway=*`. The road
  network, defined by all features holding the road network's principal tags as well as their
  connecting roads, as described in the [OSM Wiki](https://wiki.openstreetmap.org/wiki/Key:highway).
- **Filter:** `highway=* and geometry:line and name=*`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Road Comparison
  - Attribute Completeness
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Roads (cars)

- **Description:** All linear OSM features referring to a road usable by vehicles (i.e. cars).
- **Filter:** `highway in (motorway, trunk, primary, secondary, tertiary, residential, service, living_street, trunk_link, motorway_link, primary_link, secondary_link, tertiary_link, unclassified) and geometry:line`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Attribute Completeness
  - Currentness
  - User Activity
  - Road Thematic Accuracy
  :::

---

:::{dropdown} Railways

- **Description:** Railway networks.
- **Filter:** `railway in (rail, subway, tram, light_rail, monorail, funicular, narrow_gauge) and type:way`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Bridges (cars)

- **Description:** All linear OSM features referring to a bridge usable by vehicles.
- **Filter:** `highway in (motorway, trunk, primary, secondary, tertiary, residential, service, living_street, trunk_link, motorway_link, primary_link, secondary_link, tertiary_link, unclassified) and bridge=* and geometry:line`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Bridges (all ways)

- **Description:** All linear OSM features referring to a bridge, including footpaths only.
- **Filter:** `bridge=* and geometry:line`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Bridges (count)

- **Description:** Count of all polygons labelled as a bridge.
- **Filter:** `man_made=bridge and geometry:polygon`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Cycleway

- **Description:** All linear OSM features referring to cycleways. Includes standalone cycle paths
  as well as cycleways running alongside roads.
- **Filter:** `((cycleway=* and cycleway!=no) or (cycleway:both=*) or (cycleway:right=*) or (cycleway:left=*) or (cycleway:right:lane=*) or (cycleway:both:lane=*) or (cycleway:left:lane=*) or (cycleway:left:oneway=*) or (cycleway:right:oneway=*) or (highway=cycleway) or (highway=path and bicycle=designated) or (bicycle_road=yes) or (cyclestreet=yes)) and geometry:line`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Power Lines

- **Description:** All linear OSM features referring to power lines.
- **Filter:** `((power=line) or (power=minor_line)) and geometry:line`
- **Aggregation:** Length
- **Indicators:**
  - Attribute Completeness
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Power Substation

- **Description:** A facility that controls the flow of electricity in a power network using
  transformers, switchgear or compensators.
- **Filter:** `power=substation and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Attribute Completeness
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Footway

- **Description:** All linear OSM features commonly used for walking, including dedicated
  footways, shared paths, and roads where pedestrian traffic is permitted or a pavement is present.
- **Filter:** `((highway=footway) or (highway=path and (foot=designated or foot=yes)) or (highway=pedestrian) or (highway=steps) or (highway=cycleway and foot=yes) or (sidewalk=* and highway!=motorway) or (foot=yes)) and geometry:line`
- **Aggregation:** Length
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Points of Interest (POI)

- **Description:** Points of interest.
- **Filter:** `((aeroway in (aerodrome, helipad, heliport)) or (amenity in (animal_boarding, animal_shelter, arts_centre, atm, baby_hatch, bank, bar, bbq, bench, bicycle_parking, bicycle_rental, bicycle_repair_station, biergarten, boat_sharing, brothel, bureau_de_change, bus_station, bus_stop, cafe, car_sharing, car_wash, casino, charging_station, cinema, clinic, clock, college, community_centre, compressed_air, courthouse, coworking_space, crematorium, crypt, dentist, doctors, dive_centre, dojo, drinking_water, driving_school, embassy, emergency_phone, ev_charging, fast_food, ferry_terminal, fire_station, food_court, fountain, fuel, gambling, grave_yard, hospital, hunting_stand, ice_cream, internet_cafe, kindergarten, language_school, library, kneipp_water_cure, marketplace, motorcycle_parking, music_school, nightclub, nursing_home, parking, parking_entrance, parking_space, pharmacy, photo_booth, planetarium, place_of_worship, police, post_box, post_office, pub, public_bath, prison, ranger_station, recycling, rescue_station, restaurant, retirement_home, sanitary_dump_station, school, shelter, shower, social_centre, social_facility, spa, stripclub, studio, table, taxi, telephone, toilets, townhall, university, vending_machine, veterinary, waste_basket, waste_disposal, water_point)) or (emergency in (access_point, defibrillator, fire_hydrant)) or (healthcare = blood_donation) or (healthcare:speciality = vacciniation) or (highway = raceway) or (historic in (aircraft, aqueduct, archaeological_site, battlefield, boundary_stone, building, castle, cannon, city_gate, citywalls, farm, fort, gallows, highwater_mark, locomotive, manor, memorial, milestone, monastery, monument, optical_telegraph, pillory, ruins, rune_stone, ship, tomb, wayside_cross, wayside_shrine, wreck)) or (leisure in (adult_gaming_centre, amusement_arcade, beach_resort, bandstand, bird_hide, common, dance, dog_park, firepit, fishing, fitness_centre, garden, golf_course, hackerspace, horse_riding, ice_rink, marina, miniature_golf, nature_reserve, park, picnic_table, pitch, playground, sauna, slipway, sports_centre, stadium, summer_camp, swimming_area, swimming_pool, track, turkish_bath, water_park, wildlife_hide)) or (natural in (beach, cave_entrance, geyser, peak, rock, saddle, spring, volcano, water)) or (public_transport in (platform, stop_position, station, stop_area)) or (railway in (halt, station, tram_station)) or (shop in (agrarian, alcohol, antiques, art, bag, bakery, beauty, bed, beverages, bicycle, books, boutique, brewing_supplies, business_machines, butcher, cafe, camera, candles, car, car_parts, carpet, curtain, cheese, chemist, chocolate, clothes, coffee, computer, confectionery, convenience, copyshop, cosmetics, dairy, deli, department_store, doityourself, dry_cleaning, electrical, electronics, erotic, estate_agent, e-cigarette, farm, fashion, fishing, florist, funeral_directors, furniture, games, garden_centre, garden_furniture, gas, general, gift, glaziery, greengrocer, grocery, hairdresser, hairdresser_supply, hardware, hearing_aids, herbalist, hifi, houseware, hunting, insurance, interior_decoration, jewelry, laundry, leather, locksmith, kiosk, kitchen, lamps, lottery, mall, massage, medical_supply, mobile_phone, model, motorcycle, music, musical_instrument, nutrition_supplements, newsagent, optician, organic, outdoor, paint, pastry, perfumery, photo, pyrotechnics, radio, seafood, second_hand, security, shoes, spices, sports, stationery, supermarket, swimming_pool, tailor, tattoo, tea, ticket, tiles, tobacco, toys, travel_agency, trophy, tyres, variety_store, video, video_games, watches, weapons, wine, pet)) or (tourism in (alpine_hut, apartment, aquarium, artwork, attraction, camp_site, caravan_site, chalet, gallery, museum, guest_house, hostel, hotel, motel, picnic_site, theme_park, viewpoint, wilderness_hut, zoo))) and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Schools

- **Description:** Count of schools.
- **Filter:** `amenity=school and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Kindergartens

- **Description:** Count of kindergartens.
- **Filter:** `amenity=kindergarten and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Clinics

- **Description:** Count of clinics.
- **Filter:** `(amenity=clinic or healthcare=clinic) and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Doctors

- **Description:** Count of doctors.
- **Filter:** `(amenity=doctors or healthcare=doctor) and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Bus Stops

- **Description:** Count of bus stops.
- **Filter:** `highway=bus_stop and type:node`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Tram Stops

- **Description:** Count of tram stops.
- **Filter:** `railway=tram_stop and type:node`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Public Transport Stops

- **Description:** Count of public transport stops.
- **Filter:** `public_transport=platform and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Subway Stations

- **Description:** Count of subway stations.
- **Filter:** `station=subway and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Supermarkets

- **Description:** Count of supermarkets.
- **Filter:** `(shop=supermarket or shop=convenience) and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Marketplaces

- **Description:** Count of marketplaces.
- **Filter:** `amenity=marketplace and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Parks

- **Description:** Count of parks.
- **Filter:** `leisure=park and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Sports Pitches

- **Description:** Count of sports pitches (an area designed for practising a particular sport).
- **Filter:** `leisure=pitch and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Forests

- **Description:** Count of forests.
- **Filter:** `landuse=forest and geometry:polygon`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Industrial Landuse (count)

- **Description:** Industrial landuse sites (count).
- **Filter:** `landuse=industrial and type:way`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Industrial Landuse (area)

- **Description:** Industrial landuse sites (area).
- **Filter:** `landuse=industrial and type:way`
- **Aggregation:** Area
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Fitness Centres

- **Description:** Count of fitness centres.
- **Filter:** `leisure in (fitness_centre, sports_centre) and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Attribute Completeness
  - User Activity
  :::

---

:::{dropdown} Fire Stations

- **Description:** Count of fire stations.
- **Filter:** `amenity=fire_station and (type:way or type:node)`
- **Aggregation:** Count
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - User Activity
  :::

---

:::{dropdown} Land Use and Land Cover

- **Description:** Features related to land use and land cover.
- **Filter:** `(landuse=* and landuse!=no) or natural in (wood, grassland, scrub, heath, fell, beach, sand, scree, shingle, bare_rock, glacier, mud, rock, cliff, fill, wetland, water, pond) or leisure in (marina, park, garden, pitch, golf_course, playground, stadium, recreation_ground, common, dog_park) and geometry:polygon`
- **Aggregation:** Area
- **Indicators:**
  - Mapping Saturation
  - Currentness
  - Land Cover Thematic Accuracy
  - Land Cover Completeness
  - User Activity
  :::
