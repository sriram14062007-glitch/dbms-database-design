# dbms-database-design
Database Management Systems &amp; SQL design patterns with practical examples


## 📚 Table of Contents
- [Introduction](#introduction)
- [Concepts Covered](#concepts-covered)
- [SQL Examples](#sql-examples)
- [Normalization](#normalization)
- [Query Optimization](#query-optimization)

## 🎯 Introduction
This repository covers comprehensive DBMS concepts including database design, SQL optimization, and real-world application patterns.

## 📖 Concepts Covered

### Core DBMS Topics
- **ER Model & Relational Model**
- **Normalization (1NF, 2NF, 3NF, BCNF)**
- **Transaction Management & ACID Properties**
- **Indexing & Query Optimization**
- **Concurrency Control**
- **Database Security**

### SQL Design Patterns
- Complex Joins
- Window Functions
- Aggregation & Grouping
- Subqueries & CTEs

## 💾 SQL Examples
```sql
-- Example: Customer-Orders Schema
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATETIME,
    total_amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```

## 🔄 Normalization
- **1NF**: Atomic values
- **2NF**: No partial dependencies
- **3NF**: No transitive dependencies
- **BCNF**: Every determinant is a candidate key

## ⚡ Query Optimization Tips
- Use EXPLAIN ANALYZE
- Create appropriate indexes
- Avoid SELECT *
- Use LIMIT for large results
