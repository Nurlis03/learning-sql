## BEGIN

In the context of SQL transactions, `BEGIN` is a keyword used to start a transaction. It marks the point at which the data referenced by a connection is logically consistent. After the `BEGIN` statement, the transaction is considered to be “open” and remains so until it is committed or rolled back.

Once you’ve initiated a transaction with `BEGIN`, all the subsequent SQL statements will be a part of this transaction until an explicit `COMMIT` or `ROLLBACK` is given.

## Syntax

The syntax to start a transaction is:

```SQL
BEGIN TRANSACTION;
```
or simply,

```SQL
BEGIN
```

## Example

Below is a simple example of using `BEGIN` in SQL:

```SQL
BEGIN;

INSERT INTO Customers(CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES('Cardinal', 'Tom B. Ericsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');
```

In this example:

* `BEGIN`; marks the start of the transaction.
* The `INSERT` statement adds a new row of data to the `Customers` table.
* `COMMIT`; ends the transaction and permanently saves the changes made during this transaction.

Note: If something goes wrong with one of the SQL statements within the transaction (after the BEGIN; statement), you can choose to ROLLBACK the transaction, which means canceling all the changes made in this transaction up to the point of error.

## Conclusion

In summary, BEGIN in SQL is used to start a transaction, which enables modifications done in a database to be viewed as a logically coherent occurrence.