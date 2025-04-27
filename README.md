# Wildfire Analysis & Prediction

### Description
This dataset was created to predict wildfires for upto 6 months in advance by processing current day parameters.  The dataset could be used to train classification models for prediction.

### Region of Interest 
Los Angeles

### Layer CRS
EPSG:32611 - WGS 84 / UTM zone 11N

### Pixel Size
90mx90m

### Attribute Description
- **NDVI :** Normalized Difference Vegetation Index. Used to check if the vegetation is healthy/green. Range [-1, 1].
- **ELEVATION :** Shows the elevation of points from sea level in meters.
- **SLOPE :** Shows the difference between elevation points
- **ASPECT :** Shows the direction of the slope in degrees clockwise starting from North - 0.
- **AWND :** Average wind speed for the day.
- **TMAX :** Maximum temperature for the day.
- **TMIN :** Minimum temperature for the day.
- **WDF2 :** Direction of fastest 2-min wind.
- **WSF2 :** Speed of fastest 2-min wind.
- **WILDFIRE :** (Heatmap) Interpolated brightness of wildfires for next 6 months.

### Data Sources
- **DEM**
    - Data Source : [USGS](https://earthexplorer.usgs.gov/)
    - Satellite : SRTM 1 Arc-Second Global
- **NDVI**
    - Data Source : [USGS](https://earthexplorer.usgs.gov/)
    - Satellite : Landsat 8-9 OLI/TIRS C2 L2
- **Weather/Climate**
    - Data Source : [NOAA](https://www.ncei.noaa.gov/)
    - Product : GHCND
- **Wildfire Points**
    - Data Source : [NASA-FIRMS](https://firms.modaps.eosdis.nasa.gov/)
    - Product : MODIS C6.1

### Timestamp/Timerange
- **DEM :** *time independent*
- **NDVI :**
    - 26th Feb 2020
    - 30th Jan 2022
    - 9th Nov 2023
- **Weather/Climate :**
    - 26th Feb 2020
    - 30th Jan 2022
    - 9th Nov 2023
- **Wildfire Points : _~6 months from_**
    - 26th Feb 2020
    - 30th Jan 2022
    - 9th Nov 2023

### Geospatial Processing
- **NDVI :**   
    - Raster calculator
- **SLOPE, ASPECT :**  
    - Terrain Analysis
- **Weather :**  
    - IDW Interpolation
    - Distance coefficient : 1.5
    - Pixel size: 30m
- **Wildfire :**  
    - Heatmap Interpolation
    - Radius : 2km
    - Weight field: brightness
    - Kernel type: Quartic



