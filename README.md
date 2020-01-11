# Exploring Chicago Red Light Camera Ticket Data
#### by Araceli Buenrostro, Arthur Chan, and Jun Yang

## Project Outline
1. Time pattern of red light ticket data
2. How Chicago compares with other cities
3. Ticket counts compared to traffic pattern
4. How weather may affect ticket counts
5. Hot spots 

## Data Source
- Chicago red light camera citations:  https://www.propublica.org/datastore/dataset/chicago-parking-ticket-data
- Chicago traffic:  data:https://data.cityofchicago.org/Transportation/Average-Daily-Traffic-Counts/pfsx-4n4m
- New York City red light camera citations:  https://data.cityofnewyork.us/City-Government/Open-Parking-and-Camera-Violations/nc67-uf89
- New Orelans red light camera citations:  
- IDOT traffic pattern:  http://www.idot.illinois.gov/transportation-system/Network-Overview/highway-system/illinois-travel-statistics
- NOAA daily weather summary:  https://www.ncdc.noaa.gov/cdo-web/webservices/v2

## Approach
1. Group citation counts by various time intervals (month, day, hour)

   a) Explore counts patterns over time for Chicago, New York and New Orleans
   
   b) Explore counts patterns by hour and month
2. Compare pattern against traffic pattern (For Chicago only)

   Normalize citation counts by IDOT Northeast Urban annual average daily traffic (AADT) pattern
   
3. Citation Counts vs. Weather

   a) Queried daily precipitation, snow and temperature data from NOAA Climate Data Online web service API
   
   b) Explore pattern against temperature, snow days and rainy days using scatter plots and box plots
4. Chicago Citation Counts by Camera Location

   Explore citation pattern with box plots and maps


