# Retail Sales Exploratory Analysis (EDA)

### Dashboard Link : https://app.powerbi.com/groups/me/reports/384d017e-e935-44dc-9e7d-1626c1a36de1/ReportSection

## Problem Statement

This report is designed to investigate and understand the trends and patterns in an e-commerce retail shop by analyzing it's sales trend over a period of time. The shop gets to know which location needs more attention to boost sales as well as which products need more attention in other to increase yearly and seasonal sales.

### Steps followed 

- Step 1 : Load data into MySQL to clean and analyze data by using Data Definition Language (DDL) and Data Manipulation Languages (DML) to clean and standardize dataset to prepare for further analysis.
- Key SQL Queries
- SQL Queries to import data
  CREATE TABLE `sales_transactions` (
  `Transaction_No` varchar(255) DEFAULT NULL,
  `Date` date DEFAULT NULL,
  `Product_No` varchar(255) DEFAULT NULL,
  `Product_Name` varchar(255) DEFAULT NULL,
  `Price` decimal(6,2) DEFAULT NULL,
  `Quantity` int DEFAULT NULL,
  `Customer_No` varchar(255) DEFAULT NULL,
  `Country` varchar(100) DEFAULT NULL,
  `New_Product_No` int DEFAULT NULL,
  `New_Id` int NOT NULL,
  PRIMARY KEY (`New_Id`)
UPDATE retail_and_ecommerce_transactions
   SET Quantity = NULL;

 -Data Cleaning and transformation
SELECT 
    Product_No,
    LENGTH(Product_No) AS string_length,
    CASE 
        WHEN RIGHT(Product_No, 1) BETWEEN 'A' AND 'Z' THEN LENGTH(Product_No) - INSTR(REVERSE(Product_No), RIGHT(Product_No, 1)) + 1
        ELSE NULL
    END AS Alphabets_position,
    REGEXP_REPLACE(Product_No, '[^0-9]', '') AS New_Product_No,
    LENGTH(REGEXP_REPLACE(Product_No, '[^0-9]', '')) AS Numerical_length
FROM 
    Retail_and_ecommerce_transactions;

  -Syntax for creating a new table from the main table by using certain requirements
    Insert into canceled_transactions (
              Transaction_No,
              `Date`,
              Product_Name,
              Price,
              Quantity,
              Country,
              New_Product_No,
              New_Id
	) 
SELECT     Transaction_No,
              `Date`,
              Product_Name,
              Price,
              Quantity,
              Country,
              New_Product_No,
              New_Id
FROM sales_transactions
where  Transaction_No LIKE 'C%' 
    AND (Quantity < 0 OR (Price <0 AND Quantity IS NULL));

-Syntax for updating new columns in the new table from the main table
      UPDATE cancelled_products st
JOIN sales_transactions mt ON 
    st.Transaction_No LIKE 'C%' 
    AND st.`Date` = mt.`Date` 
    AND st.New_Product_No = mt.New_Product_No 
    AND st.Product_Name = mt.Product_Name 
    AND st.Price = mt.Price 
    AND st.Quantity = mt.Quantity 
    AND st.Customer_No = mt.Customer_No 
    AND st.Country = mt.Country
SET st.sales_transactions_New_ID = mt.New_ID
WHERE 
    (st.Quantity < 0 OR st.Quantity > 0);
 
    
- Step 2 Load data into Power Query and use dax functions to create new tables and measures for further analysis.
  
- Dax Query to rank products
   ProductRank = 
RANKX(
    FILTER(
        'Countries and thier most purchased products',
        'Countries and thier most purchased products'[Country] = EARLIER('Countries and thier most purchased products'[Country])
    ),
    'Countries and thier most purchased products'[TotalQuantity],
    ,
    DESC,
    Dense
)  
- Dax for analyzing time series trend
   TimeSeriesAnalysis = 
SUMMARIZE(
    'Trends analysis',
    'Trends analysis'[Year],
    'Trends analysis'[Quarter],
    'Trends analysis'[Month],
    "TotalSales", SUM('Trends analysis'[Total_Sales_Amount]),
    "TotalQuantitiesSold", SUM('Trends analysis'[Total_Quantity_Sold]),
    "AveragePrice", AVERAGE('Trends analysis'[Average_Price])
)
- Dax to analyze various country's purchasing behaviour
   TopProductsByCountry = 
SUMMARIZE(
    FILTER(
        'Countries and thier most purchased products',
        'Countries and thier most purchased products'[ProductRank] = 1 && 'Countries and thier most purchased products'[Country] <> "unspecified" && NOT ISBLANK('Countries and thier most purchased products'[Country])
    ),
    'Countries and thier most purchased products'[Country],
    "TotalQuantity", MAX('Countries and thier most purchased products'[TotalQuantity]),
    "TopProduct", MAX('Countries and thier most purchased products'[Product_Name])
)
 
- Step 8 :Four(4) cards and three(3) filters were added to the dashboard to identify the Total Sales, Total Purchased and Average Price as well as the various 4 quaters respectively.
                  ![Screenshot 2024-11-13 124111](https://github.com/user-attachments/assets/c2470c75-48a8-4f14-a768-195bcafa6320)
                  ![Screenshot 2024-11-13 124139](https://github.com/user-attachments/assets/5398f079-1407-4752-a45f-d786c206d794)
                  ![Screenshot 2024-11-13 124155](https://github.com/user-attachments/assets/816fbe7d-0375-4e6d-b695-a2c4c5195b3e)
   
           Although, by default, while calculating, blank values are ignored.
- Step 10 : 3 bar charts were included to analyze the seasonal trends, yearly and monthly trends as well as the quartely trend. 2 tables were also included to visualize the top 10 products with the highest revenue and the top 10 customer Id. A map was included in the dashbaord to visualize the varios countries. Filters of each country's total number, total sales and total quantity purchased were aslo included.
- A new table with calculated measures was created to group the various countries and their customer transactions, for visualization.
  Snap Shot of new customer transactions per country table. ![Screenshot 2024-11-13 122938](https://github.com/user-attachments/assets/c5e963e7-14d4-4798-b08f-1d6c471e3c7a)
  
 
 # Dashboard Snapshot (Power BI DESKTOP)
![Screenshot 2024-11-13 171931](https://github.com/user-attachments/assets/35c91037-9a4a-4933-a1eb-b3f18fe0baad)

# Insights

A 3 page report analyzing the Sales trend, Customer trend and the purchasing analysis was created on Power BI Desktop. A summary page of various insights observed from the analysis was also created as well as a dashbaord to summarise the entire report and give a quick view of the entire analysis. It was then published to Power BI Service.

Following inferences can be drawn from the entire report;

### Total Sales
Total sales of 62.97M was generated withing the time period of November 2018 to December 2019.
Highest sales were recorded in the early stage of the data, which could indicate a strong launch of the business or a seasonal demand of products.
Total sales and total quantity sold are positively correlated with each other.
             
### Day Sales
Sales particularly hiked on Mondays, Thursdays and Sundays as well regions such as United Kingdom, Germany and EIRE.
At 1,729,479.34,  Monday (1) had the highest Maximum Sales Day Of Week and was 337.50% higher than Wednesday (3), which had the lowest Maximum Sales Day Of Week at 395,305.25.
Amongst all 6 days of the week, the maximum sales ranged from 395,305.25 to 1,729,479.34.

  ### Seasonal Sales
August in Year 2019 made up 36.39% of Sum of the total sales with it being the highest sales for the seasons.
Followed by April and December respectively.

 ### Regional Sales
 United Kingdom, Germany and EIRE recorded high sales.
The was also a spike in seasonal sales during, August,  December and April.
August in Year 2019 made up 36.39% of Sum of Total Sales.
 
 ### Customer Trend over Time
 At 583, August had the highest Total Customers and was 577.91% higher than November, which had the lowest Total Customers at 86.
 
 ### New Customers versus Returning customers.
 ﻿At 583, August had the highest total customers and was 577.91% higher than November, which had the lowest Total Customers at 86.﻿
         
### Purchasing Product analysis
﻿In December, the transaction total of 2019 made up 15.73% of the total transaction.
The total for 2018 and 2019 diverged the most in December when 2018 weas 16405 higher than 2019.


### Most Purchased Product
The number of transactions and total quantity sold  are negatively correlated with each other.
Cream Hanging Heart T-Light Holder accounted for 0.44% of Sum of transactions.
Quantity sold and the number of transactions diverged the most when the with Paper Craft Little Birdie, when with the total quantity being 80994 higher than the number of transactions.

 ### Top 10 Products sold
 At 1,002,718.10, Paper Craft Little Birdie had the highest quantity sold and was 3,348.18% higher than Victorian Glass Hanging T-Light, which had the lowest quantity sold at 29,079.63.
Paper Craft Little Birdie accounted for 72.25% of the sales.
Across all 10 products sold, the total sales ranged from 29,079.63 to 1,002,718.10.

 ### Most Purchased product per Country
 ﻿United Kingdom with its respective most product sold, Paper Craft Little Birdie made up 74.46% of Max of the total quantity.
 Rabbit Night Light had the highest average Max of total quantity at 4077, followed by Mini Paint Set Vintage, Ice Cream Sundae Lip Gloss, and Red Harmonica In Box.

 Conclusion
 The E-commerce retail shop, can increase sales in general by increasing product quantity in the United Kingdom, Germany and Eire due to their high sales records and also pay attention to the products most purchased in the regions with low sales records. These products purchased most in these regions when strategized, can interest customers, which will increase cutomer interaction and in return increase sales. 
 
