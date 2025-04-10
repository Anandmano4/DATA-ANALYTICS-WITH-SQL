# DATA-ANALYTICS-WITH-SQL

# SQL Internship Tasks – Day 3

## Overview

This repository contains SQL queries and outputs completed during Day 3 of my internship. The focus of the task was to analyze customer transactions in an e-commerce dataset using SQL Server Management Studio (SSMS), and perform operations like creating views, using joins, and filtering with conditions.

---

## Task: Identify High Value Customers

We were asked to:

- Retrieve customers whose total purchase value exceeds 1000
- Use a `JOIN` between `Customer` and `SalesOrderHeader` tables
- Create a **view** to store the result
- Display the contents of the view



### SQL Query Used

```sql
CREATE VIEW HighValueCustomers AS
SELECT 
    c.CustomerID,
    c.FirstName,
    c.LastName,
    o.TotalDue
FROM 
    SalesLT.Customer c
JOIN 
    SalesLT.SalesOrderHeader o ON c.CustomerID = o.CustomerID
WHERE 
    o.TotalDue > 1000;

-- View the created data
SELECT * FROM HighValueCustomers;
