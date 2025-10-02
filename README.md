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

- **Source**: Sample E-Commerce Sales Data (manually created for the task)  
- **File**: `sales_data.db`  
- **Features include**:  
  - **Product** → Name of the product  
  - **Quantity** → Number of units sold  
  - **Price** → Price per unit  
  - **Sale Date** → Date of transaction  

---

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

## 🛠 SQL + Python Code  

```python
import sqlite3
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline

# Connect to SQLite (creates 'sales_data.db')
conn = sqlite3.connect('sales_data.db')
cur = conn.cursor()

# Create sales table
cur.execute('''
CREATE TABLE IF NOT EXISTS sales(
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    product TEXT,
    quantity INTEGER,
    price REAL,
    sale_date TEXT
)
''')
conn.commit()

# Insert Values
sample = [
    ('T-shirt', 10, 299.0, '2025-09-20'),
    ('T-shirt', 5, 299.0, '2025-09-21'),
    ('Mug', 20, 199.0, '2025-09-20'),
    ('Mug', 5, 199.0, '2025-09-22'),
    ('Notebook', 7, 149.0, '2025-09-21')
]
cur.executemany('INSERT INTO sales(product,quantity,price,sale_date) VALUES (?,?,?,?)', sample)
conn.commit()

# Revenue by Product
query = """
SELECT product,
       SUM(quantity) AS total_qty,
       SUM(quantity * price) AS revenue
FROM sales
GROUP BY product
"""
df = pd.read_sql_query(query, conn)
print(df)
df.plot(kind='bar', x='product', y='revenue', legend=False, figsize=(6,4), title='Revenue by Product')
plt.show()

# Revenue by Date
query2 = """
SELECT sale_date,
       SUM(quantity * price) AS daily_revenue
FROM sales
GROUP BY sale_date
ORDER BY sale_date
"""
df2 = pd.read_sql_query(query2, conn)
print(df2)
df2.plot(kind='line', x='sale_date', y='daily_revenue', marker='o', figsize=(6,4), title='Revenue by Date')
plt.show()

# Best-Selling Product (by Quantity)
query3 = """
SELECT product,
       SUM(quantity) AS total_qty
FROM sales
GROUP BY product
ORDER BY total_qty DESC
LIMIT 1
"""
df3 = pd.read_sql_query(query3, conn)
print(df3)
df3.plot(kind='barh', x='product', y='total_qty', legend=False, figsize=(6,3), title='Top Selling Product (Quantity)')
plt.show()

# Average Price per Product
query4 = """
SELECT product,
       AVG(price) AS avg_price
FROM sales
GROUP BY product
"""
df4 = pd.read_sql_query(query4, conn)
print(df4)
df4.plot(kind='bar', x='product', y='avg_price', legend=False, figsize=(6,4), title='Average Price per Product')
plt.show()

# Close connection
conn.close()
print("✅ Task 7 completed successfully!")




