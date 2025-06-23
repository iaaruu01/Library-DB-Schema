# Library-DB-Schema

#  Library Management System - Database Schema

##  Task Overview

This project is part of the SQL Developer Internship Task 1: **Database Setup and Schema Design**.  
The objective is to design and implement a normalized relational database schema for a Library Management System.

---

##  Domain Chosen: Library

A library stores books, lends them to members, manages loans, and records author and staff details.

---

##  Tools Used

- MySQL Workbench (for SQL scripting and ER diagram)
- GitHub (for version control and submission)
- [DDL Language](https://www.w3schools.com/sql/sql_create_table.asp)

---

##  Entities and Attributes

### 1. **Category**
- `CategoryID` *(PK)*: Unique ID
- `Name`: Genre/category name

### 2. **Author**
- `AuthorID` *(PK)*: Unique ID
- `Name`: Author name

### 3. **Book**
- `BookID` *(PK)*: Unique ID
- `Title`: Book title
- `AuthorID` *(FK)*: References `Author`
- `CategoryID` *(FK)*: References `Category`

### 4. **Member**
- `MemberID` *(PK)*: Unique ID
- `Name`: Member's name
- `Email`: Unique email ID

### 5. **Loan**
- `LoanID` *(PK)*: Unique loan transaction ID
- `BookID` *(FK)*: References `Book`
- `MemberID` *(FK)*: References `Member`
- `LoanDate`: Date of issue
- `ReturnDate`: Date of return

### 6. **Staff**
- `StaffID` *(PK)*: Unique staff ID
- `Name`: Staff member's name
- `Role`: Librarian / Clerk / Admin etc.

---

##  Relationships

- One **Author** can write many **Books**.
- Each **Book** belongs to one **Category**.
- One **Member** can borrow many **Books** (via **Loan**).
- **Loan** is a many-to-many bridge between **Member** and **Book**.
- **Staff** is managed separately.

---

##  ER Diagram

![ER Diagram](ER_Diagram.png)

> *Diagram illustrates keys and foreign relationships.*

---

##  SQL Script

See [`schema.sql`](schema.sql) file for the complete table creation script with proper constraints.

---

##  Key Concepts Applied

- DDL: `CREATE TABLE`, `PRIMARY KEY`, `FOREIGN KEY`
- Constraints: `UNIQUE`, `NOT NULL`, `AUTO_INCREMENT`
- Normalization: 3NF ensured
- ER Design: Visual mapping of relationships


