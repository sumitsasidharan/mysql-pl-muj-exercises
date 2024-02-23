### Differentiate between super key and composite key.

*Superkey:* A superkey is a set of one or more attributes (columns) that uniquely identifies each tuple (row) in a table. It can be a single attribute or a combination of multiple attributes. Every table must have at least one superkey, which may be composed of one or more columns. Superkeys are not necessarily minimal; that is, they may contain more attributes than required to uniquely identify a tuple. A superkey can have redundant attributes.

*Composite Key:* A composite key, also known as a compound key, is  specific type of superkey that consists of two or more attributes(columns) used together to uniquely identify a record in a table.
Unlike a superkey, a composite key must be minimal; that is, it must contain the minimum number of attributes required to uniquely identify a tuple.
Composite keys are commonly used when no single attribute can uniquely identify a record, but a combination of attributes can.
Each attribute within a composite key may not be unique on its own, but the combination of all attributes within the composite key must be unique.
Composite keys are often employed when enforcing referential integrity or ensuring uniqueness in relational databases.

### How do you view tables in SQL?

In SQL, we can view tables using various methods depending on the database management system (DBMS) you are using. Here are some common methods across different SQL-based DBMS:

Using SELECT statement:

```sql
SELECT * FROM table_name;
```

*Using GUI tools:* Many SQL database management systems come with graphical user interface (GUI) tools that allow you to browse and view tables visually. Examples of such tools include MySQL Workbench, pgAdmin for PostgreSQL, SQL Server Management Studio for Microsoft SQL Server, and Oracle SQL Developer for Oracle Database.


### What do yo mean by DML and DCL queries?

DML (Data Manipulation Language) and DCL (Data Control Language) are two categories of SQL queries that serve different purposes:

DML (Data Manipulation Language):
DML queries are used to manipulate data stored in the database. They include operations such as INSERT, UPDATE, DELETE, and sometimes SELECT (although SELECT is often considered part of the data retrieval process rather than manipulation).

INSERT: Used to add new rows of data into a table.
UPDATE: Used to modify existing data in a table.
DELETE: Used to remove existing data from a table.
SELECT: While SELECT is primarily used for retrieving data, it can also be used in combination with other DML statements to manipulate data indirectly, such as using subqueries or joins to filter, modify, or delete data.
Example:

```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
UPDATE table_name SET column1 = value1 WHERE condition;
DELETE FROM table_name WHERE condition;
```

### What is Join, discuss its types.

In SQL, a JOIN operation combines rows from two or more tables based on a related column between them. The JOIN operation allows you to retrieve data from multiple tables simultaneously, enabling you to correlate data across different tables based on common columns. There are several types of JOIN operations in SQL:

INNER JOIN:

An INNER JOIN returns rows that have matching values in both tables being joined.
It only includes rows where the join condition is satisfied.

LEFT JOIN (or LEFT OUTER JOIN):

A LEFT JOIN returns all rows from the left table (table1) and the matched rows from the right table (table2). If there is no match, NULL values are included for columns from the right table.

RIGHT JOIN (or RIGHT OUTER JOIN):

A RIGHT JOIN returns all rows from the right table (table2) and the matched rows from the left table (table1). If there is no match, NULL values are included for columns from the left table.

FULL JOIN (or FULL OUTER JOIN):

A FULL JOIN returns all rows when there is a match in either the left table (table1) or the right table (table2). If there is no match, NULL values are included for columns from the other table

CROSS JOIN:

A CROSS JOIN returns the Cartesian product of two tables, i.e., it combines each row from the first table with every row from the second table.
It doesn't require a join condition.


### What do you mean by aggregate functions.

Aggregate functions in SQL are functions that operate on a set of values and return a single aggregated value. These functions allow you to perform calculations across multiple rows in a table and summarize the result. Aggregate functions are commonly used in conjunction with the SELECT statement and the GROUP BY clause to perform calculations on groups of rows.

Some common aggregate functions in SQL include:

COUNT: Counts the number of rows in a result set or the number of non-null values in a column.

```sql
SELECT COUNT(*) FROM table_name;
```

SUM: Calculates the sum of values in a numeric column.

```sql
SELECT SUM(column_name) FROM table_name;
```

AVG: Calculates the average (mean) of values in a numeric column.

```sql
SELECT AVG(column_name) FROM table_name;
```

MIN: Finds the minimum value in a column.

```sql
SELECT MIN(column_name) FROM table_name;
```

MAX: Finds the maximum value in a column.

```sql
SELECT MAX(column_name) FROM table_name;
```

Aggregate functions can also be used with the GROUP BY clause to perform calculations on groups of rows based on the values in one or more columns. For example, to calculate the total sales amount for each product category:

```sql
SELECT category, SUM(sales_amount) AS total_sales
FROM sales
GROUP BY category;
```

Aggregate functions are essential for summarizing data, calculating statistics, and generating reports in SQL queries. They provide powerful capabilities for analyzing large datasets and extracting meaningful insights from them.