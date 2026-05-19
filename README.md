# Google Earth Engine to R Workflow for Monthly NDVI and Rainfall Extraction in Kenya

This repository demonstrates a practical workflow for extracting environmental raster data from Google Earth Engine and preparing it for analysis in R.

The example workflow extracts monthly NDVI and rainfall data for three counties in Kenya:

- Narok
- Samburu
- Laikipia

The temporal range is January 2017 through December 2025.

This workflow is designed for users who process large remote-sensing datasets in Google Earth Engine, export analysis-ready GeoTIFFs, and then complete downstream analysis in R on a local computer or server.

## Workflow overview

This repository follows the workflow I commonly use for geospatial environmental data extraction:

1. Use Google Earth Engine JavaScript to access and process remote-sensing datasets.
2. Export monthly GeoTIFFs from Google Earth Engine to Google Drive.
3. Download the GeoTIFFs from Google Drive.
4. Upload the GeoTIFFs to an analysis server.
5. Use R to read, stack, summarize, plot, and prepare the rasters for downstream analysis.

Google Earth Engine is used for large-scale raster processing. R is used for organization, quality checks, visualization, extraction, and integration with other spatial, ecological, or epidemiological datasets.

## Example application

This repository demonstrates a practical workflow for extracting environmental raster data from Google Earth Engine and preparing it for analysis in R.

The example workflow extracts:

- 16-day MODIS NDVI composites
- Daily CHIRPS rainfall rasters

for Narok, Samburu, and Laikipia counties in Kenya from 2017 to 2025.

These outputs can be used for analyses related to seasonality, vegetation dynamics, rainfall patterns, animal movement, disease ecology, spatial risk modeling, and One Health surveillance.

## Data sources

The workflow uses the following Google Earth Engine datasets:

| Data type | Google Earth Engine dataset | Temporal resolution | Exported output |
|---|---|---:|---|
| NDVI | `MODIS/061/MOD13A2` | 16-day | 16-day NDVI GeoTIFFs |
| Rainfall | `UCSB-CHG/CHIRPS/DAILY` | Daily | Daily rainfall GeoTIFFs |
| Administrative boundaries | `FAO/GAUL/2015/level2` | Static | County filter |

## Repository structure

```text
gee-r-workflow-kenya/
│
├── README.md
│
├── gee/
│   └── 01_export_monthly_ndvi_chirps_geotiffs.js
│
├── R/
│   ├── 01_read_and_stack_geotiffs.R
│   ├── 02_extract_county_monthly_summaries.R
│   └── 03_plot_monthly_covariates.R
│
├── data/
│   ├── boundaries/
│   └── gee_exports/
│
└── outputs/
    ├── tables/
    ├── rasters/
    └── figures/
