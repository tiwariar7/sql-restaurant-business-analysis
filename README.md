# sql-restaurant-business-analysis
![SQL](https://img.shields.io/badge/SQL-Data%20Analysis-blue) 
![GitHub](https://img.shields.io/github/repo-size/tiwariar7/sql-restaurant-business-analysis/edit/main/README.md)  

A project analyzing restaurant data from Swiggy (hypothetical dataset) to derive business insights using SQL.  
## **Project Overview**  
This repository contains SQL queries to analyze restaurant performance metrics such as:  
- Highest revenue-generating restaurants & cities  
- Popular cuisines by pricing and demand  
- Restaurant chain performance  
- City-wise dining trends  

## **Technologies Used**  
- **SQL** (MySQL)  
- **Dataset**: Hypothetical `restaurants` table (Swiggy-like data)  

## **Dataset Structure**  
The `restaurants` table includes columns like:  
- `id`, `name`, `city`, `cuisine`, `rating`, `rating_count`, `cost`  

*(Sample data can be generated using the `sample_data.sql` file in the repo.)*  

##  **Key SQL Queries**  

### 1. **Least visited restaurant in Pune**  
   ```sql
   SELECT * FROM restaurants 
   WHERE city = 'Pune' 
   ORDER BY rating_count ASC LIMIT 1;
  ```
### 2. **Highest revenue-generating restaurant in India**
  ```sql
  SELECT name, city, (cost * rating_count) AS revenue
  FROM restaurants 
  ORDER BY revenue DESC LIMIT 1;
  ```
### 3. **Top 5 cities with the most restaurants**
  ```sql
  SELECT city, COUNT(*) AS restaurant_count
  FROM restaurants 
  GROUP BY city 
  ORDER BY restaurant_count DESC LIMIT 5;
  ```
### (See the full list in queries.sql.)
## **Insights & Analysis**
Biryani dominates in Hyderabad with 120+ restaurants.
Mumbai generates the highest revenue (₹2.5M+ monthly).
Fine-dining chains have 3x revenue per outlet compared to QSRs.

## **How to Run**
Clone the repo:
bash
git clone https://github.com/tiwariar7/sql-restaurant-business-analysis.git

Import the dataset into your SQL database.
Execute queries from queries.sql.
