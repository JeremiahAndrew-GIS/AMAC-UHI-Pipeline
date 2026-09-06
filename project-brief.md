[project-brief.md](https://github.com/user-attachments/files/31875436/project-brief.md)
# Project Brief

## 1. The Question

Which of the six sampled localities in Abuja Municipal Area Council (AMAC)  Garki 2, Jikwoyi, Idu, Chika, Gidan Mangoro, and Gosa  have a mean Land Surface Temperature above 35°C in 2025?

## 2. Why It Matters

My undergraduate thesis already answered this once, by hand: mean LST across these six AMAC localities ran from 34.34°C to 35.22°C over 2016–2025, alongside a strong inverse NDVI/NDBI relationship (r = −0.95) as built-up area replaced vegetation. But that answer was produced through a one-off, manually-run GEE session, reproducing it next year means redoing the whole workflow by hand. A planner at AMAC, FCDA, or the Ministry of Environment shouldn't have to wait on me to re-run it. If the pipeline runs itself, the answer stays current without anyone touching the GEE code editor again.

## 3. The Data I Need

- **AMAC administrative boundary**, to clip every dataset to the study area; GADM Nigeria boundaries: https://gadm.org
- **Locality reference points** for the six sample sites (Garki 2, Jikwoyi, Idu, Chika, Gidan Mangoro, Gosa), field GPS points from my 2025 KoboToolbox survey, cross-checked against Google Earth imagery
- **Landsat 8/9 Collection 2 Level-2 surface reflectance**, 2016 and 2025, for NDVI and NDBI, USGS/NASA via Earth Engine: https://developers.google.com/earth-engine/datasets/catalog/landsat-8
- **Sentinel-2 surface reflectance**, 2016 and 2025, for LULC classification reference, Copernicus via Earth Engine: https://developers.google.com/earth-engine/datasets/catalog/sentinel-2
- **MODIS MOD11A2 Land Surface Temperature**, dry-season (Jan–Mar) 8-day composites, 2016 and 2025, NASA LP DAAC via Earth Engine: https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD11A2

## 4. Where Each Dataset Comes From

| Dataset | Source | Link |
|---|---|---|
| AMAC administrative boundary | GADM Nigeria | https://gadm.org |
| Locality reference points | My own 2025 KoboToolbox field survey | https://drive.google.com/file/d/15Ku8SG7R47YfIBlk2OG9LeBRTDF6xqWX/view?usp=drive_link |
| Landsat 8/9 Collection 2 Level-2 | USGS/NASA via Earth Engine | https://developers.google.com/earth-engine/datasets/catalog/landsat-8 |
| Sentinel-2 surface reflectance | Copernicus via Earth Engine | https://developers.google.com/earth-engine/datasets/catalog/sentinel-2 |
| MODIS MOD11A2 LST | NASA LP DAAC via Earth Engine | https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD11A2 |

## 5. What I Will Build

A Python pipeline (`ee` + `geemap`) that pulls the Landsat, Sentinel-2, and MODIS composites for AMAC and computes NDVI, NDBI, and LST for the six localities above without me touching the GEE code editor. A QGIS project reads the pipeline's output for visual QA against the known field points. A GitHub Actions workflow, on a cron schedule, re-runs the extraction periodically so the answer to the question above stays current on its own between now and month twelve.

---
*Andrew Jeremiah Ojonugwa — GeoDev Lab Africa, Cohort 2, Month 1*
