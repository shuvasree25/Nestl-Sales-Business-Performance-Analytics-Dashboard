# Nestl-Sales-Business-Performance-Analytics-Dashboard
Power BI dashboard analyzing Nestlé USA sales, profitability, product performance, regional sales, and customer segmentation from 2023–2026.
Project Overview:
The Nestlé Sales & Business Performance Analytics Dashboard is an interactive Power BI project designed to analyze sales performance, profitability, product performance, regional performance, and customer segmentation across the USA.
The project analyzes sales data from 2023 to 2026 and converts raw sales data into meaningful business insights using Power BI, DAX, Power Query, and data visualization.
Business Objective:
The main objective of this project is to analyze:
Overall sales and profit performance
Customer and order performance
Monthly sales trends
Top-performing products
State-level sales performance
Category-level sales and profitability
Customer segmentation
Average Order Value
Average Selling Price
Profit Margin
🛠️ Tools & Technologies
Power BI
DAX
Power Query
Data Cleaning & Transformation
Data Modeling
CSV / Excel
Data Cleaning:
The dataset was cleaned and transformed using Power Query.
Cleaning Steps
Removed duplicate records
Handled missing values
Corrected data types
Standardized date fields
Validated numerical fields
Checked sales and profit values
Reviewed discount values
Standardized categorical fields
Validated customer and order IDs
Checked regional and state information
Date Table
A dedicated Date Table was created for time based analysis.
DateTable = 
ADDCOLUMNS(
    CALENDAR(
        DATE(2023, 1, 1),
        DATE(2026, 12, 31)
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMM"),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Year Month", FORMAT([Date], "YYYY-MM")
)
DateTable[Date] → Nestle Sales[Order Date]
Key DAX Measures:
Total Customers
Total Customers =
DISTINCTCOUNT('Nestle Sales'[Customer ID])
Total Orders
Total Orders =
DISTINCTCOUNT('Nestle Sales'[Order ID])
Total Sales:
Total Sales =
SUM('Nestle Sales'[Sales])
Total Profit:
Total Profit =
SUM('Nestle Sales'[Profit])
Total Quantity
Total Quantity =
SUM('Nestle Sales'[Quantity])
Total Discount
Total Discount =
SUM('Nestle Sales'[Discount])
Average Order Value
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders]
)
Average Selling Price
Average Selling Price =
DIVIDE(
    [Total Sales],
    [Total Quantity]
)
Profit Margin
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales]
)
Dashboard Structure:
The dashboard contains 2 pages.
Page 1: Nestlé Sales & Business Performance Analytics Dashboard
KPI Cards
Total Customers: 793
Total Orders: 5.009K
Total Sales: $915.8K
Total Profit: $234.84K
Total Discount: 63K
Visualizations:
1. Total Orders by Product
Identifies products generating the highest order volume.
2. Total Sales by State
Highlights states contributing the highest sales.
3. Monthly Sales Trend
Shows monthly changes in sales performance.
4. Total Sales by Category
Shows the contribution of each product category to overall sales.
5. Total Orders by Category
Compares order volume across different categories.
Filters
Region
Year
Quarter
Page 2: Nestlé Product & Profitability Analysis
KPI Cards
Profit Margin: 25.6%
Average Order Value: $182.83
Average Selling Price: $6.47
Total Quantity: 142K
Visualizations
1. Total Sales by Product
Identifies the products generating the highest sales.
2. Total Profit by Product
Identifies the products contributing the highest profit.
3. Total Profit by Category
Compares profit contribution across product categories.
4. Total Sales & Total Profit by Category
Compares sales revenue and profit across categories.
5. Customer Segmentation
Analyzes customers across:
Mass Market
Family
Premium
Health & Wellness
Key Business Metrics
Metric	Value
Total Customers	793
Total Orders	5.009K
Total Sales	$915.8K
Total Profit	$234.84K
Total Discount	63K
Profit Margin	25.6%
Average Order Value	$182.83
Average Selling Price	$6.47
Total Quantity	142K
Business Recommendations
Based on the dashboard analysis, the following recommendations can support sales and profitability improvement:
1. Focus on High-Performing Products
Identify products with consistently high sales and order volumes and ensure adequate inventory availability to avoid stockouts.
2. Improve Low-Performing Products
Review products with lower sales or profit contribution. Consider pricing, promotions, product positioning, and customer demand before deciding on corrective actions.
3. Prioritize High-Performing Categories
Allocate marketing and inventory resources toward categories generating stronger sales and profit contributions.
4. Optimize Regional Sales
Use state-level sales performance to identify stronger and weaker markets. High-performing states can receive greater distribution and marketing focus, while lower-performing regions can be investigated for demand and distribution gaps.
5. Monitor Profitability
Track Profit Margin % alongside sales. Higher sales do not necessarily mean higher profitability, so both metrics should be evaluated when making product and category decisions.
6. Use Customer Segmentation
Tailor promotions and engagement strategies according to customer segments such as Premium, Family, Mass Market, and Health & Wellness.
7. Monitor Discounts
Evaluate discount levels against sales and profit performance to ensure promotions generate sufficient revenue without unnecessarily reducing margins.
8. Track Monthly Sales Trends
Use monthly sales trends to identify periods of stronger or weaker demand and improve inventory planning, promotions, and sales forecasting.
9. Improve Cross-Selling Opportunities
Analyze customer purchasing behavior to identify complementary products that can be promoted together, increasing average order value.
10. Establish Regular KPI Monitoring
Track key metrics such as Sales, Profit, Profit Margin, Orders, Average Order Value, and Quantity Sold regularly to identify changes in business performance.
