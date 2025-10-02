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

##  SQL Queries & Results



