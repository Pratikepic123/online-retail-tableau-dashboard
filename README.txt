ONLINE RETAIL SALES DASHBOARD (TABLEAU)
=======================================

An interactive Tableau dashboard that analyses online retail transactions
(online_retail_09_10.csv). It tracks sales, customers, products, countries
and time patterns, with dynamic Top-N controls and KPI selectors.


BUSINESS QUESTIONS ANSWERED
---------------------------
  - How much revenue, how many invoices and how many customers do we have?
  - What is the average order value (AOV)?
  - Which countries, products and customers generate the most sales?
  - How do sales change by month, weekday and hour of day?
  - How much revenue is lost to cancelled orders?
  - How are sales spread across customers?


TOOLS USED
----------
  - Tableau Desktop (workbook version 18.1)
  - Tableau extract (.hyper) built from a CSV file


DASHBOARD: ONLINE RETAIL DASHBOARD
----------------------------------
Size: 1366 x 768 (fixed)

  KPI cards                   : Total Sales, Total Invoices, Total
                                Customers, AOV
  Dynamic Monthly Sales Trend : Monthly sales driven by a metric selector
  Sales by Country Map        : Filled map using geographic roles
  Top 10 Products by Sales    : Bar chart with a Top-N control
  Customer Leaderboard        : Customers ranked by revenue

Dashboard actions (filter and highlight) let you click one chart to filter
the others.


ADDITIONAL WORKSHEETS
---------------------
  Hour of Day vs Sales                  : Heatmap of the busiest hours
  Sales by Weekday (Mon-Sun)            : Weekly sales pattern
  Cancelled vs Completed Sales          : Revenue impact of cancellations
  Customer Purchase Frequency           : Number of invoices per customer
  Customer Sales Distribution Histogram : Spread of total sales per customer
  Monthly Sales Trend (filters)         : Trend with country and StockCode
                                          filters
  Quantity vs Unit Price                : Scatter plot for price and volume
  Top 10 Customers by Revenue           : Best customers
  Sales by Description                  : Sales by product description
  KPI Selector                          : Switch the KPI shown


CALCULATED FIELDS
-----------------
  Total Sales             : Quantity * UnitPrice
  Total Sales (ABS)       : ABS(Quantity * UnitPrice)
  Total Invoices          : COUNTD(InvoiceNo)
  AOV                     : Total Sales / distinct invoices
  Sale Status             : "Cancelled" if the invoice number starts with
                            C, otherwise "Completed"
  Cancelled Flag          : 1 if the invoice number starts with C
  Negative Quantity Flag  : 1 if Quantity < 0
  Missing CustomerID Flag : 1 if CustomerID is empty
  Weekday / Hour of Day   : Date parts of InvoiceDate
  Top N Filter, Product Rank, Customer Rank
                          : RANK based Top-N logic controlled by a parameter
  Selected Metric / Selected KPI Value
                          : Switches the measure based on a parameter


PARAMETERS
----------
  Top N           : Number of countries, products or customers to show
  Metric Selector : Choose Total Sales, Total Quantity or Total Invoices
  KPI Selector    : Choose which KPI card to display


DATA QUALITY CHECKS BUILT IN
----------------------------
  - Cancelled invoices (invoice numbers starting with C)
  - Negative quantities (returns)
  - Missing customer IDs


REPOSITORY STRUCTURE
--------------------
  online-retail-tableau-dashboard/
      Task_1_With_Extract_.twbx   - packaged Tableau workbook (data included)
      screenshots/
          dashboard.png           - dashboard screenshot
      README.txt                  - this file


HOW TO OPEN
-----------
  1. Install Tableau Desktop (or the free Tableau Public desktop app).
  2. Download Task_1_With_Extract_.twbx from this repository.
  3. Double-click the file. The data is packaged inside it, so no extra
     setup is needed.


KEY LEARNINGS
-------------
  - Building dynamic dashboards with parameters and CASE logic
  - Top-N analysis with RANK and table calculations
  - Cleaning-style flags for cancellations, returns and missing IDs
  - Combining KPI cards, maps and trend charts in one dashboard


AUTHOR
------
Pratik
Aspiring Data Analyst | SQL | Tableau | Python
