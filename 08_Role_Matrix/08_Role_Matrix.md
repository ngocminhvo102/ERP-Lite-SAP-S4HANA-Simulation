# Role Matrix

## Project

ERP Lite SAP S/4HANA Simulation

## Objective

Define user roles, responsibilities, and system access permissions for all ERP modules.

This document serves as the foundation for user authorization design and access control management.

---

# Role Overview

| Role ID       | Role Name               |
| ------------- | ----------------------- |
| CEO           | Chief Executive Officer |
| SALES_STAFF   | Sales Staff             |
| SALES_MANAGER | Sales Manager           |
| WH_STAFF      | Warehouse Staff         |
| WH_MANAGER    | Warehouse Manager       |
| HR_STAFF      | HR Staff                |
| HR_MANAGER    | HR Manager              |
| ACCOUNTANT    | Accountant              |
| SYS_ADMIN     | System Administrator    |

---

# Sales Module Authorization

| Function              | Sales Staff | Sales Manager | CEO |
| --------------------- | ----------- | ------------- | --- |
| View Customer         | ✓           | ✓             | ✓   |
| Create Customer       | ✓           | ✓             |     |
| Edit Customer         | ✓           | ✓             |     |
| Create Quotation      | ✓           | ✓             |     |
| Edit Quotation        | ✓           | ✓             |     |
| Approve Discount >10% |             | ✓             |     |
| Create Sales Order    | ✓           | ✓             |     |
| Cancel Sales Order    |             | ✓             |     |
| View Sales Dashboard  | ✓           | ✓             | ✓   |

---

# Warehouse Module Authorization

| Function                 | WH Staff | WH Manager | CEO |
| ------------------------ | -------- | ---------- | --- |
| View Inventory           | ✓        | ✓          | ✓   |
| Goods Receipt            | ✓        | ✓          |     |
| Goods Issue              | ✓        | ✓          |     |
| Inventory Count          | ✓        | ✓          |     |
| Inventory Adjustment     |          | ✓          |     |
| Approve Adjustment       |          | ✓          |     |
| View Warehouse Dashboard | ✓        | ✓          | ✓   |

---

# HR Module Authorization

| Function              | Employee | HR Staff | HR Manager | CEO |
| --------------------- | -------- | -------- | ---------- | --- |
| View Own Profile      | ✓        | ✓        | ✓          |     |
| Update Own Profile    | ✓        | ✓        | ✓          |     |
| Create Employee       |          | ✓        | ✓          |     |
| Edit Employee         |          | ✓        | ✓          |     |
| Create Leave Request  | ✓        | ✓        | ✓          |     |
| Approve Leave Request |          |          | ✓          |     |
| View HR Dashboard     |          | ✓        | ✓          | ✓   |

---

# Finance Module Authorization

| Function                | Accountant | CEO |
| ----------------------- | ---------- | --- |
| Create AR Invoice       | ✓          |     |
| Create AP Invoice       | ✓          |     |
| Record Customer Payment | ✓          |     |
| Record Vendor Payment   | ✓          |     |
| View Finance Dashboard  | ✓          | ✓   |
| View Cash Flow          | ✓          | ✓   |
| View AR Aging Report    | ✓          | ✓   |
| View AP Aging Report    | ✓          | ✓   |

---

# Dashboard Access Matrix

| Dashboard           | CEO | Sales Manager | WH Manager | HR Manager | Accountant |
| ------------------- | --- | ------------- | ---------- | ---------- | ---------- |
| CEO Dashboard       | ✓   |               |            |            |            |
| Sales Dashboard     | ✓   | ✓             |            |            |            |
| Warehouse Dashboard | ✓   |               | ✓          |            |            |
| HR Dashboard        | ✓   |               |            | ✓          |            |
| Finance Dashboard   | ✓   |               |            |            | ✓          |

---

# Approval Matrix

## Sales Discount Approval

| Discount Level | Approver      |
| -------------- | ------------- |
| ≤ 10%          | Sales Staff   |
| > 10%          | Sales Manager |
| > 20%          | CEO           |

---

## Leave Approval

| Leave Type   | Approver   |
| ------------ | ---------- |
| Annual Leave | HR Manager |
| Sick Leave   | HR Manager |
| Unpaid Leave | CEO        |

---

## Inventory Adjustment Approval

| Adjustment Value      | Approver          |
| --------------------- | ----------------- |
| < 5% Stock Difference | Warehouse Manager |
| ≥ 5% Stock Difference | CEO               |

---

# Segregation of Duties (SoD)

To reduce fraud and operational risks:

## Sales

* User creating quotation cannot approve high-value discounts.

## Warehouse

* User performing inventory count cannot approve inventory adjustments.

## Finance

* User creating vendor invoices cannot approve vendor payments.

## HR

* Employee cannot approve their own leave request.

---

# System Administrator

## Responsibilities

* User creation
* Role assignment
* Password reset
* System configuration
* Audit log monitoring

---

# Role Summary

| Role                 | Main Responsibility                       |
| -------------------- | ----------------------------------------- |
| CEO                  | Strategic oversight and KPI monitoring    |
| Sales Staff          | Customer and sales transaction processing |
| Sales Manager        | Sales approval and performance monitoring |
| Warehouse Staff      | Inventory operations                      |
| Warehouse Manager    | Inventory control and approval            |
| HR Staff             | Employee administration                   |
| HR Manager           | Workforce management and approval         |
| Accountant           | Financial transaction processing          |
| System Administrator | ERP administration                        |

---

# Authorization Design Principles

1. Least Privilege Principle

   * Users receive only the permissions required for their job.

2. Segregation of Duties

   * Critical activities require separation of responsibilities.

3. Approval Control

   * High-risk transactions require management approval.

4. Auditability

   * All critical actions are logged and traceable.

---

# Approval

This Role Matrix document defines the user authorization framework for ERP Lite and will be used as the basis for system security configuration and access control design.

