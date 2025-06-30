# Data Warehouse Hands-on Project

Hi 👋 and welcome to the **Data Warehouse Project** repository!  
First of all, a huge thanks to **Baraa Khatib Salkini** for inspiring me to build this modern data warehouse using SQL Server. This project demonstrates how to create a modern data warehouse for data analytics purposes. It closely reflects the type of projects that data engineers work on in real-world scenarios.

---
## Table of Contents

1. [Project Overview](#project-overview)
2. [Data Architecture](#data-architecture)
3. [General Principles](#general-principles)
4. [Table Naming Conventions](#table-naming-conventions)
   - [Bronze Rules](#bronze-rules)
   - [Silver Rules](#silver-rules)
   - [Gold Rules](#gold-rules)
5. [Column Naming Conventions](#column-naming-conventions)
   - [Surrogate Keys](#surrogate-keys)
   - [Technical Columns](#technical-columns)
6. [Stored Procedure](#stored-procedure-naming-conventions)
---

## Project Overview

This project involves:
1. **Data Architecture**: Building a modern data warehouse using the Medallion Architecture, which organizes data into Bronze, Silver, and Gold layers.  
2. **ETL Pipelines**: Moving data from source systems into the warehouse through extraction, transformation, and loading processes.  
3. **Data Modeling**: Creating fact and dimension tables structured for efficient analytical querying.  
---

## Data Architecture

There are a few types of methods to build a data warehouse:  
- Inmon  
- Kimball  
- Data Vault  
- **Medallion Architecture**

The data warehouse in this project will be built using the Medallion Architecture because it is the simplest, dividing data processing into three clear stages, **Bronze**, **Silver**, and **Gold**:
![](https://github.com/Mufalta/SQL-Data-Warehouse-Project/blob/main/images/Data-Architecture.png)

1. **Bronze Layer**: Captures unprocessed data directly from source systems. Data is loaded from CSV files into the SQL Server database.  
2. **Silver Layer**: Involves cleaning, standardizing, and normalizing the data to make it suitable for analysis.  
3. **Gold Layer**: Contains business-ready data structured in a star schema for reporting and analytical purposes.  

---

## **General Principles**

- **Naming Conventions**: Use snake_case, with lowercase letters and underscores (`_`) to separate words.
- **Language**: Use English for all names.
- **Avoid Reserved Words**: Do not use SQL reserved words as object names.

## **Table Naming Conventions**

### **Bronze Rules**
- All names must start with the source system name, and table names must match their original names without renaming.
- **`<sourcesystem>_<entity>`**  
  - `<sourcesystem>`: Name of the source system (e.g., `crm`, `erp`).  
  - `<entity>`: Exact table name from the source system.  
  - Example: `crm_customer_info` → Customer information from the CRM system.

### **Silver Rules**
- All names must start with the source system name, and table names must match their original names without renaming.
- **`<sourcesystem>_<entity>`**  
  - `<sourcesystem>`: Name of the source system (e.g., `crm`, `erp`).  
  - `<entity>`: Exact table name from the source system.  
  - Example: `crm_customer_info` → Customer information from the CRM system.

### **Gold Rules**
- All names must use meaningful, business-aligned names for tables, starting with the category prefix.
- **`<category>_<entity>`**  
  - `<category>`: Describes the role of the table, such as `dim` (dimension) or `fact` (fact table).  
  - `<entity>`: Descriptive name of the table, aligned with the business domain (e.g., `customers`, `products`, `sales`).  
  - Examples:
    - `dim_customers` → Dimension table for customer data.  
    - `fact_sales` → Fact table containing sales transactions.  

#### **Glossary of Category Patterns**

| Pattern     | Meaning                           | Example(s)                              |
|-------------|-----------------------------------|-----------------------------------------|
| `dim_`      | Dimension table                  | `dim_customer`, `dim_product`           |
| `fact_`     | Fact table                       | `fact_sales`                            |
| `report_`   | Report table                     | `report_customers`, `report_sales_monthly`   |

## **Column Naming Conventions**

### **Surrogate Keys**  
- All primary keys in dimension tables must use the suffix `_key`.
- **`<table_name>_key`**  
  - `<table_name>`: Refers to the name of the table or entity the key belongs to.  
  - `_key`: A suffix indicating that this column is a surrogate key.  
  - Example: `customer_key` → Surrogate key in the `dim_customers` table.
  
### **Technical Columns**
- All technical columns must start with the prefix `dwh_`, followed by a descriptive name indicating the column's purpose.
- **`dwh_<column_name>`**  
  - `dwh`: Prefix exclusively for system-generated metadata.  
  - `<column_name>`: Descriptive name indicating the column's purpose.  
  - Example: `dwh_load_date` → System-generated column used to store the date when the record was loaded.
 
## **Stored Procedure**

- All stored procedures used for loading data must follow the naming pattern:
- **`load_<layer>`**.
  
  - `<layer>`: Represents the layer being loaded, such as `bronze`, `silver`, or `gold`.
  - Example: 
    - `load_bronze` → Stored procedure for loading data into the Bronze layer.
    - `load_silver` → Stored procedure for loading data into the Silver layer.
