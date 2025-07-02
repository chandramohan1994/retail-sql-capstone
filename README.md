Retail Sales Analytics Capstone Project (SQL + Power BI)

📊 Project Summary

This project focuses on analyzing retail sales data using SQL Server Management Studio (SSMS) and visualizing it using Power BI. The goal is to simulate a real-world retail analytics pipeline and derive actionable insights for business operations such as stock monitoring, sales trends, and pricing performance.

🧰 Tech Stack
SQL Server 2021
SQL Server Management Studio (SSMS)
Power BI Desktop
Windows OS

📁 Dataset Overview

The dataset is a daily log of product sales with the following columns:

Column	Type	Description
sale_date	DATE	Date of sale
quantity	INT	Number of units sold
stock	INT	Inventory available after the sale
price	DECIMAL(5,2)	Unit price of the product
The data was manually loaded into a SQL Server table from a CSV file.

🧱 Data Pipeline Overview
🔹 Bronze Layer
Raw data ingested from CSV into SQL Server using insert_daily_sales_mysql.sql
🔹 Silver Layer
All columns already in correct data types
Calculated revenue (quantity * price)
🔹 Gold Layer Transformations
Using CTE and window functions:

Rolling 7-day average sales
Low stock flag (stock < 500)
Price tier classification:
Low: < 1.10
Medium: 1.10 - 1.20
High: > 1.20
🔍 Key Business Insights
Daily Revenue Trend: Revealed daily fluctuations in revenue, helping identify high-performing dates.
Low Stock Alerts: Detected multiple instances where stock dropped below 500 units — useful for restocking decisions.
7-Day Rolling Average: Smoothed out short-term volatility in sales volume, aiding trend analysis.
Price Tier Performance:
Medium-priced items had the most consistent sales.
Low-priced items did not necessarily drive volume.
📈 Power BI Dashboard
The enriched table was imported into Power BI to generate interactive visualizations such as:

Revenue Over Time
Rolling Average of Sales
Low Stock Alert Flags
Price Tier Analysis
📂 File Structure
retail-sql-capstone/
├── sql_scripts/
│   ├── insert_daily_sales_mysql.sql
├── dashboard/
│   └── retail_dashboard.pbix
├── README.md

