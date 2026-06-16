# Business Blueprint

## Project Information

### Project Name

ERP Lite SAP S/4HANA Simulation

### Project Type

Greenfield ERP Implementation

### Industry

Consumer Goods Distribution

### Methodology

SAP Activate Inspired Methodology

### Document Owner

SAP Functional Consultant

---

# 1. Executive Summary

This Business Blueprint document defines the future-state ERP solution for Minh Phat Distribution.

The objective is to replace disconnected tools such as Excel, Zalo, and manual processes with an integrated ERP platform covering:

* Sales Management
* Warehouse Management
* Human Resource Management
* Finance Management
* Management Reporting

The blueprint serves as the foundation for system design, database design, API development, testing, and deployment.

---

# 2. Business Scope

## In Scope

### Sales Management

* Customer Master
* Quotation
* Sales Order
* Delivery
* Invoice

### Warehouse Management

* Goods Receipt
* Goods Issue
* Inventory Transfer
* Inventory Count
* Batch Management
* Expiry Date Management

### Human Resource Management

* Employee Master
* Leave Request
* Leave Approval
* Attendance Tracking

### Finance Management

* Accounts Receivable
* Accounts Payable
* Payment Management
* Cash Flow Monitoring

### Reporting

* CEO Dashboard
* Sales Dashboard
* Warehouse Dashboard
* HR Dashboard
* Finance Dashboard

---

## Out of Scope

* Production Planning
* Manufacturing Execution
* Payroll Calculation
* Asset Management
* Mobile Application
* E-Commerce Integration

---

# 3. Organization Structure

## Company

Minh Phat Distribution

### Branches

| Branch Code | Branch Name |
| ----------- | ----------- |
| DN          | Da Nang     |
| HCM         | Ho Chi Minh |

### Warehouses

| Warehouse Code | Warehouse Name        |
| -------------- | --------------------- |
| DN-WH01        | Da Nang Warehouse     |
| HCM-WH01       | Ho Chi Minh Warehouse |

### Departments

| Department Code | Department      |
| --------------- | --------------- |
| SALE            | Sales           |
| WH              | Warehouse       |
| HR              | Human Resources |
| ACC             | Accounting      |
| MGMT            | Management      |

---

# 4. Master Data Blueprint

## Customer Master

### Purpose

Store all customer information used throughout the sales process.

### Data Fields

| Field         | Mandatory |
| ------------- | --------- |
| Customer Code | Yes       |
| Customer Name | Yes       |
| Tax Code      | Yes       |
| Address       | Yes       |
| Phone Number  | Yes       |
| Email         | No        |
| Credit Limit  | Yes       |
| Payment Terms | Yes       |
| Status        | Yes       |

---

## Product Master

### Purpose

Maintain all products sold and managed in inventory.

### Data Fields

| Field            | Mandatory |
| ---------------- | --------- |
| Product Code     | Yes       |
| Product Name     | Yes       |
| Product Category | Yes       |
| Unit of Measure  | Yes       |
| Standard Cost    | Yes       |
| Selling Price    | Yes       |
| Batch Managed    | Yes       |
| Expiry Managed   | Yes       |
| Status           | Yes       |

---

## Employee Master

### Purpose

Maintain employee information for HR operations.

### Data Fields

| Field         | Mandatory |
| ------------- | --------- |
| Employee ID   | Yes       |
| Employee Name | Yes       |
| Department    | Yes       |
| Position      | Yes       |
| Join Date     | Yes       |
| Email         | No        |
| Phone Number  | No        |
| Status        | Yes       |

---

## Vendor Master

### Purpose

Maintain supplier information.

### Data Fields

| Field          | Mandatory |
| -------------- | --------- |
| Vendor Code    | Yes       |
| Vendor Name    | Yes       |
| Tax Code       | Yes       |
| Contact Person | No        |
| Payment Terms  | Yes       |
| Status         | Yes       |

---

# 5. Sales Process Blueprint

## Business Process Flow

Customer Inquiry

↓

Quotation

↓

Sales Order

↓

Delivery

↓

Invoice

↓

Customer Payment

---

## Sales Documents

| Document    |
| ----------- |
| Quotation   |
| Sales Order |
| Delivery    |
| Invoice     |

---

## Business Rules

### Rule SAL-001

Discount ≤ 10%

→ Sales can approve

### Rule SAL-002

Discount > 10%

→ Manager approval required

### Rule SAL-003

Customer exceeds credit limit

→ Sales Order blocked

### Rule SAL-004

Inventory unavailable

→ Sales Order cannot proceed

---

# 6. Warehouse Process Blueprint

## Business Process Flow

Goods Receipt

↓

Put Away

↓

Inventory Storage

↓

Goods Issue

↓

Inventory Count

---

## Warehouse Documents

| Document             |
| -------------------- |
| Goods Receipt        |
| Goods Issue          |
| Inventory Adjustment |
| Stock Count          |

---

## Business Rules

### Rule INV-001

Stock cannot be issued if inventory is insufficient.

### Rule INV-002

Batch-managed products require batch assignment.

### Rule INV-003

Expired products cannot be shipped.

### Rule INV-004

Inventory adjustments require approval.

---

# 7. Human Resource Blueprint

## Business Process Flow

Employee Creation

↓

Attendance Recording

↓

Leave Request

↓

Manager Approval

↓

Leave Balance Update

---

## HR Documents

| Document          |
| ----------------- |
| Employee Profile  |
| Leave Request     |
| Attendance Record |

---

## Business Rules

### Rule HR-001

Employees must submit leave requests before absence.

### Rule HR-002

Managers approve leave requests.

### Rule HR-003

Approved leave automatically reduces leave balance.

---

# 8. Finance Blueprint

## Business Process Flow

Invoice Creation

↓

AR/AP Update

↓

Payment Processing

↓

Cash Flow Update

↓

Financial Reporting

---

## Finance Documents

| Document         |
| ---------------- |
| Customer Invoice |
| Vendor Invoice   |
| Receipt Voucher  |
| Payment Voucher  |

---

## Business Rules

### Rule FIN-001

Customer payments automatically update Accounts Receivable.

### Rule FIN-002

Vendor payments automatically update Accounts Payable.

### Rule FIN-003

Cash Flow Dashboard updates in real time.

---

# 9. Workflow Blueprint

## Sales Approval Workflow

Sales

↓

Create Quotation

↓

Discount > 10%

↓

Manager Approval

↓

Customer Submission

---

## Leave Approval Workflow

Employee

↓

Leave Request

↓

Manager Approval

↓

HR Notification

↓

Leave Balance Update

---

## Inventory Adjustment Workflow

Warehouse

↓

Inventory Adjustment Request

↓

Warehouse Manager Approval

↓

Inventory Updated

---

# 10. Reporting Blueprint

## CEO Dashboard

### KPIs

* Revenue Today
* Revenue MTD
* Inventory Value
* Employee Count
* Open Receivables
* Open Payables

---

## Sales Dashboard

### KPIs

* Revenue
* Orders Today
* Top Customers
* Open Quotations

---

## Warehouse Dashboard

### KPIs

* Current Stock
* Low Stock Items
* Inventory Value
* Expiring Products

---

## HR Dashboard

### KPIs

* Employee Count
* Attendance Rate
* Leave Requests

---

## Finance Dashboard

### KPIs

* AR Balance
* AP Balance
* Cash Flow
* Monthly Revenue

---

# 11. Integration Blueprint

| Source Module | Target Module | Purpose                |
| ------------- | ------------- | ---------------------- |
| Sales         | Warehouse     | Inventory Availability |
| Sales         | Finance       | Invoice Generation     |
| Warehouse     | Finance       | Inventory Valuation    |
| HR            | Dashboard     | Workforce Reporting    |
| Finance       | Dashboard     | Financial Reporting    |

---

# 12. Security & Authorization Concept

| Role                 | Access                        |
| -------------------- | ----------------------------- |
| CEO                  | View All Dashboards           |
| Sales Staff          | Create Quotation, Sales Order |
| Sales Manager        | Approve Discounts             |
| Warehouse Staff      | Goods Receipt, Goods Issue    |
| Warehouse Manager    | Inventory Adjustment Approval |
| HR Staff             | Employee Management           |
| HR Manager           | Leave Approval                |
| Accountant           | AR/AP Management              |
| System Administrator | Full Access                   |

---

# 13. Success Criteria

The ERP implementation will be considered successful when:

* Inventory information is available in real time.
* Sales orders are processed without duplicate entry.
* Leave requests are fully digital.
* Financial information is available on demand.
* Management dashboards provide real-time visibility.
* Inventory accuracy exceeds 98%.

---

# 14. Blueprint Approval

This document serves as the approved Business Blueprint for the ERP Lite SAP S/4HANA Simulation project and will be used as the foundation for:

* Role Matrix Design
* Database Design (ERD)
* API Design
* UI/UX Design
* UAT Preparation
* Go-Live Planning
