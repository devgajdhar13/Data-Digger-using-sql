# 🧠 Data Digger — SQL E-Commerce Database Project

> **A practical MySQL project demonstrating relational database design, CRUD operations, foreign keys, aggregate functions, joins, subqueries, and business-oriented SQL queries.**

![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/Language-SQL-336791)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white)
![Python](https://img.shields.io/badge/Integration-Python-3776AB?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Project Overview

**Data Digger** is a relational SQL project built around an online-shopping database.

The project uses four related tables:

- 👤 `Customers`
- 🛒 `Orders`
- 📦 `Products`
- 🧾 `OrderDetails`

The work is organized in a Jupyter Notebook and focuses on practical SQL operations such as data insertion, retrieval, updating, deletion, filtering, sorting, aggregation, grouping, joins, and subqueries.

---

## 🎯 Objectives

- 🗄️ Design a relational database
- 🔑 Use primary and foreign keys
- ➕ Insert sample records
- 🔎 Retrieve and filter records
- ✏️ Update existing records
- 🗑️ Delete records
- 📅 Perform date-based filtering
- ↕️ Sort and limit query results
- 📊 Use `COUNT()`, `SUM()`, `AVG()`, `MAX()`, and `MIN()`
- 🧩 Use `GROUP BY` and `HAVING`
- 🔗 Join related tables
- 🧠 Use subqueries for analysis

---

## 📊 Database Flow Chart

```mermaid
flowchart TD
    A[👤 Customers] -->|CustomerID| B[🛒 Orders]
    B -->|OrderID| C[🧾 OrderDetails]
    D[📦 Products] -->|ProductID| C
    C --> E[📊 SQL Analysis]
    E --> F[📈 Business Insights]
```

---

## 🔗 Table Relationships

```mermaid
erDiagram
    CUSTOMERS ||--o{ ORDERS : places
    ORDERS ||--o{ ORDERDETAILS : contains
    PRODUCTS ||--o{ ORDERDETAILS : included_in

    CUSTOMERS {
        int CustomerID PK
        varchar Name
        varchar Email
        varchar Address
    }

    ORDERS {
        int OrderID PK
        int CustomerID FK
        date OrderDate
        decimal TotalAmount
    }

    PRODUCTS {
        int ProductID PK
        varchar ProductName
        decimal Price
        int Stock
    }

    ORDERDETAILS {
        int OrderDetailID PK
        int OrderID FK
        int ProductID FK
        int Quantity
        decimal SubTotal
    }
```

---

## 🗂️ Database Schema

| Table | Important Columns | Purpose |
|---|---|---|
| 👤 `Customers` | `CustomerID`, `Name`, `Email`, `Address` | Customer information |
| 🛒 `Orders` | `OrderID`, `CustomerID`, `OrderDate`, `TotalAmount` | Customer orders |
| 📦 `Products` | `ProductID`, `ProductName`, `Price`, `Stock` | Product catalog |
| 🧾 `OrderDetails` | `OrderDetailID`, `OrderID`, `ProductID`, `Quantity`, `SubTotal` | Order line items |

---

# 🖼️ Complete Project Evidence

> **All screenshots supplied in the conversation are included below.**  
> The original folder-view screenshots are preserved, and the individual query screenshots visible inside those folder views have also been extracted into separate image files for easier GitHub viewing.

---


# 👤 Customer Queries

### Retrieve All Customer Details

![Retrieve All Customer Details](assets/screenshots/customer-retrieve-all.png)

### Delete Customer Using CustomerID

![Delete Customer](assets/screenshots/customer-delete.png)

### Display All Customers Whose Name Is Alice

![Alice Customers](assets/screenshots/customer-alice.png)

### Insert Customer Values

![Insert Customers](assets/screenshots/customer-insert.png)

### Update Customer Address

![Update Customer Address](assets/screenshots/customer-update-address.png)

---

# 🛒  Order Queries

### Delete Order Using OrderID

![Delete Order](assets/screenshots/order-delete.png)

### Highest, Lowest and Average Order Amount

![Highest Lowest Average](assets/screenshots/order-highest-lowest-avg.png)

### Insert Orders

![Insert Orders](assets/screenshots/order-insert.png)

### Retrieve Orders in the Last 30 Days

![Last 30 Days Orders](assets/screenshots/order-last-30-days.png)

### Retrieve Orders for a Specific Customer

![Specific Customer Orders](assets/screenshots/order-specific-customer.png)

### Update Order Total Amount

![Update Order Total](assets/screenshots/order-update-total.png)

---

# 📦 Product Queries

### Delete Product if Out of Stock

![Delete Out of Stock Product](assets/screenshots/product-delete-out-of-stock.png)

### Insert Sample Products

![Insert Products](assets/screenshots/product-insert.png)

### Most Expensive and Cheapest Product

![Min Max Products](assets/screenshots/product-min-max.png)

### Products Between ₹500 and ₹2000

![Product Price Range](assets/screenshots/product-price-range.png)

### Sort Products by Price

![Sorted Products](assets/screenshots/product-sort-price.png)

### Update Product Price

![Update Product Price](assets/screenshots/product-update-price.png)

---

# 🧾 OrderDetails Queries

### Insert OrderDetails Records

![Insert OrderDetails](assets/screenshots/order-details-insert.png)

### Retrieve Order Details for a Specific Order

![Specific Order Details](assets/screenshots/order-details-specific-order.png)

### Count Product Sales

![Product Count](assets/screenshots/order-details-product-count.png)

### Top 3 Most Ordered Products

![Top 3 Products](assets/screenshots/order-details-top3-products.png)

### Total Revenue

![Total Revenue](assets/screenshots/order-details-total-revenue.png)

---

## 🧪 Practical Queries Covered

### 👤 Customers

- Insert at least 5 sample customers
- Retrieve all customer details
- Update a customer's address
- Delete a customer using `CustomerID`
- Display all customers whose name is `Alice`

### 🛒 Orders

- Insert at least 5 sample orders
- Retrieve orders for a specific customer
- Update an order's total amount
- Delete an order using `OrderID`
- Retrieve orders placed in the last 30 days
- Find highest, lowest and average order amount

### 📦 Products

- Insert at least 5 sample products
- Sort products by price descending
- Update a product price
- Delete a product if it is out of stock
- Retrieve products between ₹500 and ₹2000
- Retrieve the most expensive and cheapest products using `MAX()` and `MIN()`

### 🧾 OrderDetails

- Insert at least 5 sample records
- Retrieve details for a specific order
- Calculate total revenue with `SUM()`
- Retrieve top 3 most ordered products
- Count how many times a product has been sold using `COUNT()`

---

## 📚 SQL Concepts Demonstrated

| Category | Concepts |
|---|---|
| 🏗️ DDL | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` |
| ✏️ DML | `INSERT`, `UPDATE`, `DELETE` |
| 🔎 DQL | `SELECT` |
| 🔐 Constraints | Primary Key, Foreign Key, `NOT NULL`, `UNIQUE`, `CHECK`, `DEFAULT` |
| 🎯 Filtering | `WHERE`, `BETWEEN`, `IN`, `LIKE` |
| 🧠 Logic | `AND`, `OR`, `NOT` |
| ↕️ Sorting | `ORDER BY` |
| 🎯 Limiting | `LIMIT` |
| 📊 Aggregation | `COUNT`, `SUM`, `AVG`, `MAX`, `MIN` |
| 🧩 Grouping | `GROUP BY`, `HAVING` |
| 🔗 Relationships | `JOIN` |
| 🧠 Advanced querying | Subqueries |
| 📅 Date analysis | `CURDATE()`, `INTERVAL` |

---

## 🛠️ Tech Stack

- 🐬 **MySQL** — Relational database
- 🧮 **SQL** — Query language
- 📓 **Jupyter Notebook (`.ipynb`)** — Interactive execution
- 🐍 **Python** — Notebook environment
- 🔌 **PyMySQL** — MySQL connection
- ⚙️ **SQLAlchemy** — Database connection layer
- 🧩 **SQL Magic** — Run SQL inside notebook cells

---

## 🚀 How to Run

### 1️⃣ Install packages

```bash
pip install ipython-sql pymysql sqlalchemy
```

### 2️⃣ Start MySQL

Start the MySQL service from XAMPP.

### 3️⃣ Open the notebook

Open `shop_sql.ipynb` in VS Code using the Jupyter extension.

### 4️⃣ Connect to MySQL

```python
%load_ext sql
%config SqlMagic.feedback = False
%config SqlMagic.displaycon = False

%sql mysql+pymysql://root:YOUR_PASSWORD@localhost/mysql
```

### 5️⃣ Run SQL cells in order

```text
Connect → Create Database → Create Tables → Insert Data → Run Queries
```

---

## 📁 Recommended GitHub Structure

```text
SQL-Assignment-1/
│
├── 📓 shop_sql.ipynb
├── 📄 README.md
│
└── 📁 assets/
    └── 📁 screenshots/
        ├── 01-project-scope-customers-orders.png
        ├── 02-project-scope-products-orderdetails.png
        ├── 03-customer-queries-folder.png
        ├── 04-order-queries-folder.png
        ├── 05-order-details-folder.png
        ├── 06-product-table-folder.png
        ├── customer-retrieve-all.png
        ├── customer-delete.png
        ├── customer-alice.png
        ├── customer-insert.png
        ├── customer-update-address.png
        ├── order-delete.png
        ├── order-highest-lowest-avg.png
        ├── order-insert.png
        ├── order-last-30-days.png
        ├── order-specific-customer.png
        ├── order-update-total.png
        ├── product-delete-out-of-stock.png
        ├── product-insert.png
        ├── product-min-max.png
        ├── product-price-range.png
        ├── product-sort-price.png
        ├── product-update-price.png
        ├── order-details-insert.png
        ├── order-details-specific-order.png
        ├── order-details-product-count.png
        ├── order-details-top3-products.png
        └── order-details-total-revenue.png
```

---

## 🎓 Learning Outcomes

By completing this project, you demonstrate hands-on experience with:

**Database Design → Table Relationships → CRUD → Filtering → Sorting → Aggregation → Grouping → Joins → Subqueries → Business-Oriented SQL Analysis**

---

## 🔐 Security Note

Never upload real MySQL passwords, API keys, or other credentials to a public GitHub repository.

Use placeholders such as:

```text
YOUR_PASSWORD
```

---

## ⭐ Project Summary

**Project:** Data Digger — SQL E-Commerce Database Project  
**Domain:** E-Commerce / Database Management  
**Database:** MySQL  
**Notebook:** `shop_sql.ipynb`  
**Core Skills:** SQL, Relational Database Design, CRUD, Constraints, Aggregation, `GROUP BY`, `HAVING`, Joins and Subqueries

---

## ✅ Screenshot Coverage

**Included from the supplied screenshots:**

- ✅ 2 assignment-scope screenshots
- ✅ 4 folder-view screenshots
- ✅ 5 Customer query screenshots
- ✅ 6 Order query screenshots
- ✅ 6 Product query screenshots
- ✅ 5 OrderDetails query screenshots

**Total: 28 screenshot images in the README package.**
