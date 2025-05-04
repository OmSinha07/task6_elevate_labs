# task6_elevate_labs

# Task6_Elevate_Labs
# 📊 Task 6: Sales Trend Analysis Using Aggregations

## 🎯 Objective
Analyze monthly revenue and order volume from an e-commerce dataset using SQL aggregations and time-based grouping.

---

## 🛠 Tools Used
- PostgreSQL / MySQL / SQLite (adjust syntax accordingly)
- SQL Editor / DBMS Client

---

## 📂 Dataset
- Table Name: online_sales
- Fields:
  - order_id (unique ID)
  - order_date (timestamp)
  - amount (numeric)
  - product_id (optional for breakdown)

---

## 📈 SQL Steps

### A. Monthly Revenue & Order Volume
```sql
SELECT 
  EXTRACT(YEAR FROM order_date) AS year,
  EXTRACT(MONTH FROM order_date) AS month,
  SUM(amount) AS total_revenue,
  COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY year, month
ORDER BY year, month;
