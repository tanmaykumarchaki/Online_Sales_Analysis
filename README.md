# 📊 Online Sales Analysis (January–August)

This project provides a monthly breakdown of online sales performance using SQL and presents results in a tabular format.

## 📁 Files

- `Online_Sales_Analysis.sql`: Contains SQL queries that compute monthly summaries (January to August).
- `Online_Sales_Result_Table_Jan_to_Aug.png`: Visual representation of the monthly result table.

## 📈 Metrics Calculated

Each month's analysis includes the following:

| Column             | Description                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| `Month`            | Name of the month                                                           |
| `Avg_Units_Sold`   | Average number of units sold per day                                        |
| `Avg_Revenue`      | Average revenue per unit sold                                               |
| `Total_Revenue`    | Total revenue generated in that month                                       |
| `Total_Units_Sold` | Total number of units sold in that month                                    |
| `Revenue_Check`    | Validation column (avg_revenue × total_units_sold = total_revenue expected) |

## 🧮 Sample SQL Snippet

```sql
SELECT
  'January' AS Month,
  ROUND(SUM(`Units Sold`) / 31, 2) AS avg_units_sold,
  ROUND(SUM(`Total Revenue`) / SUM(`Units Sold`), 2) AS avg_revenue,
  ROUND(SUM(`Total Revenue`), 2) AS total_revenue,
  ROUND(SUM(`Units Sold`), 2) AS total_units_sold,
  ROUND(SUM(`Total Revenue`) / SUM(`Units Sold`) * SUM(`Units Sold`), 2) AS total_revenue_check
FROM `online sales data`
WHERE `Date` BETWEEN '2024-01-01' AND '2024-01-31'
