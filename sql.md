# Joins
  - inner: returns only rows matching values in both tables
  - left/right outer: returns all rows in the left/right table and the matched rows from the opposite table. If no match is found, it is filled with NULL
  - full outer: returns all rows from both tables. includes matching, left only, and right only
  - cross: returns a cross product of the two tables. every pairwise combination between all rows in both tables

# UNION vs. UNION ALL
UNION will merge and remove duplicate rows. UNION ALL will merge and keep duplicate rows.

# Correlated subqueries
a subquery that uses values from the outer query
```
SELECT employee_number, name
   FROM employees emp
  WHERE salary > (
        SELECT AVG(salary)
          FROM employees
         WHERE department = emp.department);
```

• Aggregations
• “Where” versus “having”
• Handling NULL values
• Case statements, etc.
• Filters
• Groupings
• Rankings
• Verifying results and taking care of exceptions and NULL handling
