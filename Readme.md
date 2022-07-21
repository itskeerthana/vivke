Data Source
================
Keerthana Vallamkonda
July 20, 2022

`Link` : https://www.epa.gov/air-emissions-inventories/2011-national-emissions-inventory-nei-data#dataq

This directory contains a pipeline to produce a data set that provides amount of emissions(in tons) of different pollutants from various county's in Virginia 
All data needed to recreate this data is provided in this directory.

## Raw Data

All source data is in the `NEI Data` directory(on the home page). The data was downloaded from the Netional Emmissions Inventory website. All downloaded data is contained in the directory is from the year 2011 , 2014 and 2017. Additionally, we can try to download the emmissions information from other years by following the below guidelines. 

Variables in the output data set:

- `Sector` : Pollutant Source
- `State` : State Details
- `State_FIPS` : population density per square mil
-`County` : County Details
- `County_FIPS` : median household income
- `Pollutant` : Pollutant Name
- `Pollutant Type` : Type of Pollutant
- `Emissions` : Amount of Emission
- `Unit Of Measure` : Tons
