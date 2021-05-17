# STRUCTURED QUERY LANGUAGE  (SQL)

### What is SQL?
_SQL is a Structured Query Language sometimes it is referred to as SEQUEL (Structured English Query Language) which is used to handle with Database where the data is stored in the form of Tables permanently with some relationship between the tables. So can refer it as Relational Database Management System (RDBMS)._

### Why we need SQL?
_We can store the data in some format in an excel sheet. Here also we can store the data permanently. But there is a problem here with this format. The problem is we cannot get or build relationships with two or more excel sheets. To overcome this problem we have to go for a database so that we can build the relationship between tables as many as we can._

### How to use Database?
We can use a database with the help of Queries. The query is an inquiry about a set of relational data to get the result in the form of a table.

In this discussion, we are not going to discuss creating the Table, Inserting the data into the table, rather we are going to discuss how can fetch the data from the database with the help of Queries.

Before that, first, we will get familiar with types of data that we can manage with a database.
### Note
> SQL is case in-sensitive language in terms of syntax i.e Not and NOT both are the same. But the data that is fetched/inserted is case-sensitive.

### DataTypes
It is used to store the whole range of values (both positive and negative integers/numbers).
| Data Type | Description |
| ------ | ------ |
| int | It is used to store the whole range of values (both positive and negative) Eg: -194,204 |
| number | It holds a whole range of values (both positive and negative) including decimal values. Eg : 1234.403, -3942.2342 |
| char |It is static in nature used to store string values up to 2000 bytes. Eg: "India", "Australia" |
| varchar | It is dynamic in nature used to store string values up to 4000 bytes. Eg: "India", "Australia" |
| date | It is used to store the data values Eg: dd/mm/yy|
|clob, blob| Used to store images and videos Eg: song.mp3, video.mp4 |

### Statements in SQL
| Statement | Description |
| ------ | ------ |
| select |It is a statement that is used to select fields/columns from the database. * is used to select all columns of a table from the database.|
| insert |It is a statement that is used to insert fields/columns into the database. |
| update |It is a statement that is used to update fields/columns in the database. |
| delete |It is a statement that is used to delete fields/columns from the database. |
| distinct |It is a statement that is used to return unique values from the database. |
### Clauses in SQL
| Clause | Description |
| ------ | ------ |
| where |It is a clause that is used to check the condition row by row. |
| having |It is a clause that is used to check the condition group of rows. Simple we can say group by group. |
| group by |It is a clause that is used to filter the data into groups based on some parameter. |
| join |It is used to combine rows from two or more tables, based on a related column between them. |
| asc |It is used to order the data by ascending order. |
| desc |It is used to order the data by descending order. |

### Arithmetic Operators in SQL
| Operator | Description |
| ------ | ------ |
| + | Used to add two integer/number values |
| - | Used to subtract integer/number two values. |
| * | Used to multiply integer/number two values. |
| / | Used to divide integer/number two values. |

### Logical Operators in SQL
| Operator | Description |
| ------ | ------ |
| and |It is used when both the conditions should be satisfied. |
| or |It is used when either of the conditions to be satisfied. |
| not | It is used to negate the condition that not to be satisfied. |
| is | It is used to select the null values from the database. In SQL 'null' and 'null' are not the same. |
| between and | It is used to select the data between the set of range values. |
| in | It is used to select the data within the set of specified values. |
| \|\| |It is used to concat two String values. |

So far we got familiar with some basic data types, terminology, and arithmetic and logical operators in SQL. Now we will explore some basic queries. For our understanding, I am considering a 5 rows Customers table 
### Customers Table
| CustomerID | CustomerName | ContactName | Address | City | PostalCode | Country |
|-----|-----|-----|-----|-----|-----|-----|
| 1 | Alfreds Futterkiste | Maria Anders | Obere Str. 57|Berlin | 12209	| Germany |
| 2 | 	Ana Trujillo Emparedados y helados | Ana Trujillo | Avda. de la Constitución 2222  | México D.F. | 05021	| Mexico |
| 3 | Antonio Moreno Taquería | Antonio Moreno | Mataderos 2312 | México D.F. | 05023	| Mexico |
| 4 | Around the Horn | AThomas Hardy | 120 Hanover Sq. | London | WA1 1DP	| UK |
| 5 | Berglunds snabbköp | Christina Berglund | Berguvsvägen 8 | Luleå | S-958 22	| Sweden |

```sh
Query to select all columns from Customers Table?

SELECT * FROM Customers;
```

```sh
Query to select CustomerName and city from Customers Table?

SELECT CustomerName, City FROM Customers;
```
[Run Query](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_columns)

*Functions in SQL*
There are two types of functions in SQL.
1. Single-Row Functions
2. Multi-Row or Aggregate Functions

#### Single-Row Functions
Single row functions in SQL that applies the functionality for each row.
For example, if we want to convert the column data to uppercase, we can make use of Upper().
Length(), Upper(), Lower(), Concat(), Substr(), Replace(), Trim()Roundoff(), Trunc()Mod(), Sqrt() are the frequently used functions on each row.

#### Multi-Row Functions
Multi-row functions in SQL that applies functionality group by group. for example, if we have a group of mixed data consisting of Mobiles, Laptops, Tabs, etc. To make the data clear, we can group the data by all Mobiles, Tabs, and Laptops. If we still want more clear data, we can group all grouped data based on the brand of a product.
GroupBy, Having, OrderBy are the frequently used clauses to group the data. Count(), Sum(), Min(), Max(), Avg() are the frequently used funtions on grouped data.

#### Joins in SQL
The most advanced and main feature of the Relational Database Management System is Joins. It is used to establish relationships between tables of a database. Even though there are different types of joins, every join clause functionality is the same. But the output format is different. If we want to fetch the data from two or more tables where the column data of a row from Table1 and column data of a row from Table2 is equal.

### Table1
| A | B |
|---|---|
|1|2|
|3|4|
|5|6|
|7|8|

### Table2
| B| C |
|---|---|
|2|1|
|8|1|
|9|1|


### Different types of Joins in SQL
#### 1. Inner Join
```sh
select * 
from Table1 innerjoin Table2
on Table1.B = Table2.B
```
Output
| A | B | B | C |
|---|---|---|---|
|1|2|2|1|
|7|8|8|1|
#### 2. Natural Join
```sh
select * 
from Table1 naturaljoin Table2
on Table1.B = Table2.B
```
Output
| A | B | C |
|---|---|---|
|1|2|1|
|7|8|1|
#### 3. Right Outer Join
```sh
select * 
from Table1 rightouterjoin Table2
on Table1.B = Table2.B
```
Output
| A | B | B | C |
|---|---|---|---|
|1|2|2|1|
|7|8|8|1|
|-|-|9|1|
#### 4. Left Outer Join
```sh
select * 
from Table1 leftouterjoin Table2
on Table1.B = Table2.B
```
Output
| A | B | B | C |
|---|---|---|---|
|1|2|2|1|
|7|8|8|1|
|5|6|-|-|
|3|4|-|-|

#### 5. Full Outer Join
```sh
select * 
from Table1 fullouterjoin Table2
on Table1.B = Table2.B
```
Output
| A | B | B | C |
|---|---|---|---|
|1|2|2|1|
|7|8|8|1|
|5|6|-|-|
|3|4|-|-|
|-|-|9|1|

#### 6. Cross Join
```sh
select * 
from Table1 crossjoin Table2
on Table1.B = Table2.B
```
Output
| A | B | B | C |
|---|---|---|---|
|1|2|2|1|
|1|2|8|1|
|1|2|9|1|
|3|4|2|1|
|3|4|8|1|
|3|4|9|1|
|5|6|2|1|
|5|6|8|1|
|5|6|9|1|
|7|8|2|1|
|7|8|8|1|
|7|8|9|1|

#### 7. Self Join
It is a type of join where the table joins with itself.
#### 8. Non-Equi Join
It is a type of join where the data will fetch even there is no common column between the tables.

For more information and practice, go through  [W3Schools](https://www.w3schools.com/sql/).
