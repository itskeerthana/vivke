Data Source
================
Keerthana Vallamkonda
July 20, 2022

`Link` : https://www.epa.gov/air-emissions-inventories/2011-national-emissions-inventory-nei-data#dataq

This directory contains a pipeline to produce a data set that provides amount of emissions(in tons) of different pollutants from different county's in Virginia 
All data needed to recreate this data is provided in this directory.

## Raw Data

All source data is in the `raw_data` directory. The data was downloaded from the census social explorer website by Fei Carnes, a former research assistant working for Dr. Francesca Dominici, who assisted with geographically available data. All downloaded data is contained in the directory `raw_data/raw_census`. The data within that directory is stored with the structure `<variable>/<census or acs>/zcta/<year>`. In that directory is the CSV and readme downloaded from the Social explorer. To reacquire the source data, the same report number (found in the included readme) should be downloaded from social explorer.

Additionally in this directory we have a list of all ZCTAs (`zcta_list`)
and a crosswalk going from ZCTAs to zip code
(`Zip_to_ZCTA_crosswalk_2015_JSI.csv`)
