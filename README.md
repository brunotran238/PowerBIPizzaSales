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
- **Microsoft Excel (simulated dataset)**

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

- Split ingredient column into rows
- Trimmed and cleaned ingredient text
- Removed duplicate records
- Created `Dim_Ingredient` from distinct ingredient list
- Created `Dim_Pizza` using Pizza Name
- Generated Date and Time dimension tables
- Created calculated columns:
  - `Order DateTime`
  - `Order Type`
  - `Minutes Between Orders (Day Only)`
  - `SizeSort`

No preprocessing was performed outside Power BI.

---

## 🏗️ Data Modeling

The final model follows a structured dimensional approach.

### Fact Table

**Fact**
- One row per pizza per order
- Contains quantity, price, revenue, order ID, and date/time attributes

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

The dashboard consists of multiple analytical views:

### 1️⃣ Executive Overview

- **Total Revenue:** $817.86K  
- **Total Orders:** 21,350  
- **Total Quantity Sold:** 49.57K  
- **Average Order Value:** $38.31  
- **Multi-item Orders:** 62%  
- **Average Minutes Between Orders (Day Only):** 10.9 minutes  

---

### 2️⃣ Sales Trends

- Strongest Month: **July**
- Strongest Day of Week: **Friday**
- Peak Hours: **12:00–13:59 (Lunch peak)**
- Identified seasonal and intra-day demand patterns

---

### 3️⃣ Product Performance

- Strongest Category: **Classic**
- Clear revenue and volume concentration among top 5 pizzas
- Bottom performers identified for menu optimisation

---

### 4️⃣ Ingredient Analysis

- Dominant Ingredients: **Tomatoes, Garlic**
- Ingredient revenue vs quantity segmentation using quadrant analysis
- Average reference lines implemented for performance grouping

---

### 5️⃣ Pricing & Demand Correlation

- Correlation between Average Pizza Price and Total Quantity: **-0.95**
- Indicates strong inverse relationship
- Suggests price elasticity at category level

---

### 6️⃣ Order Behaviour

- 62% of orders contain multiple pizzas
- Demand clustering during peak hours
- Average 10.9 minutes between orders (excluding overnight gaps)

This metric was calculated using day-only logic to avoid inflation from non-operating hours.

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

- `Pizza Sales_Dashboard.pbix`
- Supporting documentation
- `README.md`

---

## 👨‍💻 Author

Bruno Tran  
Business Intelligence & Data Analytics Enthusiast  
