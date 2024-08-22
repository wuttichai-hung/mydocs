# SQL

## 1. Show duplicate columns
Keywords: `HAVING COUNT(*) > 1`
```sql
SELECT *
FROM tablename
GROUP BY key_col1, key_col2
HAVING COUNT(*) > 1;
```

## 2. Delete duplicate rows

```sql
DELETE FROM tablename
WHERE id IN (
    SELECT id
    FROM (
        SELECT id,
        ROW_NUMBER() OVER (
            PARTITION BY col1, col2, col3
            ORDER BY id
        ) AS row_num
        FROM tablename
    ) t
    WHERE t.row_num > 1
);
```

## 3. Use COALESCE for default values

```sql
SELECT COALESCE(column_name, 'Default Value') AS column_alias
FROM tablename;
```

## 4. Pivot table using CASE

```sql
SELECT
    category,
    SUM(CASE WHEN status = 'active' THEN 1 ELSE 0 END) AS active_count,
    SUM(CASE WHEN status = 'inactive' THEN 1 ELSE 0 END) AS inactive_count
FROM tablename
GROUP BY category;
```

## 5. Running totals using window functions

```sql
SELECT
    date,
    amount,
    SUM(amount) OVER (ORDER BY date) AS running_total
FROM transactions;
```

## 6. Find nth highest value

```sql
SELECT DISTINCT amount
FROM (
    SELECT amount, DENSE_RANK() OVER (ORDER BY amount DESC) AS rnk
    FROM tablename
) ranked
WHERE rnk = n;  -- Replace n with the desired rank (e.g., 2 for 2nd highest)
```

## 7. Use EXPLAIN to analyze query performance

```sql
EXPLAIN SELECT * FROM tablename WHERE condition;
```

## 8. Handling dates

```sql
-- Extract parts of a date
SELECT
    EXTRACT(YEAR FROM date_column) AS year,
    EXTRACT(MONTH FROM date_column) AS month,
    EXTRACT(DAY FROM date_column) AS day
FROM tablename;

-- Date arithmetic
SELECT date_column + INTERVAL '1 day' AS tomorrow
FROM tablename;
```

## 9. String aggregation

```sql
-- For MySQL
SELECT
    category,
    GROUP_CONCAT(product_name SEPARATOR ', ') AS products
FROM products
GROUP BY category;

-- For PostgreSQL
SELECT
    category,
    STRING_AGG(product_name, ', ') AS products
FROM products
GROUP BY category;
```

## 10. Use CTEs for complex queries

```sql
WITH ranked_products AS (
    SELECT
        product_name,
        category,
        price,
        ROW_NUMBER() OVER (PARTITION BY category ORDER BY price DESC) AS price_rank
    FROM products
)
SELECT *
FROM ranked_products
WHERE price_rank <= 3;
```

## 11. Percentile calculations

```sql
-- For PostgreSQL
SELECT
    category,
    PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY price) AS median_price
FROM products
GROUP BY category;
```

Remember to adjust syntax as needed for your specific database system, as some functions may vary between SQL dialects.
