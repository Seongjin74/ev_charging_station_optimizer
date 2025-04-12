# EV Charging Station Optimization Analysis

This repository contains a complete research project on optimizing the placement of electric vehicle (EV) charging stations using statistical and spatial analysis techniques. The project includes a thesis document, a Jupyter Notebook containing the analysis code, and several datasets used in the study.

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Data Files](#data-files)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Citation](#citation)
- [License](#license)

## Overview

As the adoption of electric vehicles grows worldwide, the efficient placement of EV charging stations becomes an increasingly critical issue. This project analyzes EV charging station distribution using datasets from the Korea Electric Power Corporation, transportation data from the National Transportation Data Open Market, and EV registration data from the Public Data Portal. A statistical approach is used to compute a demand index for each region by normalizing both traffic data (total annual traffic, ALL_AADT) and EV registration numbers. The overall EV charging station network is then optimally redistributed by proportionally allocating the total number of stations to each region based on the computed demand index, and the supply-demand gap is quantified.

For regions with a positive gap (indicating a shortage of charging stations), a K-Means clustering algorithm is applied using geocoded candidate coordinates from traffic data (with demand weighting) to propose additional station locations. The results are visualized using interactive maps and bar charts.

## Repository Structure

├── EV_Charging_Status.xls # EV charging station status dataset from the Korea Electric Power Corporation 

├── EV_Charging_geo.zip # Shapefile containing EV charging station geographic data 

├── area_code.csv # Administrative area code data for traffic dataset 

├── ev_charging_geo_map.html # Interactive HTML map visualizing charging station locations and candidate sites 

├── ev_charging_station_optimizer.ipynb # Jupyter Notebook with the analysis code and visualization examples 

├── ev_data.csv # EV registration data (as of 2025-02-28) 

├── traffic.csv # Traffic data (with ALL_AADT values) 

├── traffic_geocoded.pkl # Pre-processed and geocoded traffic data (pickle file) 

├── ECSOA.pdf # Thesis document in Korean 

└── README.md # This README file


## Data Files

- **EV_Charging_Status.xls:** Contains the EV charging station status data from the Korea Electric Power Corporation.
- **EV_Charging_geo.zip:** A shapefile with the geographic locations and relevant attributes of the installed charging stations.
- **area_code.csv:** Provides administrative area codes used to match with the traffic dataset.
- **ev_data.csv:** EV registration data, based on data dated 2025-02-28 from the Public Data Portal.
- **traffic.csv:** Contains estimated 2021 traffic volume data (ALL_AADT) at the level of administrative subregions (읍·면·동).
- **traffic_geocoded.pkl:** The geocoded version of the traffic data, created via the Nominatim API.
- **ev_charging_geo_map.html:** An interactive HTML map displaying current EV charging station locations (blue dots) and proposed candidate locations for additional stations (red stars).
- **ECSOA.pdf:** The complete thesis document (in Korean) describing the methodology and results of the project.

## Usage

1. **Jupyter Notebook:**  
   Open `ev_charging_station_optimizer.ipynb` in Jupyter Notebook. The notebook contains detailed code to load data, compute the demand index, calculate the supply-demand gap, and generate candidate locations using K-Means clustering.
  
2. **Interactive Map:**  
   Open `ev_charging_geo_map.html` in a web browser to view the interactive map with visualizations of existing charging stations and the proposed additional candidate sites.
  
3. **Thesis Document:**  
   Review the thesis PDF (`ECSOA.pdf`) for a detailed description of the methodology, experiments, and evaluation.

## Dependencies

The project requires the following Python packages:
- geopandas
- pandas
- numpy
- plotly
- scikit-learn
- geopy

Ensure you have these packages installed. For example, you can install them using pip:

```bash
pip install geopandas pandas numpy plotly scikit-learn geopy








