# 🛒 Online Shopping Sales Analysis Project

**Schema Name:** `sales`  
**Difficulty Level:** `Advanced`  
**Database Used:** PostgreSQL / MySQL

---

## 📘 Project Overview

This project focuses on analyzing the complete lifecycle of an e-commerce business through SQL. Using a structured relational database consisting of 9 tables, it simulates an Amazon-like sales environment.

Through querying, transformation, and analysis, we aim to draw valuable business insights related to customer behavior, product sales, order management, shipping delays, payment trends, and inventory performance.

---

## 🛠 Database Setup & Design

**Schema:** `sales`  
**Total Tables:** 9  
- `category`  
- `customers`  
- `product`  
- `orders`  
- `order_item`  
- `payment`  
- `shipping`  
- `inventory`  
- `returns` *(optional)*

The schema design is normalized to reduce redundancy and ensures data integrity through proper foreign key relationships.

---

## 🎯 Project Objectives

- Build a realistic sales database with 20K+ records
- Perform queries from beginner to advanced level
- Clean, transform, and enrich raw data using SQL
- Analyze and visualize key business metrics
- Simulate real-world business scenarios using SQL

---

## 🧪 Tasks Performed

### ✅ Data Cleaning
- Removed duplicate records
- Standardized inconsistent values
- Converted date formats and null fields

### ✅ Handling Nulls
- Replaced nulls using COALESCE, CASE statements
- Identified missing relationships via LEFT JOINs

### ✅ Identifying Business Problems
- What products are underperforming?
- Which customers are returning products most often?
- Which regions are causing delays in shipping?

### ✅ Solving Business Problems
- Using SQL window functions to rank top customers
- Inventory restock alerts via conditional logic
- Delivery time vs. return rate correlation analysis

---

## 🧩 Sample Queries Used

```sql
-- Top 5 products by revenue
SELECT p.product_name, SUM(oi.quantity * oi.unit_price) AS total_revenue
FROM order_item oi
JOIN product p ON oi.product_id = p.product_id
GROUP BY p.product_name
ORDER BY total_revenue DESC
LIMIT 5;
