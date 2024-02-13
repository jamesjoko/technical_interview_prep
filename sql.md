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

# Aggregations
- count
- sum
- min
- max
- avg

# “Where” versus “having”
WHERE cannot be used with aggregates, HAVING can

# Handling NULL values
- IS NULL, IS NOT NULL. null does not work with =, <, <>
- COALESCE(col, NULL, 1) takes the first non-null value. useful when doing left/right joins and some values are null, but want default 0

# Case statements, etc.
```
CASE
  WHEN condition1 THEN result1
  WHEN condition2 THEN result2
  ...
  ELSE default_result
END
```

# Filters
- WHERE
- can use regex with LIKE
  - WHERE col LIKE '% S%'
  - '% is any sequence of characters
# Groupings
GROUP BY

# Rankings
- ROW_NUMBER() OVER (ORDER BY col DESC) assigns a unique sequential integer to each row based on the specified ordering
- RANK() OVER (ORDER BY col DESC) assigns a unique rank to each distinct row. rows with equal values receive the same rank and the next rank is incremented by the number of rows that received the previous rank
- DENSE_RANK() OVER (ORDER BY col DESC) does the same as rank but does not account for ties
- NTILE(n) OVER (ORDER BY col DESC) divides the result set into a specified number of buckets and assigns a bucket number to each row
