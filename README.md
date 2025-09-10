I worked with Looker Studio to visualize a dataset for Aircraft movements. The data is from the Automatic Dependent Surveillance–Broadcast (ADS-B) system that aircraft use to broadcast their location and other data, enabling them to be more easily tracked. This is the same information that applications like "Flightradar24" use to visualize plane locations.

All aircraft have a unique ID hex value (icao) and this can be cross-referenced to a lookup table to establish airplane details, such as make, model, operator, etc. I used BigQuery tables of both historical ADS-B aircraft positional data, and of aircraft details. I then used Looker Studio to explore and visualize specific flights.

I was provided two sets of data to use in this part of the lab: aircraft details and ADS-B. The aircraft_details_matched table is a lookup table containing aircraft make, model, operator, etc. The aircraft_data_sample table contains ADS-B data collected by an ADS-B receiver located in the UK near Heathrow Airport. It has been filtered to allow it to be more easily cross referenced with the supplied details table. It contains timestamp, altitude, and positional data.

Aircrafts are identified by an icao value; this is a unique aircraft designator. The icao number is provided in the Hex column in the aircraft_data_sample table, and the icao column in the aircraft_details_matched table. Aircraft location is provided in BigQuery ST_GEOGPOINT POINT(lat, lon) format. The plane altitude alt column units are in feet.

STEPS I TOOK

1. I created three (3) pages report: RAW DATA, BLENDED DATA AND FLIGHT OPERATIONS

a. I added a table to display raw flight data. Placing Alt, timestamp and hex inside the dimension field, then we set the Alt dimension to descending. This is so that I can see the highest altitude at a glance. I observe the null (missing) values. This was a result of some ADS-B messages not containing altitude data. The flight data I used for this task had essential flight information (id number, altitude, and timestamp) but it did not provide any information about the aircraft itself (type, operator, etc.)

b. I added a second dataset: To facilitate looking up more information about the aircraft, add another data connection to a new table in BigQuery. I added a second data source and a second table chart to your report, this one containing raw information about the planes themselves. I created a new table chart and set the following in the dimension field: icao, operator, mdl, type, regid.

c. I created a new page and named it BLENDED DATA. In this task, i blended my two datasets together and then visualized the results. Blending datasets are the Looker Studio equivalent to relational database table joins. It allows to combine (blend) data from multiple data sources into a single view. I edited the dimensions according for both datasets. I used INNER JOIN, set the join condition for Hex on table 1 and icao on table 2 and then saved.

d. I added a table chart to page 2, filled the dimension fields and set the metric to Record Count (Table 1).

e. To help the flight operations team look up a single aircraft and to visualize its operations. I blended the two datasets together into a single joined data source which I displayed as both a table and as a map. I added an input field to allow the report viewer to enter the ID number for a particular plane. I used Input Box and changed the control properties to Aircraft_ID. I then added the Google Maps - Filled Map chart. I added a slider control which should work nicely in filtering by an altitude range. I also set the filter condition to greater than 0 so that the display will stop showing negative values of altitude.

