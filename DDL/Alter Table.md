## Alter Table
The `ALTER TABLE` command in SQL is used to add, delete/drop, or modify columns in an existing table. It’s also useful for adding and dropping constraints such as primary key, foreign key, etc.

## Add Column
A single column can be added using the following syntax:

```SQL
ALTER TABLE tableName
ADD columnName datatype;
```

To add more than one column:

```SQL
ALTER TABLE tablename
ADD (columnName1 datatype,
     columnName2 datatype),
     ...
```

## Drop Column
To drop a single column:

```SQL
ALTER TABLE tableName
DROP COLUMN columnName;
```

To drop multiple columns:

```SQL
ALTER TABLE tableName
DROP (columnName1,
      columnName2,
      ...
     );
```

## Modify Column

to modify the datatype of a column:

```
ALTER TABLE tablename
ALTER COLUMN columnName TYPE newData Type;
```

## Add/Drop Constraints
To add constrainst:

```SQL
ALTER TABLE tableName
ADD CONSTRAINT constraintNme
PRIMARY KEY  (column1, column2, ... column_n);
```

To drop constraints:

```SQL
ALTER TABLE tableName
DROP CONSTRAINT constraintName;
```

In conclusion, ALTER TABLE in SQL lets you alter the structure of an existing table. This is a powerful command that lets you dynamically add, modify, and delete columns as well as the constraints placed on them. It ensures you are more flexible in dealing with changing data storage requirements.

## Examples

```SQL
ALTER TABLE distributors ADD COLUMN address varchar(30);
```

That will cause all existing rows in the table to be filled with null values for the new column.

To add a column with a non-null default:

```SQL
ALTER TABLE measurements
ADD COLUMN mtime timestamp with time zone DEFAULT now();
```

To drop a column from a table:

```SQL
ALTER TABLE distributors DROP COLUMN address RESTRICT;

--The "RESTRICT" option is used to specify that the column should only be dropped if it is not referenced by any other database objects, such as views, triggers, or stored procedures.
```

```SQL
ALTER TABLE distributors
ALTER COLUMN address TYPE varchar(80),
ALTER COLUMN name TYPE varchar(100);
```

Rename column:

```SQL
ALTER TABLE distributors RENAME COLUMN address TO city;
```

Rename table:

```SQL
ALTER TABLE distributors RENAME TO suppliers;
```

Rename constraint:

```SQL
ALTER TABLE distributors
RENAME CONSTRAINT zipchk TO zip_check;
```

Add not-null constraint:

```SQL
ALTER TABLE distributors
ALTER COLUMN street SET NOT NULL;
```

Remove a not-null constraint from a column:

```SQL
ALTER TABLE distributors
ALTER COLUMN street DROP NOT NULL;
```
To add a check constraint to a table and all its children:

```SQL
ALTER TABLE distributors ADD CONSTRAINTS zipchk CHECK (char_length(zipcode))
```

To add a check constraint only to a table and not to its children:

```SQL
ALTER TABLE distributors ADD CONSTRAINT zipchk CHECK (char_length(zipcode) = 5) NO INHERIT;
```

To remove a check constraint from a table and all its children:

```SQL
ALTER TABLE distributors DROP CONSTRAINT zipchk;
```

To remove a check constraint from one table only:

```SQL
ALTER TABLE ONLY distributors DROP CONSTRAINT zipchk;
```

To add a foreign key constraint to a table:

```SQL
ALTER TABLE distributors
ADD CONSTRAINT distfk FOREIGN KEY (address) REFERENCES addresses (address);
```

To add a (multicolumn) unique constraint to a table:

```SQL
ALTER TABLE distributors ADD CONSTRAINT dist_id_zipcode_key UNIQUE (dist_id, zipcode);
```

```SQL
ALTER TABLE distributors ADD PRIMARY KEY (dist_id);
```



