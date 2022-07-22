Data Pipeline
================
Keerthana Vallamkonda
July 20, 2022

This directory contains a pipeline to produce interactive visualizations in R showing the amount of emissions(in tons) in various Virginia's county for the years 2011, 2014, and 2017 at various levels.

`Source-Maps` is an interactive shiny app used to display EPA NEI (National Emissions Inventory) data collected from 2011, 2014, and 2017 in Virginia. The shiny app output is a Virginia counties heat map based on user-specified data inputs for `Source Emissions Category` and `Year`. This app focuses on Sulfur Dioxide emissions (SO2). 
All data needed to recreate this data is provided in this directory.

# 1. Data Source
## Raw Data

All source data is in the `NEI Data` directory(on the home page). The data was downloaded from the Netional Emmissions Inventory website. All downloaded data is contained in the directory is from the year 2011 , 2014 and 2017. Additionally, we can try to download the emmissions information from other years by following the below guidelines. 

`Link` : https://www.epa.gov/air-emissions-inventories/2011-national-emissions-inventory-nei-data#dataq

**Extracting the Data in CSV format :** (use the link avove)
 
   - [X]  Filter the State from National / State / County or Tribe column
   - [X]  Filter Virgina From Geographic Aggregation Column
   - [X]  Choose the pollutant of Interest from Pollutant Column
   - [X]  Leave out the sector column and submit your choices
  

Variables in the output data set:

- `Sector` : Pollutant category
- `State` : State Details
- `State_FIPS` : population density per square mil
- `County` : County Details
- `County_FIPS` : median household income
- `Pollutant` : Pollutant Name
- `Pollutant Type` : Type of Pollutant
- `Emissions` : Amount of Emission
- `Unit Of Measure` : Tons

# 2. Data Pre-Processing Using RStudio

Libraries used for Mapping coordinates of varous counties in Virgina are 
```
   library(here)
   library(ggplot2)
   library(ggh4x)
   library(USAboundaries)
   library(sf)
   library(dplyr)
   library(data.table)
   library(stringr)
   library(stringi)
   library(writexl)
  ```
 **MAP_NEI**: Map_NEI use functions to map county's in CSV files with US boundaries geographical information and geometric coordinates that were collected from inbuilt sf library in RStudio. 
  - We use If, else statements to extract select emissions in desired category
  - Merge emissions data with county geographical data by geoid
  -  Group and summarize emissions by county (otherwise variable color fill has problems)

# 3. Data Analysis 
   **App.R** : This Shiny project combines both User Interface and Server functions to produces interactive visualizations by the users inputs through UI
   - Use  fluidpage and select input functions to display  various sector and years options via dropbox to users
   - Based on the useres input switch the data needed to be loaded accordingly to reduce the processing time
   - Use Renderplot function via server function to display the resulting visualization from the users choices through UI inputs 
