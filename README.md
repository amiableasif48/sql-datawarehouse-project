# 📊 SQL Server Data Warehouse Project using Medallion Architecture

## 📖 Overview

This project demonstrates the implementation of a modern **Data Warehouse** using **Microsoft SQL Server** and the **Medallion Architecture**. The objective is to transform raw operational data into clean, reliable, and business-ready datasets for reporting and analytics.

The project follows industry best practices by organizing data into **Bronze**, **Silver**, and **Gold** layers, allowing scalable data ingestion, transformation, and analytical reporting.

---

## 🏗️ Architecture

```
                +--------------------+
                |   Source Systems   |
                +---------+----------+
                          |
                          ▼
                +--------------------+
                |   Bronze Layer     |
                |  (Raw Data)        |
                +---------+----------+
                          |
                          ▼
                +--------------------+
                |   Silver Layer     |
                | Cleansed &         |
                | Standardized Data  |
                +---------+----------+
                          |
                          ▼
                +--------------------+
                |    Gold Layer      |
                | Business Ready     |
                | Fact & Dimension   |
                +---------+----------+
                          |
                          ▼
                Dashboards / Reports / BI
```

---

# 📂 Project Structure

```
SQL-DataWarehouse/
│
├── Bronze/
│   ├── Create Tables.sql
│   ├── Load Raw Data.sql
│   └── Stored Procedures.sql
│
├── Silver/
│   ├── Data Cleaning.sql
│   ├── Data Transformation.sql
│   └── Data Validation.sql
│
├── Gold/
│   ├── Dimension Tables.sql
│   ├── Fact Tables.sql
│   ├── Views.sql
│   └── Analytical Queries.sql
│
├── Documentation/
│   ├── Data Model.png
│   ├── ER Diagram.png
│   └── Architecture.png
│
└── README.md
```

---

# 🥉 Bronze Layer

The Bronze layer stores data exactly as received from the source systems.

### Objectives

* Store raw source data
* Preserve historical records
* Enable auditability
* Minimal or no transformations

### Characteristics

* Raw data ingestion
* Source-specific schema
* No business rules applied
* Used as the landing zone

---

# 🥈 Silver Layer

The Silver layer transforms raw data into clean, consistent, and validated datasets.

### Transformations

* Remove duplicates
* Handle NULL values
* Standardize formats
* Clean inconsistent values
* Data type conversions
* Apply business rules
* Generate surrogate keys
* Data quality validation

### Objectives

* Improve data quality
* Create trusted datasets
* Prepare data for dimensional modeling

---

# 🥇 Gold Layer

The Gold layer contains business-ready data optimized for reporting and analytics.

It follows the **Kimball Dimensional Modeling** approach.

### Objects

### Fact Tables

* FactInternetSales
* FactResellerSales
* FactProductInventory

### Dimension Tables

* DimCustomer
* DimProduct
* DimDate
* DimSalesTerritory
* DimEmployee
* DimPromotion

---

# ⭐ Star Schema

```
                 DimCustomer
                      |
DimDate ---- FactInternetSales ---- DimProduct
                      |
              DimSalesTerritory
```

The Star Schema enables:

* Fast analytical queries
* Simple joins
* Better reporting performance
* Easy integration with BI tools

---

# ⚙️ ETL Process

## Extract

* Import data from operational databases
* Load source files into Bronze layer

## Transform

* Clean invalid records
* Remove duplicates
* Apply business rules
* Generate surrogate keys
* Standardize formats

## Load

* Populate dimension tables
* Populate fact tables
* Build analytical views

---

# 📈 Analytics

The Gold layer supports analytical queries such as:

* Total Sales by Year
* Sales by Product Category
* Top Selling Products
* Customer Purchase Trends
* Regional Sales Analysis
* Running Totals
* Year-over-Year Growth
* Product Contribution Analysis
* Customer Lifetime Value (CLV)

---

# 🛠️ Technologies Used

| Technology                          | Purpose               |
| ----------------------------------- | --------------------- |
| SQL Server                          | Database Engine       |
| T-SQL                               | Data Transformation   |
| SQL Server Management Studio (SSMS) | Development           |
| AdventureWorksDW2022                | Sample Data Warehouse |
| Git & GitHub                        | Version Control       |

---

# 🚀 Key Features

* Medallion Architecture
* Layered Data Processing
* ETL Pipelines
* Data Cleaning
* Data Validation
* Dimensional Modeling
* Star Schema
* Fact & Dimension Tables
* Window Functions
* Common Table Expressions (CTEs)
* Aggregate Functions
* Analytical SQL Queries
* Business Intelligence Ready

---

# 📊 SQL Concepts Demonstrated

* Joins
* CTEs
* Window Functions
* Ranking Functions
* Running Totals
* Aggregate Functions
* CASE Expressions
* Pivoting
* GROUP BY
* HAVING
* Subqueries
* Views
* Stored Procedures
* Indexing
* Performance Optimization

---

# 🎯 Learning Objectives

This project demonstrates how to:

* Design a modern SQL Server Data Warehouse
* Implement the Medallion Architecture
* Build ETL pipelines using T-SQL
* Create Fact and Dimension tables
* Design Star Schemas
* Write advanced analytical SQL queries
* Apply data warehouse best practices
* Prepare data for Business Intelligence tools

---

# 📌 Future Enhancements

* SQL Server Integration Services (SSIS)
* SQL Server Agent Scheduling
* Incremental Data Loading
* Slowly Changing Dimensions (SCD Type 2)
* Data Quality Framework
* Power BI Dashboard
* Azure Data Factory Integration
* Azure Synapse Analytics
* CI/CD Pipeline using GitHub Actions

---

# 📚 References

* AdventureWorksDW2022 Sample Database
* Microsoft SQL Server Documentation
* Kimball Dimensional Modeling Methodology

---

## 👨‍💻 Author

Developed as a hands-on Data Engineering project to demonstrate modern Data Warehouse design principles using SQL Server and the Medallion Architecture.
