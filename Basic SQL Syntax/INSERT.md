syntax:

```SQL
INSERT INTO table_name(column1, column2, column3, ...)  
VALUES(value1, valu2, value3, ...);
```

INSERT INTO **set**

In this form, you’re able to insert data using the SET keyword. Here, you specify each column you want to insert data into, and then the data for that column.

```SQL
INSERT INTO table_name
SET column1 = value1, column2 = value2, ...;
```

INSERT INTO **select**

The INSERT INTO SELECT statement is used to copy data from one table and insert it into another table. Or, to insert data into specific columns from another table.

```SQL
INSERT INTO table_name1 (colum1, column2, column3, ...)
SELECT column1, column2, column3, ...
FROM table_name2
WHERE condition;
```
