# Basic Sales Summary Using Python and SQLite

##  Objective
- Load sales data from a CSV file into a SQLite database.
- Use SQL queries inside Python to get basic sales insights:
  - Total quantity sold per product category.
  - Total revenue per product category.
  - Overall sales summary.
- Visualize results using simple **matplotlib** bar charts.

## 🗂 Dataset
**File:** `sales_data.csv`


##  Work Performed

### 1. Load CSV and Create SQLite Database
- Loaded CSV into a pandas DataFrame.
- Created `sales_data.db` and stored the data into a table called `sales`.

### 2️. SQL Queries
- **Query 1:** Total quantity and revenue by product category.
```sql
SELECT Product_Category AS product,
       SUM(Quantity_Sold) AS total_qty,
       SUM(Quantity_Sold * Unit_Price) AS revenue
FROM sales
GROUP BY Product_Category
ORDER BY revenue DESC; ```

- **Query 2:** Overall sales summary
```sql

SELECT SUM(Quantity_Sold) AS total_quantity_sold,
       SUM(Quantity_Sold * Unit_Price) AS total_revenue
FROM sales;

