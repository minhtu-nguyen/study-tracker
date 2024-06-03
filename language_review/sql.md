## SQL Syntax
SQL keywords are NOT case sensitive: `select` is the same as `SELECT`
Some database systems require a semicolon at the end of each SQL statement.
## SQL Select
```sql
SELECT column1, column2, ...
FROM table_name;

SELECT CustomerName, City FROM Customers;
SELECT * FROM Customers;
```
## SQL Select Distinct
```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;

SELECT COUNT(DISTINCT Country) FROM Customers;
```
## SQL Where
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;

SELECT * FROM Customers
WHERE Country='Mexico';
```
## SQL Order By
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```
## SQL And
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

SELECT * FROM Customers
WHERE Country = 'Spain' AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```
## SQL Or
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

SELECT * FROM Customers
WHERE City = 'Berlin' OR CustomerName LIKE 'G%' OR Country = 'Norway';
```
## SQL Not
```sql
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;

SELECT * FROM Customers
WHERE CustomerID NOT BETWEEN 10 AND 60;

SELECT * FROM Customers
WHERE City NOT IN ('Paris', 'London');
```
## SQL Insert Into
```sql
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```
If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the INSERT INTO syntax would be as follows:

```sql
INSERT INTO table_name
VALUES (value1, value2, value3, ...);

INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES
('Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway'),
('Greasy Burger', 'Per Olsen', 'Gateveien 15', 'Sandnes', '4306', 'Norway'),
('Tasty Tee', 'Finn Egan', 'Streetroad 19B', 'Liverpool', 'L1 0AA', 'UK');
```
## SQL Null Values
```sql
SELECT column_names
FROM table_name
WHERE column_name IS NULL;

SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;

SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
```
## SQL Update",
## SQL Delete",
## SQL Select Top",
## SQL Aggregate Functions",
## SQL Min and Max",
## SQL Count",
## SQL Sum",
## SQL Avg",
## SQL Like",
## SQL Wildcards",
## SQL In",
## SQL Between",
## SQL Aliases",
## SQL Joins",
## SQL Inner Join",
## SQL Left Join",
## SQL Right Join",
## SQL Full Join",
## SQL Self Join",
## SQL Union",
## SQL Group By",
## SQL Having",
## SQL Exists",
## SQL Any, All",
## SQL Select Into",
## SQL Insert Into Select",
## SQL Case",
## SQL Null Functions",
## SQL Stored Procedures",
## SQL Comments",
## SQL Operators",
## SQL Create DB",
## SQL Drop DB",
## SQL Backup DB",
## SQL Create Table",
## SQL Drop Table",
## SQL Alter Table",
## SQL Constraints",
## SQL Not Null",
## SQL Unique",
## SQL Primary Key",
## SQL Foreign Key",
## SQL Check",
## SQL Default",
## SQL Index",
## SQL Auto Increment",
## SQL Dates",
## SQL Views",
## SQL Injection",
## SQL Hosting",
## SQL Data Types",
## SQL Keywords",
## MySQL Functions",
## SQL Server Functions",
## MS Access Functions",
## SQL Quick Ref",
## SQL Examples",
## SQL Editor",
## SQL Quiz",
## SQL Exercises",
## SQL Server",
## SQL Bootcamp",
## SQL Certificate"