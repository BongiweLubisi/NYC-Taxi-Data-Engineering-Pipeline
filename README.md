# NYC Taxi Data Engineering Pipeline Project (Fabrics)

## 🎯Project Overview

This project demonstrates an end-to-end data engineering and analytics solution built using a modern Lakehouse and Data Warehouse architecture. The solution ingests raw NYC taxi trip data, processes and cleans it through scalable pipelines, and delivers business-ready insights via a Power BI reporting layer

The primary objective of this project is to transform raw transportation data into meaningful insights that support demand analysis, revenue optimization, and data-driven decision-making.

---

## ⚙️Technologies Used

- Microsoft Fabric (Lakehouse, Warehouse, Pipelines)
- Dataflow Gen2 (Power Query)
- SQL (Stored Procedures, Transformations)
- Power BI (Semantic Model & Reporting)
- Pipeline Orchestration & Automation

---
## 📂Data source and Context

The dataset used in this project is sourced from the NYC Open Data and contains NYC taxi trip records for 2025 in parquet format.

### [View dataset source](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)

---

## 🏗️ Data Architecture

This solution follows a layered data architecture approach to ensure scalability, maintainability, and clear separation of responsibilities across the data lifecycle.

### 🔷Landing Layer (Lakehouse)

Raw NYC taxi data (Parquet files) is ingested into the Lakehouse, which serves as the initial storage layer. This layer preserves the data in its original format and acts as a single source of truth.

### 🔷Staging Layer (Warehouse – STG Schema)

Data is loaded from the Lakehouse into staging tables within the data warehouse. This layer is used for controlled data processing, including validation and cleansing.

A stored procedure is applied to:
- Remove outliers 
- Ensure data consistency (e.g., aligning records to the correct month)

This layer prepares the data for downstream transformations

### 🔷 Transformation Layer (Dataflow Gen2)

Dataflow Gen2 is used to perform transformations using Power Query. This includes:
- Handling missing values  
- Standardizing formats  
- Filtering invalid records
- Merging datasets to enrich trip data (e.g., combining trip records with lookup/reference data such as zones or locations)

This step ensures the data is structured and analysis-ready.

### 🔷 Presentation Layer (Warehouse – DBO Schema)

Cleaned data is loaded into presentation tables optimized for reporting and analytics. 

