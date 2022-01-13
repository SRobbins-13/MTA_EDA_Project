# Locating Vaccination Clinics Based on Subway Ridership Trends

## Abstract
The goal of this project is to determine which MTA stations would be ideal locations to set up pop-up vaccination clinics as a means of reaching under-vaccinated areas of the city. I worked with turnstile traffic data provided from the Metropolitan Transit Agency (MTA), public health data from the NYC Department of Health, and geospatial data from the City of New York to map ridership and vaccination status differences across different zip codes. I developed choropleth maps to illustrate trends across the city and isolate the zip codes with the lowest vaccination rates. Integrating the MTA traffic data, I then determined which MTA stations could be suitable to host pop-up vaccination clinics in those zip codes based on their traffic patterns.

## Design

As many people begin to return to a post-pandemic "normal", and with the possibility of new variants arising, the city of New York has a vested interest in getting as many New Yorkers vaccinated as quickly as possible. Given that the NYC subway system is one of the busiest [in the world](https://en.wikipedia.org/wiki/List_of_metro_systems#List), having pop-up or mobile vaccination clinics in MTA stations could facilitate more people getting vaccinated, as it removes an extra errand from their daily schedule. The MTA and the NYC Department of Public Health has solicited a review of MTA ridership and vaccination status across the city - organized by zip code - to find the stations with the heaviest traffic in the areas with the lowest vaccination rates as a means of selecting the best location for pop-up or mobile vaccination sites. 

## Data

To tackle this problem I used the following datasets:

1. [MTA Ridership:](http://web.mta.info/developers/turnstile.html)
> CSV file with each row representing 4-hour windows of a single turnstiles entrances and exits. This was used to determine the flow of traffic at each MTA station from 04/24/2021 to 08/06/2021. The data was pulled from this range to observe recent behavior after vaccines became readily available to the public in March/April. This file contained 3140294 rows of data with 11 attributes.
2. [Station Location:](https://data.cityofnewyork.us/Transportation/Subway-Stations/arq3-7z49)
> CSV file with the lat/long and full station name for the MTA stations. Lat/long were converted to zip code and the station names were mapped to the MTA data. This file contained 361 rows of data with 3 attributes.
3. [NYC Vaccine Administration:](https://github.com/nychealth/covid-vaccine-data/tree/main/doses/#doses-by-daycsv)
> CSV file tracking doses of the COVID-19 vaccine given daily in NYC. This file contained 244 rows of data with 11 attributes.
4. [Vaccination Percentages:](https://github.com/nychealth/covid-vaccine-data/tree/main/people#coverage-by-modzcta-allagescsv)
> CSV file tracking the vaccination status by zip code in NYC. This file contained 177 rows of data with 11 attributes.
5. [Zip code boundaries:](https://catalog.data.gov/dataset/zip-code-boundaries/resource/bc521079-c1e1-4819-8acb-5c7e7b0ec7ee)
> Shapefile containing geospatial data on NYC zip codes. This file contained 263 rows of data with 7 attributes.

## Algorithms

**_Data Cleaning_**
1. Cleaning exit and entry data and transform from cumulative counts to daily counts
2. Identifying and correct instances where turnstile counters were working in reverse or reset
3. Removeing outliers in ridership data attributed to weekends and holidays

**_Feature Engineering_**
1. Transforming latitude and longitude to zipcode via geopy function
2. Classifying zipcode vaccination status in categorical terms
3. Producing new numeric data from existing columns to highlight longer term trends
4. Normalizing station density to area zipcode for better comparisons

## Tools

- SQLAlchemy for database connection
- Pandas and Numpy for managing and analyzing data
- Matplotlib, Seaborn, plotly, and mpl_toolkits for plotting and data visualization
- Geopy for location analysis
- Geopandas for mapping and handling geospatial data
