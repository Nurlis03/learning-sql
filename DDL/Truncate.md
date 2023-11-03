## Truncate Table

The `TRUNCATE TABLE` statement is a Data Definition Language (DDL) operation that is used to mark(пометки) the extents of a table for deallocation(освобождения) (empty for reuse(повторного использования)). The result of this operation quickly removes all data from a table, typically bypassing(как правило) a number of integrity enforcing mechanisms(в обход ряда механизмов обеспечения целостности) intended(предназначенных) to protect data (like triggers).

It effectively eliminates(удаляет) all records in a table, but not the table itself. Unlike(в отличие) the `DELETE` statement, `TRUNCATE TABLE` does not generate individual row delete statements(инструкции удаления отдельных строк), so the usual overhead for logging or locking(накладные расходы на ведение журнала или блокировку) does not apply(не применяются).

## Syntax
```
TRUNCATE TABLE table_name;
```

Remember, while(хотя) `TRUNCATE TABLE` is faster and uses fewer system(использует меньше ресурсов) and transaction log resources(журнала транзакций) than DELETE, it does not invoke triggers(не вызывает триггеров) and cannot be rolled back(не может быть откатано), so use with caution.

## Limitations

Truncate preserves(сохраняет) the structure of the table for future use. But you can’t truncate a table that:

* Is referenced by a FOREIGN KEY constraint. (You can truncate a table that has a foreign key that references itself.)
* Participates in an indexed view.
* Is published by using transactional replication or merge replication.

If you try to truncate a table with a foreign key constraint, SQL Server will prevent you from doing so and you will have to use the DELETE statement instead.

For partitioned tables, TRUNCATE TABLE removes all rows from all partitions. The operation is not allowed if the table contains any LOB columns - varchar(max), nvarchar(max), varbinary(max), text, ntext, image, xml, or if the table contains any filestream columns or spatial geo, geography, geometry, and hierarchyid data type columns, or any columns of CLR user-defined data types.