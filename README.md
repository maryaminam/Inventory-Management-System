# Grocery Store Inventory Management System

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Java](https://img.shields.io/badge/Java-v8+-orange.svg)](https://www.java.com/)
[![Database](https://img.shields.io/badge/Database-SQL%20Server%20%26%20MySQL-blue.svg)](#tools)

---

## 📋 Table of Contents

- [Introduction](#introduction)
- [Key Objectives](#key-objectives)
- [System Features](#system-features)
- [Technology Stack](#technology-stack)
- [Use Cases](#use-cases)
- [User Interface](#user-interface)
- [Database Architecture](#database-architecture)
- [Installation & Setup](#installation--setup)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction

The **Inventory Management System (IMS)** is a comprehensive enterprise solution designed to automate and optimize inventory operations across various organizational units. This robust system addresses the critical challenges of modern supply chain management by providing real-time visibility, automated workflows, and data-driven insights.

The IMS streamlines complex inventory operations, reduces operational overhead, and enables organizations to make informed business decisions quickly and accurately.

---

## Key Objectives

The Inventory Management System is built to achieve the following strategic goals:

- ✅ **Operational Efficiency**: Streamline inventory procedures and automate repetitive manual tasks
- ✅ **Accuracy**: Ensure precise product quantity tracking and reduce manual errors
- ✅ **Real-Time Intelligence**: Provide actionable insights into inventory levels, sales patterns, and supplier performance
- ✅ **Speed & Reliability**: Process orders promptly and accurately
- ✅ **Decision Support**: Improve decision-making capabilities with comprehensive reporting
- ✅ **Customer Satisfaction**: Enhance service quality and overall business profitability

---

## System Features

### Core Functionalities

- **Inventory Tracking**: Real-time monitoring of stock levels across multiple locations
- **Sales Management**: Complete transaction processing with detailed sales records
- **Purchase Order Management**: Automated purchase order creation and tracking
- **Supplier Management**: Comprehensive supplier relationship and performance management
- **Customer Database**: Centralized customer information and history
- **Refund Processing**: Streamlined refund management with automated inventory adjustments
- **Production Order Tracking**: Monitor work-in-progress and production orders
- **Automated Triggers**: Business logic automation through database triggers
- **Discount Management**: Flexible discount policies and calculations
- **Reporting & Analytics**: Purchase history and performance analytics

---

## Technology Stack

| Component | Technology |
|-----------|-----------|
| **IDE** | NetBeans |
| **Primary Database** | Microsoft SQL Server |
| **Secondary Database** | MySQL Workbench |
| **Language** | Java |
| **Architecture** | Client-Server |

---

## Use Cases

### 🏬 Retail Stores
- Enhanced inventory decision-making
- Product stock management and tracking
- Sales transaction processing
- Real-time reporting and performance analytics

### 🏭 Manufacturing Companies
- Production operation optimization
- Multi-level inventory tracking (raw materials, work-in-progress, finished goods)
- Supply chain coordination
- Production order management

### 🚚 Distributors
- Prompt product replenishment management
- Purchase order automation
- Stock level optimization
- Supplier relationship management and performance tracking

---

## User Interface

### System Screenshots

#### Dashboard & Overview
> *Primary dashboard screenshot here*
```
[Screenshot placeholder: Dashboard]
```

#### Inventory Management
> *Inventory tracking interface*
```
[Screenshot placeholder: Inventory Management Module]
```

#### Sales Transaction Processing
> *Sales entry and processing interface*
```
[Screenshot placeholder: Sales Module]
```

#### Purchase Order Management
> *Purchase order creation and tracking*
```
[Screenshot placeholder: Purchase Order Module]
```

#### Supplier Management
> *Supplier database and management interface*
```
[Screenshot placeholder: Supplier Management Module]
```

#### Refund Processing
> *Refund transaction processing*
```
[Screenshot placeholder: Refund Module]
```

#### Reports & Analytics
> *System reporting and analytics interface*
```
[Screenshot placeholder: Reports & Analytics Module]
```

---

## Database Architecture

### Entity Relationship Overview

The system implements a comprehensive relational database design with the following components:

#### Core Tables

| Table | Purpose |
|-------|---------|
| **customer** | Customer profile and contact information |
| **product** | Product catalog with pricing and classifications |
| **supplier** | Supplier details and banking information |
| **inventory** | Real-time stock quantity tracking |
| **employee** | Employee records and department information |
| **users** | User authentication credentials |
| **sales** | Sales transaction headers |
| **sales_child** | Detailed line items for sales transactions |
| **PurchaseOrder** | Purchase order records and status tracking |
| **ProdOrder** | Production order tracking |
| **refund** | Refund transaction records |
| **PCls** | Product classification and rate tracking |

#### Database Views

| View | Description |
|------|-------------|
| **purchase_history** | Historical purchase data for analytics and reporting |

#### Automated Triggers

| Trigger | Functionality |
|---------|---------------|
| **UpdateProductPrice** | Automatically updates product pricing |
| **CalDiff** | Calculates inventory discrepancies |
| **sales_child_AFTER_INSERT** | Triggers inventory updates on sales entry |
| **refund_AFTER_INSERT** | Processes inventory adjustments for refunds |
| **UpdateProductAndInventory** | Synchronizes product and inventory data |
| **AddToInventory** | Manages inventory additions |

#### Stored Procedures

| Procedure | Function |
|-----------|----------|
| **GetDiscount** | Retrieves and calculates applicable discounts |

---

### Detailed Schema

#### Product Classification (PCls)
| Column | Type | Description |
|--------|------|-------------|
| pcl_no | INT | Product class unique identifier |
| p_date | DATE | Creation date |
| created_by | VARCHAR | Creator identifier |
| date_effect | DATE | Effective date |
| p_status | VARCHAR | Status flag |
| last_rate | DECIMAL | Previous rate value |
| onhand_rate | DECIMAL | Current rate value |
| diff | DECIMAL | Rate difference |
| prod_id | INT | Product reference |

#### Supplier
| Column | Type | Description |
|--------|------|-------------|
| s_id | INT | Supplier unique identifier |
| factory_name | VARCHAR | Supplier business name |
| s_date | DATE | Registration date |
| focal_person | VARCHAR | Primary contact person |
| address | VARCHAR | Business address |
| bank | VARCHAR | Bank name |
| branch | VARCHAR | Bank branch |
| account_no | VARCHAR | Bank account number |
| contact | VARCHAR | Contact information |
| s_type | VARCHAR | Supplier category |
| s_status | VARCHAR | Active/Inactive status |

#### Customer
| Column | Type | Description |
|--------|------|-------------|
| cust_id | INT | Customer unique identifier |
| cust_name | VARCHAR | Customer name |
| cust_phone | VARCHAR | Contact phone number |
| cust_type | VARCHAR | Customer category |

#### Product
| Column | Type | Description |
|--------|------|-------------|
| prod_id | INT | Product unique identifier |
| prod_name | VARCHAR | Product name |
| prod_price | DECIMAL | Current selling price |
| prod_quantity | INT | Total quantity available |
| prod_group | VARCHAR | Product category/group |

#### Inventory
| Column | Type | Description |
|--------|------|-------------|
| prod_id | INT | Product reference |
| Quantaisle | INT | Quantity on retail aisle |
| Quantstore | INT | Quantity in storage |

#### Purchase Order
| Column | Type | Description |
|--------|------|-------------|
| orderNo | INT | Order unique identifier |
| orderDate | DATE | Order creation date |
| quantity | INT | Order quantity |
| costValue | DECIMAL | Cost value |
| salesValue | DECIMAL | Sales value |
| orderStatus | VARCHAR | Current order status |
| appDate | DATE | Approval date |
| appBy | VARCHAR | Approved by (user) |
| s_id | INT | Supplier reference |
| emp_id | INT | Employee reference |

#### Production Order
| Column | Type | Description |
|--------|------|-------------|
| prod_id | INT | Product reference |
| orderNo | INT | Order reference |

#### Employee
| Column | Type | Description |
|--------|------|-------------|
| emp_id | INT | Employee unique identifier |
| name | VARCHAR | Full name |
| dob | DATE | Date of birth |
| eType | VARCHAR | Employment type |
| doj | DATE | Date of joining |

#### User Credentials
| Column | Type | Description |
|--------|------|-------------|
| emp_id | INT | Employee reference |
| username | VARCHAR | Login username |
| password | VARCHAR | Encrypted password |

#### Sales Transaction
| Column | Type | Description |
|--------|------|-------------|
| Transno | INT | Transaction unique identifier |
| amount | DECIMAL | Total transaction amount |
| exchange | DECIMAL | Exchange rate applied |
| discount | DECIMAL | Discount amount |
| transType | VARCHAR | Transaction type |
| postedDate | DATE | Transaction date |
| postedBy | VARCHAR | Posting user |
| paidAmount | DECIMAL | Amount paid |
| cust_id | INT | Customer reference |
| emp_id | INT | Employee reference |

#### Sales Line Item
| Column | Type | Description |
|--------|------|-------------|
| Transno | INT | Transaction reference |
| prod_id | INT | Product reference |
| quantity | INT | Item quantity |
| rate | DECIMAL | Unit rate |
| entry_date | DATE | Entry date |
| prod_amount | DECIMAL | Line item total |

#### Refund Transaction
| Column | Type | Description |
|--------|------|-------------|
| refund_no | INT | Refund unique identifier |
| quantity | INT | Refunded quantity |
| rate | DECIMAL | Refund rate |
| date | DATE | Refund date |
| refundBy | VARCHAR | Processed by user |
| Transno | INT | Original transaction reference |
| prod_id | INT | Product reference |

---

## Installation & Setup

### Prerequisites

- Java Development Kit (JDK) 8 or higher
- NetBeans IDE
- Microsoft SQL Server OR MySQL Server
- Network connectivity to database server

### Database Setup

1. **For SQL Server:**
   ```sql
   CREATE DATABASE InventoryManagement
   -- Run provided SQL scripts to create tables, views, and triggers
   ```

2. **For MySQL:**
   ```sql
   CREATE DATABASE inventory_management;
   -- Run provided SQL scripts to create tables, views, and triggers
   ```

### Application Setup

1. Open NetBeans IDE
2. Import the project
3. Configure database connection strings
4. Build and run the application
5. Log in with administrator credentials

---

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add YourFeature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Submit a Pull Request

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## Support & Contact

For questions, issues, or suggestions, please contact the development team or submit an issue through GitHub.

---

**Last Updated**: June 2026  
**Version**: 1.0.0
