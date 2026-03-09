# Database Fundamentals

## Introduction

A database is an organized collection of structured information or data that is stored electronically in a computer system. Databases allow users to store, manage, retrieve, and manipulate data efficiently.

A Database Management System (DBMS) is the software used to interact with the database. It enables users to create, read, update, and delete data.

Examples of DBMS:

* MySQL
* PostgreSQL
* Oracle Database
* Microsoft SQL Server
* MongoDB

---

# Why Databases Are Important

Databases play a critical role in modern applications because they provide a reliable way to manage large amounts of data.

Key reasons databases are used:

* Efficient data storage
* Fast data retrieval
* Data consistency and accuracy
* Multi-user access
* Data security
* Backup and recovery support

Example:

In a banking system, databases store:

* Customer information
* Account balances
* Transaction history
* Loan records

Without databases, managing this information would be extremely difficult.

---

# Components of a Database

## Tables

A table is the primary structure used to store data in a relational database. It organizes data into rows and columns.

Example table: Customers

| Customer_ID | Name | City      |
| ----------- | ---- | --------- |
| 1           | John | New York  |
| 2           | Rita | Chennai   |
| 3           | Arun | Bangalore |

---

## Rows

Rows represent individual records in a table.

Example:

Customer_ID = 1
Name = John
City = New York

Each row represents one customer.

---

## Columns

Columns represent attributes of the data stored in the table.

Example:

Customer_ID
Name
City

Each column defines a specific type of information.

---

# Primary Key

A primary key uniquely identifies each record in a table.

Characteristics:

* Must be unique
* Cannot contain NULL values
* Only one primary key per table

Example:

Customer_ID is usually used as a primary key.

Example SQL:

```sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    name VARCHAR(50),
    city VARCHAR(50)
);
```

---

# Foreign Key

A foreign key is used to link two tables together.

It establishes a relationship between tables.

Example:

Customers table
Orders table

Orders table may contain a column called customer_id that references the Customers table.

Example SQL:

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
);
```

---

# Types of Databases

## Relational Databases

Relational databases store data in tables with relationships between them.

Examples:

* MySQL
* PostgreSQL
* Oracle
* SQL Server

These databases use SQL (Structured Query Language).

---

## NoSQL Databases

NoSQL databases are designed to handle unstructured or semi-structured data.

Examples:

* MongoDB
* Cassandra
* Redis
* DynamoDB

NoSQL databases are commonly used for big data and real-time applications.

---

# Indexing

Indexing improves the speed of data retrieval.

Instead of scanning the entire table, the database can use an index to find records faster.

Example SQL:

```sql
CREATE INDEX idx_customer_name
ON customers(name);
```

Indexes are commonly used on columns that are frequently searched.

---

# Data Integrity

Data integrity ensures that the data stored in the database remains accurate and consistent.

Types of integrity:

Entity Integrity
Ensures each record has a unique primary key.

Referential Integrity
Ensures foreign keys correctly reference existing records.

Domain Integrity
Ensures values fall within acceptable ranges.

Example:

A customer's age cannot be negative.

---

# SQL Operations (CRUD)

Databases commonly support four main operations called CRUD.

Create
Insert new data into the database.

Example:

```sql
INSERT INTO customers VALUES (1,'Rita','Chennai');
```

Read
Retrieve data from the database.

Example:

```sql
SELECT * FROM customers;
```

Update
Modify existing data.

Example:

```sql
UPDATE customers
SET city = 'Madurai'
WHERE customer_id = 1;
```

Delete
Remove data from the database.

Example:

```sql
DELETE FROM customers
WHERE customer_id = 1;
```

---

# Summary

Database systems are fundamental to modern software applications. They allow organizations to efficiently store, manage, and retrieve large volumes of structured data.

Understanding database fundamentals such as tables, keys, relationships, indexing, and SQL operations is essential for careers in data engineering, data analytics, and software development.
