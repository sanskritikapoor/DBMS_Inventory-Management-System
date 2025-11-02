# DBMS_Inventory-Management-System
The Inventory Management System efficiently manages products, suppliers, stock, and purchase data using SQL and relational database concepts. It ensures accurate tracking, reduces redundancy, and supports better decision-making through structured storage and efficient data retrieval.
# 📦 Inventory Management System (DBMS Project)

## 🧩 Overview
The **Inventory Management System** is a database-driven project developed to manage and monitor inventory operations efficiently. It helps track **products**, **suppliers**, **stock levels**, and **purchase records** using SQL-based database management.

This project ensures data consistency, reduces redundancy, and simplifies inventory handling through a well-structured relational database design.

---

## 🎯 Aim
To design and implement a database system that efficiently manages product inventory, supplier details, and purchase transactions for small to medium-scale businesses.

---

## 📝 Objectives
- Manage and organize inventory data efficiently.  
- Maintain supplier and product information accurately.  
- Implement normalization up to **3NF** to remove redundancy.  
- Execute SQL queries for data manipulation and analysis.  
- Apply constraints to ensure data integrity and accuracy.

---

## 🛠️ Tools & Technologies Used
- **Database:** MySQL / Oracle / PostgreSQL  
- **ER Diagram Tool:** Draw.io / Lucidchart  
- **Language:** SQL  
- **Editor:** VS Code / MySQL Workbench  

---

## 💾 System Requirements
- **Operating System:** Windows / macOS / Linux  
- **RAM:** Minimum 4 GB  
- **Software:** MySQL Server, MySQL Workbench or equivalent SQL IDE  

---

## 🧠 Database Design
### Entities:
- **Product(Product_ID, Product_Name, Category, Unit_Price, Quantity_In_Stock, Supplier_ID)**  
- **Supplier(Supplier_ID, Supplier_Name, Contact_Number, Email, Address)**  
- **Purchase(Purchase_ID, Product_ID, Supplier_ID, Purchase_Date, Quantity_Purchased, Total_Cost)**  
- **Stock(Stock_ID, Product_ID, Available_Quantity, Last_Updated_Date)**  

### Relationships:
- Supplier → Product (1:M)  
- Product → Purchase (1:M)  
- Supplier → Purchase (1:M)  
- Product → Stock (1:1)

---

## 💻 Implementation
Includes:
- **DDL Commands:** Table creation with PK, FK, and constraints.  
- **DML Commands:** Insertion, updating, and deletion of records.  
- **Queries:** Using `SELECT`, `WHERE`, `GROUP BY`, `HAVING`, `JOIN`, and `VIEWS`.

---

## 🧩 Sample Query
```sql
SELECT p.Product_Name, s.Supplier_Name, SUM(pr.Quantity_Purchased) AS Total_Quantity
FROM Product p
JOIN Purchase pr ON p.Product_ID = pr.Product_ID
JOIN Supplier s ON s.Supplier_ID = pr.Supplier_ID
GROUP BY p.Product_Name, s.Supplier_Name
HAVING SUM(pr.Quantity_Purchased) > 50;
