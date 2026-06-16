# User Acceptance Testing (UAT)

## Project

ERP Lite SAP S/4HANA Simulation

## Objective

The purpose of User Acceptance Testing (UAT) is to validate that the ERP system supports business requirements defined during the Discovery, Requirement Gathering, and Business Blueprint phases.

The UAT phase ensures that end users can successfully execute business processes before Go-Live.

---

# UAT Scope

The following modules are included in UAT:

- Sales Management
- Warehouse Management
- Human Resource Management
- Finance Management
- Dashboard Reporting

---

# UAT Approach

Testing will be performed by business users representing each department.

| Department | Tester |
|------------|---------|
| Sales | Sales Staff |
| Warehouse | Warehouse Staff |
| HR | HR Staff |
| Finance | Accountant |
| Management | CEO |

---

# UAT Entry Criteria

Before UAT can begin:

- Business Blueprint approved
- API Design completed
- Core functionality developed
- Test environment available
- Master data loaded

---

# Test Scenario Structure

Each test scenario contains:

- Test Case ID
- Business Process
- Test Steps
- Expected Result
- Actual Result
- Status

Status Values:

- Pass
- Fail
- Blocked

---

# SALES UAT

## UAT-SAL-001

### Process

Create Customer

### Steps

1. Open Customer Screen
2. Click Create Customer
3. Enter Customer Information
4. Save

### Expected Result

Customer is successfully created.

### Status

PASS

---

## UAT-SAL-002

### Process

Create Quotation

### Steps

1. Select Customer
2. Add Product
3. Enter Quantity
4. Save Quotation

### Expected Result

Quotation number generated automatically.

### Status

PASS

---

## UAT-SAL-003

### Process

Create Sales Order

### Steps

1. Open Approved Quotation
2. Convert to Sales Order

### Expected Result

Sales Order created successfully.

### Status

PASS

---

# WAREHOUSE UAT

## UAT-WH-001

### Process

Goods Receipt

### Steps

1. Create Goods Receipt
2. Select Product
3. Enter Quantity
4. Save

### Expected Result

Inventory quantity increases.

### Status

PASS

---

## UAT-WH-002

### Process

Goods Issue

### Steps

1. Select Sales Order
2. Create Goods Issue

### Expected Result

Inventory quantity decreases.

### Status

PASS

---

## UAT-WH-003

### Process

Inventory Count

### Steps

1. Open Inventory Count
2. Enter Physical Quantity
3. Save

### Expected Result

Inventory adjustment created.

### Status

PASS

---

# HR UAT

## UAT-HR-001

### Process

Create Employee

### Steps

1. Open Employee Screen
2. Create Employee

### Expected Result

Employee record created.

### Status

PASS

---

## UAT-HR-002

### Process

Leave Request

### Steps

1. Employee submits leave request
2. Manager approves

### Expected Result

Leave balance reduced automatically.

### Status

PASS

---

## UAT-HR-003

### Process

Attendance Check-In

### Steps

1. Employee Check-In
2. Employee Check-Out

### Expected Result

Attendance record created.

### Status

PASS

---

# FINANCE UAT

## UAT-FIN-001

### Process

Create Invoice

### Steps

1. Select Sales Order
2. Generate Invoice

### Expected Result

Invoice created successfully.

### Status

PASS

---

## UAT-FIN-002

### Process

Customer Payment

### Steps

1. Select Invoice
2. Record Payment

### Expected Result

Accounts Receivable reduced.

### Status

PASS

---

## UAT-FIN-003

### Process

Cash Flow Report

### Steps

1. Open Finance Dashboard

### Expected Result

Cash Flow displayed correctly.

### Status

PASS

---

# DASHBOARD UAT

## UAT-DASH-001

### Process

CEO Dashboard

### Steps

1. Login as CEO
2. Open Dashboard

### Expected Result

Display:

- Revenue Today
- Inventory Value
- Employee Count
- Open AR
- Open AP

### Status

PASS

---

# Negative Testing

## UAT-NEG-001

### Process

Create Sales Order with Insufficient Inventory

### Expected Result

System blocks transaction.

### Status

PASS

---

## UAT-NEG-002

### Process

Approve Own Leave Request

### Expected Result

System denies approval.

### Status

PASS

---

## UAT-NEG-003

### Process

Issue Expired Product

### Expected Result

System blocks Goods Issue.

### Status

PASS

---

# UAT Summary

| Module | Test Cases |
|----------|----------|
| Sales | 3 |
| Warehouse | 3 |
| HR | 3 |
| Finance | 3 |
| Dashboard | 1 |
| Negative Test | 3 |

Total Test Cases: 16

---

# UAT Sign-Off

The business users confirm that the ERP Lite system satisfies the agreed business requirements and is ready for Go-Live preparation.

Approved By:

- Sales Manager
- Warehouse Manager
- HR Manager
- Finance Manager
- CEO

Approval Date:

YYYY-MM-DD
