# 🛒 Grocery Store Management System (SQL Project)

## 📘 Project Overview
The **Grocery Store Management System** is a SQL-based project designed to manage and analyze day-to-day operations of a grocery store.  
This project focuses on **inventory tracking, sales analysis, customer management**, and **supplier transactions**, helping store managers make data-driven decisions efficiently.

---

## 🎯 Objectives
- Design a **normalized relational database** for grocery store operations.
- Write **SQL queries** for CRUD (Create, Read, Update, Delete) operations.
- Perform **data analysis using aggregate and join queries**.
- Generate insights such as **top-selling products**, **monthly revenue**, and **supplier performance**.

---

## 🗂️ Database Structure

### **Main Tables**
1. **Customers** – Stores customer details.
2. **Products** – Contains product info (name, category, price, stock).
3. **Suppliers** – Details of suppliers providing the goods.
4. **Orders** – Tracks sales transactions.
5. **OrderDetails** – Line items for each order.
6. **Inventory** – Stock updates after purchases and sales.

---

## 💾 Key SQL Features Used
- **DDL Commands:** `CREATE`, `ALTER`, `DROP`
- **DML Commands:** `INSERT`, `UPDATE`, `DELETE`
- **DQL Commands:** `SELECT`, `JOIN`, `GROUP BY`, `ORDER BY`
- **Aggregate Functions:** `SUM()`, `AVG()`, `COUNT()`
- **Subqueries & Views**
- **Stored Procedures and Triggers** *(optional enhancement)*

---

## 📊 Sample Analysis Queries
```sql
-- 1️⃣ Top 5 best-selling products
SELECT p.ProductName, SUM(od.Quantity) AS TotalSold
FROM OrderDetails od
JOIN Products p ON od.ProductID = p.ProductID
GROUP BY p.ProductName
ORDER BY TotalSold DESC
LIMIT 5;

-- 2️⃣ Monthly revenue report
SELECT MONTH(OrderDate) AS Month, SUM(TotalAmount) AS Revenue
FROM Orders
GROUP BY MONTH(OrderDate)
ORDER BY Month;

-- 3️⃣ Low stock alert
SELECT ProductName, Stock
FROM Products
WHERE Stock < 10;
