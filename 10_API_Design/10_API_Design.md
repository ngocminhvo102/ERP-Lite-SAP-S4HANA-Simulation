# API Design

## Objective

The purpose of this document is to define the REST APIs required to support the ERP Lite system.

The APIs will serve as the communication layer between:

* Frontend Application
* Backend Services
* Database

The design follows RESTful API best practices.

---

# API Architecture

```text
Frontend (React / NextJS)
        │
        ▼
REST API (FastAPI)
        │
        ▼
PostgreSQL Database
```

---

# Authentication API

## Login

### Endpoint

```http
POST /api/auth/login
```

### Request

```json
{
  "username": "sales01",
  "password": "******"
}
```

### Response

```json
{
  "access_token": "jwt-token",
  "role": "SALES_STAFF"
}
```

---

## Logout

```http
POST /api/auth/logout
```

---

# Customer API

## Get Customers

```http
GET /api/customers
```

---

## Get Customer Detail

```http
GET /api/customers/{id}
```

---

## Create Customer

```http
POST /api/customers
```

### Request

```json
{
  "customer_code": "CUS001",
  "customer_name": "ABC Company",
  "tax_code": "123456789"
}
```

---

## Update Customer

```http
PUT /api/customers/{id}
```

---

## Delete Customer

```http
DELETE /api/customers/{id}
```

---

# Product API

## Get Products

```http
GET /api/products
```

---

## Product Detail

```http
GET /api/products/{id}
```

---

## Create Product

```http
POST /api/products
```

---

## Update Product

```http
PUT /api/products/{id}
```

---

# Quotation API

## Create Quotation

```http
POST /api/quotations
```

### Request

```json
{
  "customer_id": "uuid",
  "quotation_date": "2026-01-01",
  "items": [
    {
      "product_id": "uuid",
      "quantity": 10,
      "unit_price": 100
    }
  ]
}
```

---

## Get Quotations

```http
GET /api/quotations
```

---

## Approve Quotation

```http
POST /api/quotations/{id}/approve
```

---

# Sales Order API

## Create Sales Order

```http
POST /api/sales-orders
```

---

## Get Sales Orders

```http
GET /api/sales-orders
```

---

## Sales Order Detail

```http
GET /api/sales-orders/{id}
```

---

## Cancel Sales Order

```http
POST /api/sales-orders/{id}/cancel
```

---

# Warehouse API

## Inventory List

```http
GET /api/inventory
```

---

## Inventory Detail

```http
GET /api/inventory/{product_id}
```

---

## Goods Receipt

```http
POST /api/goods-receipts
```

### Request

```json
{
  "vendor_id": "uuid",
  "warehouse_id": "uuid",
  "items": []
}
```

---

## Goods Issue

```http
POST /api/goods-issues
```

### Request

```json
{
  "sales_order_id": "uuid",
  "warehouse_id": "uuid"
}
```

---

## Inventory Count

```http
POST /api/inventory-count
```

---

# Batch Management API

## Get Batch List

```http
GET /api/batches
```

---

## Create Batch

```http
POST /api/batches
```

---

## Expiring Products

```http
GET /api/batches/expiring
```

---

# Employee API

## Get Employees

```http
GET /api/employees
```

---

## Employee Detail

```http
GET /api/employees/{id}
```

---

## Create Employee

```http
POST /api/employees
```

---

## Update Employee

```http
PUT /api/employees/{id}
```

---

# Leave Management API

## Create Leave Request

```http
POST /api/leave-requests
```

---

## Approve Leave Request

```http
POST /api/leave-requests/{id}/approve
```

---

## Leave Request List

```http
GET /api/leave-requests
```

---

# Attendance API

## Check In

```http
POST /api/attendance/check-in
```

---

## Check Out

```http
POST /api/attendance/check-out
```

---

## Attendance Report

```http
GET /api/attendance
```

---

# Finance API

## Create Invoice

```http
POST /api/invoices
```

---

## Invoice List

```http
GET /api/invoices
```

---

## Invoice Detail

```http
GET /api/invoices/{id}
```

---

## Customer Payment

```http
POST /api/payments
```

---

## Payment History

```http
GET /api/payments
```

---

# Dashboard API

## CEO Dashboard

```http
GET /api/dashboard/ceo
```

### Response

```json
{
  "revenue_today": 150000,
  "inventory_value": 250000,
  "employee_count": 45,
  "open_ar": 35000
}
```

---

## Sales Dashboard

```http
GET /api/dashboard/sales
```

---

## Warehouse Dashboard

```http
GET /api/dashboard/warehouse
```

---

## HR Dashboard

```http
GET /api/dashboard/hr
```

---

## Finance Dashboard

```http
GET /api/dashboard/finance
```

---

# API Security

## Authentication

* JWT Token

## Authorization

Role-Based Access Control (RBAC)

Roles:

* CEO
* SALES_STAFF
* SALES_MANAGER
* WH_STAFF
* WH_MANAGER
* HR_STAFF
* HR_MANAGER
* ACCOUNTANT
* SYS_ADMIN

---

# Error Response Standard

```json
{
  "success": false,
  "message": "Inventory not available",
  "error_code": "INV_001"
}
```

---

# API Summary

| Module         | API Count |
| -------------- | --------- |
| Authentication | 2         |
| Customer       | 5         |
| Product        | 4         |
| Quotation      | 3         |
| Sales Order    | 4         |
| Warehouse      | 4         |
| Batch          | 3         |
| Employee       | 4         |
| Leave          | 3         |
| Attendance     | 3         |
| Finance        | 5         |
| Dashboard      | 5         |

Total APIs: 45+

---

