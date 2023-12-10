In some cases, you can modify the data of the underlying tables via a VIEW.

Syntax:

```SQL
UPDATE view_name
SET column1 = value1, column2 = value, ...
WHERE condition;
```

Example:

```SQL
UPDATE customer_view
SET country = 'USA'
WHERE customer_name = 'John Doe';
```

This command will update the country of ‘John Doe’ to ‘USA’ in both the VIEW and the underlying table.

However, not every VIEW is updatable. You can only modify the data if the VIEW you’re modifying is a simple VIEW that returns results from a single table without any aggregation or complex clauses. If you attempt to modify a complex view (i.e., it includes JOIN, GROUP BY, HAVING, DISTINCT), you will get an error.