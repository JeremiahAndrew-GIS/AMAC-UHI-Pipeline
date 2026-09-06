[README.md](https://github.com/user-attachments/files/31875292/README.md)
# AMAC Urban Heat Island Pipeline

Which of AMAC's six sampled localities Garki 2, Jikwoyi, Idu, Chika, Gidan Mangoro, and Gosa have a mean Land Surface Temperature above 35°C in 2025?

Built over twelve months with GeoDev Lab Africa, Cohort 2. See [`project-brief.md`](./project-brief.md) for the full brief.

## Datasets used

| Dataset | Source |
|---|---|
| AMAC administrative boundary | [GADM Nigeria](https://gadm.org) |
| Locality reference points (6 sample sites) | Own 2025 KoboToolbox field survey  https://drive.google.com/file/d/15Ku8SG7R47YfIBlk2OG9LeBRTDF6xqWX/view?usp=drive_link |
| Landsat 8/9 Collection 2 Level-2 SR | [USGS/NASA via Earth Engine](https://developers.google.com/earth-engine/datasets/catalog/landsat-8) |
| Sentinel-2 SR | [Copernicus via Earth Engine](https://developers.google.com/earth-engine/datasets/catalog/sentinel-2) |
| MODIS MOD11A2 LST | [NASA LP DAAC via Earth Engine](https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD11A2) |

## What this repo builds toward

A Python pipeline (`ee` + `geemap`) that computes NDVI, NDBI, and LST for the six AMAC localities above, QA'd in QGIS against known field points, and re-run on a schedule via GitHub Actions, so the answer above stays current without manual GEE work.

## Status

Month 1, Week 1: question drafted, data sources checked and linked above, repository created.

---
Andrew Jeremiah Ojonugwa
