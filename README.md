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

## 🛠 SQL Analysis Steps

### 1. Database Setup
Created `sales` table in SQLite with the following schema:

CREATE TABLE sales (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    product TEXT,
    quantity INTEGER,
    price REAL,
    sale_date TEXT
); 

## 📊 Visualizations

- 📊 Bar chart → Revenue by Product
- 📈 Line chart → Revenue by Date
- 📉 Horizontal bar chart → Best-Selling Product
- 📊 Bar chart → Average Price per Product

(All visualizations are generated using Pandas + Matplotlib in the notebook.)

## 📂 Output Files

- 📒 Notebook: <a href="https://github.com/sabaribala2004-dataanalyst/Business-Insights-from-Sales-Data-SQL-Python-/blob/main/SQL_Python_Data_Analysis.ipynb"> Click to View the Notebook </a>
- 🗄️ Database File: sales_data.db
- 📊 Charts & Visualizations: Available inside the notebook.

## ✅ Status
- ✔ Database created successfully in SQLite
- ✔ Inserted and analyzed sales data using SQL queries
- ✔ Generated insights on product performance and revenue trends
- ✔ Visualized SQL outputs using Pandas & Matplotlib
- ✔ Task completed as per internship requirements

This project demonstrates:

- SQL for Data Analysis
- Extracting business insights from raw sales data
- Integration of SQL queries + Python visualization

📌 The dataset is now analysis-ready and SQL skills are effectively applied to generate actionable insights.


