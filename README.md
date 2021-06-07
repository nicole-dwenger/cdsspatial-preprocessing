# Spatial Analytics: Data Preprocessig for Finding Home :house:

[Description](#descripton) | [Content](#content) | [Data](#data) | [Reproducability](reproducability) | [Credits and References](#credits-and-references) | [License](#license) | [Contact](#contact)

---

## Description
This repository contains scripts and data, used for preprocessing spatial and attribute data for the boroughs in London and Bezirke in Berlin. The preprocessed data is used as input for a Shiny App, which can be found under the following link: 

## Contents 

### Dot Density Scripts 
The scripts `london/london_dot_density.rmd` and `berlin/berlin_dot_density.rmd` are used to sample dots based on population data of ethnicities in output areas of London, or sample dots based on popultion data of place of origin in Planungsräume of Berlin. The raw data can be found in `london/raw_data/ethnicity` and `berlin/raw_data/country_of_origin`, and preprocessed data is stored as `london/preprocessed_data/dot_coordinates.csv` / `london/preprocessed_data/dot_coordinates.rds` and `berlin/preprocessed_data/london_dot_coordinates.csv` / `berlin/preprocessed_data/berlin_dot_coordinates.rds`. 
The scripts were run on macOS 10.14.6, using R Version 3.6.2 and RStudio 1.2.5033.

### OSM - Culture and Religion Scripts 
The scripts `london/london_osm_culture_religion.Rmd` and `berlin/berlin_osm_culture_religion.Rmd`, sample locations of cultural places (Museums, Theates and Nighlife) and religious places (Places of Worship) for London and Berlin. The output are coordinates of the extracted locations, for cultural locations stored in `london/preprocessed_data/london_culture_locations.csv` / `london/preprocessed_data/london_culture_locations.rds` and `berlin/preprocessed_data/berlin_culture_locations.csv` / `london/preprocessed_data/berlin_culture_locations.rds`. Counts of locations per borough or district are also stored in data frames in `london/preprocessed_data/culture_counts.csv` / `london/preprocessed_data/culture_counts.csv` and `berlin/preprocessed_data/culture_counts.csv` / `berlin/preprocessed_data/culture_counts.rds`, and corresponding files for religious locations. 
The scripts were run on macOS 11.4, using R Version 4.0.2 and RStudio 1.3.1073. 

### Preprocessing 
The scripts `london/london_preprocessing.Rmd` and `berlin/berlin_preprocessing.Rmd` preprocesses as set of variables, for which raw data is stored in `london/raw_data/` and `berlin/raw_data/`. Further, it loads all the preprocessed data of the Dot Density and OSM scripts. In a last step, it joins all preprocessed data to a common dataframe, stored in `london/preprocessed_data/london.csv`/ `london/preprocessed_data/london.rds` and `berlin/preprocessed_data/berlin.csv`/ `berlin/preprocessed_data/berlin.rds`.
The scripts were run on macOS 11.4, using R Version 4.0.2 and RStudio 1.3.1073. 

### Credits 
This script contains data from the following sources: 


