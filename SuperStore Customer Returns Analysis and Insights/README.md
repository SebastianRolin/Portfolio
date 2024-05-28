# SuperStore Customer Returns Analysis and Insights.

This project is part of the TripleTen Business Intelligence Analyst program and is designed to demonstrate the use of the data visualization tool Tableau. 
In this project, we simulate an analysis for the CEO of an online store to understand the causes of the high number of customer return orders and to provide
recommendations on how to reduce these returns. [Here](https://public.tableau.com/app/profile/sebastian.rolin.guerra/viz/Project6TripleTen/SuperstoreAnalysis) 
you can have access the project final upload and the 5 minutes presentation [Here](https://youtu.be/VVsWl2m5Jlg )

[<img src="https://github.com/SebastianRolin/Portfolio/blob/main/Extra%20Resources/SuperStore%20Customer%20Returns%20Analysis%20and%20Insights.png">](https://public.tableau.com/app/profile/sebastian.rolin.guerra/viz/Project6TripleTen/SuperstoreAnalysis)


### File Description.

| File | Description |
| ----------- |----------- |
| README.md  | This document contains all pertinent information regarding the project, including its objectives, methodologies, and findings. |
| [Requirements.txt](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Customer%20Returns%20Analysis%20and%20Insights/Requirements.txt) | A text file listing the project's dependencies and requirements as specified by TripleTen. |
| [SuperStore Customer Returns Analysis and Insights.twbx](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Customer%20Returns%20Analysis%20and%20Insights/Project%206%20Customer%20Return%20Analysis.twbx) | This is the Tableau file containing the presentation, which includes all the sheets created for the Tableau story.|
| [Review.png](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Customer%20Returns%20Analysis%20and%20Insights/Review.png) | A visual representation of feedback and comments provided by the project reviewer, offering insights into the project's evaluation and areas for improvement.  |
| [Superstore.xls](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Customer%20Returns%20Analysis%20and%20Insights/Superstore.xls) | The raw dataset supplied by TripleTen, utilized extensively throughout the project for analysis and insights generation. |
|[Mockups 1 & 2](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Customer%20Returns%20Analysis%20and%20Insights/Mockup%202.png) | These images were created as a required part of the project to produce mock-ups for the dashboard. |

### Section Description.

| Section Title | Description |
| ----------- |----------- |
| Data Overview | This section provides a comprehensive description of the data utilized in the project, outlining the files and their corresponding sheets. |
| Assumptions | Here, you'll find a detailed description of the assumptions made during the analysis process, derived from both the data files and assumptions provided by TripleTen. |
| Analysis Methodology | Offering a broad overview, this section outlines the process undertaken to analyze the data, spanning from initial data ingestion to final insights extraction. |
| Data Insights | Contained within this section are the key insights derived from the analysis of the dataset, shedding light on significant trends, patterns, and discoveries uncovered during the project. |

### Data Overview.
TripleTen provided an excel dataset to be used in tableau to make the analysis, the dataset contains the following sheets and data.

- `'Superstore.xls'`: Data set that contains the following sheets.
  - `'Orders'`: In this sheet we have entries for all the products sold in the online store with valuable information such:
    - `'Row ID'`: A unique identifier for each row in the dataset.
    - `'Order ID'`: A unique identifier assigned to each order placed in the system.
    - `'Order Date'`: The date when the order was placed.
    - `'Ship Date'`: The date when the order was shipped to the customer.
    - `'Ship Mode'`: The method or mode of shipping chosen for the order.
    - `'Customer ID'`: A unique identifier assigned to each customer.
    - `'Customer Name'`: The name of the customer who placed the order.
    - `'Segment'`: The market segment to which the product belongs
    - `'Country/Region'`: The country or region where the customer is located.
    - `'City'`: The city where the customer resides.
    - `'State'`: The state where the customer resides
    - `'Postal Code'`: The postal code of the customer’s address.
    - `'Region'`: The geographic region where the customer is located 
    - `'Product ID'`: A unique identifier assigned to each product.
    - `'Category'`: The category to which the product belongs
    - `'Sub-Category'`: The sub-category of the product within its main category
    - `'Product Name'`: The name of the product.
- `'People'`: This sheet contains information about the individual responsible for overseeing operations in a specific region.
    - `'Regional Manager'`: The individual responsible for overseeing operations and performance in a specific geographic region
    - `'Region'`: The geographic area or territory managed by the regional manager
- `'Returns'`: Details all fields for each returned item
    - `'Returned'`: Indicates whether an order was returned by the customer.
    - `'Order ID'`: A unique identifier assigned to each order placed in the system.



### Assumptions:
- I’ll utilize the Return Rate as our primary measure, as it offers a clearer insight into the percentage of returns attributed to each product,
providing greater precision in our analysis.
- For the customers with the highest return rate I filtered out all the customers with only one order.


### Analysis Methodology:
After reviewing the data provided in the Excel spreadsheet from TripleTen, I transitioned to the visualization tool Tableau. In Tableau, I imported the 
Excel spreadsheet and performed a LEFT JOIN to merge the "Returns" table with the "Orders" table. To address the data type issue in the "Returned" field, I 
created a calculated field that converts "Null" values to "0" and "Yes" values to "1." 

With the data prepared, I proceeded to create visualizations to identify the root causes of return orders. Following the creation of these visualizations, 
I developed three dashboard mockups. I then selected the most suitable mockup for the final dashboard presentation. Finally, I prepared a presentation to 
explain the dashboard and each of the visualizations in detail.
 

### Data Insights:
1. The states of California, Utah, and Oregon exhibit return rates exceeding 40%
2. Across the Western region, all subcategory products demonstrate return rates surpassing 30%, with some exceeding 50%
3. Technology emerges as the predominant category with the highest return rates among all product categories
4. Seasonal spikes in returns are observed in August, September, and October, followed by another notable peak in December..
5. Blinders and papers emerge as our top-selling products; however, they also lead in total return.
6. Despite a 4% increase in returns from 2020 to 2021, it's noteworthy that our profitability surged from $85k in 2020 to $151k in 2021.
