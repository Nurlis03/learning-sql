## Types of Subquries

1. `Scalar Subquery`: It returns single value.

```SQL
SELECT name
FROM student
WHERE roll_id = (SELECT roll_id FROM student WHERE name='John');
```

2. `Row subquery`: It returns single of two or more values.

```SQL
SELECT * FROM student
WHERE (rool_id, age)=(SELECT MIN(roll_id), MIN(age) FROM student);
```

3.` Column subquery`: It returns single column value which is more than one row and one column.

```SQL
SELECT name, age FROM student
WHERE name(SELECT name FROM student);
```

4. `Table subquery`: It returns more than one row and more than one column.

```SQL
SELECT name, age
FROM student
WHERE (name, age) IN (SELECT name, age FROM student);
```

