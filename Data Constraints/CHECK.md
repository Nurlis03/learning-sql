## CHECK

In SQL, `CHECK` is a constraint that limits the value range that can be placed in a column. It enforces domain integrity by limiting the values in a column to meet a certain condition.

`CHECK` constraint can be used in a column definition when you create or modify a table.

## Syntax

```SQL
CREATE TABLE table_name (
    column1 datatype CONSTRAINT constraint_name CHECK (condition),
    column2 datatype,
    ...
);
```

If you need to apply the `CHECK` constraint on multiple columns, use the following syntax:

```SQL
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...,
    CONSTRAINT constraint_name CHECK (condition)
);
```

## Examples

```SQL
CREATE TABLE Employees (
    ID int NOT NULL,
    Age int,
    Salary int CHECK (Salary > 0),
);
```

Here is an example of applying a `CHECK` constraint on multiple columns:

```SQL
CREATE TABLE Employees (
    ID int NOT NULL,
    Age int,
    Salary int,
    CONSTRAINT CHK_Person CHECK (Age >= 18 AND Salary >= 0)
);
```

Above SQL ensures that the persons’ age must be greater than or equal to 18, and their salary is more than or equal to 0.

It is also possible to use the `ALTER TABLE` command to add a `CHECK` constraint after the table has been created.

```SQL
ALTER TABLE Employees
ADD CONSTRAINT CHK_EmployeeAge CHECK(Age >= 21 AND Age <= 60);
```

```SQL
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    birth_date DATE CHECK(birth_date > '1900-01-01'),
    joined_date DATE CHECK (joined_date > birth_date),
    salary numeric CHECK(salary > 0)
)
```

```
column_name data_type CONSTRAINT constraint_name CHECK(...)
```

```SQL
salary numeric CONSTRAINT positive_salary CHECK(salary > 0)
```