# 🛒 Business Insights from Sales Data (SQL + Python) (Task 7)

## 📌 Description  
This project is part of a **Data Analyst Internship Task (Task 7)**.  
The dataset used is a **sample E-Commerce sales dataset**, analyzed using **SQL (SQLite in Google Colab)** along with **Python (Pandas, Matplotlib)**.  

The main objective of this task was to perform **SQL-based data analysis** to extract meaningful business insights, and visualize them using Python.  
The analysis includes **table creation, data insertion, SQL queries, and visualizations**.  

---

## 🔑 Key tasks performed  

- Created a **sales database** using SQLite.  
- Inserted **sample transaction data** (Product, Quantity, Price, Sale Date).  
- Executed **SQL queries** for data analysis:  
  - Revenue by product  
  - Revenue by date  
  - Best-selling product by quantity  
  - Average price per product  
- Used **Python (Pandas, Matplotlib)** to run SQL queries and plot results.  
- Documented **key insights** from visualizations.  

---

## 📊 Dataset  

- Source: Sample E-Commerce Sales Data (manually created for the task)  
- File: `sales_data.db`  
- Features include:  
  - **Product** → Name of the product  
  - **Quantity** → Number of units sold  
  - **Price** → Price per unit  
  - **Sale Date** → Date of transaction  

---

## 🛠️ SQL Analysis Steps  

### 1. Database Setup  
Created `sales` table in SQLite with the following schema:  

```sql
CREATE TABLE sales (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    product TEXT,
    quantity INTEGER,
    price REAL,
    sale_date TEXT
);

## 2. SQL Queries & Results

### 📌 Query 1: Revenue by Product
```sql
SELECT product, SUM(quantity) AS total_qty, SUM(quantity * price) AS revenue
FROM sales
GROUP BY product;

- Description: Calculates total quantity sold and total revenue generated for each product.
- Visualization: Bar Chart → Revenue by Product


### 📌 Query 2: Revenue by Date
```sql
SELECT sale_date, SUM(quantity * price) AS daily_revenue
FROM sales
GROUP BY sale_date
ORDER BY sale_date;

### 📌 Query 3: Best-Selling Product (Quantity)
```sql
SELECT product, SUM(quantity) AS total_qty
FROM sales
GROUP BY product
ORDER BY total_qty DESC
LIMIT 1;

### 📌 Query 4: Average Price per Product
```sql
SELECT product, AVG(price) AS avg_price
FROM sales
GROUP BY product;

-------




