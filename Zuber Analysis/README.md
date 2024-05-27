# File name: Zuber SQL Database.

This marks the second project within the TripleTen bootcamp, where I'll apply the SQL skills acquired through my second spring lessons

<img src="https://github.com/SebastianRolin/Portfolio/blob/main/Zuber%20Analysis/Zuber%20Database%20Scheme.png">

### File Description.

| File | Description |
| ----------- |----------- |
| README.md  | This document contains all pertinent information regarding the project, including its objectives, methodologies, and findings. |
| [Requirements.txt](https://github.com/SebastianRolin/Portfolio/blob/main/Vacation%20Rental%20Market%20Analysis/Requirements.txt) | A text file listing the project's dependencies and requirements as specified by TripleTen. |
| [Zuber Database Scheme.png](https://github.com/SebastianRolin/Portfolio/blob/main/Zuber%20Analysis/Zuber%20Database%20Scheme.png) | This png shows the relationship between tables used in this projects. 
### Section Description.

| Section Title | Description |
| ----------- |----------- |
| Data Overview | This section provides a comprehensive description of the data utilized in the project, outlining the files and their corresponding sheets. |
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

### Assumptions:
- There is no direct link between the "trips" and "weather_records" tables in the database. However, they can be joined using the ride start time "trips.start_ts" and the weather record time "weather_records.ts".
- The primary key for the "trips" table is "trip_id".
- The primary key for the "cabs" table is "cab_id".
- The primary key for the "neighborhoods" table is "neighborhood_id".
- The primary key for the "weather_records" table is "record_id"

### Analysis Methodology:
This task involves a 6-step SQL query. The objective is to perform an exploratory data analysis to determine if the duration of rides from the “Loop” to “O’Hare International Airport” varies on rainy Saturdays. This analysis aims to identify patterns in passenger preferences and assess the impact of external factors on ride durations.

### Data Insights:
1. The taxi company "Flash Cab" recorded the highest number of rides on November 15th-16th, 2017, with a total of 19,558 trips.
2. For taxi companies containing the keyword "Yellow" or "Blue," "Blue Diamond" had the highest number of rides during November 1st-7th, 2017, with 6,764 trips.
3. When comparing "Flash Cab" and "Taxi Affiliation Services" with all other companies for November 1st-7th, 2017, the total number of rides from "Other" companies was significantly higher than the combined total of the two most popular companies.
4. The SQL "neighborhood_id" identifiers for the O'Hare and Loop neighborhoods are 63 and 50, respectively.
5. Each hour was assigned a designated weather condition, initially marked as "Good."
6. A SQL table was generated to display all rides starting in the Loop on a Saturday and ending at O'Hare, including the start time, weather conditions, and duration.
