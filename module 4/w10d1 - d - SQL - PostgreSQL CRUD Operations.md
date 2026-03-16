
# SQL - PostgreSQL CRUD Operations

<!-- 

status: ready

-->


## Intro to SQL

- SQL: "Structured Query Language"

- Created in the early 1970s 

- It's the primary way to interact with relational database management systems (RDBMS), such as PostgreSQL, MySQL, and Oracle.

- Allows to create and modify tables. Allows to CRUD data in your tables.


## Create a database

On Beekeeper, follow these steps:
- Create a new db "ecommerce_demo"
- Get a list of dbs
- Connect to our new db


## Create our first table

Create a first table for "users"
- follow example here: https://gist.github.com/luisjunco/a3c7dc8a8a8c3468bd387e4f3acbd107




## Data Types

Follow this cheat-sheet:
- https://gist.github.com/luisjunco/c0ab5b09bdd75b158425b7a50db9aa59



## CRUD Operations


1. Demo: "Create" + "Read" + "Update" + "Delete"
    - Create a table "products" and do a demo on that table.
    - Do a demo for each of them (follow Student Portal)

    <!-- 

    Tip: include a "SELECT" after each statement, so that we don't need to keep refreshing the UI to see the result

    -->

2. Discover: "Logical Operators", "Comparison Operators", etc
    - For all the other operations (logical, comparison, etc), let students discover them by themselves → see exercise below.



## Practice: SQL statements


1. Create a new DB + Connect to your new database
    - If you use Beekeeper, you can do these two operations directly on with the user interface.

2. Run this statements to create some tables and initial data:
    - https://gist.github.com/luisjunco/a3c7dc8a8a8c3468bd387e4f3acbd107

3. Follow these sections in the Student Portal & practice those commands in your new database:
    - CRUD Operations (refresh & practice)
    - Logical Operators
    - Comparison Operators
    - Other SQL Clauses
    - Aggregate Functions

Time: 30min.



---

Examples of GROUP BY:

- Know how many products we have each price:
    - `SELECT price, COUNT(*) FROM products GROUP BY price;`

- Know the total stock of items for each price:
    - `SELECT price, SUM(stock_quantity) AS total_stock FROM products GROUP BY price;`


