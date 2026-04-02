# SQL Query Patterns & Best Practices

## Common SQL Patterns

### 1. Window Functions
```sql
SELECT 
  employee_id,
  salary,
  AVG(salary) OVER (PARTITION BY department_id) as avg_dept_salary
FROM employees;
```

### 2. CTEs (Common Table Expressions)
```sql
WITH sales_data AS (
  SELECT customer_id, SUM(amount) as total
  FROM orders
  GROUP BY customer_id
)
SELECT * FROM sales_data WHERE total > 1000;
```

### 3. Recursive CTEs
```sql
WITH RECURSIVE employee_hierarchy AS (
  SELECT id, name, manager_id, 1 as level
  FROM employees
  WHERE manager_id IS NULL
  UNION ALL
  SELECT e.id, e.name, e.manager_id, h.level + 1
  FROM employees e
  JOIN employee_hierarchy h ON e.manager_id = h.id
)
SELECT * FROM employee_hierarchy;
```

## Performance Tips
- Use EXPLAIN PLAN for query analysis
- Index frequently queried columns
- Avoid using functions in WHERE clause
- Use LIMIT for result limiting
