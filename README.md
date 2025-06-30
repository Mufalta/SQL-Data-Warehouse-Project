# Data Warehouse Hands-on Project

Hi 👋 and welcome to the **Data Warehouse Project** repository!  
First of all, a huge thanks to **Baraa Khatib Salkini** for inspiring me to build this modern data warehouse using SQL Server. This project demonstrates how to create a modern data warehouse for data analytics purposes. It closely reflects the type of projects that data engineers work on in real-world scenarios.

---
## Table of Contents

1. [Data Architecture](#data-architecture)
---

## Data Architecture

There are a few types of methods to build a data warehouse:
1. Inmon
2. Kimball
3. Data Vault
4. Medallion Architecture
The data warehouse in this project will be built using the Medallion Architecture because it is the simplest, dividing data processing into three clear stages, **Bronze**, **Silver**, and **Gold**:
![](https://github.com/Mufalta/SQL-Data-Warehouse-Project/blob/main/images/Data-Architecture.png)

1. **Bronze Layer**: Captures unprocessed data directly from source systems. Data is loaded from CSV files into the SQL Server database.
2. **Silver Layer**: Involves cleaning, standardizing, and normalizing the data to make it suitable for analysis.
3. **Gold Layer**: Contains business-ready data structured in a star schema for reporting and analytical purposes.

---
