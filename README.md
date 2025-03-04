

# Wholesale Revenue Analysis by Product Line**  

## 📊 Project Overview  
This project analyzes **wholesale sales data** to determine how much net revenue each product line generated **per month per warehouse**. The dataset contains sales transactions from **June to August 2021**, including details such as payment methods, warehouses, and client types.  

The insights from this analysis can help business stakeholders understand revenue trends across **product categories, warehouses, and time periods** to optimize supply chain and sales strategies.  

## 🎯 Objectives  
✅ Filter sales data to include **only wholesale orders**  
✅ Calculate **net revenue** as `SUM(total - payment_fee)`  
✅ Group results by **product line, month, and warehouse**  
✅ Format **month names** as `'June'`, `'July'`, and `'August'`  
✅ Sort results by **product line, month, and net revenue (descending order)**  

## 🛠 Tech Stack  
- SQL (PostgreSQL)  
- **Data Aggregation & Query Optimization**  

## 📝 SQL Query Breakdown  
The main query performs the following operations:  
1. **Filters only "Wholesale" orders** using `WHERE client_type = 'Wholesale'`  
2. **Extracts the month name** using `TO_CHAR(date, 'Month')`  
3. **Calculates net revenue** as `SUM(total - payment_fee)`  
4. **Groups results** by `product_line, month, warehouse`  
5. **Sorts the final output**  

## 📌 SQL Query  
```sql
SELECT 
    product_line,
    TO_CHAR(date, 'Month') AS month,
    warehouse,
    SUM(total - payment_fee) AS net_revenue
FROM sales
WHERE client_type = 'Wholesale'
GROUP BY product_line, month, warehouse
ORDER BY product_line, month, net_revenue DESC;
```

## 📊 Expected Output  
| product_line | month  | warehouse | net_revenue |
|-------------|--------|-----------|-------------|
| Product A   | June   | North     | $XX,XXX     |
| Product B   | June   | West      | $XX,XXX     |
| ...         | ...    | ...       | ...         |


## 📌 Key Learnings  
- Using `TO_CHAR()` to format date values  
- Applying `SUM()` for revenue aggregation  
- Structuring SQL queries for performance optimization  
- Sorting results for better insights  

