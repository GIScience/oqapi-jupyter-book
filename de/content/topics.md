# Themadefinitionen

Ein Thema beschreibt die Anfrage, die an die [ohsome API](https://api.ohsome.org) gestellt werden soll. 
Jedes Thema steht für eine bestimmte Menge von Objekten, aggregierten Informationen oder Nutzerstatistiken, 
die aus der OpenStreetMap-Datenbank abgeleitet werden. Jedes Thema wird durch den ohsome API _endpoint_, 
einen _aggregation_type_ und den Parameter _filter_ definiert. Zusätzlich besitzt jedes Thema einen Schlüssel
(Key), einen Namen, eine Beschreibung, eine Liste gültiger Indikatoren sowie eine Liste von Projekten, zu 
denen das Thema gehört.

Wenn Sie im Dashboard ein Thema auswählen, erscheinen darunter automatisch alle verfügbaren Indikatoren.

Sie finden außerdem eine Tabelle zur Verfügbarkeit der Indikatoren für jedes Thema, wenn Sie auf die 
Schaltfläche „Durchsuche Themenkatalog“ direkt neben dem Themafeld klicken.

:::{dropdown} Gebäude (Anzahl)

- **Beschreibung:** Alle Gebäude, definiert durch alle Objekte mit dem Tag `building=*`.
- **Filter:** `building=* and building!=no and geometry:polygon`  
:::

---

:::{dropdown} Gebäude (Fläche)

- **Beschreibung:** Alle Gebäude, definiert durch alle Objekte mit dem Tag `building=*`.
- **Filter:** `building=* and building!=no and geometry:polygon`  
:::

---

:::{dropdown} Straßen (alle highways)

- **Beschreibung:** Alle linearen OSM-Objekte mit dem Haupt-Tag `highway=*`. Das Straßennetz, definiert durch alle Objekte mit den Haupt-Tags des Straßennetzes sowie deren Verbindungsstraßen, wie im [OSM Wiki](https://wiki.openstreetmap.org/wiki/Key:highway) beschrieben.
- **Filter:** `highway=* and geometry:line and name=*`  
:::

---

:::{dropdown} Straßen (Autos)

- **Beschreibung:** Alle linearen OSM-Objekte, die sich auf Straßen beziehen, die von Fahrzeugen (z. B. Autos) genutzt werden können. Das Straßennetz, definiert durch alle Objekte mit den Haupt-Tags des Straßennetzes sowie deren Verbindungsstraßen, wie im [OSM Wiki](https://wiki.openstreetmap.org/wiki/Highways#Roads_and_tracks) beschrieben.
- **Filter:** `highway in (motorway, trunk, primary, secondary, tertiary, residential, service, living_street, trunk_link, motorway_link, primary_link, secondary_link, tertiary_link, unclassified) and geometry:line`  
:::

---

:::{dropdown} Eisenbahnen

- **Beschreibung:** Eisenbahnnetze.
- **Filter:** `railway in (rail, subway, tram, light_rail, monorail, funicular, narrow_gauge) and type:way`  
:::

---

:::{dropdown} Brücken (Autos)

- **Beschreibung:** Alle linearen OSM-Objekte, die sich auf Brücken beziehen, die von Fahrzeugen genutzt werden können.
- **Filter:** `highway in (motorway, trunk, primary, secondary, tertiary, residential, service, living_street, trunk_link, motorway_link, primary_link, secondary_link, tertiary_link, unclassified) and bridge=* and geometry:line`  
:::

---

:::{dropdown} Brücken (alle Wege)

- **Beschreibung:** Alle linearen OSM-Objekte, die sich auf Brücken beziehen, einschließlich reiner Fußwege.
- **Filter:** `bridge=* and geometry:line`  
:::

---

:::{dropdown} Brücken (Anzahl)

- **Beschreibung:** Anzahl aller als Brücke gekennzeichneten Polygone.
- **Filter:** `man_made=bridge and geometry:polygon`  
:::

---

:::{dropdown} Radweg

- **Beschreibung:** Alle linearen OSM-Objekte, die sich auf Radwege beziehen. Beinhaltet eigenständige Radwege sowie Radwege entlang von Straßen.
- **Filter:** `((cycleway=* and cycleway!=no) or (cycleway:both=*) or (cycleway:right=*) or (cycleway:left=*) or (cycleway:right:lane=*) or (cycleway:both:lane=*) or (cycleway:left:lane=*) or (cycleway:left:oneway=*) or (cycleway:right:oneway=*) or (highway=cycleway) or (highway=path and bicycle=designated) or (bicycle_road=yes) or (cyclestreet=yes)) and geometry:line`  
:::

---

:::{dropdown} Stromleitungen

- **Beschreibung:** Alle linearen OSM-Objekte, die sich auf Stromleitungen beziehen.
- **Filter:** `((power=line) or (power=minor_line)) and geometry:line`  
:::

---

:::{dropdown} Umspannwerk

- **Beschreibung:** Eine Anlage, die den Stromfluss in einem Stromnetz mit Transformatoren, Schaltanlagen oder Kompensatoren steuert.
- **Filter:** `power=substation and (type:way or type:node)`  
:::

---

:::{dropdown} Fußweg

- **Beschreibung:** Alle linearen OSM-Objekte, die üblicherweise zum Gehen genutzt werden, einschließlich spezieller Fußwege, gemeinsam genutzter Wege sowie Straßen, auf denen Fußverkehr erlaubt ist oder Gehwege vorhanden sind.
- **Filter:** `((highway=footway) or (highway=path and (foot=designated or foot=yes)) or (highway=pedestrian) or (highway=steps) or (highway=cycleway and foot=yes) or (sidewalk=* and highway!=motorway) or (foot=yes)) and geometry:line`  
:::

---

:::{dropdown} Points of Interest (POI)

- **Beschreibung:** Points of Interest (Sehenswürdigkeiten).
- **Filter:** `((aeroway in (aerodrome, helipad, heliport)) or (amenity in (animal_boarding, animal_shelter, arts_centre, atm, baby_hatch, bank, bar, bbq, bench, bicycle_parking, bicycle_rental, bicycle_repair_station, biergarten, boat_sharing, brothel, bureau_de_change, bus_station, bus_stop, cafe, car_sharing, car_wash, casino, charging_station, cinema, clinic, clock, college, community_centre, compressed_air, courthouse, coworking_space, crematorium, crypt, dentist, doctors, dive_centre, dojo, drinking_water, driving_school, embassy, emergency_phone, ev_charging, fast_food, ferry_terminal, fire_station, food_court, fountain, fuel, gambling, grave_yard, hospital, hunting_stand, ice_cream, internet_cafe, kindergarten, language_school, library, kneipp_water_cure, marketplace, motorcycle_parking, music_school, nightclub, nursing_home, parking, parking_entrance, parking_space, pharmacy, photo_booth, planetarium, place_of_worship, police, post_box, post_office, pub, public_bath, prison, ranger_station, recycling, rescue_station, restaurant, retirement_home, sanitary_dump_station, school, shelter, shower, social_centre, social_facility, spa, stripclub, studio, table, taxi, telephone, toilets, townhall, university, vending_machine, veterinary, waste_basket, waste_disposal, water_point)) or (emergency in (access_point, defibrillator, fire_hydrant)) or (healthcare = blood_donation) or (healthcare:speciality = vacciniation) or (highway = raceway) or (historic in (aircraft, aqueduct, archaeological_site, battlefield, boundary_stone, building, castle, cannon, city_gate, citywalls, farm, fort, gallows, highwater_mark, locomotive, manor, memorial, milestone, monastery, monument, optical_telegraph, pillory, ruins, rune_stone, ship, tomb, wayside_cross, wayside_shrine, wreck)) or (leisure in (adult_gaming_centre, amusement_arcade, beach_resort, bandstand, bird_hide, common, dance, dog_park, firepit, fishing, fitness_centre, garden, golf_course, hackerspace, horse_riding, ice_rink, marina, miniature_golf, nature_reserve, park, picnic_table, pitch, playground, sauna, slipway, sports_centre, stadium, summer_camp, swimming_area, swimming_pool, track, turkish_bath, water_park, wildlife_hide)) or (natural in (beach, cave_entrance, geyser, peak, rock, saddle, spring, volcano, water)) or (public_transport in (platform, stop_position, station, stop_area)) or (railway in (halt, station, tram_station)) or (shop in (agrarian, alcohol, antiques, art, bag, bakery, beauty, bed, beverages, bicycle, books, boutique, brewing_supplies, business_machines, butcher, cafe, camera, candles, car, car_parts, carpet, curtain, cheese, chemist, chocolate, clothes, coffee, computer, confectionery, convenience, copyshop, cosmetics, dairy, deli, department_store, doityourself, dry_cleaning, electrical, electronics, erotic, estate_agent, e-cigarette, farm, fashion, fishing, florist, funeral_directors, furniture, games, garden_centre, garden_furniture, gas, general, gift, glaziery, greengrocer, grocery, hairdresser, hairdresser_supply, hardware, hearing_aids, herbalist, hifi, houseware, hunting, insurance, interior_decoration, jewelry, laundry, leather, locksmith, kiosk, kitchen, lamps, lottery, mall, massage, medical_supply, mobile_phone, model, motorcycle, music, musical_instrument, nutrition_supplements, newsagent, optician, organic, outdoor, paint, pastry, perfumery, photo, pyrotechnics, radio, seafood, second_hand, security, shoes, spices, sports, stationery, supermarket, swimming_pool, tailor, tattoo, tea, ticket, tiles, tobacco, toys, travel_agency, trophy, tyres, variety_store, video, video_games, watches, weapons, wine, pet)) or (tourism in (alpine_hut, apartment, aquarium, artwork, attraction, camp_site, caravan_site, chalet, gallery, museum, guest_house, hostel, hotel, motel, picnic_site, theme_park, viewpoint, wilderness_hut, zoo))) and (type:way or type:node)`  
:::

---

:::{dropdown} Schulen

- **Beschreibung:** Anzahl der Schulen.
- **Filter:** `amenity=school and (type:way or type:node)`  
:::

---

:::{dropdown} Kindergärten

- **Beschreibung:** Anzahl der Kindergärten.
- **Filter:** `amenity=kindergarten and (type:way or type:node)`  
:::

---

:::{dropdown} Kliniken

- **Beschreibung:** Anzahl der Kliniken.
- **Filter:** `(amenity=clinic or healthcare=clinic) and (type:way or type:node)`  
:::

---

:::{dropdown} Ärzte

- **Beschreibung:** Anzahl der Ärzte.
- **Filter:** `(amenity=doctors or healthcare=doctor) and (type:way or type:node)`  
:::

---

:::{dropdown} Bushaltestellen

- **Beschreibung:** Anzahl der Bushaltestellen.
- **Filter:** `highway=bus_stop and type:node`  
:::

---

:::{dropdown} Straßenbahnhaltestellen

- **Beschreibung:** Anzahl der Straßenbahnhaltestellen.
- **Filter:** `railway=tram_stop and type:node`  
:::

---

:::{dropdown} ÖPNV-Haltestellen

- **Beschreibung:** Anzahl der Haltestellen des öffentlichen Verkehrs.
- **Filter:** `public_transport=platform and (type:way or type:node)`  
:::

---

:::{dropdown} U-Bahn-Stationen

- **Beschreibung:** Anzahl der U-Bahn-Stationen.
- **Filter:** `station=subway and (type:way or type:node)`  
:::

---

:::{dropdown} Supermärkte

- **Beschreibung:** Anzahl der Supermärkte.
- **Filter:** `(shop=supermarket or shop=convenience) and (type:way or type:node)`  
:::

---

:::{dropdown} Marktplätze

- **Beschreibung:** Anzahl der Marktplätze.
- **Filter:** `amenity=marketplace and (type:way or type:node)`  
:::

---

:::{dropdown} Parks

- **Beschreibung:** Anzahl der Parks.
- **Filter:** `leisure=park and (type:way or type:node)`  
:::

---

:::{dropdown} Sportplätze

- **Beschreibung:** Anzahl der Sportplätze (Flächen zur Ausübung einer bestimmten Sportart).
- **Filter:** `leisure=pitch and (type:way or type:node)`  
:::

---

:::{dropdown} Wälder

- **Beschreibung:** Anzahl der Wälder.
- **Filter:** `landuse=forest and geometry:polygon`  
:::

---

:::{dropdown} Industrieflächen (Anzahl)

- **Beschreibung:** Industrieflächen (Anzahl).
- **Filter:** `landuse=industrial and type:way`  
:::

---

:::{dropdown} Industrieflächen (Fläche)

- **Beschreibung:** Industrieflächen (Fläche).
- **Filter:** `landuse=industrial and type:way`  
:::

---

:::{dropdown} Fitnesszentren

- **Beschreibung:** Anzahl der Fitnesszentren.
- **Filter:** `leisure in (fitness_centre, sports_centre) and (type:way or type:node)`  
:::

---

:::{dropdown} Feuerwachen

- **Beschreibung:** Anzahl der Feuerwachen.
- **Filter:** `amenity=fire_station and (type:way or type:node)`  
:::

---

:::{dropdown} Landnutzung und Landbedeckung

- **Beschreibung:** Objekte im Zusammenhang mit Landnutzung und Bodenbedeckung.
- **Filter:** `(landuse=* and landuse!=no) or natural in (wood, grassland, scrub, heath, fell, beach, sand, scree, shingle, bare_rock, glacier, mud, rock, cliff, fill, wetland, water, pond) or leisure in (marina, park, garden, pitch, golf_course, playground, stadium, recreation_ground, common, dog_park) and geometry:polygon`  
:::