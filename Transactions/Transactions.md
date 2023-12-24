## Transactions

A transaction in SQL is a unit(единица) of work that is performed against a database. Transactions are units(единицы) or sequences of work accomplished(выполняемые) in a logical order, whether(будь то вручную) in a manual fashion by a user or automatically by some sort of a database program.

Transactions are used to ensure data integrity and to handle database errors while processing. SQL transactions are controlled by the following commands:

BEGIN TRANSACTION
COMMIT
ROLLBACK

## BEGIN TRANSACTION

This command is used to start a new transaction.

```SQL
BEGIN TRANSACTION;
```

## COMMIT
The COMMIT command is the transactional command used to save changes invoked by(вызванный) a transaction to the database.

```SQL
COMMIT;
```

When you commit the transaction, the changes are permanently saved in the database.

## ROLLBACK

The `ROLLBACK` command is the transactional command used to undo transactions that have not already been saved to the database.

```SQL
ROLLBACK;
```

When you roll back a transaction, all changes made since the last commit in the database are undone, and the database is rolled back to the state it was in at the last commit.

## Transaction Example

```SQL
BEGIN TRANSACTION;

UPDATE Accounts SET Balance = Balance - 100 WHERE id = 1;
UPDATE Accounts SET Balance + 100 WHERE id = 2;

IF @@ERROR = 0
    COMMIT;
ELSE
    ROLLBACK;
```

In this example, we are transferring 100 units from account 1 to account 2 inside a transaction. If any errors occurred during any of the update statements (captured by @@ERROR), the transaction is rolled back, otherwise, it is committed.

Remember that for the transaction to be successful, all commands must execute successfully. If any command fails, the transaction fails, the database state is left unchanged and an error is returned.