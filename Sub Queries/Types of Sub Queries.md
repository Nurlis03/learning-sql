## Types of Sub Queries

Subqueries, sometimes referred to as inner queries or nested queries, are queries that are embedded(встроенный) within the clause of another SQL query. There are different types of SQL subqueries that are frequently(часто) used including Scalar, Row, Column, and Table subqueries.

## Scalar Subqueries

A scalar subquery is a query that returns exactly one column with a single value. This type of subquery can be used anywhere in your SQL where expressions are allowed.

Example:

```SQL
SELECT column_name [, column_name ]
FROM table1 [, table2]
WHERE column_name operator
    (SELECT column_name [,    column_name]
    FROM table_name
    WHERE condition);
```

## Row Subqueries

Row subqueries are used to return one or more rows to the outer SQL select query. However, the subquery returns multiple columns and rows, so it cannot be directly used where scalar expressions are used.

```SQL
SELECT column_name [, column_name ]
FROM   table1 [, table2 ]
WHERE  (column_name [, column_name ])
        IN (SELECT column_name [, column_name ]
            FROM table_name 
            WHERE condition);
```