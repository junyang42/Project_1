## Processing Chicago Red Light Tickets
* using Propublica dataset (https://www.propublica.org/datastore/dataset/chicago-parking-ticket-data)

1) `ChicagoTickets` aggregate number of tickets by hour, day and month

2) `ChicagoCameraGeocode` uses Google Map API to find coordinates of camera addresses

3) `ChicagoTrafficCount` uses Chicago Data Portal API to find traffic data in the vicinity of red light cameras; calculates `number of tickets per 1,000 vehicles`

4) `TicketsHeatMap` plots ticket data into 2 heat maps; one using daily average, the other using tickets per 1,000 vehicles

5) `TicketsMapbyZipCode` look at citation counts by zip code; create box plot and map

Results and charts stored in *.csv and *.png files in the same folder