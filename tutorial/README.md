
# OpenRouteService API with Docker

This directory provides instructions on how to:

1. Run the **OpenRouteService (ORS)** API using **Docker**.
2. Access and use the API using **R** and **Python** scripts.


## Step 1: Clone the OpenRouteService Repository

Open a terminal and run the following command:

```bash
git clone https://github.com/NewYorkCityCouncil/openrouteservice
cd openrouteservice
```

---

## Step 2: Download Map Data for New York

Download the New York map data from [Geofabrik](https://download.geofabrik.de/north-america/us/new-york.html) into the appropriate folder:

```bash
mkdir -p ors-docker/files
curl -o ors-docker/files/new-york-latest.osm.pbf https://download.geofabrik.de/north-america/us/new-york-latest.osm.pbf
```

---

## Step 3: Start the Docker Container

1. **Ensure Docker is running**  
   Launch Docker Desktop to start the Docker daemon.

2. **Navigate to the cloned ORS repository** (if not already there):

   ```bash
   cd openrouteservice
   ```

3. **Start the ORS container**:

   ```bash
   docker compose up -d
   ```

   > This process may take a few minutes depending on your system.

4. **Check API status**:

   Run the following command to check if the ORS API is ready:

   ```bash
   curl http://127.0.0.1:8080/ors/v2/health
   ```

   If the API is running, the response should be:

   ```json
   {"status":"ready"}
   ```

---

## Step 4: Access the API using R or Python

Once the ORS API is ready, you can interact with it using the provided:

- **R script** (e.g., `r-walkthrough.Rmd`)
- **Python script** (e.g., `python-walkthorugh.ipynb`)

These scripts should contain sample requests such as directions, distance matrix, or isochrones. Make sure they point to your local instance at `http://localhost:8080/ors`.

