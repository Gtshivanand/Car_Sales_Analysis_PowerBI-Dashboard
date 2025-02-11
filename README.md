# 🚘 Car Sales Analysis Power BI Dashboard 🚘

![image](https://github.com/user-attachments/assets/c6aeb6c9-6e9f-4a4c-9442-cbc317f8d88a)


Analyzed car sales data using Power BI, utilizing Power Query for data cleaning and transformation. Applied DAX for advanced calculations and insights. Created interactive visualizations with time intelligence functions to track sales trends and developed dynamic reports for stakeholders to explore sales by region, model, and period.

## INTRODUCTION:
The Car Sales Dashboard was developed in Power BI to provide a comprehensive overview of sales performance for a car dealership. This dynamic and interactive dashboard enables stakeholders to track key performance indicators (KPIs), identify trends, and make data-driven decisions. The project was structured into various phases, including data import, modeling, DAX formula creation, visualization, and optimization. 

## PROJECT BACKGROUND:
The project is centred around the critical analysis of a car dealership. The report evaluates the development and implementation of a Power BI Car Sales Dashboard for the same. The dashboard aims to optimize sales performance tracking and enable data-driven decision-making. 

## Business Problem:

Car dealerships need an efficient way to monitor sales performance, understand customer preferences, and optimize inventory. This dashboard addresses these needs by visualizing key metrics and providing insights into sales patterns.

##  Project Overview:

This Power BI dashboard provides a comprehensive analysis of car sales data, offering stakeholders dynamic visualizations and key insights. The project involves data cleaning, transformation, and modeling using Power Query and DAX to enhance sales performance tracking and decision-making.

## Problem Statement:

The goal is to create a dynamic Car Sales Dashboard in Power BI that visualizes key performance indicators (KPIs) to track and analyze sales performance. The dashboard will focus on:

KPI Requirements:
- Sales Overview (YTD, MTD, YOY growth, PTYD comparisons)
- Average Price Analysis (YTD, MTD, YOY growth, PTYD comparisons)
- Cars Sold Metrics (YTD, MTD, YOY growth, PTYD comparisons)

Chart Requirements:
- Weekly YTD Sales Trend (line chart)
- YTD Sales by Body Style and Color (pie charts)
- YTD Cars Sold by Dealer Region (map chart)
- Company-wise Sales Trend (grid)
- Detailed Sales Information Grid (table with car model, style,   color, sales data, etc.)

The dashboard will offer real-time insights to help monitor performance, identify trends, and support data-driven decision-making.

## Project Workflow:

### Data Import and Pre-processing:

1. Import sales data into Power BI (CSV, Excel).
2. Cleanse the data using Power Query: replace erroneous values (e.g., fix "DoubleÂ Overhead Camshaft"), and ensure correct headers by using the first row.
3. Check column quality and distribution in Power Query for errors.

### Creating Calendar Table for Time Intelligence:

Generate a Calendar Table: CALENDAR(MIN(car_data[Date]), MAX(car_data[Date])).

Extract Year, Month, and Week from the Calendar Table for time-based analysis:

Year = YEAR('Calendar Table'[Date])

Month = FORMAT('Calendar Table'[Date], "MMMM")

Week = WEEKNUM('Calendar Table'[Date])

### Data Modeling:

Connect the Calendar Table to the car sales data via the Date column.
Use model view to establish relationships between tables.
![image](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Scheme%20Diagram.png)

### Calculating KPIs with DAX:

1. YTD Sales: TOTALYTD(SUM(car_data[Price ($)]), 'Calendar Table'[Date])
2. PYTD Sales: CALCULATE(SUM(car_data[Price ($)]), SAMEPERIODLASTYEAR('Calendar Table'[Date]))
3. Sales Difference: YTD Sales - PYTD Sales
4. YOY Growth: (Sales Difference) / PYTD Sales
5. MTD Sales: TOTALMTD(SUM(car_data[Price ($)]), 'Calendar Table'[Date])
6. Average Price: SUM(car_data[Price ($)]) / COUNT(car_data[Car_id])
7. YTD Average Price: TOTALYTD([Avg Price], 'Calendar Table'[Date])
8. MTD Average Price: TOTALMTD([Avg Price], 'Calendar Table'[Date])
9. Cars Sold: COUNT(car_data[Car_id])
10. YTD Cars Sold: TOTALYTD(COUNT(car_data[Car_id]), 'Calendar Table'[Date])

Format KPIs as needed, e.g., concatenate sales info and format in millions or thousands.

###  Visualization Development:

Line Chart: YTD Sales Weekly Trend.
Pie Charts: YTD Sales by Body Style and Color.
Map Chart: Sales distribution by dealer region.
Grid Table: Company-wise sales trend and detailed car sales data.
Area Chart: Display YTD Sales Weekly Trend with max sales point.
Dashboard Design:
Arrange KPIs at the top and detailed visualizations below.
Add slicers for filtering by body style, color, region, and company.

## Key Features:

* Sales Performance Metrics: Year-to-Date (YTD), Month-to-Date (MTD), Year-over-Year (YOY) comparisons.

* Advanced DAX Calculations: Implemented time intelligence functions to analyze trends.

* Dynamic Visualizations: Sales trends by region, car model, body style, and color.

* Interactive Filtering: Users can explore sales by different dimensions such as time, region, and car brand.

* Stakeholder-Focused Reporting: Optimized reports for clear and actionable insights.


# Snapshot of Dashboard 

![Car sales Data Analysis project overview](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Car%20sales%20Data%20Analysis%20OVERVIEW.png)

![Car sales Data Analysis project Details](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Car%20sales%20Data%20Analysis%20DETAILS.png)
 

# Insights

### Sales Overview:

Year-to-Date (YTD) Total Sales: $371.2M
Month-to-Date (MTD) Total Sales: $54.28M
Year-over-Year (YOY) Growth in Total Sales: 23.59%
Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales: $70.8M

![Car sales Data Analysis  1](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Sales%20Overview.png)

### Average Price Analysis:

YTD Average Price: $28.02K
MTD Average Price: $28.26K
YOY Growth in Average Price: -0.79% (indicating a slight price decrease compared to last year)
Difference between YTD Average Price and PTYD Average Price: The average price has slightly decreased compared to the previous year.

![Car sales Data Analysis  2](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Average%20Price%20Analysis.png)

### Cars Sold Metrics:

YTD Cars Sold: 13.3K
MTD Cars Sold: (This seems to be an error as it shows sales amount, which should be the total number of cars sold.)
YOY Growth in Cars Sold: 19.73%
Difference between YTD Cars Sold and PTYD Cars Sold: 2.62K more cars sold compared to the previous year.

![Car sales Data Analysis  3](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Cars%20Sold%20Metrics.png)


## visualizations for deeper analysis:

### YTD Sales Weekly Trend:

A line chart showcasing weekly YTD sales, highlighting that the 36th week had the highest sales, which can help identify peak sales periods.

![Car sales Data Analysis  4](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/YTD%20Sales%20Weekly%20Trend.png)

### YTD Total Sales by Body Style:

A pie chart displaying the distribution of YTD total sales across different body styles. SUVs and Hatchbacks are the two most popular body styles.

![Car sales Data Analysis  5](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/YTD%20Total%20Sales%20by%20Body%20Style.png)

### YTD Total Sales by Color:

A pie chart showing the distribution of YTD sales by car color, with pale white being the most popular color among customers.

![Car sales Data Analysis  6](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/YTD%20Total%20Sales%20by%20Color.png)

### YTD Cars Sold by Dealer Region:

A map chart showing the distribution of sales by geographical region, identifying Austin, Janesville, and Scottsdale as the top-performing dealer regions.

### Company-Wise Sales Trend in Grid Form:

A tabular grid displaying YTD sales data for each company. The grid will include major car brands like Chevrolet, Ford, and Dodge, helping to compare the performance of each.

![Car sales Data Analysis  7](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/YTD%20Cars%20Sold%20by%20Dealer_Region.png)
### Details Grid Showing All Car Sales Information:

A detailed grid presenting all relevant data for each car sale, including car model, body style, color, sales amount, dealer region, and sale date (covering sales from January 2, 2022, to December 31, 2023).

![Car sales Data Analysis  8](https://github.com/Gtshivanand/Car_Sales_Analysis_PowerBI-Dashboard/blob/main/Images/Details%20Grid%20Showing%20All%20Car%20Sales%20Information.png)


### Dealer and Company Performance:

The company-wise sales grid enables comparisons between different car companies like Chevrolet, Ford, and Dodge, helping to focus on top-performing brands.

### Car Sales Information:

The detailed sales grid gives a deeper view into each sale, including sales amount, car model, and other key attributes, assisting in understanding customer preferences and improving sales tactics.

### 🔍 Key Insights

1️⃣.📈 Sales Performance

YTD Sales: $371.2M  | YOY Growth: 🚀 +23.59%

Best-Selling Brands: Chevrolet, Ford, Dodge

Top Dealer Regions: Austin, Janesville, Scottsdale

2️⃣.🚗 Customer Preferences

Most Popular Body Style: SUVs (25.41%)

Most Preferred Color: Pale White (46%)

Highest-Priced Brand: Oldsmobile ($31.6K per unit)

## BUSINESS INSIGHTS DRAWN FROM THE DATA:
1.	Sales Performance Trends:
	The total YTD sales for 2023 amounted to $371.2M, reflecting a 24% increase from the previous year.
	The highest weekly sales were observed in the 50th week ($28M), with a significant drop in weeks 40 and 41, highlighting potential seasonal trends or market fluctuations.
2.	Brand & Model Performance:
	Chevrolet leads the market with 1,043 units sold, generating $27.1M, followed by Ford ($25.4M) and Dodge ($25.0M).
	Oldsmobile has the highest average price per vehicle ($31.6K), though it has fewer total sales (622 units).
	Toyota and Cadillac are among the top-selling brands, with models like the Toyota Land Cruiser ($33K) contributing significantly to total revenue.
3.	Customer Preferences:
	SUVs (25.41%) and Hatchbacks (24.75%) dominate sales, indicating high consumer demand.
	Passenger and Hardtop cars have lower market shares (17% and 12.9%, respectively), presenting opportunities for growth.
	Pale White is the most preferred car color (46% of total sales), while Red is the least popular.
4.	Regional Sales Insights:
	Austin has the highest YTD car sales, making it the strongest regional market.
	Janesville is another key market with significant sales, while smaller markets like Pasco, Aurora, and Greenville show lower sales volumes.
	The Southern and Midwestern regions have higher sales concentration, suggesting strong market demand in these areas.
5.	Inventory vs. Sales Analysis:
	High sales in specific models and brands indicate the need for better stock management and forecasting to meet consumer demand.
	Inventory turnover insights suggest that brands with lower sales may require targeted marketing strategies to boost performance.
6.	Revenue & Pricing Trends:
	The YOY growth in average car prices suggests a favourable pricing strategy or increased demand for higher-priced models.
	Competitive pricing strategies may be required for brands with lower sales to enhance market penetration.

## 🏆 Business Recommendations

✔ Optimize Inventory Management: Stock high-demand models & colors

✔ Enhance Marketing Strategies: Target underperforming regions with promotions

✔ Refine Pricing Strategies: Adjust prices based on regional demand

## CONCLUSION:
The Car Sales Dashboard developed in Power BI provides actionable insights that empower dealerships and manufacturers to make data-driven decisions. By analysing sales trends, customer preferences, and regional performance, businesses can optimize their inventory management, enhance marketing strategies, and drive overall growth. The findings indicate strong market demand for SUVs and Hatchbacks, with Chevrolet, Ford, and Dodge leading sales. Regional insights highlight Austin and Janesville as key markets, while emerging markets like Pasco and Greenville offer growth opportunities.
Moving forward, dealerships can leverage these insights to improve stock forecasting, tailor promotional campaigns, and refine pricing strategies, ultimately driving higher sales and profitability.


# Feedback and Suggestions:

Thank you for visiting my repository! If you have any questions or feedback, feel free to reach out.

I’d love to hear your thoughts, feedback, and suggestions! Feel free to connect with me:

 LinkedIn: [Shivanand Nashi](https://www.linkedin.com/in/shivanand-s-nashi-79579821a)
 
 Email: shivanandnashi97@gmail.com


Looking forward to connecting and exchanging ideas!

# ✨ Support this project!
If you found this project helpful or interesting, please consider giving it a ⭐ on GitHub!
Your support helps keep the project active and encourages further development.

Thank you for your support! 💖
