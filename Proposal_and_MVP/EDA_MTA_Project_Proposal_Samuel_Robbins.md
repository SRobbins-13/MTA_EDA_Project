# Exploratory Data Analysis Project Proposal
#### Samuel Robbins

### Premise/Question:
As the city of New York continues to monitor the spread of COVID-19 and ongoing vaccination efforts, the MTA - in partnership with various public health agencies - wants to plan pop-up vaccination clinics at key spots within the city. The subways are an integral part of the culture of New York City and link centers of activity across the five boroughs, so having clinics close to subway stations could facilitate more people getting vaccinated without having to dramatically alter their daily routine. The MTA wants to understand where the highest volume subway stations are in relation to the vaccination sites across the city, and explore if there is any correlation between average distance between a subway station and a vaccination clinic and a neighborhoods present rate of vaccinated persons. This analysis will allow public health officials to more efficiently plan pop-up clinics to reach the neighborhoods with the lowest vaccination rate.

### Data Description:
- Weekly [MTA data](http://web.mta.info/developers/turnstile.html) of entries and exits at different stations combined with location data for the subway stations. This will allow me to determine which stations see the highest flux of passengers and locate peak times of day for subway ridership. I will be using data from January-July of 2021 to see how patterns changed before and after vaccines became readily available to New Yorkers. 
- Additional dataset on the [location of COVID-19 vaccination clinics](https://vaccinefinder.nyc.gov/locations)  to calculate the average distance between subway stations and vaccine clinics.
- Dataset on [vaccinations by ZIP code](https://www1.nyc.gov/site/doh/covid/covid-19-data-vaccines.page#byzip) to determine if average distance to a vaccination clinic is related to the overall vaccination rate of a neighborhood.

##### Potential Additional Datasets:
- The size of NYC subway stations to group stations by similar size in an effort to make more robust comparisons
- [Income level](https://data.cccnewyork.org/data/map/66/median-incomes#66/39/6/107/62/a/a) of different zip codes to determine if there are equity issues in the distance New Yorkers must travel from a subway stop to a vaccine clinic.

### Tools:
- SQL to explore and clean the data
- Pandas for data analysis and database/dataframe manipulation
- Matplotlib/seaborn for visualization - plots, maps, graphs, etc.

### Minimum Viable Product:
A minimum Viable Product for this project would be tabular data on the distance between subway stations and vaccination clinics linked to volume of subway ridership with accompanying graphs and maps.
