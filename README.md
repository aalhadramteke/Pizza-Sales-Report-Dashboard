# 🍕 Pizza Sales Report Dashboard

A comprehensive **Power BI Dashboard** designed to analyze pizza sales performance, identify key sales trends, evaluate peak order times, and provide actionable business insights for menu optimization and revenue growth.

---

## 📋 Table of Contents
- [Overview](#overview)
- [Key Features & Metrics](#key-features--metrics)
- [Dashboard Pages & Layout](#dashboard-pages--layout)
- [Data Model & Architecture](#data-model--architecture)
- [Key DAX Measures](#key-dax-measures)
- [Installation & Setup](#installation--setup)
- [How to Use](#how-to-use)
- [Insights & Business Recommendations](#insights--business-recommendations)
- [License](#license)

---

## 🎯 Overview

This Power BI project presents an end-to-end analytics solution for a pizza restaurant chain. By transforming raw transactional data into interactive visual reports, store managers and stakeholders can track sales targets, monitor order volume, evaluate menu performance, and streamline operational efficiency during peak hours.

---

## 📊 Key Features & Metrics

### High-Level KPIs
* **Total Revenue:** Overall income generated from pizza sales.
* **Average Order Value (AOV):** Average amount spent per order (`Total Revenue / Total Orders`).
* **Total Pizzas Sold:** Total count of individual pizzas sold.
* **Total Orders:** Distinct count of customer orders processed.
* **Average Pizzas Per Order:** Average quantity of pizzas purchased per order (`Total Pizzas Sold / Total Orders`).

### Detailed Analytical Views
* **Daily & Monthly Sales Trends:** Visualizing revenue and order volume patterns by day of the week and month to pinpoint high-traffic periods.
* **Sales by Pizza Category:** Percentage share and total revenue across categories (Classic, Supreme, Chicken, Veggie).
* **Sales by Pizza Size:** Customer preference distribution across Regular (S), Medium (M), Large (L), XL, and XXL sizes.
* **Best & Worst Performers (Top 5 / Bottom 5):**
  * **By Revenue:** Best-selling vs. lowest-grossing pizzas.
  * **By Total Quantity:** Most popular vs. least ordered items.
  * **By Total Orders:** Highest vs. lowest transaction counts.

---

## 🖥️ Dashboard Pages & Layout

The report **`Pizza Sales Report Dashboard.Report`** consists of two primary analytical views:

### 1. Home / Overview Page
Designed for executive decision-makers to get a quick pulse of overall business health.
* **Header / Summary Bar:** Core KPI Cards (Revenue, AOV, Total Pizzas, Total Orders, Avg Pizzas/Order).
* **Trend Analysis:** Column chart showing total orders by day of week; line chart showing monthly sales trends.
* **Category & Size Breakdown:** Pie/Donut charts displaying Revenue Share by Category and Sales Share by Size.

### 2. Best / Worst Sellers Page
Designed for menu engineering, operational planning, and inventory management.
* **Top 5 Pizzas:** Bar charts identifying top-performing pizzas by Revenue, Quantity, and Orders.
* **Bottom 5 Pizzas:** Bar charts identifying bottom-performing pizzas by Revenue, Quantity, and Orders to evaluate menu rationalization or marketing promotions.

---

## 🗄️ Data Model & Architecture

The report leverages a clean, star-schema data model (or flat relational model) with optimized DAX measures:

* **Fact Table:** `pizza_sales`
  * `pizza_id`: Unique identifier for each item line.
  * `order_id`: Order identifier.
  * `pizza_name_id`: Product code.
  * `quantity`: Number of units sold.
  * `order_date`: Transaction date.
  * `order_time`: Transaction time.
  * `unit_price`: Price per pizza.
  * `total_price`: Line item total revenue.
  * `pizza_size`: Size designation (S, M, L, XL, XXL).
  * `pizza_category`: Category grouping (Classic, Supreme, Chicken, Veggie).
  * `pizza_name`: Detailed pizza name.

---

## 🧮 Key DAX Measures

// Total Revenue
Total Revenue = SUM(pizza_sales[total_price])

// Total Orders
Total Orders = DISTINCTCOUNT(pizza_sales[order_id])

// Total Pizzas Sold
Total Pizzas Sold = SUM(pizza_sales[quantity])

// Average Order Value (AOV)
Average Order Value = [Total Revenue] / [Total Orders]

// Average Pizzas Per Order
Avg Pizzas Per Order = [Total Pizzas Sold] / [Total Orders]


# 🚀 Installation & Setup
Prerequisites
Microsoft Power BI Desktop (Latest Version recommended).

Steps
Clone or Download the Repository: https://github.com/aalhadramteke/Pizza-Sales-Dashboard.git

Bash
git clone 
Open the Project: https://github.com/aalhadramteke/Pizza-Sales-Dashboard.git

Navigate to the project folder.

Open Pizza Sales Report Dashboard.Report using Power BI Desktop.

Data Source Configuration:

If required, update the file source path in Power Query Editor (Transform Data > Data Source Settings) to point to your local dataset path (pizza_sales.csv or SQL database).

Click Apply & Close to refresh data.

# 💡 Insights & Business Recommendations
Peak Operations: Fridays and Saturdays during evening hours account for the highest volume of orders. Ensure adequate staffing and driver availability.

Menu Focus: Large (L) and Medium (M) sizes dominate sales revenue. Consider bundling promotions around these sizes.

Category Strategy: Classic and Chicken categories drive the highest gross margin; promote bottom-performing veggie options or optimize ingredient stock to minimize waste.

# 📜 License
This project is licensed under the MIT License - see the LICENSE file for details.
