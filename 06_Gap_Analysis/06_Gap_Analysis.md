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

# Warehouse Management
