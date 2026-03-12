# MODIS Snow Cover Gap-Filling Using Python API (Xee): Langtang Basin 
## Overview

Satellite-based snow monitoring is essential for understanding mountain hydrology, glacier dynamics, and seasonal water availability in high-altitude regions. However, optical satellite products such as MODIS snow cover frequently contain data gaps caused by cloud contamination and missing observations.

This project demonstrates a gap-filling workflow for MODIS Snow Cover data using the Google Earth Engine Python API and Xee, enabling efficient access and processing of Earth Engine ImageCollections as xarray datasets.

Using the Langtang Basin in Nepal as a case study, the workflow retrieves MODIS snow cover data, converts it into an xarray dataset, and applies temporal rolling median interpolation to fill missing values. The processed dataset is then exported as a NetCDF file for further scientific analysis.

This approach illustrates how Earth observation datasets can be integrated with Python-based data science tools to improve the usability of satellite products for environmental research.

## Study Area
The analysis focuses on the Langtang Basin, located in the central Himalayas of Nepal.

1. The region is characterized by:
- High elevation terrain
- Extensive seasonal snow cover
- Glacier-fed river systems
- Strong sensitivity to climate variability

2. Bounding box used in the study:
- Longitude: 85.25 – 85.75
- Latitude: 28.05 – 28.40

## Dataset
MODIS Daily Snow Cover Product
- Dataset: MODIS/061/MOD10A1
- Provider: NASA MODIS Snow Products

Key characteristics:
1. Spatial Resolution: 500 meters
2. Temporal Resolution: Daily

Snow detection based on Normalized Difference Snow Index (NDSI)

Variable used:
- NDSI_Snow_Cover
This variable represents the percentage of snow cover detected within each pixel.

## Tools & Technologies
This workflow integrates cloud-based geospatial processing with Python scientific computing tools.
1. Google Earth Engine (GEE) – satellite data access and processing
2. geemap – visualization and Earth Engine interaction
3. xee – Earth Engine to xarray data bridge
4. xarray – multidimensional data analysis
5. NetCDF4 – exporting datasets for scientific workflows
6. Python – computational environment

### Figure 1. Original MODIS Snow Cover (Before Gap Filling)
<img width="1999" height="1490" alt="11" src="https://github.com/user-attachments/assets/aaac7ab0-af79-4c23-b937-7c576294a97c" />

### Figure 2. Gap-Filled MODIS Snow Cover Dataset
<img width="1999" height="1490" alt="12" src="https://github.com/user-attachments/assets/5f0457fd-9dcc-4862-b4d2-618b68cb4923" />

## Results
- The raw MODIS snow cover images contain significant missing pixels caused by cloud cover, particularly during early January. These gaps make it difficult to analyze spatial and temporal snow patterns.
- After applying the 10-day rolling median gap-filling method, the dataset becomes more spatially continuous, reducing missing values and revealing clearer snow cover patterns. Persistent snow cover is visible in higher elevations of the Langtang Basin, while lower elevations show more variable snow presence.
- Overall, the gap-filling approach improves the usability of MODIS snow data for time-series analysis and hydrological studies.

## Notes
1. MODIS snow products are widely used for large-scale snow monitoring.
2. Cloud cover remains a major challenge in optical satellite snow detection.
3. The rolling median approach provides a simple yet effective method for reconstructing missing observations.
4. Exporting to NetCDF format enables compatibility with scientific modeling workflows.

## Limitations
1. MODIS spatial resolution (500 m) may not capture very small snow patches.
2. Gap filling through temporal smoothing may introduce slight biases during rapid snowmelt or snowfall events.
3. The study area is defined using a bounding box rather than a precise watershed boundary.
4. The analysis covers a short time period (2020–2021) and does not represent long-term snow trends.
