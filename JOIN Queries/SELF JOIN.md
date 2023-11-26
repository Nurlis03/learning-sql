## Self Join

A `SELF JOIN` is a standard SQL operation where a table is joined to itself. This might sound counter-intuitive, but it’s actually quite useful in scenarios where comparison operations need to be made within a table. Essentially, it is used to combine rows with other rows in the same table when there’s a match based on the condition provided.

It’s important to note that, since it’s a join operation on the same table, alias(es) for table(s) must be used to avoid confusion during the join operation.

## Syntax of a Self Join

Here is the basic syntax for a `SELF JOIN` statement:

```SQL
SELECT a.column_name, b.column_name
FROM table_name AS a, table_name AS b
WHERE a.common_field=b.common_field;
```