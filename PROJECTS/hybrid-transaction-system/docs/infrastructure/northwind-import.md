# Northwind Database Import

## Overview

The project uses the Microsoft Northwind sample database as the initial enterprise relational dataset.

Northwind simulates a commercial environment containing:
- customers,
- orders,
- products,
- suppliers,
- employees,
- and shipping operations.

The database is used to support:
- backend API development,
- SQL relationship studies,
- enterprise query simulations,
- and future legacy integration scenarios.

---

# Database Creation

The database was manually created using SQL Server Management Studio.

```sql
CREATE DATABASE Northwind;
GO
```

---

# Import Process

The official Microsoft SQL script was imported into the `Northwind` database using SQL Server Management Studio.

## Import Steps

1. Create the database
2. Select the `Northwind` database
3. Open `instnwnd.sql`
4. Execute the full script

---

# Important Observation

The execution context inside SSMS is critical.

The import script must be executed with:

```text
Northwind
```

selected as the active database.

Executing the script against `master` may cause import failures or unintended object creation.

---

# Validation Queries

## Customers Table

```sql
SELECT TOP 10 * FROM Customers;
```

## Orders Table

```sql
SELECT TOP 10 * FROM Orders;
```

## Relational Query Example

```sql
SELECT
    o.OrderID,
    c.CompanyName,
    o.OrderDate,
    o.Freight,
    o.ShipCountry
FROM Orders o
INNER JOIN Customers c
    ON o.CustomerID = c.CustomerID
ORDER BY o.OrderID;
```

---

# Current Status

## Operational

The Northwind database is fully operational and validated.

The environment currently supports:
- relational queries,
- joins,
- backend integrations,
- and enterprise-style data exploration.