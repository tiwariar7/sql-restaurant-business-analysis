# SQL Restaurant Business Analysis

![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-blue)

A practice project analyzing restaurant data (Swiggy-like, hypothetical dataset) to get business insights using SQL.

## Project Overview

This repo contains SQL queries to analyze restaurant performance.  
Topics covered include:
- Highest/lowest revenue restaurants and cities
- Popular/expensive cuisines
- Restaurant chain performance
- City-wise dining trends

## Technologies Used

- **SQL (MySQL)**
- **Dataset**: Hypothetical `restaurants` table based on food delivery data

## Dataset Structure

The `restaurants` table includes the following fields:

| Column         | Description                                  |
|----------------|----------------------------------------------|
| id             | Unique restaurant ID                         |
| name           | Restaurant name                              |
| city           | City where the restaurant is located         |
| cuisine        | Primary cuisine served                       |
| rating         | Average customer rating                      |
| rating_count   | Number of customers who rated                |
| cost           | Average meal cost per order (in INR)         |

> 🔹 Sample dataset can be generated using the `sample_data.sql` file in the repository.

## Key SQL Queries (Examples)

### 1. Least visited restaurant in Pune
```sql
SELECT * FROM restaurants 
WHERE city = 'Pune' 
ORDER BY rating_count ASC 
LIMIT 1;
```

### 2. Highest revenue-generating restaurant in India

```sql
SELECT name, city, (cost * rating_count) AS revenue 
FROM restaurants 
ORDER BY revenue DESC 
LIMIT 1;
```

### 3. Top 5 cities with the most restaurants

```sql
SELECT city, COUNT(*) AS restaurant_count 
FROM restaurants 
GROUP BY city 
ORDER BY restaurant_count DESC 
LIMIT 5;
```

> 📝 Full query set available in `queries.sql`.

## Insights & Highlights

* **Biryani** is the top cuisine in Hyderabad with over 120 outlets.
* **Mumbai** leads with the highest revenue, exceeding ₹2.5M/month.
* **Fine dining chains** generate 3x more revenue per outlet than quick-service restaurants (QSRs).

## How to Run

1. **Clone the repository**

   ```bash
   git clone https://github.com/tiwariar7/sql-restaurant-business-analysis.git
   ```

2. **Import the dataset**

   * Use `sample_data.sql` to create and populate the table in your SQL environment.

3. **Run queries**

   * Execute queries from `queries.sql` using MySQL Workbench, DBeaver, or any SQL tool.

---
Feedback or suggestions? Feel free to open an issue or PR.
Note: This is a practice assignment project. Dataset is hypothetical and meant for learning SQL only.
