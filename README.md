# Power BI ETL Project – AdventureWorks Sales Data Transformation

## Project Overview

This project demonstrates an **end-to-end ETL (Extract, Transform, Load) workflow using Power BI Power Query**.
The goal is to clean, transform, and integrate multiple sales data sources from the AdventureWorks dataset to prepare a reliable dataset for business analysis.

This project was completed as part of the **Microsoft Power BI Data Analyst learning journey**.
---
# Business Scenario
Adventure Works is an international company that generates a large volume of sales data.
Sales information is stored across multiple files:

* Order2022 – sales orders from 2022
* Order2023 – sales orders from 2023
* OrderDetails – detailed transaction records

The management team wants to analyze store sales performance, but the data must first be cleaned, validated, and combined before analysis.
The objective of this project is to:

• Clean and validate the data
• Detect and remove anomalies
• Combine multiple yearly datasets
• Enrich detailed sales records with order information

The final output is a **clean dataset ready for sales analysis**.
---

# Dataset
The project uses three data sources:

| Dataset      | Description                               |
| ------------ | ----------------------------------------- |
| Order2022    | Sales orders for year 2022                |
| Order2023    | Sales orders for year 2023                |
| OrderDetails | Detailed product-level sales transactions |
---

# ETL Workflow
## 1 Data Import
Imported Excel datasets into Power BI using **Power Query**.
```
Get Data → Excel
```
---

## 2 Data Cleaning
Removed unnecessary columns from OrderDetails and kept only:

• SalesOrderID
• ProductID
• OrderQty
• UnitPrice

---

## 3 Data Profiling
Enabled Power Query data profiling tools:

• Column Quality
• Column Distribution
• Column Profile

These tools helped identify:
* valid values
* errors
* empty rows
* statistical distributions

---
## 4 Detecting Data Anomalies
Using column profiling, three extreme outliers were detected in the **UnitPrice column**.
Example anomalous values:

```
1,000,000.5
1,250,000
1,500,000.6
```
These values were identified as data entry errors and removed to prevent incorrect calculations.

---

## 5 Appending Multiple Data Sources
The **Order2022** and **Order2023** datasets were appended to create a unified **Orders table**.

```
Append Queries → Orders
```
Validation checks performed:

• row count verification
• column structure consistency
• data type validation

---
## 6 Merging Tables
The Orders table was merged with the OrderDetails dataset using:

```
SalesOrderID
```
Join type:

```
Inner Join
```
The **OrderDate column** was extracted from the Orders table and added to the OrderDetails dataset.

---
# Final Dataset

The final cleaned dataset contains:

| Column       | Description             |
| ------------ | ----------------------- |
| SalesOrderID | Unique order identifier |
| ProductID    | Product sold            |
| OrderQty     | Quantity ordered        |
| UnitPrice    | Product price           |
| OrderDate    | Date of the order       |

This dataset is now ready for **sales analysis and reporting**.
---

# Skills Demonstrated

Power BI
Power Query
ETL Process
Data Cleaning
Data Profiling
Anomaly Detection
Appending Tables
Merging Tables
Data Validation

---

# Tools Used
Microsoft Power BI
Power Query

---

# Author

Vidya Vishnuvihar Geetha
