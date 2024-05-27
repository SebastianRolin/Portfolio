# File name: E-Commerce Transaction Log Analysis: Business Analytics Project.

As part of the TripleTen program, this project aims to convert event logs into valuable business metrics. The key objectives include 
building a conversion funnel, conducting cohort analysis, and calculating retention rates. These skills, among others, were acquired during 
the Business Analytics spring program. [Here](https://docs.google.com/spreadsheets/d/171sS1a2hmd0GbJ4Fpk6iVn9ngcWuwg8HsDea7sVlENA/edit?usp=sharing) 
you can have access the project final upload.

[<img src="https://github.com/SebastianRolin/Portfolio/blob/main/Extra%20Resources/E-Commerce%20Transaction%20Log%20Analysis.png">](https://docs.google.com/spreadsheets/d/171sS1a2hmd0GbJ4Fpk6iVn9ngcWuwg8HsDea7sVlENA/edit?usp=sharing)


### File Description.

| File | Description |
| ----------- |----------- |
| README.md  | This document contains all pertinent information regarding the project, including its objectives, methodologies, and findings. |
| [Requirements.txt]() | A text file listing the project's dependencies and requirements as specified by TripleTen. |
| [E-Commerce Transaction Log Analysis](https://docs.google.com/spreadsheets/d/171sS1a2hmd0GbJ4Fpk6iVn9ngcWuwg8HsDea7sVlENA/edit?usp=sharing) | The project I completed and submitted to TripleTen for review.|
| [Review.png]() | A visual representation of feedback and comments provided by the project reviewer, offering insights into the project's evaluation and areas for improvement.  |
| [Business Analytics Project]() | The raw dataset supplied by TripleTen, utilized extensively throughout the project for analysis and insights generation. |

### Section Description.

| Section Title | Description |
| ----------- |----------- |
| Data Overview | This section provides a comprehensive description of the data utilized in the project, outlining the files and their corresponding sheets. |
| Assumptions | Here, you'll find a detailed description of the assumptions made during the analysis process, derived from both the data files and assumptions provided by TripleTen. |
| Analysis Methodology | Offering a broad overview, this section outlines the process undertaken to analyze the data, spanning from initial data ingestion to final insights extraction. |
| Data Insights | Contained within this section are the key insights derived from the analysis of the dataset, shedding light on significant trends, patterns, and discoveries uncovered during the project. |

### Data Overview.
The data file was provided by TripleTen in CSV format, and all processes were conducted using Google Spreadsheets. 
The spreadsheet consists of 8 pages and includes the following data

- `'Business Analyst Project.csv'`: raw transaction logs.
    - `'Table of Contents'`: This front page describes each sheet, using color coding to distinguish between raw data, calculations, analysis, and summary.
    - `'Executive Summary'`: This page contains the results of the cohort analysis and retention rates, as well as an analysis and description of the raw data, conversion funnel, and retention rates.
    - `'conversion_funnel'`: This section presents the conversion funnel based on the various actions taken by users on the website, using data from the "raw_user_activity" sheet.
    - `'retention_rates'`: In this section, we showcase the retention rates calculated from the month a user initiates activity on the online store until the last entry in our dataset.
    - `'purchase_activity'`: This is a duplicate of the "raw_user_activity" data, containing only information related to purchase actions. It has been refined for use in the "retention_rates," "conversion_funnel," and "cohort analysis" sheets.
    - `'First_purchase'`: In this sheet, we utilize calculations from the "purchase_activity" sheet to generate a pivot table, identifying the date when each user made their initial purchase.
    - `'cohort_analysis'`: In this sheet, we utilize data from the "purchase_activity" sheet to ascertain the number of users who are still active on the online store within various cohort age ranges.
    - `'raw_user_activity'`: Each row represents an activity, or event, by a user on the company’s website.
      - `'user_id'`: Unique customer IDs.
      - `'event_type'`: The type of activity by the user.
      - `'category_code'`: Category of the product being viewed or purchased.
      - `'brand'`: Company that makes the product.
      - `'price'`: Price of the product, in USD.
      - `'event_date'`: Date of the user activity, in YYYY-MM-DD format.

### Assumptions:
- The "raw_user_activity" sheet accurately captures all website activity within the specified timeframe.
- Missing values or data inconsistencies are minimal and negligible.
- The data format, including columns and data types, is correct and consistent.

### Analysis Methodology:
First, we explored the raw data by reviewing each sheet in the Google Spreadsheet. We began by creating a conversion funnel, as the executive team was interested 
in understanding how effectively the website converts product page views into purchases. For this, we used data from the "raw_user_activity" sheet.

After developing the conversion funnel, we moved on to cohort analysis to build an acquisition cohort based on the month of a user’s first purchase. 
Finally, we completed the project by calculating retention rates.


### Data Insights:
1. Conversion Tunnel: The cohort analysis clearly shows a significant decline in user retention over time, indicating that most customers are not returning. To address this issue, we need to prioritize and improve our customer retention strategies.
2. Retention Rates: In the first month, there is a significant drop in user numbers, and by the third month, the user base has nearly disappeared, with a retention rate of less than 1%.
