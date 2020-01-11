# Exploring Chicago Red Light Camera Ticket Data
#### by Araceli Buenrostro, Arthur Chan, and Jun Yang

## Project Outline
1. Explore historical time pattern of red light citation data
2. How Chicago compares with other cities
3. Citation counts compared to traffic pattern
4. How weather may affect citation counts
5. Hot spots/pattern across the city

## Data Source
- Chicago red light camera citations:  https://www.propublica.org/datastore/dataset/chicago-parking-ticket-data
- Chicago traffic:  data:https://data.cityofchicago.org/Transportation/Average-Daily-Traffic-Counts/pfsx-4n4m
- New York City red light camera citations:  https://data.cityofnewyork.us/City-Government/Open-Parking-and-Camera-Violations/nc67-uf89
- New Orelans red light camera citations:  https://data.nola.gov/Public-Safety-and-Preparedness/Traffic-Camera-Citations/va3u-jspg
- IDOT traffic pattern:  http://www.idot.illinois.gov/transportation-system/Network-Overview/highway-system/illinois-travel-statistics
- NOAA daily weather summary:  https://www.ncdc.noaa.gov/cdo-web/webservices/v2

## Approach
1. Group citation counts by various time intervals (month, day, hour)
   1. Explore counts patterns over time for Chicago, New York and New Orleans
   2. Explore counts patterns by hour and month
2. Compare pattern against traffic pattern (For Chicago only)

   Normalize citation counts by IDOT Northeast Urban annual average daily traffic (AADT) pattern
   
3. Citation Counts vs. Weather

   1. Queried daily precipitation, snow and temperature data from NOAA Climate Data Online web service API
   
   2. Explore pattern against temperature, snow days and rainy days using scatter plots and box plots
4. Chicago Citation Counts by Camera Location

   Explore citation pattern with box plots and maps

## Analysis
### Daily Citation Counts over Time
1. Chicago
![ImageDailyPlotChicago](https://github.com/junyang42/Project_1/blob/master/Summary/Daily_Count_Chicago.png)
   1. Citation counts increased significantly after spring 2014. It coincides with the period with new vendor and allegations that tickets were issued with yellow lights less than 3 seconds
   2. Sharp drops on snow days (e.g. Feb 1, 2015: 397 tickets citywide)
   3. Further analysis limits to 2014 and 2018 data
  
2. New York City
![ImageDailyPlotNYC](https://github.com/junyang42/Project_1/blob/master/Summary/Daily_Count_NY.png)

3. New Orleans
![ImageDailyPlotNO](https://github.com/junyang42/Project_1/blob/master/Summary/Daily_Count_New_Orleans.png)
Change in pattern after 2017

### Time Pattern
#### Citations by Month (Left) and Hour (Right)
![ImageMonthPattern](https://github.com/junyang42/Project_1/blob/master/Summary/MonthlyCount.png)![ImageHourPattern](https://github.com/junyang42/Project_1/blob/master/Summary/HourCount.png)

### Citation Pattern vs. Traffic Pattern
#### Citations by Month (Left) and Hour (Right)
![ImageMonthPatternTraffic](https://github.com/junyang42/Project_1/blob/master/Summary/Traffic%20vs%20Month%20Count.png)![ImageHourPatternTraffic](https://github.com/junyang42/Project_1/blob/master/Summary/Traffic%20vs%20Hour%20Count.png)

### Citation vs. Weather
#### Temperature
![ImageChicagoTemp](https://github.com/junyang42/Project_1/blob/master/Summary/Temp%20vs%20Violation%20Count%20for%20CHI.png)![ImageNYCTemp](https://github.com/junyang42/Project_1/blob/master/Summary/Temp%20vs%20Violation%20Count%20for%20NY.png)![ImageNOTemp](https://github.com/junyang42/Project_1/blob/master/Summary/Temp%20vs%20Violation%20Count%20for%20NOLA.png)

#### Snow Day
![ImageBoxSnowChicago](https://github.com/junyang42/Project_1/blob/master/Summary/Boxplot%20of%20Snow%20for%20Chicago.png)
Images to add Chicago and New York

### Precipitation
Images to add for three cities

### Citation counts across the city
* Camera locations geocoded
* Normalize by traffic using nearby traffic study

#### Box Plot by Zip Code
Image to add...
* At most locations, it is about 1 citation per 1000 vehicles
* Top 5 are Cicero x Lawrence, Jackson at Columbus Park, Ogden at Douglas Park, 445 127th St by Little Calumet River, and 4124 W Foster Ave (by North Branch Chicago River)

#### Heat Map
![ImageHeatMap](https://github.com/junyang42/Project_1/blob/master/Chicago/AvgPerVehicleHeatMap.png)

#### Another Map Aggregating Daily Citation Counts by Zip Code
![ImageZCMap](https://github.com/junyang42/Project_1/blob/master/Chicago/DailyTotal_ZipCode.png)
