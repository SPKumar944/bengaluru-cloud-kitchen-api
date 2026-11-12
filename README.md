# Bangalore Cloud Kitchen Geospatial Intelligence REST API & Datasets

Production-grade geospatial intelligence, F&B competitor landscape, residential density proxies, voter demographic cohorts, and OSRM dispatch mobility matrix for cloud kitchen feasibility analysis across Bengaluru's prime food delivery corridors:
* **`560034`**: Koramangala (1,485 entities)
* **`560041`**: Jayanagar (1,602 entities)
* **`560038`**: Indiranagar (1,268 entities)
* **`560102`**: HSR Layout (1,255 entities)

**Grand Total:** 5,610 verified, geocoded entities across all 4 corridors.

---

## 🚀 Live API Portal (Browser Chrome Console)

The API documentation, catalog of access points, and interactive request inspector are hosted live at:
👉 **[https://spkumar944.github.io/bengaluru-cloud-kitchen-api/](https://spkumar944.github.io/bengaluru-cloud-kitchen-api/)**

*(All endpoints are publicly accessible with CORS enabled: `Access-Control-Allow-Origin: *`)*

---

## 📡 Base API URL

```
https://spkumar944.github.io/bengaluru-cloud-kitchen-api/api/v1
```

### Global Access Points:
* `GET /pincodes.json`: List all 4 markets with centroids, bounding boxes, feasibility scores & kitchen hub coordinates.
* `GET /summary.json`: Cross-market GMV, orders, and entity saturation statistics.
* `GET /openapi.json`: OpenAPI / Swagger 3.0 specification contract.

### Market Pincode Access Points (`560034`, `560041`, `560038`, `560102`):
* `GET /{pincode}/datasets.json`: Dataset discovery & schema definitions.
* `GET /{pincode}/fact_competitors.json`: F&B Competitor directory, cloud kitchens, QSRs, ratings, AOV & GMV.
* `GET /{pincode}/fact_demand_generators.json`: IT parks, corporate offices, colleges, transit, and hospitals.
* `GET /{pincode}/dim_housing_density_proxies.json`: Gated communities, apartments, PGs, and dwelling counts.
* `GET /{pincode}/dim_localities.json`: Sub-localities, electoral roll voting sections, and demographic cohorts.
* `GET /{pincode}/fact_popular_times.json`: 24-hour weekday vs weekend footfall & midnight surge curves.
* `GET /{pincode}/log_mobility.json`: OSRM road routes, peak lunch/dinner travel times, and SLAs.
* `GET /{pincode}/geojson.json`: Master vector GeoJSON FeatureCollection.

---

## 💻 Quick Code Usage

### JavaScript (`fetch` in Chrome Console):
```javascript
const res = await fetch("https://spkumar944.github.io/bengaluru-cloud-kitchen-api/api/v1/560034/fact_competitors.json");
const data = await res.json();
console.log(data.records);
```

### Python (`requests`):
```python
import requests

url = "https://spkumar944.github.io/bengaluru-cloud-kitchen-api/api/v1/560041/fact_competitors.json"
data = requests.get(url).json()
print(f"Total competitors in Jayanagar: {data['total_records']}")
```

### cURL:
```bash
curl -s "https://spkumar944.github.io/bengaluru-cloud-kitchen-api/api/v1/pincodes.json"
```

---

## 📊 Master File Downloads
* **Unified SQLite Database (5,610 rows):** [`data/master_cloud_kitchen.sqlite`](data/master_cloud_kitchen.sqlite)
* **Master Excel Workbooks:** Available in `data/{pincode_folder}/`
