## FROM

### FROM with Multiple Tables

```SQL
SELECT employees.name, departments.department
FROM employees, departments
WHERE employees.dept_id = departments.dept_id;
```

## FROM with Aliases

```SQL
SELECT e.name, d.department
FROM employees AS e, departments AS d
WHERE e.dept_id = d.dept_id;
```

That’s it! Remember that `FROM` is not limited only to `SELECT`. It is applicable to `UPDATE` and `DELETE` operations as well.