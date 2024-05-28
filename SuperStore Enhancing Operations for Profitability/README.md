# SuperStore Enhancing Operations for Profitability.

In this project assigned from the TripleTen Business Intelligence Analyst program I work as a consultant to review e-commerce store operations and increase 
profitability to avoid bankruptcy and for that I have to analyze the store data and create individual visualizations that justify my conclusions. These 
visualizations are made with the powerful visualization tool Tableau. [Here](https://public.tableau.com/app/profile/sebastian.rolin.guerra/viz/Project-SavingSuperStore-/Project-SavingSuperStore-#1) 
you can have access the project final upload.

[<img src="https://github.com/SebastianRolin/Portfolio/blob/main/Extra%20Resources/SuperStore%20Enhancing%20Operations%20for%20Profitability.png">](https://public.tableau.com/app/profile/sebastian.rolin.guerra/viz/Project-SavingSuperStore-/Project-SavingSuperStore-#1)


### File Description.

| File | Description |
| ----------- |----------- |
| README.md  | This document contains all pertinent information regarding the project, including its objectives, methodologies, and findings. |
| [Requirements.txt](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Enhancing%20Operations%20for%20Profitability/Requirements.txt) | A text file listing the project's dependencies and requirements as specified by TripleTen. |
| [SuperStore Enhancing Operations for Profitability.twbx](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Enhancing%20Operations%20for%20Profitability/SuperStore%20Enhancing%20Operations%20for%20Profitability.twbx) | This is the Tableau file containing the presentation, which includes all the sheets created for the Tableau story.|
| [Review.png](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Enhancing%20Operations%20for%20Profitability/Review.png) | A visual representation of feedback and comments provided by the project reviewer, offering insights into the project's evaluation and areas for improvement.  |
| [Superstore.xls](https://github.com/SebastianRolin/Portfolio/blob/main/SuperStore%20Enhancing%20Operations%20for%20Profitability/Superstore.xls) | The raw dataset supplied by TripleTen, utilized extensively throughout the project for analysis and insights generation. |

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

- `'Superstore.xls'`: Each row represents a product sold, with sheets joined using a LEFT JOIN.
    - `'orders'`: Contains detailed information for each ordered item.
    - `'returns'`: Contains detailed information for each returned item.


### Assumptions:
- The willingness to pay for advertising is determined based on the return on ad spend (ROAS) ratio. I decided to allocate 1/5 of the advertising profit
for this purpose. 
- To handle the returned field, I created a calculated field where "null" values are converted to "0" and "Yes" values are converted to "1".


### Analysis Methodology:
After spending some time examining the data and understanding its structure, I began by identifying the key areas of profit and loss in the online store. I analyzed 
the profits and losses across different regions and found that our largest losses come from the Central and East regions. Specifically, within the Central region, 
the sub-category with the biggest loss is binders, and in the East region, it is tables. Based on this analysis, I identified which products the store should stop 
selling. I also created a visualization showing the best and worst performing subcategories.

Next, I focused on identifying which states have the best advertising performance by comparing advertising fees and the profits generated from those ads. In the 
final section of this project, I provided insights into which customers have the highest return rates and the products they return most frequently. To conclude, 
I created a visualization showing the average profit against the average return rate by state. 


### Data Insights:
1. Tables (East region) and binders (Central region) are the subcategories with the highest losses.
2. The store has five poorly performing products, with "TEC-MA-10000418" being the worst, incurring over $20k in losses.
3. The best performing products are "copiers," generating over $75k in profit, followed by "phones" with more than $55k.
4. The best states for advertising are "Indiana," "Vermont," and "Rhode Island."
5. Several products have a 100% return rate and should be discontinued, along with other products that have over a 75% return rate.
6. "Roland Murray" and "Hilary Holder" are customers with a 100% return rate, and we recommend investigating the reasons for their returns.
