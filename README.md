# Participant catchment maps (postcode-based)

A Jupyter notebook that demonstrates a few ways to visualise **counts per Australian postcode** (e.g., study participants per postcode):

- **Option A (centroids):** point markers and proportional circles on a Folium (Leaflet) map
- **Option B (polygons):** choropleth using ABS Postal Areas (POA 2021) boundaries (GeoPandas + Matplotlib, and an interactive Folium version)

The notebook is written so you can swap the public example counts for your own cohort’s participant counts.

## What’s in this repo

```
.
├── PlotParticipantCatchment.ipynb
├── example_data.csv 
├── australian_postcodes.csv
└── README.md
```

## Data

The notebook expects three inputs:

1) `example_data.csv`  
A small CSV with **one row per postcode** (recommended) with at least:
- `postcode`
- `total_licences` (or your cohort count column)

If you have participant-level rows, aggregate first (e.g., count participants per postcode) before merging with polygons.

2) `australian_postcodes.csv`  
A postcode lookup with centroid lat/long (used for centroid maps). The notebook uses the dataset from the `matthewproctor/australianpostcodes` repo.

3) ABS POA 2021 boundary files (for polygon maps)  
Download **ASGS Edition 3 – POA 2021** boundary files (Shapefile) from the ABS, unzip, and place the folder as:

`POA_2021_AUST_GDA94_SHP/POA_2021_AUST_GDA94.shp` (plus its companion files)

## Running the notebook with your cohort data

- Replace `example_data.csv` with your dataset (or keep the example and change the filename).
- Set `COUNT_COL` to your count column (e.g., `n_participants`).
- Ensure `postcode` is present and formatted as 4-digit strings (the notebook includes a cleaning function).

## Outputs

- Interactive maps are shown inline in Jupyter.
- You can optionally export a standalone HTML file (see the “save as HTML” cell) and put it into `outputs/`.

## Attribution & licences

If you use the NSW open data example and/or ABS boundaries, keep their attribution statements in your derived outputs and repo notes.
