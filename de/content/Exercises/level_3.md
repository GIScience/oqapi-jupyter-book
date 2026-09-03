# Level 3 - Automatisierung mit Python

Alle OSM Qualitätsindikatoren können auch automatisiert bzw. ohne Nutzung des ohsome Dashboard berechnet werden.
Dafür kannst du die *ohsome quality API* direkt abfragen, z.B. mit Python.
Die Automatisierung, z.B. mittels Python, ermöglicht es die OSM-Datenqualität für eine Vielzahl an Regionen zu berechnen und anschließend systematisch zu vergleichen.

Die [Dokumentation der API]([https://api.quality.ohsome.org/v1/docs) beschreibt die einzelnen API-Endpunkte und wie diese genutzt werden können.

## Aktualität
```python

import geojson
import requests
import geopandas as gpd
import pandas as pd
import time
from concurrent.futures import ThreadPoolExecutor, as_completed
import sys

# füge hier deinen HeiGIT-API-Key ein
api_key="YOUR_API_KEY"

indicator = "/currentness"
topic = "land-cover"
input_geom_path = "friedberg.geojson"
output_geom_path = "your_output_layer.gpkg"
max_workers = 20

base_url = "https://api.heigit.org/ohsome-quality-api/v2"
endpoint = "/indicators"
url = base_url + endpoint + indicator

gdf = gpd.read_file(input_geom_path)
gdf["result_value"] = pd.Series([None] * len(gdf), dtype="float")
gdf["response_time"] = pd.Series([None] * len(gdf), dtype="float")

headers = {"accept": "application/json", "authorization": api_key}

def fetch(index, geometry):
    bpolys = geojson.Feature(geometry=geometry)
    bpolys_collection = geojson.FeatureCollection([bpolys])

    parameters = {
        "topic": topic,
        "bpolys": bpolys_collection,
    }
    for attempt in range(5):
        try:
            print(f"posting request for index {index}")
            startresponse = time.time()
            response = requests.post(url, headers=headers, json=parameters, timeout=600)
            response.raise_for_status()
            result = response.json()
            endresponse = time.time()
            responsetime = endresponse - startresponse
            value = result["result"][0]["result"]["value"]
            return index, value, responsetime
        except requests.RequestException as e:
            print(f"Attempt {attempt + 1} failed at index {index}: {e}")
            if attempt < 3:
                print("Retrying...")
                time.sleep(2)
            else:
                print("Max retries reached. Skipping.")
                return index, None, None

start = time.time()
with ThreadPoolExecutor(max_workers=max_workers) as executor:
    futures = [executor.submit(fetch, i, gdf.geometry.iloc[i]) for i in range(len(gdf))]

    for future in as_completed(futures):
        index, value, responsetime = future.result()
        gdf.at[index, "result_value"] = value
        gdf.at[index, "response_time"] = responsetime
        print(f"Completed index {index}: {value}")

end = time.time()
print(f"Calculation took {end - start:.2f} seconds")

gdf.to_file(output_geom_path, driver="GPKG")
```

## Attributvollständigkeit

```python
# Attribute Completeness

import geojson
import requests
import geopandas as gpd
import pandas as pd
import time
from concurrent.futures import ThreadPoolExecutor, as_completed
import sys

# füge hier deinen HeiGIT-API-Key ein
api_key="YOUR_API_KEY"

indicator = "/attribute-completeness"
topic = "roads"
input_geom_path = "your_bounding_box.geojson"
output_geom_path = "your_output_layer.gpkg"
max_workers = 20



base_url = "https://api.heigit.org/ohsome-quality-api/v2"
endpoint = "/indicators"
url = base_url + endpoint + indicator

gdf = gpd.read_file(input_geom_path)
gdf["result_value"] = pd.Series([None] * len(gdf), dtype="float")
gdf["response_time"] = pd.Series([None] * len(gdf), dtype="float")

headers = {"accept": "application/json"}

def fetch(index, geometry):
    bpolys = geojson.Feature(geometry=geometry)
    bpolys_collection = geojson.FeatureCollection([bpolys])

    parameters = {
        "topic": topic,
        "bpolys": bpolys_collection,
        "attributes": ["surface"]
    }
    for attempt in range(5):
        try:
            print(f"posting request for index {index}")
            startresponse = time.time()
            response = requests.post(url, headers=headers, json=parameters, timeout=600)
            response.raise_for_status()
            result = response.json()
            endresponse = time.time()
            responsetime = endresponse - startresponse
            value = result["result"][0]["result"]["value"]
            return index, value, responsetime
        except requests.RequestException as e:
            print(f"Attempt {attempt + 1} failed at index {index}: {e}")
            if attempt < 3:
                print("Retrying...")
                time.sleep(2)
            else:
                print("Max retries reached. Skipping.")
                return index, None, None

start = time.time()
with ThreadPoolExecutor(max_workers=max_workers) as executor:
    futures = [executor.submit(fetch, i, gdf.geometry.iloc[i]) for i in range(len(gdf))]

    for future in as_completed(futures):
        index, value, responsetime = future.result()
        gdf.at[index, "result_value"] = value
        gdf.at[index, "response_time"] = responsetime
        print(f"Completed index {index}: {value}")

end = time.time()
print(f"Calculation took {end - start:.2f} seconds")

gdf.to_file(output_geom_path, driver="GPKG")
```
