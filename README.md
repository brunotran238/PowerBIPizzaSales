# 🍕 Pizza Sales Analytics Dashboard (Power BI)

## End-to-End Data Modeling & Analytics Case Study

---

## 📌 Project Overview

This project presents an end-to-end Business Intelligence solution built in **Power BI**, analysing 2015 transactional sales data for a simulated pizza company.

The objective was to transform raw transactional data into a structured dimensional model and deliver actionable insights through an interactive dashboard.

This project demonstrates:

- Dimensional data modeling (Star/Snowflake schema)
- Data transformation using Power Query
- Advanced DAX calculations
- Business-driven KPI development
- Analytical storytelling & dashboard design

---

## 🌐 Live Dashboard

You can explore the interactive Power BI dashboard here:

🔗 **[View Live Dashboard on Power BI Service](https://app.powerbi.com/links/ndF8bMa2y3?ctid=6a425d0d-58f2-4e36-8689-10002b2ec567&pbi_source=linkShare)**

---

## 🎯 Problem Statement

The business needs to understand:

- What drives revenue and sales volume?
- Which products and ingredients contribute most to performance?
- How do ordering patterns vary by time and day?
- Is pricing influencing demand?
- How can operational efficiency and profitability be improved?

The goal was to design a dashboard that supports **strategic decision-making** in pricing, menu engineering, staffing, and inventory planning.

---

## 🛠️ Technical Stack

- **Power BI Desktop**
- **Power Query (M)**
- **DAX**
- **Microsoft Excel**

---

## 📊 Dataset Information

- **Source:** Simulated Excel dataset  
- **Year Covered:** 2015  
- **Rows:** 48,620  
- **Columns:** 10  
- **Grain:** One row per pizza per order  
  *(One order may contain multiple pizza line items)*  

### Data Preparation & Cleaning

The following transformations were performed in Power Query:

- Removed duplicate records
- Created `Dim_Ingredient` by splitting ingredient column into rows, trimmed and cleaned to retrieve distinct ingredient list
- Created `Dim_Pizza` contains distinct Pizza Name
- Created `Dim_PizzaIngredient` connected to both `Dim_Ingredient` and `Dim_Pizza`
- Generated Date and Time dimension tables
- Created calculated columns:
  - `Order DateTime`
  - `Order Type`
  - `Minutes Between Orders (Day Only)`
  - `SizeSort`

---

## 🏗️ Data Modeling

Below is the star schema model used in this project:
![Data Model](/images/data_model.png)


### Fact Table

**Fact**
- One row per pizza per order
- Contains quantity, size, price, order ID, pizza ID, pizza name, category, ingredients and date/time attributes

### Dimension Tables

- `Dim_Date`
- `Dim_Time`
- `Dim_Pizza`
- `Dim_Ingredient`

### Bridge Table

- `Dim_PizzaIngredient`
  - Links pizzas to ingredients
  - Resolves many-to-many relationship via bridge design

### Relationship Design

- Single-direction filters for most relationships
- Both-direction filter used only between:
  - `Dim_Pizza` ↔ `Dim_PizzaIngredient`

This ensures proper ingredient-level filtering while maintaining model integrity.

---

## 📈 Analysis & Visualisation

The Power BI dashboard consists of multiple visual elements to display insights:

### 🏠 Overview Page

- **Total Revenue – KPI Card –** Used to display overall revenue performance for 2015.

- **Total Quantity – KPI Card –** Shows total pizzas sold, representing overall demand volume.

- **Total Orders – KPI Card –** Indicates transaction volume and business activity level.

- **Average Order Value – KPI Card –** Measures revenue efficiency per order.

- **Average Pizza per Order – KPI Card –** Identifies purchasing behaviour (single vs bundled purchases).

- **Average Minutes Between Orders – KPI Card –** Shows operational order cadence (day-only logic to exclude overnight gaps).

- **Total Sales by Category and Size – Clustered Column Chart –** Used to compare revenue contribution across categories and pizza sizes.

- **Pizza Categories Ranked by Quantity and Total Sales – Matrix Table –** Displays category ranking by volume and revenue for performance benchmarking.

- **Order Type Proportion – Pie Chart –** Visualises distribution between single-item and multi-item orders.

- **Total Sales by Month – Line Chart –** Shows monthly revenue trend and seasonality patterns.

- **Category, Month, Weekday, Weekend – Slicers –** Enable interactive filtering for multi-dimensional analysis.

![Overview](/images/overview.png)

---

### 📊 Sales Trend Page

- **Total Sales by Month – Line Chart –** Identifies seasonal revenue fluctuations.

- **Total Sales by Weekday Name – Clustered Column Chart –** Compares weekday performance to determine strongest trading days.

- **Total Sales by Week Number – Line Chart –** Detects short-term trends and anomalies throughout the year.

- **Total Sales by Day – Line Chart –** Enables daily-level anomaly detection.

- **Total Sales by Hour – Column Chart –** Identifies intra-day peak demand periods (e.g., lunch and dinner peaks).

![Sales Trend](/images/sales_trend.png)

---

### 🍕 Product Performance Page

- **Most Popular Pizza by Quantity – Bar Chart –** Highlights top-selling pizzas by volume.

- **Most Popular Pizza by Revenue – Bar Chart –** Identifies highest revenue-generating pizzas.

- **Least Popular Pizza by Quantity – Bar Chart –** Detects low-volume products for potential optimisation.

- **Least Popular Pizza by Revenue – Bar Chart –** Highlights low-revenue SKUs for pricing or menu review.

- **Category Slicer – Interactive Filter –** Allows segmentation of product performance by category.

![Product Performance](/images/product_performance.png)

---

### 🧄 Ingredients Analysis Page

- **Average Pizza Price vs Total Quantity by Category – Scatter Plot with Trend Line –** Used to analyse price-volume relationship and calculate correlation (-0.95).

- **Most Popular Ingredients – Horizontal Bar Chart –** Identifies top-demand ingredients by quantity.

- **Total Quantity and Total Revenue by Ingredients – Scatter Plot with Average Reference Lines –** Segments ingredients into performance quadrants (High/Low Quantity vs High/Low Revenue).

- **Least Popular Ingredients – Horizontal Bar Chart –** Detects low-impact ingredients for inventory or cost review.

- **Category Slicer – Interactive Filter –** Enables ingredient performance analysis by category.

![Ingredients Analysis](/images/ingredients_analysis.png)

---

## 📌 Key Insights

- Revenue is concentrated in a limited number of pizzas and ingredients.
- Strong negative correlation suggests pricing sensitivity.
- Multi-item orders dominate purchasing behaviour.
- Peak operational hours require targeted staffing and batching strategies.
- Ingredient-level insights support supplier negotiation and cost management.

---

## 🚀 Business Recommendations

### Demand Optimisation
- Formalise Friday and peak-hour campaigns.
- Leverage seasonal peaks (July and late-November).

### Menu Engineering
- Promote high-performing Classic pizzas.
- Review bottom performers for repositioning or removal.

### Pricing Strategy
- Test targeted promotions in higher-priced categories.
- Protect margin on premium/niche ingredients.

### Operational Efficiency
- Align staffing with 12–14 and 17–20 peak windows.
- Use order cadence data for batching and kitchen throughput planning.

### Inventory Management
- Ensure safety stock for high-demand ingredients (Tomatoes, Garlic).
- Negotiate supplier pricing for high-volume ingredients.

---

## ▶️ How to Use This Dashboard

1. Use slicers (Category, Month, Weekday) to explore patterns.
2. Navigate between pages:
   - Overview
   - Sales Trend
   - Product Performance
   - Ingredients Analysis
3. Hover over scatterplots to inspect ingredient-level performance.
4. Use correlation and quadrant visuals to identify core vs niche contributors.

The dashboard is designed for interactive exploration to support strategic and operational decisions.

---

## 💡 Skills Demonstrated

- Dimensional Data Modeling (Star & Bridge)
- Many-to-many resolution using bridge tables
- Advanced DAX (Ranking, Correlation, Time Intelligence)
- KPI engineering
- Operational metric design (Day-only interval calculation)
- Data cleaning & transformation
- Business storytelling & executive reporting

---

## 📎 Repository Contents

- `Pizza Sales_Dashboard.pbix` – Power BI source file
- `README.md` – Project documentation
- Power BI Service Live Link – Interactive dashboard

---

## 👨‍💻 Author

Bruno Tran  
Business Intelligence & Data Analytics Enthusiast  
