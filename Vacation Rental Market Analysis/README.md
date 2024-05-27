# File Title: Vacation Rental Market Analysis.

Throughout this project, I effectively applied the knowledge and skills acquired during my participation in the "Advanced Spreadsheets" course within the TripleTen curriculum. Over the duration of the course, which coincided with my first spring term, I delved into various topics essential for proficient spreadsheet utilization. These encompassed understanding spreadsheet structures, managing diverse data types, harnessing a multitude of functions, executing data cleaning and pre-processing techniques, and leveraging pivot tables and charts for enhanced communication of analytical findings. The comprehensive training received through the course enabled me to adeptly navigate and manipulate data, resulting in more insightful and impactful analyses within the context of this project.

[<img src="https://github.com/SebastianRolin/Portfolio/blob/main/Extra%20Resources/Vacation%20Rental%20Market%20Analysis%20Snapshot.png">](https://docs.google.com/spreadsheets/d/16BqeMVC8iU_18BjpdTLVXn98V5ZIRwNHG6GKz3_FX9Q/edit?pli=1#gid=122074218)


For a brief overview, you can watch the explanatory video [here](link to video), and access the project spreadsheet [here](https://docs.google.com/spreadsheets/d/16BqeMVC8iU_18BjpdTLVXn98V5ZIRwNHG6GKz3_FX9Q/edit?pli=1#gid=122074218).

### File Description.

| File | Description |
| ----------- |----------- |
| README.md | This document contains all pertinent information regarding the project, including its objectives, methodologies, and findings. |
| Requirements.txt | A text file listing the project's dependencies and requirements as specified by TripleTen. |
| Vacation Rental Market Analysis | The dataset supplied by TripleTen, utilized extensively throughout the project for analysis and insights generation.|
| Review N°1.1, 1.2, 1.3 & Final Review | A visual representation of feedback and comments provided by the project reviewer, offering insights into the project's evaluation and areas for improvement.  |

### Section Description.

| Section Title | Description |
| ----------- |----------- |
| Data Overview | This section provides a comprehensive description of the data utilized in the project, outlining the files and their corresponding sheets. |
| Assumptions | Here, you'll find a detailed description of the assumptions made during the analysis process, derived from both the data files and assumptions provided by TripleTen. |
| Analysis Methodology | Offering a broad overview, this section outlines the process undertaken to analyze the data, spanning from initial data ingestion to final insights extraction. |
| Data Insights | Contained within this section are the key insights derived from the analysis of the dataset, shedding light on significant trends, patterns, and discoveries uncovered during the project. |

### Data Overview.
The data file was provided by TripleTen, the files is a CSV and all the processes were made using Google Spreadsheets.
- `'nyc_airbnb_data.csv'`: The data from this file is from the airbnb listing from the month of september 2022 and it contains the following sheets.
    - `'Data_dictionary(Raw)'`: Small description of the fields from the listings and calendar sheet, it also provides the data types.
    - `'listings(Raw)'`: Here we have in each row all the listings properties available.
    - `'calendar(Raw)'`: A list of the properties availability for 30 days.
    - `'Assumptions & Change Log:`: A sheet where we write down all the assumptions made during the analysis process and the records of the modifications made to the file and the versions.
    - `'Listings(Processed)'`: The cleaned version of the listings(Raw).
    - `'Neighborhood with Most Reviews'`: A pivot table where we can see the neighborhood with most reviews.
    - `'Neighborhood with Most Reviews and Sizes'`: A pivot table showing the most review neighborhoods from the prior pivot table now separating the count of reviews by size
    - `'Recommended Neighborhood to invest'`: A pivot table showcasing the recommended neighborhood base in the average price, average occupancy rate, estimated annual revenue and the number of rental properties available to invest.
    - `'Calendar(Processed)'`: The clean version of Calendar(Raw)
    - `'Average Occupancy for each listing'`: A pivot table with the average occupancy rate from each listing using listing_id.
    - `'Best Day for Renting'`: Using the information from Calendar(Processed) I created a pivot table to understand what days have a higher occupancy rate.

### Assumptions:
- Listings without data in the columns first and last review are going to be categorized as listings never been rented and therefore removed from the analysis.
- I’m going to use “number_of_reviews_ltm” as a proxy for gauging how frequently the listings are rented.
- Listings without reviews over the last 12 months are removed.
- The listings will have a maximum of 7 nights or less since the client is focusing only on vacation rentals.
- I'm going to use only properties with a rent price between $200.00 to $1000.00 

### Analysis Methodology:
In the initial data exploration phase, I identified and processed columns containing actionable insights, creating a refined version of the dataset. I performed data cleansing by removing redundant columns, filtering out listings without reviews, and standardizing data formatting. Leveraging pivot tables, I extracted key insights such as occupancy rates, estimated revenue, optimal rental days, and ROI analysis.

### Data Insights:
1. Top 10 Attractive Neighborhoods: In this analysis, the research has unveiled the top 10 most attractive neighborhoods for vacation rentals, each presenting unique opportunities for investment and revenue generation. These neighborhoods include Hell's Kitchen, Lower East Side, Harlem, Midtown, Upper West Side, Chelsea, East Village, East Harlem, West Village, and Nolita. Each neighborhood offers distinct characteristics and appeal, providing potential investors with a diverse range of options to explore.		
2. Popular Vacation Rental Sizes: Additionally, the analysis highlights trends in vacation rental sizes and occupancy rates. One-bedroom units emerge as the most popular configuration overall, with Lower East Side exhibiting particularly high demand for this size. Furthermore, 2-bedroom units in Hell's Kitchen and studio apartments in Midtown are identified as desirable options for renters.			
3. Occupancy Rate by Day: Moreover, the study delves into the dynamics of occupancy rates by day, revealing that Mondays and Tuesdays consistently experience the highest occupancy rates throughout the week. This insight into booking behavior can inform pricing strategies and resource allocation for property management.			
4. Return on Investment (ROI) Analysis: Finally, the analysis examines the return on investment (ROI) potential of select neighborhoods. While "Nolita" showcases an impressive annual return exceeding $70,000, it's noted that only one listing is available based on filtered data. Conversely, "Lower East Side" presents three available properties, demonstrating the potential for a combined annual return surpassing $100,000.		
