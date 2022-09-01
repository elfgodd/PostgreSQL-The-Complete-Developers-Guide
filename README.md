# SQL and PostgreSQL: The Complete Developer's Guide

Become an expert with SQL and PostgreSQL! Store and fetch data, tune queries, and design efficient database structures!
Instructor: Stephen Grider
Course Repository:
Course Link: https://udemy.com/course/sql-and-postgresql/

## What you'll learn

- Master the fundamentals of relational databases
- Design fast and efficient databases using the latest technologies
- Learn and apply multiple database design patterns
- Understand how PostgreSQL stores information at the hardware level
- Build common app features, such as a 'like' and 'mention' systems
- Advance your database designs using schema migrations
- Acquire the skills necessary to obtain a database administrator (DBA) or database developer job
- Practice your skills with many quizzes, projects, and built-in exercises
- Optimize queries for superb read and write efficiency
- Connect PostgreSQL to front-end apps using an API
- Handle complex concurrency issues and race conditions
- See how to use PostgreSQL to speed up automated tests

## Course content

37 sections • 290 lectures • 22h 13m total length

- Simple - But Powerful - SQL Statements
- Filtering Records
- Working with Tables
- Relating Rcords
- Aggregation of Records
- Working with Large Datasets
- Sorting Records
- Unions and Intersections with Sets
- Assembling Queries with SubQueries
- Selecting Distinct Records
- Utility Operators, Keywords, and Functions
- Local PostgreSQL Installation
- PostgreSQL Complex Datatypes
- Database-Side Validation and Constraints
- Database Structure Design Patterns
- How to Build a 'Like' System
- How to Build a 'Mention' System
- How to Build a 'Hashtag' System
- How to Design a 'Follower' System
- Implementing Database Design Patterns
- Approaching and Writing Complex Queries
- Understanding the Internals of PostgreSQL
- A look at Indexes for Performance
- Basic Query Tuning
- Advanced Query Tuning
- Simple Common Table Expressions
- Recursive Common Table Expressions
- Simplifying Queries with Views
- Optimizing Queries with Materialized Views
- Handling Concurrency and Reversibility with Transactions
- Managing Database Design with Schema Migrations
- Schema vs Data Migrations
- Accessing PostgreSQL from API's
- Data Access Pattern - Repositories
- Security Around PostgreSQL
- Bonus!

## Section 1: Simple - But Powerful - SQL Statements

### 1. Links

List of largest cities:  
https://en.wikipedia.org/wiki/List_of_largest_cities

PH SQL:  
Tool to get a free Postgres database + run some queries  
https://pg-sql.com/

### 2. Analyzing CREATE TABLE

Keyword: CREATE TABLE
keywords: Tell the database that we want to do something.
Always written out in capital letters

Identifier: cities
Identifiers: Tell the database what thing we want to act on.
Always written out in lowercase letters

```
CREATE TABLE cities (
  name VARCHAR(50),
  country VARCHAR(50),
  population INTEGER,
  area INTEGER
);
```

VARCHAR(50) -> Column Data Types:  
Variable length character. Text! if we put in a string longer
than 50 characters, we'll get an error

INTEGER -> Column Data Types:
Number without a decimal. -2,147,483,647 to +2,147,483,647.
Anything larger or smaller = error!

### 3. Inserting Data Into a Table

```
INSERT INTO cities (name, country, population, area)
VALUES ('Tokyo', 'Japan', 38505000,8223)
```

```
INSERT INTO cities (name, country, population, area)
VALUES
	('Delhi', 'India', 28125000,2240),
  ('Shanghai', 'China', 2212500, 4015),
  ('Sao Paulo', 'Brazil', 20935000, 3043);
```

This query , gets all columns from cities table

```
SELECT * FROM cities;
```

This query , gets the name and country columns from cities table

```
SELECT name, country FROM cities;
```

### 4. Coding Exercise 1: Create, Insert, and Select!

```
CREATE TABLE movies (
    title VARCHAR(60),
    box_office INTEGER
);

INSERT INTO movies (title, box_office)
VALUES
    ('The Avengers', 1500000000),
    ('Batman v Superman', 873000000);


-- WRITE YOUR SOLUTION BELOW THIS LINE!
SELECT title, box_office from MOVIES
```

### 5. Calculated Columns

Calculated column with math operations:  
`SELECT name, population / area FROM cities;`

```
| +  |  Add   | ^  |  Exponent    |
|----|--------|----|--------------|
| -  |Subtract| |/ |Square Root   |
| *  |Multiply|  @ |Absolute Value|
| /  |Divide  |  % |Remainder     |
```

### 6. Coding Exercise 2: Using Calculated Columns

Renaming a calculated column:  
SELECT name, population / area AS population_density
FROM cities;

Using Calculated Columns  
Take a look at the following table called phones. This table has already been inserted into the database for you.

Write a query that will select the name of each phone and calculate the total revenue for each phone (price X units_sold)

Rename this calculated column to revenue

`SELECT name, price * units_sold AS revenue FROM phones;`
