## TRIM Function

The TRIM function removes leading and trailing spaces of a string. You can also remove other specified characters.

Syntax:

```SQL
TRIM([LEADING|TRAILING|BOTH] [removal_string] FROM original_string)
```

Example:

```SQL
SELECT TRIM('     Hello World     ');
SELECT TRIM('h' FROM 'hello');
```

The output of the first query will be ‘Hello World’ and that of the second query will be ‘ello’.