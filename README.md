# Weapon Inventory Management Database

A relational SQL database project designed to manage weapon inventory, suppliers, customers, orders, and stock transactions. The project demonstrates database design principles, normalization, relationships, indexing, and inventory tracking using Microsoft SQL Server.

## Overview

This database simulates a weapon store or armory management system where products can be purchased from suppliers, sold to customers, and tracked through inventory and transaction records.

The project was created to practice:

* Relational database design
* Primary and foreign keys
* Table normalization
* SQL querying
* Indexing and performance optimization
* Inventory management concepts

---

## Database Schema

### Core Tables

| Table          | Description                  |
| -------------- | ---------------------------- |
| `GunTypes`     | Stores weapon categories     |
| `Products`     | Main catalog of firearms     |
| `Customers`    | Customer information         |
| `Orders`       | Customer orders              |
| `OrderItems`   | Products contained in orders |
| `Suppliers`    | Supplier information         |
| `Inventory`    | Incoming stock records       |
| `Transactions` | Purchase and sale history    |
| `Employees`    | Employee information         |

### Weapon-Specific Tables

Additional tables store specifications for different firearm categories:

* Handguns
* Rifles
* Shotguns
* Assault Rifles
* Machine Guns
* Revolvers

---

## Entity Relationships

```text
GunTypes
    │
    └── Products
            │
            ├── Transactions
            ├── Inventory
            └── OrderItems

Customers
    │
    └── Orders
            │
            └── OrderItems

Suppliers
    │
    └── Inventory
```

---

## Features

* Product inventory management
* Weapon categorization
* Supplier management
* Customer management
* Order processing
* Transaction tracking
* Inventory monitoring
* Employee records
* Indexed database structure

---

## Technologies

* Microsoft SQL Server
* T-SQL
* Relational Database Design
* Foreign Key Constraints
* Database Indexing

---

## Sample Data

The database includes sample records for:

* Weapon categories
* Products
* Suppliers
* Customers
* Orders
* Transactions

Example firearms included:

* AK-47
* HK416
* AN-94
* FAMAS
* Colt Python
* Smith & Wesson Model 686
* Benelli Nova
* MG42

---

## Indexing

Indexes are implemented to improve query performance on commonly searched columns.

Examples include:

```sql
CREATE INDEX idx_GunTypes_Name ON GunTypes(Name);
CREATE INDEX idx_Products_Name ON Products(Name);
CREATE INDEX idx_Products_GunTypeID ON Products(GunTypeID);
CREATE INDEX idx_Transactions_ProductID ON Transactions(ProductID);
CREATE INDEX idx_Transactions_Date ON Transactions(TransactionDate);
```

---

## Installation

1. Open Microsoft SQL Server Management Studio (SSMS).
2. Create a new database.
3. Open the `Project.sql` file.
4. Execute the script.
5. Verify that all tables and sample data are created successfully.

---

## Example Queries

### View all products

```sql
SELECT *
FROM Products;
```

### View products by category

```sql
SELECT p.Name, gt.Name AS GunType
FROM Products p
JOIN GunTypes gt
ON p.GunTypeID = gt.GunTypeID;
```

### View customer orders

```sql
SELECT *
FROM Orders;
```

### View inventory records

```sql
SELECT *
FROM Inventory;
```

---

## Future Improvements

* Stored procedures
* Triggers for stock updates
* Reporting views
* User authentication system
* Audit logging
* Sales analytics
* Inventory alerts
* Dashboard integration

---

## Author

**Murad**
Computer Science Student (Cloud Engineering & DevOps)

### Skills Demonstrated

* SQL Database Design
* Data Modeling
* Normalization
* Foreign Keys
* Indexing
* Inventory Management Systems
* Relational Databases

---

**Project Type:** Academic Database Project
**Database:** Microsoft SQL Server
**Focus:** Database Design, SQL Development, Inventory Management
