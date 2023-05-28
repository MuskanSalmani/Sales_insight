## Sales_Insights Data Analysis Project


The Sales Insight Project is a comprehensive data analysis and visualization project that I developed using SQL analysis and Power BI. This project was aimed at providing valuable insights into sales data to support strategic decision-making and drive business growth.


## Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

1. M-language Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

## DAX to define custom calculations for Calculated Columns and for Measures:

2. Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)
3. Profit Margin Contribution % = DIVIDE([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
4. Revenue = SUM('Sales transactions'[norm_sales_amount])
5. Revenue Contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
6. Revenue LY = CALCULATE([Revenue],SAMEPERIODLASTYEAR('sales date'[date]))
7. Sales Qty = SUM('sales transactions'[sales_qty])
8. Total Profit Margin = SUM('Sales transactions'[Profit_Margin])

Key Features:

**Data Extraction and Transformation:** I utilized SQL to extract data from various sources, including sales databases, customer information, and transaction records. Through data cleansing and transformation techniques, I ensured the accuracy and consistency of the data.

**Data Analysis:** Leveraging SQL's analytical capabilities, I performed in-depth analysis on the sales data. This involved querying and aggregating data to uncover meaningful patterns, trends, and relationships. I utilized advanced SQL functions and techniques to derive key metrics, such as total revenue, sales by region, top-selling products, and customer segmentation.

**Power BI Visualization:** To effectively communicate the insights derived from the data analysis, I employed Power BI, a powerful business intelligence tool. I designed interactive and visually appealing dashboards, reports, and charts to present the sales data in a comprehensive and intuitive manner. The visualizations included dynamic filters, drill-down functionality, and slicers to facilitate deep exploration of the sales metrics.

**Sales Performance Monitoring:** The project also focused on creating a real-time sales performance monitoring system. I developed interactive dashboards that allowed stakeholders to track sales progress, compare actual performance against targets, and identify areas of improvement. These dashboards provided clear visual indicators, such as KPIs, sales trends, and performance heat maps.

**Data-driven Insights and Recommendations:** By combining the SQL analysis and Power BI visualizations, I generated actionable insights and recommendations for the sales team and management. These insights ranged from identifying underperforming products or regions to suggesting targeted marketing strategies and customer retention initiatives

**Benefits and Impact:**

**Enhanced decision-making:** The Sales Insight Project empowered stakeholders to make informed decisions based on accurate and comprehensive sales data analysis. It provided a holistic view of the sales performance and enabled the identification of opportunities and potential risks.

**Increased sales efficiency:** By visualizing the sales data in Power BI, the project enabled the sales team to monitor performance metrics in real-time, identify bottlenecks, and make data-driven adjustments to their strategies. This led to improved sales efficiency and productivity.

**Improved customer targeting:** The project's customer segmentation analysis helped identify different customer groups and their preferences. This information assisted in developing personalized marketing campaigns and enhancing customer targeting, resulting in higher conversion rates and customer satisfaction.

**Scalability and adaptability:** The project's architecture and design allowed for easy scalability and adaptability to accommodate future growth and changes in the sales landscape. New data sources can be incorporated, and additional analytics can be implemented to support evolving business needs.

The Sales Insight Project showcases my expertise in SQL analysis and Power BI visualization, as well as my ability to translate complex data into meaningful insights. Through this project, I demonstrated the value of data-driven decision-making and the potential for leveraging technology to drive sales growth and improve business performance.








