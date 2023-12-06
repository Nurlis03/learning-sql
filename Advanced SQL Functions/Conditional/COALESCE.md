## COALESCE

The `COALESCE` function in SQL is used to manage NULL values in data. It scans from left to right through the arguments and returns the first argument that is not `NULL`.

Syntax:

```SQL
COALESCE(value1, value2,..., valueN)
```

The `COALESCE` function allows handling the case where you have possible `NULL` values in your data and you want to replace it with some other value.

For instance, here is an example of how you might use `COALESCE`:


```SQL
SELECT product_name, COALESCE(price, 0) AS Price
FROM products;
```

In this example, if the “price” column for a product entry is `NULL`, it will instead return “0”.

Another common use case is using `COALESCE` to find the first non-NULL value in a list:

```SQL
SELECT COALESCE(NULL, NULL, 'third value', 'fourth value');
```

In this case, it would return “third value”, as that’s the first non-NULL value in the list.

Remember, `COALESCE` does not update the original data. It only returns the first non-NULL value in the runtime. To update any NULL values permanently, you would need to use an `UPDATE` statement.

The `COALESCE` function in SQL improves the reliability of your queries when null values are involved. Whether it’s replacing nulls with default values or finding the earliest valid date, it’s a very useful function to grasp.

## `IIF` expression


`IIF` function returns value_true if the condition is TRUE, or value_false if the condition is FALSE.

Example of using `IIF`:

```SQL
SELECT IIF (1>0, 'One is greater than zero', 'One is not greater than zero');
```

These are essential constructs that can greatly increase the flexibility and functionality of your SQL code, particularly when dealing with elaborate conditions and specific data selections.