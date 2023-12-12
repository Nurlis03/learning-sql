## Indexes

An index in SQL is a database object which is used to improve the speed of data retrieval operations(скорости поиска операций данных) on a database table. Similarly to how an index in a book helps you find information quickly without reading the entire book, an index in a database helps the database software find data quickly without scanning the entire table.

## Clustered Index

A clustered index determines the physical order(порядок) of data inside a table. It sorts and stores(сохраняет) the data rows in the table based(на основе) on their key values. There can be only one clustered index per table.

Creating a clustered index:

```SQL
CREATE CLUSTERED INDEX index_name ON table_name (column_name);
```

## Non-Clustered Index

A non-clustered index doesn’t sort the physical data inside the table. Instead, it creates a separate object within(внутри) a table which points back to the original table rows(на исходные строки) after creating. You can create numerous(множество) non-clustered indexes per table.

Creating a non-clustered index:

```SQL
CREATE NONCLUSTERED INDEX index_name
ON table_name (column_name);
```

## Indexes on Multiple Columns

An index can be built on more than one column of a table, which results in index entries having values of multiple columns. This is known as a composite index.

Creating a composite index:

```SQL
CREATE INDEX index_name
ON table_name (column1, column2);
```

## Unique Indexes

A unique index doesn’t allow any field to have duplicate values if the field is unique indexed. If a primary key is defined, a unique index can be applied automatically.

Creating a unique index:

```SQL
CREATE UNIQUE INDEX index_name
ON table_name (column_name);
```

## Explicit vs Implicit Indexes

Indexes explicitly created by users are known as explicit indexes, while indexes automatically created by SQL Server when a primary key or unique constraint is defined are known as implicit indexes.

Creating an explicit index:

```SQL
CREATE INDEX index_name
ON table_name (column_name);
```

## Full-Text Indexes

If you’re dealing with text searching within a large string of text, full-text indexes are especially helpful. These indexes do not work using a standard comparison search but instead use word-breakers, filters, and noise-words (stop words).

Creating a full-text index:

```SQL
CREATE FULLTEXT INDEX ON table_name (column_name)
KEY INDEX index_name;
```

Please note that the creation and maintenance of indexes involve a trade-off between query speed and update costs. Indexes speed up retrieval at the expense of slower updates and increased storage space.