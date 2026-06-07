# GAP Analysis

## Project

ERP Lite SAP S/4HANA Simulation

## Objective

Identify the gaps between the current business processes (AS-IS) and the future business processes (TO-BE), and define the ERP solutions required to bridge those gaps.

---

# GAP Classification

| Type | Description |
|--------|--------|
| Standard | Supported by ERP standard functionality |
| Configuration | Requires system configuration |
| Enhancement | Requires custom development |
| Integration | Requires integration with external systems |

---
# Sales Management

| Gap ID      | Current State (AS-IS)      | Future State (TO-BE)           | Gap                            | Solution                   | Type          |
| ----------- | -------------------------- | ------------------------------ | ------------------------------ | -------------------------- | ------------- |
| GAP-SAL-001 | Quotation created in Excel | Quotation created in ERP       | No quotation management system | Implement Quotation Module | Standard      |
| GAP-SAL-002 | Inventory checked by phone | Real-time inventory visibility | No inventory visibility        | Inventory Integration      | Standard      |
| GAP-SAL-003 | Discount approval via Zalo | Workflow approval              | No approval workflow           | Approval Workflow          | Configuration |
| GAP-SAL-004 | Order tracking manual      | Real-time order tracking       | No order status management     | Sales Order Module         | Standard      |
| GAP-SAL-005 | Multiple data entry        | One-time entry                 | Duplicate work                 | Integrated ERP Process     | Standard      |

# Warehouse Management

| Gap ID      | Current State            | Future State        | Gap                         | Solution                      | Type        |
| ----------- | ------------------------ | ------------------- | --------------------------- | ----------------------------- | ----------- |
| GAP-INV-001 | Inventory in Excel       | Real-time inventory | No inventory system         | Inventory Module              | Standard    |
| GAP-INV-002 | Manual batch tracking    | Batch management    | No traceability             | Batch Management              | Standard    |
| GAP-INV-003 | Manual expiry tracking   | Expiry monitoring   | No expiry control           | Expiry Management             | Standard    |
| GAP-INV-004 | Inventory count on paper | ERP inventory count | Manual process              | Inventory Count Function      | Standard    |
| GAP-INV-005 | No warehouse locations   | Bin management      | Poor warehouse organization | Warehouse Location Management | Enhancement |

# HR Management

| Gap ID     | Current State                  | Future State           | Gap                              | Solution                   | Type        |
| ---------- | ------------------------------ | ---------------------- | -------------------------------- | -------------------------- | ----------- |
| GAP-HR-001 | Employee data in Excel         | Employee Master        | No centralized employee database | Employee Management Module | Standard    |
| GAP-HR-002 | Leave requests via Zalo        | Leave Workflow         | No leave management process      | Leave Request Workflow     | Standard    |
| GAP-HR-003 | Attendance maintained manually | Attendance integration | No attendance integration        | Attendance Interface       | Integration |
| GAP-HR-004 | Manual HR reporting            | HR Dashboard           | No HR analytics                  | Dashboard Module           | Standard    |

# FINANCE Management

| Gap ID      | Current State                 | Future State               | Gap                    | Solution                | Type        |
| ----------- | ----------------------------- | -------------------------- | ---------------------- | ----------------------- | ----------- |
| GAP-FIN-001 | AR tracked manually           | Real-time AR visibility    | No AR management       | AR Module               | Standard    |
| GAP-FIN-002 | AP tracked manually           | Real-time AP visibility    | No AP management       | AP Module               | Standard    |
| GAP-FIN-003 | Cash flow in Excel            | Real-time cash flow        | No cash flow dashboard | Finance Dashboard       | Standard    |
| GAP-FIN-004 | MISA isolated from operations | Integrated finance process | No integration         | ERP Finance Integration | Integration |

# GAP Summary

| Module    | Gap Count |
| --------- | --------- |
| Sales     | 5         |
| Warehouse | 5         |
| HR        | 4         |
| Finance   | 4         |
| Total     | 18        |

# Development Prioritization
# Phase 1 (Must Have)
Sales
- Quotation
- Sales Order
- Customer Management
Warehouse
- Inventory Management
- Goods Receipt
- Goods Issue
HR
- Employee Management
- Leave Request
Finance
- AR
- AP
# Phase 2 (Should Have)
- Batch Management
- Expiry Tracking
- Dashboard Reporting
# Phase 3 (Could Have)
- Attendance Integration
- Bin Location Management
- AI Reporting
# Conclusion

A total of 18 business gaps were identified between the current state and future state processes.

Most gaps can be addressed through standard ERP functionality, while a small number require integration or custom enhancements.

The GAP Analysis will serve as the foundation for the Business Blueprint and Solution Design phases.


