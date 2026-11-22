# Sales-Dashboard-Power-BI
An interactive Power BI dashboard that analyzes sales performance from 2020 to 2022 across product categories, countries, and time periods.

Dashboard

Objective

Give decision-makers a clear view of total sales, average sales, and profit, and let them explore the results by year, country, and customer income level.

Key Insights
Total sales: 24.9M, with a total profit of 10.5M.
The United States and Australia generate around 60% of total sales.
Bikes make up the vast majority of sales compared with Accessories and Clothing.
Monthly sales show a sharp drop starting in July.
Dashboard Features
KPI cards: Total Sales, Average Sales, Profit
Pie chart: sales by product category
Bar chart: sales by country
Line chart: sales by month
Map: sales by geographic region
Slicers: year, country, and customer income level
Data Model

Star schema with Sales as the fact table, connected to:

Calendar Lookup
Customer Lookup
Product Lookup, Product Subcategories Lookup, Product Categories Lookup
Territory Lookup
Returns Data
What I Did
Imported 10 CSV files into Power BI.
Cleaned the data in Power Query (removed corrupted rows from the customer table).
Combined the 2020, 2021, and 2022 sales files into one table using Append Queries.
Built the data model with Many-to-One relationships.
Created a conditional column to classify customers as High or Low income (threshold: $100,000).
Created a calculated column for profit using DAX.
Created DAX measures for total sales and average sales.
Designed the dashboard with interactive visuals, slicers, and filters.
DAX Used
DAX
Profit =
(RELATED('Product Lookup'[ProductPrice]) - RELATED('Product Lookup'[ProductCost]))
    * Sales[OrderQuantity]

Total Sales =
SUMX(Sales, Sales[OrderQuantity] * RELATED('Product Lookup'[ProductPrice]))

Average Sales =
AVERAGEX(Sales, Sales[OrderQuantity] * RELATED('Product Lookup'[ProductPrice]))
Tools

Power BI, Power Query, DAX, Data Modeling

Files
Sales_Dashboard.pbix: the Power BI project file
Sales_Dashboard.png: dashboard screenshot
