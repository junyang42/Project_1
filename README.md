# Exploring Chicago Red Light Camera Ticket Data
#### by Araceli Buenrostro, Arthur Chan, and Jun Yang

## Project Outline
1. Explore historical time pattern of red light camera citation data
2. How Chicago compared with other cities
3. Citation counts compared to traffic pattern
4. How weather may affect citation counts
5. Hot spots/pattern across the city

## Data Source
- Chicago red light camera citations:  https://www.propublica.org/datastore/dataset/chicago-parking-ticket-data
- New York City red light camera citations:  https://data.cityofnewyork.us/City-Government/Open-Parking-and-Camera-Violations/nc67-uf89
- New Orelans red light camera citations:  https://data.nola.gov/Public-Safety-and-Preparedness/Traffic-Camera-Citations/va3u-jspg
- IDOT traffic pattern:  http://www.idot.illinois.gov/transportation-system/Network-Overview/highway-system/illinois-travel-statistics
- Chicago traffic:  https://data.cityofchicago.org/Transportation/Average-Daily-Traffic-Counts/pfsx-4n4m
- NOAA daily weather:  https://www.ncdc.noaa.gov/cdo-web/webservices/v2

## Approach
1. Condense raw data to daily citation numbers; raw data contains millions of citation entries. Each entry is one citation with address, time stamp and other info.
2. Group citation counts by various time intervals (month and hour)
   1. Explore counts patterns over time for Chicago, New York and New Orleans
   2. Explore counts patterns by hour and month
3. Compare pattern against traffic pattern (For Chicago only)

   Compared against IDOT annual average daily traffic (AADT) pattern for Northeast Urban area
   
4. Citation Counts vs. Weather
   1. Queried daily precipitation, snow and temperature data from NOAA Climate Data Online web service API
   2. Explore pattern against temperature, snow days and rainy days using scatter plots and box plots
5. Chicago Citation Counts by Neighborhood
   1. Geocoded camera locations
   2. Queried traffic counts around camera locations using Chicago Data Portal API
   3. Calculate citation per 1,000 vehicle traffic rate for each location
   4. Locate the camera locations with highest rate of citation per vehicle traffic
   5. Explore citation pattern with box plots and maps

## Analysis
### Daily Citation Counts over Time
1. Chicago
![ImageDailyPlotChicago](https://github.com/junyang42/Project_1/blob/master/Summary/Daily_Count_Chicago.png)
   1. Citations has increased significantly since spring 2014. Coincided with the period with new vendor and allegations that citations were issued with yellow lights less than 3 seconds
   2. Sharp drops on snow days (e.g. Feb 1, 2015: 397 tickets citywide)
   3. Further analysis limits to 2014 - 2018 data
  
2. New York City
![ImageDailyPlotNYC](https://github.com/junyang42/Project_1/blob/master/Summary/Daily_Count_NY.png)
   1. Regular year-to-year pattern; higher in summer
   2. Pattern similar to Chicago

3. New Orleans
![ImageDailyPlotNO](https://github.com/junyang42/Project_1/blob/master/Summary/Daily_Count_New_Orleans.png)
   1. Pattern changed in 2009 and then in 2017

### Time Pattern
#### Citations by Month (Left) and Hour (Right)
![ImageMonthPattern](https://github.com/junyang42/Project_1/blob/master/Summary/MonthlyCount.png)![ImageHourPattern](https://github.com/junyang42/Project_1/blob/master/Summary/HourCount.png)
* Lowerer in winter for Chicago and New York; lower in summer for New Orleans
* Higher during day time; two spikes (8 am and 3 pm) for New Orleans

### Chicago: Citation Pattern vs. Traffic Pattern
#### Citations by Month (Left) and Hour (Right)
![ImageMonthPatternTraffic](https://github.com/junyang42/Project_1/blob/master/Summary/Traffic%20vs%20Month%20Count.png)![ImageHourPatternTraffic](https://github.com/junyang42/Project_1/blob/master/Summary/Traffic%20vs%20Hour%20Count.png)
* citation (green) generally follow the traffic (blue dash line) pattern
* note: y-axis is percentage of analysis period. For example on the graph to the left, May has 10% of annual citations and ~8.7% of annual traffic in Chicago

### Citation vs. Weather
#### Temperature
![ImageChicagoTemp](https://github.com/junyang42/Project_1/blob/master/Summary/Temp%20vs%20Violation%20Count%20for%20CHI.png)![ImageNYCTemp](https://github.com/junyang42/Project_1/blob/master/Summary/Temp%20vs%20Violation%20Count%20for%20NY.png)![ImageNOTemp](https://github.com/junyang42/Project_1/blob/master/Summary/Temp%20vs%20Violation%20Count%20for%20NOLA.png)

#### Snow
![ImageBoxSnowChicago](https://github.com/junyang42/Project_1/blob/master/Summary/Boxplot%20of%20Snow%20for%20Chicago.png)![ImageBoxSnowNYC](https://github.com/junyang42/Project_1/blob/master/Summary/Boxplot%20of%20Snow%20for%20New%20York.png)

#### Rain
![ImageBoxPrcpChicago](https://github.com/junyang42/Project_1/blob/master/NOLA/Chicago%20Citation%20Counts%20by%20Precipitation%20Variety.png)![ImageBoxPrcpNYC](https://github.com/junyang42/Project_1/blob/master/NOLA/NY%20Citation%20Counts%20by%20Precipitation%20Variety.png)![ImageBoxPrcpNO](https://github.com/junyang42/Project_1/blob/master/NOLA/NOLA%20Citation%20Counts%20by%20Precipitation%20Variety.png)

### Citation Counts across the City
* Camera locations geocoded
* Normalize by traffic using nearby traffic study (calculated `Number of citations per 1,000 vehicular traffic`)

#### Box Plot by Zip Code
![ImageBoxZipCode](https://github.com/junyang42/Project_1/blob/master/Chicago/BoxPlotbyZipCode.png)
1. Median is 0.4 citation per 1,000 vehicular traffic (or 0.04%)
2. Top 5 Locations are 
   1. Cicero x Lawrence by I90/94 junction (Albany Park), 
   2. Jackson at Columbus Park,
   3. Ogden at Douglas Park,
   4. 445 127th St (West Pullman), and 
   5. 4124 W Foster Ave (Albany Park)

#### Heat Map
![ImageHeatMap](https://github.com/junyang42/Project_1/blob/master/Chicago/AvgPerVehicleHeatMap.png)

#### Another Map Aggregating Daily Citation Counts by Zip Code
![ImageZCMap](https://github.com/junyang42/Project_1/blob/master/Chicago/DailyTotal_ZipCode.png)

## Summary (Chicago)
* Interesing spikes in number of citations in spring 2014 without significant increase in camera locations
* Monthly and hourly citation patterns appear to follow traffic pattern
* Citation counts appear lower during snow days; higher during rainy days
* Median: 0.4 citation per 1,000 vehicular traffic (or 4 citations per 10,000)
* 2 of top 5 are in Albany Park
