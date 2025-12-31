# NOAA Tides and Currents Data

This R script automates the retrieval and organization of metadata and time series data from the NOAA Tides and Currents API for specified station IDs and years. It is designed for those who need historical water level and meteorological data and have the specific station id.

## Features
- Downloads station metadata (including sensors, bins, deployments, and available products)
- Fetches water level and meteorological data for specified years and stations
- Organizes output into station-specific directories with clear file structure
- Handles missing data 
- Optional Plots data for given stations


## Requirements
- R (version 4.0 or higher recommended)
- The following R packages:
  - httr
  - jsonlite
  - lubridate
  - dplyr
  - ggplot2

You can install the required packages with:

```r
install.packages(c("httr", "jsonlite", "lubridate", "dplyr","ggplot2"))
```

## Usage
1. Clone this repository or download the script.
2. Edit the script to specify your desired station IDs and years.
3. Run the script in your R environment:
   
   ```r
   source("noaa_downloader.R")
   ```
4. Output will be saved in station-specific folders in your working directory.

## Output Structure
```
<station_id>/
  ├── <station_id>_metadata.json
  ├── Water Levels/
  │     └── <param>_<year>.csv
  └── Meteorological/
        └── <param>_<year>.csv
```

## Customization
- To add more stations, update the `station_ids` vector in the script.
- To change the years, update the `years` vector.
- To add or remove data products, modify the `wl_params` and `met_params` vectors.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Disclaimer
This script is provided as-is and is not affiliated with NOAA. Please check NOAA's data usage policies before using the data for publication or commercial purposes.
