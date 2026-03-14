# 📊 E-Commerce Sales Performance Dashboard

## 📝 Project Overview
This project is an interactive Power BI dashboard designed to analyze the sales performance of an e-commerce retail store. The goal of this project is to transform raw, transactional sales data into a high-level visual narrative, allowing business stakeholders to quickly understand revenue trends, identify top-performing product categories, and evaluate regional market dominance. 


## 🗂️ Dataset
* **Source:** Kaggle (Superstore Sales Dataset)
* **Description:** The dataset contains historical sales records, including detailed information on order dates, geographic locations, customer segments, and product categories.
* **Size:** ~9,800 rows and 18 columns.

## 🛠️ Tech Stack & Skills Highlighted
* **Business Intelligence:** Microsoft Power BI
* **Data Transformation (ETL):** Power Query Editor
* **Analytics & Calculations:** DAX (Data Analysis Expressions)
* **Dashboard Design:** Page navigation, synchronized slicers, conditional formatting, and custom corporate themes.

## 📈 Dashboard Structure
The dashboard is built with a multi-page, app-like navigation system for optimal user experience.

### 1. Overview Page (Executive Summary)
* **KPI Cards:** High-level metrics for Total Sales, Total Orders, Average Order Value (AOV), and Total Customers.
* **Sales Trend:** A Line Chart tracking revenue growth over time to identify seasonality.
* **Segment & Regional Breakdown:** Donut charts and maps distributing market share across consumer segments and states.

### 2. Details Page (Deep-Dive Analytics)
* **Product Matrix:** An interactive drill-down table with conditional data bars to view sales by Category and specific Product Names.
* **Top 10 Customers:** A filtered bar chart identifying the most valuable VIP clients.
* **Shipping Efficiency:** A column chart tracking the custom `Delivery Days` metric across different shipping modes.
* **Category Revenue:** A proportional Treemap showcasing revenue distribution across primary product categories.

## ⚙️ Data Preparation & DAX Measures
The raw CSV file was extracted and transformed using **Power Query**. Key data cleaning steps included:
* Correcting date localization formatting.
* Filtering out null values to ensure geographic mapping accuracy.
* Engineering a custom column (`Delivery Days`) by calculating the difference between `Ship Date` and `Order Date`.

**Key DAX Measures Created:**
```dax
Total Sales = SUM('train'[Sales])

Total Orders = DISTINCTCOUNT('train'[Order ID])

Average Order Value = DIVIDE([Total Sales], [Total Orders], 0)

Total Customers = DISTINCTCOUNT('train'[Customer ID])