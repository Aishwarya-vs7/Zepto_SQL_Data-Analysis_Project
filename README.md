# 🛒 Zepto E-Commerce Inventory SQL Analysis 💜

## 📌 Project Overview

This project simulates a real-world **E-commerce Inventory Analysis** workflow using SQL.
The dataset represents product listings scraped from Zepto’s inventory system and includes pricing, discounts, stock status, and product-level metadata.

The goal was to perform:

* Database creation from raw CSV data
* Exploratory Data Analysis (EDA)
* Data cleaning and transformation
* Business-driven SQL analysis
* Retail-focused insight generation

This project demonstrates practical SQL skills aligned with **retail, quick-commerce, and product analytics** roles.

---

## 📊 Dataset Information

* **Source:** Kaggle – Zepto Inventory Dataset
* **Total Records:** 3,732 SKUs
* **In-Stock Products:** 3,279
* **Out-of-Stock Products:** 453
* **Categories:** 14 major product categories

Each row represents a unique SKU (Stock Keeping Unit).
Duplicate product names exist because products appear in multiple variations (size, weight, discount, packaging), reflecting real-world retail catalog behavior.

---

## 🛠 Tech Stack

* PostgreSQL
* SQL (Joins, Aggregations, Group By, Filtering, Ranking)
* pgAdmin
* CSV Import Handling

---

## 🏗 Database Schema

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
```

---

## 🔍 Exploratory Data Analysis (EDA)

Performed the following:

* Counted total number of records
* Checked for null values
* Identified distinct product categories
* Compared in-stock vs out-of-stock products
* Detected products with multiple SKUs

### Key Observation

* ~87% of products are currently in stock
* Significant SKU duplication exists — common in e-commerce platforms

---

## 🧹 Data Cleaning

### 1️⃣ Removed Invalid Price Records

```sql
DELETE FROM zepto
WHERE mrp = 0;
```

### 2️⃣ Converted Prices from Paise to Rupees

```sql
UPDATE zepto
SET mrp = mrp / 100.0,
    discountedSellingPrice = discountedSellingPrice / 100.0;
```

This ensured pricing consistency and readability.

---

## 📈 Business Analysis Performed

### 💰 Top Discounted Products

Identified products offering highest discount percentages.

### 🏷 High-MRP Products Out of Stock

Detected premium products currently unavailable (revenue opportunity).

### 📊 Revenue Estimation by Category

Estimated potential revenue using:

```
discountedSellingPrice × availableQuantity
```

### 📦 Price Per Gram Analysis

Calculated value-for-money products.

### 🎯 Category Ranking

Ranked categories based on:

* Average discount percentage
* Revenue potential
* Inventory weight contribution

---

## 📌 Key Insights

✔ Majority of inventory is in stock
✔ 14 diverse product categories analyzed
✔ SKU duplication reflects realistic catalog structure
✔ Price standardization improved financial analysis accuracy
✔ SQL aggregation functions enabled business KPI simulation

---

## 💡 Business Use Case Simulation

If this were a real retail analytics environment, this analysis would support:

* Pricing optimization
* Inventory planning
* Revenue forecasting
* Discount strategy decisions
* Category performance evaluation

---

## 🚀 Skills Demonstrated

* SQL Database Design
* Data Cleaning & Transformation
* Aggregation & Grouping
* Business KPI Thinking
* Retail & Inventory Analytics
* Analytical Problem Solving

---

## 📂 How to Run This Project

1. Clone the repository:

```bash
git clone <your-repo-link>
```

2. Open the SQL file in PostgreSQL / pgAdmin

3. Create a database and run the schema

4. Import CSV dataset (ensure UTF-8 encoding)

5. Execute business analysis queries

---

## 🎯 Why This Project Matters

This project demonstrates end-to-end data analyst workflow:

Raw Data → Structured Database → Cleaning → EDA → Business Insights

It reflects real-world responsibilities of:

* Data Analyst
* Retail Analyst
* E-commerce Analyst
* Business Intelligence Analyst

---

## 👩‍💻 About Me

Aishwarya V S
Aspiring Data Analyst | SQL | Power BI | Python | Tableau | Excel
Linkedin profile : www.linkedin.com/in/aishwarya-v-s-52410b270
I enjoy turning raw datasets into structured insights that support business decisions.



