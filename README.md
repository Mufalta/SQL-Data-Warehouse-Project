# Data Warehouse Hands-on Project

Hi 👋 and welcome to the **Data Warehouse Project** repository!  
First of all, a huge thanks to **Baraa Khatib Salkini** for inspiring me to build this modern data warehouse using SQL Server. This project demonstrates how to create a modern data warehouse for data analytics purposes. It closely reflects the type of projects that data engineers work on in real-world scenarios.

---
## Table of Contents

1. [Data Architecture](#data-architecture)
2. [Project Overview](#project-overview)
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
