# Grocery Store Inventory Management System

## Introduction

The Inventory Management System (IMS) is a comprehensive solution designed to automate and enhance the management of various components in an organization's inventory. In today’s fast-paced commercial world, effective inventory management is crucial for optimizing expenses, minimizing errors, and improving overall performance. This system simplifies the storage, retrieval, and management of data related to different inventory components such as goods, transactions, staff, and vendors, while providing graphical data representation.

## Objective

The primary goal of the Inventory Management System is to streamline operations by automating repetitive tasks, boosting accessibility, and improving decision-making. It aims to enhance business performance by:

- Streamlining inventory procedures
- Ensuring accurate product quantity tracking
- Offering real-time insights into inventory levels, sales patterns, and supplier performance
- Processing orders promptly and accurately
- Reducing manual errors
- Improving precision and decision-making
- Elevating customer satisfaction and company profitability

## Tools

The Inventory Management System is developed using the following tools:

- **Database Management System**: Microsoft SQL Server & MySQL Workbench
- **Integrated Development Environment (IDE)**: NetBeans

## Practical Applications

The system is applicable to a wide range of businesses, including:

- **Retail Stores**: Enhances decision-making, manages product inventory, handles sales, and generates real-time reports efficiently.
- **Manufacturing Companies**: Maximizes production operations, tracks inventory for finished goods, work-in-progress, and raw materials.
- **Distributors**: Ensures prompt product replenishment, manages purchase orders, stock levels, and supplier relationships.

## Database Objects

The system utilizes various database objects, including:

### Tables

- **customer**: Stores customer details.
- **product**: Contains product information.
- **supplier**: Holds supplier details.
- **PCls**: Manages product class data.
- **inventory**: Tracks inventory quantities.
- **Employee**: Stores employee information.
- **users**: Contains user credentials.
- **sales**: Records sales transactions.
- **sales_child**: Manages detailed sales records.
- **refund**: Handles refund information.
- **PurchaseOrder**: Manages purchase orders.
- **ProdOrder**: Tracks production orders.

### View

- **purchase_history**: Provides a view of purchase history.

### Triggers

- **UpdateProductPrice**: Updates product prices.
- **CalDiff**: Calculates differences.
- **sales_child_AFTER_INSERT**: Triggered after inserting into sales_child.
- **refund_AFTER_INSERT**: Triggered after inserting into refund.
- **UpdateProductAndInventory**: Updates product and inventory data.
- **AddToInventory**: Adds items to inventory.

### Procedure

- **GetDiscount**: Retrieves discount information.

## ERD

[Include an Entity-Relationship Diagram here if available.]

## Relational Schema

### PCls
| Column        | Description            |
|---------------|------------------------|
| pcl_no        | Product class number   |
| p_date        | Date of creation       |
| created_by    | Creator                |
| date_effect   | Date of effect         |
| p_status      | Status                 |
| last_rate     | Last rate              |
| onhand_rate   | On-hand rate           |
| diff          | Difference             |
| prod_id       | Product ID             |

### supplier
| Column         | Description            |
|----------------|------------------------|
| s_id           | Supplier ID            |
| factory_name   | Factory name           |
| s_date         | Date of registration   |
| focal_person   | Contact person         |
| address        | Address                |
| bank           | Bank                   |
| branch         | Branch                 |
| account_no     | Account number         |
| contact        | Contact information    |
| s_type         | Supplier type          |
| s_status       | Supplier status        |

### customer
| Column       | Description      |
|--------------|------------------|
| cust_id      | Customer ID      |
| cust_name    | Customer name    |
| cust_phone   | Customer phone   |
| cust_type    | Customer type    |

### product
| Column        | Description      |
|---------------|------------------|
| prod_id       | Product ID       |
| prod_name     | Product name     |
| prod_price    | Product price    |
| prod_quantity | Product quantity |
| prod_group    | Product group    |

### inventory
| Column        | Description       |
|---------------|-------------------|
| prod_id       | Product ID        |
| Quantaisle    | Quantity in aisle |
| Quantstore    | Quantity in store |

### PurchaseOrder
| Column        | Description           |
|---------------|-----------------------|
| orderNo       | Order number          |
| orderDate     | Order date            |
| quantity      | Quantity              |
| costValue     | Cost value            |
| salesValue    | Sales value           |
| orderStatus   | Order status          |
| appDate       | Approval date         |
| appBy         | Approved by           |
| s_id          | Supplier ID           |
| emp_id        | Employee ID           |

### ProdOrder
| Column        | Description           |
|---------------|-----------------------|
| prod_id       | Product ID            |
| orderNo       | Order number          |

### Employee
| Column        | Description     |
|---------------|-----------------|
| emp_id        | Employee ID     |
| name          | Name            |
| dob           | Date of Birth   |
| eType         | Employee Type   |
| doj           | Date of Joining |

### users
| Column        | Description      |
|---------------|------------------|
| emp_id        | Employee ID      |
| username      | Username         |
| password      | Password         |

### sales
| Column        | Description       |
|---------------|-------------------|
| Transno       | Transaction number|
| amount        | Amount            |
| exchange      | Exchange rate     |
| discount      | Discount          |
| transType     | Transaction type  |
| postedDate    | Posted date       |
| postedBy      | Posted by         |
| paidAmount    | Paid amount       |
| cust_id       | Customer ID       |
| emp_id        | Employee ID       |

### sales_child
| Column        | Description       |
|---------------|-------------------|
| Transno       | Transaction number|
| prod_id       | Product ID        |
| quantity      | Quantity          |
| rate          | Rate             |
| entry_date    | Entry date        |
| prod_amount   | Product amount    |

### refund
| Column        | Description       |
|---------------|-------------------|
| refund_no     | Refund number     |
| quantity      | Quantity          |
| rate          | Rate             |
| date          | Date             |
| refundBy      | Refunded by       |
| Transno       | Transaction number|
| prod_id       | Product ID        |
| Transno       | Transaction number |

