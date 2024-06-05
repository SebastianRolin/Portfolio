# Zuber SQL Database.

This marks the second project within the TripleTen bootcamp, where I'll apply the SQL skills acquired through my second spring lessons

<img src="https://github.com/SebastianRolin/Portfolio/blob/main/Zuber%20Analysis/Zuber%20Database%20Scheme.png">

### File Description.

| File | Description |
| ----------- |----------- |
| README.md  | This document contains all pertinent information regarding the project, including its objectives, methodologies, and findings. |
| [Requirements.txt](https://github.com/SebastianRolin/Portfolio/blob/main/Zuber%20Analysis/Requirements.txt) | A text file listing the project's dependencies and requirements as specified by TripleTen. |
| [Zuber Database Scheme.png](https://github.com/SebastianRolin/Portfolio/blob/main/Zuber%20Analysis/Zuber%20Database%20Scheme.png) | This png shows the relationship between tables used in this projects. 
### Section Description.

| Section Title | Description |
| ----------- |----------- |
| Data Overview | This section provides a comprehensive description of the data utilized in the project. |
| Assumptions | Here, you'll find a detailed description of the assumptions made during the analysis process, derived from both the data files and assumptions provided by TripleTen. |
| Analysis Methodology | Offering a broad overview, this section outlines the process undertaken to analyze the data, spanning from initial data ingestion to final insights extraction. |
| Data Insights | Contained within this section are the key insights derived from the analysis of the dataset, shedding light on significant trends, patterns, and discoveries uncovered during the project. |

### Data Overview.
The information in the database of the taxi company are these tables with their respective information.
- `'neighborhoods table'`: Data on city neighborhoods.
    - `'name'`: Name of the neighborhood.
    - `'neighborhood_id'`: Neighborhood code.
    - `'cabs table'`: Data on taxis.
    - `'cab_id`: Vehicle code.
    - `'vehicle_id'`: The vehicle's technical ID.
    - `'company_name'`: The company that owns the vehicle.
- `'trips table'`: Data on rides.    
    - `'trip_id'`: Ride code.
    - `'cab_id'`: Code of the vehicle operating the ride.
    - `'start_ts'`: Date and time of the beginning of the ride (time rounded to the hour).
    - `'end_ts'`: Date and time of the end of the ride (time rounded to the hour).
    - `'duration_seconds'`: Ride duration in seconds.
    - `'distance_miles'`: Ride distance in miles.
    - `'pickup_location_id'`: Pickup neighborhood code.
    - `'dropoff_location_id'`: Dropoff neighborhood code.
- `'weather_records table'`: Data on weather.
    - `'record_id'`: Weather record code.
    - `'ts'`: Record date and time (time rounded to the hour).
    - `'temperature'`: Temperature when the record was taken.
    - `'description'`: Brief description of weather conditions, e.g. "light rain" or "scattered clouds".

### Assumptions.
- There is no direct link between the "trips" and "weather_records" tables in the database. However, they can be joined using the ride start time "trips.start_ts" and the weather record time "weather_records.ts".
- The primary key for the "trips" table is "trip_id".
- The primary key for the "cabs" table is "cab_id".
- The primary key for the "neighborhoods" table is "neighborhood_id".
- The primary key for the "weather_records" table is "record_id"

### Analysis Methodology.
This task involves a 6-step SQL query. The objective is to perform an exploratory data analysis to determine if the duration of rides from the “Loop” to “O’Hare International Airport” varies on rainy Saturdays. This analysis aims to identify patterns in passenger preferences and assess the impact of external factors on ride durations.

**Task N-1.** 

The first task is to find the number of taxi rides for each taxi company from November 15 to 16, 2027. To achieve this I use the following steps:

1- Select the company name from the cabs table and alias it as company_name.

2- Count the number of trips by using the COUNT function on trip_id from the trips table and 
alias it as trips_amount.

3- Join the cabs and trips tables using an INNER JOIN on the cab_id column.

4- Filter the trips to only include those that occurred between November 15 and 16, 2027, by 
casting trips.start_ts to a DATE.

5- Group the results by company name to get the trip counts for each company.

6- Order the results by trips_amount in descending order to list companies by the number of 
trips during that period.

```sql
SELECT
    cabs.company_name AS company_name,
    COUNT(trips.trip_id) AS trips_amount
FROM
    cabs
    INNER JOIN trips ON trips.cab_id = cabs.cab_id
    WHERE CAST(trips.start_ts AS date) BETWEEN '2017-11-15' AND  '2017-11-16'
GROUP BY company_name
ORDER BY trips_amount DESC;
```

**Task N-2.** 

For this task, we need to count the number of rides from the most popular taxi companies, "Flash Cab" and "Taxi Affiliation Services," and group rides from all other companies under the category "Other" for the dates of November 1-7, 2017.

1- Select the company name from the cabs table and alias it as company_name.

2- Count the number of trips by using the COUNT function on trip_id from the trips table and alias it as trips_amount.

3- Join the cabs and trips tables using an INNER JOIN on the cab_id column.

4- Filter the trips to only include those that occurred between November 1st and 7th, 2017 by casting trips.start_ts to a DATE.

5- Filter the companies to include only those whose names contain "Yellow" or "Blue".

6- Group the results by company name to get the trip counts for each relevant company.

7- Use UNION ALL to combine the results for companies with "Yellow" and "Blue" in their names.

```sql
SELECT
    cabs.company_name AS company_name,
    COUNT(trips.trip_id) AS trips_amount
FROM
    cabs
INNER JOIN trips ON trips.cab_id = cabs.cab_id
WHERE
   CAST(trips.start_ts AS date) BETWEEN '2017-11-01' AND '2017-11-07'
   AND cabs.company_name LIKE '%%Yellow%%'
GROUP BY
    company_name
UNION ALL
SELECT
    cabs.company_name AS company_name,
    COUNT(trips.trip_id) AS trips_amount
FROM
    cabs
INNER JOIN trips ON trips.cab_id = cabs.cab_id
WHERE
   CAST(trips.start_ts AS date) BETWEEN '2017-11-01' AND '2017-11-07'
   AND cabs.company_name LIKE '%%Blue%%'
GROUP BY
    company_name
```

**Task N-3.** 

For the second task, I need to count the number of rides made between November 1st and 7th, 2017. We are specifically interested in taxi companies whose names contain the words "Yellow" or "Blue".To achieve this:

1- CASE statement: Categorizes company_name into 'Flash Cab', 'Taxi Affiliation Services', or 'Other'.

- If the company name is "Flash Cab", it is labeled as 'Flash Cab'.

- If the company name is "Taxi Affiliation Services", it is labeled as 'Taxi Affiliation Services'.

- For all other company names, they are labeled as 'Other'.

2- COUNT function: Counts the number of trips (trip_id) and aliases it as trips_amount.

3- INNER JOIN: Joins the cabs and trips tables on cab_id.

4- WHERE clause: Filters the trips to include only those between November 1 and 7, 2017.

5- CAST(trips.start_ts AS DATE) ensures the date is in the correct format for comparison.

6- GROUP BY clause: Groups the results by the categorized company name (company).

7- ORDER BY clause: Sorts the results in descending order by trips_amount.

```sql
SELECT
    CASE WHEN company_name =  'Flash Cab' THEN 'Flash Cab'
    WHEN company_name = 'Taxi Affiliation Services' THEN 'Taxi Affiliation Services'
    ELSE 'Other'
    END AS company,
    COUNT (trips.trip_id) AS trips_amount
FROM
    cabs
    INNER JOIN trips ON trips.cab_id = cabs.cab_id
WHERE CAST(trips.start_ts AS date) BETWEEN '2017-11-01' AND  '2017-11-07'
GROUP BY company
ORDER BY trips_amount DESC;
```

### Data Insights.
1. The taxi company "Flash Cab" recorded the highest number of rides on November 15th-16th, 2017, with a total of 19,558 trips.
2. For taxi companies containing the keyword "Yellow" or "Blue," "Blue Diamond" had the highest number of rides during November 1st-7th, 2017, with 6,764 trips.
3. When comparing "Flash Cab" and "Taxi Affiliation Services" with all other companies for November 1st-7th, 2017, the total number of rides from "Other" companies was significantly higher than the combined total of the two most popular companies.
4. The SQL "neighborhood_id" identifiers for the O'Hare and Loop neighborhoods are 63 and 50, respectively.
5. Each hour was assigned a designated weather condition, initially marked as "Good."
6. A SQL table was generated to display all rides starting in the Loop on a Saturday and ending at O'Hare, including the start time, weather conditions, and duration.
