# Spatial Analytics: Data Preprocessig for Finding Home :house:

[Description](#descripton) | [Content](#content) | [Reproducability](reproducability) | [Data Sources](#data-sources) | [License](#license) | [Contact](#contact)

---

## Description
This repository contains scripts and data, used for pre processing spatial and attribute data for the boroughs in London and Bezirke in Berlin. The preprocessed data is used as input for a Shiny App, which can be found under the following link: 
https://cds-spatial.shinyapps.io/finding-home/ 

## Content
This repository contains several corresponding scripts for pre processing data of London and Berlin, which are stored in their corresponding directories. However, scripts the scripts for the two cities fulfill similar functions, as described below: 

### Dot Density Scripts 
Scripts called `{city}_dot_density.rmd` were used to sample dots based on population data of ethnicities in output areas of London, or based on population data of place of origin in Planungsräume of Berlin. The raw data can be found in `london/raw_data/ethnicity` and `berlin/raw_data/country_of_origin`, and pre-processed data is stored as `{city}/preprocessed_data/{city}_dot_coordinates.csv/rds` for each city.  

### OSM - Culture and Religion Scripts 
Scripts called `{city}_osm_culture_religion.Rmd`, extract locations of cultural places (Museums, Theaters and Nightlife) and religious places (Places of Worship) for London and Berlin. The output are coordinates of the extracted locations, for cultural locations stored in `{city}/preprocessed_data/{city}_culture_locations.csv/rds`. Counts of locations per borough or district are also stored in data frames in `{city}/preprocessed_data/{city}_culture_counts.csv/rds` and corresponding files for religious locations.  

### Preprocessing 
Scripts called `{city}_preprocessing.Rmd` preprocess all relevant variables for the two cities, for which raw data is stored in corresponding `{city}/raw_data/` directories. Further, it loads the pre-processed data of Dot Density Scripts and OSM - Culture and Religion Scripts. In a last step, it joins all pre-processed data to a common data frame, stored in `london/preprocessed_data/london.csv`/ `london/preprocessed_data/london.rds` and `berlin/preprocessed_data/berlin.csv`/ `berlin/preprocessed_data/berlin.rds`.  

## Reproducability 
The scripts were developed on macOS 11.4, using R Version 4.0.2 and RStudio 1.3.1073. Detailed information about the used packages and their versions are stored in a file called `sessionInfo.txt`. If you which to clone files to run them locally, you can run the following commands in the terminal: 

```bash
git clone https://github.com/nicole-dwenger/cdsspatial-preprocessing.git
```

All required packages are loaded at the beginning of each script. If you need to install some of these packages, you can use the following commands in R: 

```r
# Example of installing raster package
install.packages("raster")
```

### Data Sources
The data was extracted from several sources, to which references are provided below: 

##### London 
This project contains Ordnance Survey data © Crown copyright and database right 2011.  
This project contains National Statistics data © Crown copyright and database right 2011.  

- Greater London Authority (2011a) London Borough Profiles and Atlas [Data Set, Web app].  
Retrieved May 2021 from https://data.london.gov.uk/dataset/london-borough-profiles. Licensed under UK Open Government License.
- Greater London Authority (2011b). Statistical GIS Boundary Files for London [Data Set].  
Retrieved May 2021 from https://data.london.gov.uk/dataset/statistical-gis-boundary-files-london. Licensed under UK Open Government Licence.
- Greater London Authority. (2020). 2019-based trend projections, Central Range (upperbound) [Data Set].  
Retrieved May, 2021 from https://data.london.gov.uk/dataset/gla-population-projections-custom-age-tables?q=ae%20demographics. Licensed under UK Open Government License.
- Metropolitan Police Service. (2021). MPS Borough Level Crime (most recent 24 months) [Data Set].  
Retrieved May 2021 from https://data.london.gov.uk/dataset/recorded_crime_summary. Licensed under UK Open Government Licence.
- Office for National Statistics (2011). Census Data 2011 - Workday Population - Ethnic Group. [Data	Set]. Retrieved May 2021, from https://www.nomisweb.co.uk/census/2011/wd201ew.  
Licensed under UK Open Government License.
- Office for National Statistics (2021). Private rental market in London: January to December 2020 [Data Set]. Retrieved May 2021 from  
https://www.ons.gov.uk/peoplepopulationandcommunity/housing/adhocs/12871privaerentalmarketinlondonjanuarytodecember2020. Licensed under UK Open Government License.
- UCL (on behalf of Greater London Authority), 2014. London Output Area Classification [Data Set]. Retrieved May 2021, from
https://data.london.gov.uk/dataset/london-area-classification. Licensed under CC.
 
##### Berlin

- Amt für Statistik Berlin-Brandenburg (2015a). Lebensweltlich orientierte Räume (LOR)-Planungsräume [Data Set].  
Retrieved May 2021, through FIS-Broker, from https://fbinter.stadt-berlin.de/fb/index.jsp. Licensed under CC BY-SA 3.0 DE
- Amt für Statistik Berlin-Brandenburg (2015b). Lebensweltlich orientierte Räume (LOR)-Prognoseräume. [Data Set].  
Retrieved May 2021, through FIS-Broker, from https://fbinter.stadt-berlin.de/fb/index.jsp. Licensed under CC BY-SA 3.0 DE.
- Amt für Statistik Berlin-Brandenburg (2019). Einwohnerregisterstatistik Berlin [Data Set]. Retrieved May 2021, from Statistisches Informationssystem Berlin Brandenburg, https://www.statistik-berlin-brandenburg.de/webapi/jsf/tableView/tableView.xhtml. Licensed under CC BY 3.0 DE. 
- Geoportal Berlin (2017). Bezirksgrenzen, ESRI Shapefile [Data Set]. Retrieved May 2021, from https://daten.odis-berlin.de/de/dataset/bezirksgrenzen/. 
- Geoportal Berlin (2019). Wohnatlas Berlin - Angebotsmieten 2018 (in EUR/m² monatlich, netto kalt). [Data Set]]. Retrieved May 2021, through FIS-Broker, https://www.stadtentwicklung.berlin.de/wohnen/wohnatlas/index.shtml. Licensed under Data licence Germany – attribution – Version 2.0 
- Polizei Berlin (2020). Polizeiliche Kriminalstatistik [Data Set]. Retrieved May 2021 from https://daten.berlin.de/datensaetze/kriminalitätsatlas-berlin. Licensed under CC BY-SA 3.0 DE.

##### Global

- © European Union, Copernicus Land Monitoring Service, European Environment Agency (EEA) (2018a). High Resolution Layer: Imperviousness Density (IMD) 2018 [Data Set]. Retrieved May 2021, from https://land.copernicus.eu/pan-european/high-resolution-layers/imperviousness/statusmaps/imperviousness-density-2018?tab=metadata. Licensed under Copernicus data and information policy Regulation (EU).
- © European Union, Copernicus Land Monitoring Service, European Environment Agency (EEA) (2018b). High Resolution Layer: Tree Cover Density (TCD) 2018 [Data Set]. Retrieved from May 2021, from https://land.copernicus.eu/pan-european/high-resolution-layers/forests/tree-cover-denity/status-maps/tree-cover-density-2018?tab=mapview. Licensed under Copernicus data and information policy Regulation (EU)
- Google (n.d.). [Google Maps coordinates for defined PoI]. Retrieved 1 June 2021 from https://www.google.de/maps.
- OpenStreetMap contributors. (2021) Data of Places of Worship, Museums, Theaters and Nightlife
[Data Sets from 2021]. Retrieved May 2021. Licensed under Open Data Commons Open Database License. 

### License 
<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/3.0/80x15.png" /></a> This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.

### Contact 
If you have any questions, feel free to contact us at [orla.mallon95@gmail.com](orla.mallon95@gmail.com]) or [nicole.dwengr@gmail.com](nicole.dwengr@gmail.com).
