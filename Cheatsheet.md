# SQL Cheat Sheet – COMPLETE LEARNING VERSION 📘 (SQL Standard / MySQL / PostgreSQL)

This cheat sheet covers **core SQL concepts**, queries, joins, functions, data definition, and modern SQL features.  
Suitable for beginners and refreshers (Database / Backend).

---

## Table of Contents

- [SQL Cheat Sheet – COMPLETE LEARNING VERSION 📘 (SQL Standard / MySQL / PostgreSQL)](#sql-cheat-sheet--complete-learning-version--sql-standard--mysql--postgresql)
  - [Table of Contents](#table-of-contents)
  - [1. Basics](#1-basics)
  - [2. Creating \& Dropping Tables](#2-creating--dropping-tables)
  - [3. Inserting Data](#3-inserting-data)
  - [4. Selecting Data](#4-selecting-data)
  - [5. Filtering \& Sorting](#5-filtering--sorting)
  - [6. Aggregate Functions](#6-aggregate-functions)
  - [7. Grouping](#7-grouping)
  - [8. Joins](#8-joins)
  - [9. Subqueries](#9-subqueries)
  - [10. Updating \& Deleting](#10-updating--deleting)
  - [11. Constraints](#11-constraints)
  - [12. Indexes \& Views](#12-indexes--views)
  - [13. Transactions](#13-transactions)
  - [14. Data Types](#14-data-types)
  - [15. String \& Date Functions](#15-string--date-functions)
  - [16. Best Practices](#16-best-practices)
  - [End](#end)

---

## 1. Basics

~~~sql
-- SQL statements end with ;
-- Case-insensitive (SELECT = select)
SELECT 'Hello World';
~~~

---

## 2. Creating & Dropping Tables

~~~sql
-- Create table
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Drop table
DROP TABLE users;
~~~

---

## 3. Inserting Data

~~~sql
INSERT INTO users (id, name, age) VALUES (1, 'Max', 30);
INSERT INTO users VALUES (2, 'Anna', 25);
~~~

---

## 4. Selecting Data

~~~sql
SELECT * FROM users;
SELECT name, age FROM users;
SELECT DISTINCT age FROM users;
~~~

---

## 5. Filtering & Sorting

~~~sql
-- WHERE clause
SELECT * FROM users WHERE age > 25;
SELECT * FROM users WHERE name LIKE 'A%';

-- ORDER BY
SELECT * FROM users ORDER BY age DESC;

-- LIMIT / OFFSET
SELECT * FROM users LIMIT 5 OFFSET 10;
~~~

---

## 6. Aggregate Functions

~~~sql
SELECT COUNT(*) FROM users;
SELECT SUM(age) FROM users;
SELECT AVG(age) FROM users;
SELECT MIN(age), MAX(age) FROM users;
~~~

---

## 7. Grouping

~~~sql
SELECT age, COUNT(*) 
FROM users 
GROUP BY age
HAVING COUNT(*) > 1;
~~~

---

## 8. Joins

~~~sql
-- Inner join
SELECT u.name, o.amount
FROM users u
JOIN orders o ON u.id = o.user_id;

-- Left join
SELECT u.name, o.amount
FROM users u
LEFT JOIN orders o ON u.id = o.user_id;

-- Right join
SELECT u.name, o.amount
FROM users u
RIGHT JOIN orders o ON u.id = o.user_id;

-- Full outer join (PostgreSQL)
SELECT u.name, o.amount
FROM users u
FULL OUTER JOIN orders o ON u.id = o.user_id;
~~~

---

## 9. Subqueries

~~~sql
SELECT name FROM users WHERE age = (SELECT MAX(age) FROM users);

SELECT name FROM users WHERE id IN (SELECT user_id FROM orders);
~~~

---

## 10. Updating & Deleting

~~~sql
-- Update
UPDATE users SET age = age + 1 WHERE name = 'Max';

-- Delete
DELETE FROM users WHERE age < 20;
~~~

---

## 11. Constraints

~~~sql
CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    age INT CHECK (age > 0),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
~~~

---

## 12. Indexes & Views

~~~sql
-- Index
CREATE INDEX idx_name ON users(name);

-- View
CREATE VIEW adult_users AS
SELECT * FROM users WHERE age >= 18;
~~~

---

## 13. Transactions

~~~sql
BEGIN;

UPDATE accounts SET balance = balance - 100 WHERE id = 1;
UPDATE accounts SET balance = balance + 100 WHERE id = 2;

COMMIT;    -- or ROLLBACK;
~~~

---

## 14. Data Types

~~~sql
INT, BIGINT, SMALLINT
DECIMAL(p,s), NUMERIC
VARCHAR(n), CHAR(n), TEXT
DATE, TIME, TIMESTAMP
BOOLEAN
~~~

---

## 15. String & Date Functions

~~~sql
-- Strings
SELECT LENGTH(name), UPPER(name), LOWER(name), CONCAT(name, ' Smith') FROM users;

-- Dates
SELECT CURRENT_DATE, CURRENT_TIMESTAMP;
SELECT EXTRACT(YEAR FROM created_at) FROM users;
~~~

---

## 16. Best Practices

- Use meaningful table & column names
- Always use primary keys
- Use foreign keys for relationships
- Normalize your database
- Prefer prepared statements to prevent SQL injection
- Comment complex queries
- Use transactions for multiple dependent operations
- Test queries on small datasets before production

---

## End
