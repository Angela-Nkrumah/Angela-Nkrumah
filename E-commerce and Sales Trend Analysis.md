# Retail Sales Exploratory Analysis (EDA)


### Table Content

   [Project Overview](#project-overview)
   
   [Source](#source)
   
   [Tools](#tools)
   
   [Columns in Dataset](#columns-in-dataset)
   
   [Data Preparation](#data-preparation)
   
   [Steps followed](#steps-followed)
   
   [Visualization](#visualization)
   
   [Dashboard Snapshot](#dashboard-snapshot) 
   
   [Insights](#insights)
   
   [Recomemndation](#recomemndation)
   
   [Conclusion](#conclusion)
   
   
## Project Overview

This report is designed to investigate and understand the trends and patterns in a Uk based e-commerce retail shop by analyzing it's sales trend over a period of time as well as it's customers behaviours. The retail business develops an in-depth knowledge about which location needs more attention to boost sales as well as which products need more attention in other to increase yearly and seasonal sales. A 3 page report and a dashboard to summarize and give a quick view of the entire report was created.
Link to report: https://drive.google.com/file/d/1wspQ-Oplk1X5ubJi1p2zhiFAb9SCaP8a/view?usp=sharing


### Source
Data was sourced from: https://www.kaggle.com/datasets/gabrielramos87/an-online-shop-business. 


### Tools
 - My SQL (for cleaning and analysing the data)
 - Power BI (Using Dax queries for further analysis and visualization)
 - Data was cleaned using sql queries whereas DAX was used in generating further analysis.

### Columns in Dataset
   The dataset contained eight (8) columns; 
   
 1. Transaction_No
 2.  DateProduct_No
 3.  Product
 4.  Price
 5. Quantity
 6. Customer_No
 7.  Country   
    

### Data Preparation
 Data was cleaned using My SQL.

### Steps followed 

- Step 1 : Load data into MySQL to clean and analyze data by using Data Definition Language (DDL) and Data Manipulation Languages (DML) to clean and standardize dataset for further analysis.
  
- Key SQL Queries

- SQL Queries to import data
  
  ```sql
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
    SELECT    
      Transaction_No,
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

  ```DAX
   ProductRank = 
   RANKX(
    FILTER(
        'Countries and their most purchased products',
        'Countries and their most purchased products'[Country] = EARLIER('Countries and thier most purchased products'[Country])
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
        'Countries and their most purchased products',
        'Countries and their most purchased products'[ProductRank] = 1 && 'Countries and thier most purchased products'[Country] <> "unspecified" && NOT ISBLANK('Countries and thier most purchased products'[Country])
      ),
  
      'Countries and thier most purchased products'[Country],
      "TotalQuantity", MAX('Countries and thier most purchased products'[TotalQuantity]),
      "TopProduct", MAX('Countries and thier most purchased products'[Product_Name])
      )


 ### Visualization
 
- Three(3) cards and four (4) filters were added to the dashboard to identify the Total Sales, Total Purchased and Average Price as well as the various 4 quaters respectively.
  
   ![Screenshot 2024-11-13 124111](https://github.com/user-attachments/assets/c2470c75-48a8-4f14-a768-195bcafa6320)
   ![Screenshot 2024-11-13 124139](https://github.com/user-attachments/assets/5398f079-1407-4752-a45f-d786c206d794)
   ![Screenshot 2024-11-13 124155](https://github.com/user-attachments/assets/816fbe7d-0375-4e6d-b695-a2c4c5195b3e)
   
  
- 3 bar charts were included to analyze the seasonal trends, yearly and monthly trends as well as the quartely trend.
- 2 tables were also included to visualize the top 10 products with the highest revenue and the top 10 customer Id.
- A map was included in the dashbaord to visualize the varios countries. Filters of each country's total number, total sales and total quantity purchased were aslo included.
- A new table with calculated measures was created to group the various countries and their customer transactions, for visualization.
  
  Snap Shot of new customer transactions per country table.

  ![Screenshot 2024-11-13 122938](https://github.com/user-attachments/assets/c5e963e7-14d4-4798-b08f-1d6c471e3c7a)
  
 
 # Dashboard Snapshot
 
![Screenshot 2024-11-13 171931](https://github.com/user-attachments/assets/35c91037-9a4a-4933-a1eb-b3f18fe0baad)

# Insights

### Total Sales
A Total sales of 62.97M was generated withing the time period of November 2018 to December 2019. with the highest sales been recorded in the early stage of the data, which could indicate a strong launch of the business or a seasonal demand of products.There is also a positve correlatoin between the total sales and total quantity sold 
             
### Day Sales
Sales particularly hiked on Mondays, Thursdays and Sundays as well regions such as United Kingdom, Germany and EIRE. With a total sales of 1,729,479.34, Monday recorded the highest sales of the weeks and was 337.50% higher than Wednesday), which recorded the lowest sales of the weeks at 395,305.25. Amongst all 6 days of the week, highest sales ranged from 395,305.25 to 1,729,479.34.

### Seasonal Sales
In August 2019, a total sales of 36.39% of the overall sales was recorded making it the highest sales for the seasons, which was then followed by April and December respectively.

 ### Regional Sales
 United Kingdom, Germany and EIRE recorded the most sales.
 
 ### Customer Trend over Time
 At 583, August had the highest Total Customers and was 577.91% higher than November, which had the lowest customer count the business saw at 86.
 
         
### Purchasing Product analysis
﻿In December, the transaction total of 2019 made up 15.73% of it's total. The total for 2018 and 2019 diverged the most in December when 2018 weas 16405 higher than 2019.


### Most Purchased Product
The number of transactions and total quantity sold are negatively correlated with each other. Which could signify bulk buying behavior or seasonal and promotional purchases. Quantity sold and the number of transactions diverged the most  with Paper Craft Little Birdie, with the total quantity being 80994 higher than the number of transactions.


 ### Top 10 Products sold
 At 1,002,718.10, Paper Craft Little Birdie had the highest quantity sold and was 3,348.18% higher than Victorian Glass Hanging T-Light, which had the lowest quantity sold at 29,079.63.
 Across all 10 products sold, the total sales ranged from 29,079.63 to 1,002,718.10.

 ### Most Purchased product per Country
 ﻿United Kingdom with its respective most product sold, (Paper Craft Little Birdie) made up 74.46% of the total quantity. 

 ### Top 10 Customers with Most Purchased
 Customer Id 16446 purchased the most product withing Novemeber 2018 to December 2019 with a total purchased of 80995. Followd by Customer ID number 14641, also with a total purchase 
 number of 34760. The least purchased amongst the top 10 was Customer Id number 17450 with a total purchase count of 5354.

  ### Recomemndation

  
 1. Optimize Marketing Plans Using Sales Trends
    
  - Peak Sales Times:
    
  - Since the early stages saw the largest sales, think about examining the marketing or promotional initiatives that were carried out during this time. To increase 
    sales, repeat these tactics at other times.
    
  - Seasonal Demand:
    
  - Plan and allot marketing resources for the months of August, December, and April, when sales tend to peak. Think of introducing new product lines, discounts, or     
    exclusive marketing for certain months.

 2. Make Inventory Management Better
    
  - Stock Levels:
  
  - Make sure you keep enough product on hand for when demand is at its highest (Mondays, Thursdays, and Sundays). To avoid stockouts and also increase the quantity of popular items 
   like Paper Craft Little Birdie.

 3.Regional Inventory: 
 
 - Make sure that areas such as the UK, Germany, and EIRE continue to have higher levels of inventory. Customer pleasure and prompt fulfillment are ensured by this.

 4. Focused Interaction with Customers
    
  - Highest Number of Customers:
  
  - August has the most customers overall. Use this month to run focused promotions that will increase sales and engagement to draw in new business and keep existing ones, implement 
    loyalty programs and promotions.
    
  - Customer Retention:

    Use techniques to turn prospects into loyal patrons, especially in high-demand months. Exclusive incentives and tailored communications can aid in keeping these 
    clients.

5. Enhance the Client Experience
   
   - Consumer input and improvement:

   - Gather consumer feedback on a regular basis, particularly on well-liked products and at times of high sales. Utilize these suggestions to enhance the caliber of the products, the 
     packaging, and the delivery options.
     
   - Customer service:
     
   - To effectively manage more questions and problems, make sure there is strong customer service during times of high sales.


6. Emphasizing Products and Adding Variety

  - Best-Selling Items:
    
 - Focus on marketing best-selling items such as "Paper Craft Little Birdie." To boost sales, emphasize these in marketing efforts and think about combining them with 
   other items.
 - Diversification:
   
 - Examine the reasons behind the reduced sales of products such as the "Victorian Glass Hanging T-Light" and determine if they require improved marketing or even a 
   redesign.

7. Make Strategic Decisions with Data
   
  - Data-Based Approaches:
    
  - To improve pricing strategies, apply the knowledge gained from the association between the total quantity sold and the number of transactions. Offer discounts for greater purchases, 
    for example, to encourage larger transactions.
    
  - Trend Analysis:
  
  - Keep an eye out for new patterns by continuously observing consumer behavior and sales trends. Make proactive strategy adjustments and remain ahead of market trends 
    with the help of this data.

 8. Region Expansion
    
   - High-Performing Regions:
   
   - Since the United Kingdom, Germany, and EIRE are performing well, consider expanding marketing and distribution channels in these regions.

9. Sales Optimization on Specific Days
    
   - Day-Specific Promotions: Implement special promotions on days with high sales like Mondays, Thursdays, and Sundays. This could further boost sales on these days and even out sales 
   throughout the week.


 ### Conclusion
   The E-commerce retail shop, can increase sales in general by increasing product quantity in the United Kingdom, Germany and Eire due to their high sales records and also attention 
   needs to be given to the products most purchased in the regions with low sales records. These products purchased most in these regions when strategized, can interest customers, which 
   will increase customer interaction and in return increase sales. Customer satisfaction should also be prioritized to encourage more new customers and also ensure new customers remain 
   as permanent customers of the business.
 
