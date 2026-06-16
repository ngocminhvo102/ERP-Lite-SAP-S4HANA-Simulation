# 09. ERD (Entity Relationship Diagram)

## Objective

The objective of this phase is to transform business requirements and process designs defined in the Business Blueprint into a logical database model.

The ERD serves as the foundation for:

* Database Design
* API Design
* Application Development
* Reporting Design
* Data Integration

This design follows ERP best practices inspired by SAP S/4HANA concepts.

---

# ERP Data Model Overview

The ERP Lite solution consists of four core business domains:

```text
Sales
│
├── Customers
├── Quotations
├── Sales Orders
└── Invoices

Warehouse
│
├── Products
├── Inventory
├── Goods Receipts
├── Goods Issues
└── Inventory Batches

Human Resources
│
├── Employees
├── Departments
├── Attendance
└── Leave Requests

Finance
│
├── Invoices
├── Payments
├── Accounts Receivable
└── Accounts Payable
```

---

# Master Data Entities

Master Data contains business information that is reused across multiple processes.

## Customer

Stores customer information used throughout the sales cycle.

### Main Attributes

* Customer Code
* Customer Name
* Tax Code
* Address
* Phone Number
* Email
* Credit Limit
* Payment Terms
* Status

---

## Product

Stores product information used in sales and inventory processes.

### Main Attributes

* Product Code
* Product Name
* Product Category
* Unit of Measure
* Standard Cost
* Selling Price
* Batch Managed
* Expiry Managed
* Status

---

## Employee

Stores employee information used in HR processes.

### Main Attributes

* Employee ID
* Employee Name
* Department
* Position
* Join Date
* Contact Information
* Status

---

## Vendor

Stores supplier information used for procurement and inventory replenishment.

### Main Attributes

* Vendor Code
* Vendor Name
* Tax Code
* Contact Person
* Payment Terms
* Status

---

## Department

Stores organizational department structure.

### Main Attributes

* Department Code
* Department Name

---

# Sales Data Model

The Sales module manages the complete Order-to-Cash process.

## Business Flow

```text
Customer
↓
Quotation
↓
Sales Order
↓
Delivery
↓
Invoice
↓
Payment
```

---

## Sales Entities

### Quotations

Stores customer quotations prepared by sales staff.

### Quotation Items

Stores product details associated with each quotation.

### Sales Orders

Stores confirmed customer orders.

### Sales Order Items

Stores line items associated with sales orders.

### Invoices

Stores billing documents generated after delivery.

---

# Warehouse Data Model

The Warehouse module manages inventory operations and stock movements.

## Business Flow

```text
Goods Receipt
↓
Inventory Storage
↓
Goods Issue
↓
Inventory Count
```

---

## Warehouse Entities

### Warehouses

Stores warehouse master information.

### Inventory

Stores current stock quantities by warehouse and product.

### Inventory Batches

Stores batch and expiry information.

### Goods Receipts

Records inventory received from suppliers.

### Goods Issues

Records inventory issued to customers.

---

# Human Resource Data Model

The HR module manages employee administration and workforce activities.

## Business Flow

```text
Employee
↓
Attendance
↓
Leave Request
↓
Approval
```

---

## HR Entities

### Employees

Employee master records.

### Attendance

Daily attendance records.

### Leave Requests

Employee leave applications and approval status.

---

# Finance Data Model

The Finance module manages financial transactions and cash flow.

## Business Flow

```text
Invoice
↓
Accounts Receivable
↓
Payment
↓
Cash Flow
```

---

## Finance Entities

### Invoices

Customer billing records.

### Payments

Customer payment transactions.

---

# Logical Relationships

## Customer Relationships

```text
Customer
│
├── Quotation
│       └── Quotation Item
│
├── Sales Order
│       └── Sales Order Item
│
└── Invoice
```

---

## Product Relationships

```text
Product
│
├── Quotation Item
├── Sales Order Item
├── Inventory
└── Inventory Batch
```

---

## Employee Relationships

```text
Department
│
└── Employee
        │
        ├── Attendance
        └── Leave Request
```

---

## Warehouse Relationships

```text
Warehouse
│
├── Inventory
├── Goods Receipt
└── Goods Issue
```

---

## Finance Relationships

```text
Invoice
│
└── Payment
```

---

# SAP S/4HANA Mapping

| ERP Lite Entity | SAP S/4HANA Equivalent |
| --------------- | ---------------------- |
| Customer        | Business Partner       |
| Vendor          | Business Partner       |
| Product         | Material Master        |
| Quotation       | Sales Quotation        |
| Sales Order     | Sales Order            |
| Inventory       | Stock Overview         |
| Goods Receipt   | Material Document      |
| Goods Issue     | Material Document      |
| Invoice         | Billing Document       |
| Payment         | FI Document            |
| Employee        | Employee Master Data   |

---

# Database Summary

| Category        | Entity Count |
| --------------- | ------------ |
| Master Data     | 5            |
| Sales           | 4            |
| Warehouse       | 5            |
| Human Resources | 3            |
| Finance         | 2            |
| Total           | 19           |

---

# Design Principles

The ERP Lite database model follows the following principles:

1. Single Source of Truth

   * Business data is stored once and reused across modules.

2. Data Integrity

   * Relationships are enforced through primary and foreign keys.

3. Scalability

   * The model supports future expansion such as Purchasing, Manufacturing, and Payroll.

4. ERP Integration

   * Transactions automatically update related modules.

5. Auditability

   * Business transactions can be traced from source document to financial impact.

---


