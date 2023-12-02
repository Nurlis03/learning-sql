## MOD

The SQL `MOD()` function is a mathematical function that returns the remainder(остаток) of the values from the division of two numbers. It calculates the modulo operation. This function is very useful when you want to find the remainder value after one number is divided by another.

## Syntax

The syntax of the MOD function in SQL is:

```SQL
MOD(expression1, expression2)
```

* `Expression1` and `Expression2` are the values that you want to apply the function to.

## Basic Usage

For instance, if you want to find the remainder of the division of 15 by 4 you would write:

```SQL
SElECT MOD(15, 4) AS result;
```

The result would be `3` because 3 is the remainder after dividing 15 by 4.

## Usage with Table Columns

The `MOD()` function can also be applied to table columns. Let’s imagine that you have a table named “Orders” with an “OrderNumber” column and you want to find the remainder of every order number when divided by 7, you would do:

```SQL
SELECT OrderNumber, MOD(OrderNumber, 7) AS result
FROM Orders;
```

This will return a list of all order numbers, along with the remainder when each order number is divided by 7.