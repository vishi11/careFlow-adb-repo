# CareFlow – Azure Databricks

This repository contains the **Azure Databricks notebooks and implementation files** for the CareFlow data engineering project.

The project follows a **Medallion Architecture** in Azure Databricks, where data is progressively ingested, cleaned, transformed, and prepared for analytical use across the Bronze, Silver, and Gold layers.

## 🏗️ Architecture

```
                    Source / Landing Data
                           │
                           ▼
                    ┌──────────────┐
                    │    Bronze    │
                    │ Raw / Ingested│
                    │     Data      │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │    Silver    │
                    │ Cleaned and  │
                    │ Transformed  │
                    │     Data      │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │     Gold     │
                    │ Analytical / │
                    │ Business Data│
                    └──────────────┘
```

## 📂 Repository Structure

```text
careFlow-adb-repo/
│
├── Gold/
│   └── Gold layer notebooks / implementation
│
├── from_landing_to_bronze.ipynb
│   └── Landing → Bronze ingestion
│
├── Bronze_to_Silver.ipynb
│   └── Bronze → Silver transformation
│
├── Calendar table.ipynb
│   └── Calendar / Date dimension creation
│
└── README.md
```

## 🔄 Data Processing Flow

### 1. Landing → Bronze

The `from_landing_to_bronze.ipynb` notebook handles the ingestion of data from the landing layer into the Bronze layer.

The Bronze layer maintains the ingested data in a form suitable for downstream processing while preserving the source data structure.

### 2. Bronze → Silver

The `Bronze_to_Silver.ipynb` notebook processes Bronze data and prepares the Silver layer.

The transformation process includes:

* Data cleansing
* Data type handling
* Null handling
* Duplicate handling
* Data validation
* Source field transformations
* Preparation of structured data for downstream processing

### 3. Silver → Gold

The Gold layer contains business-oriented and analytical data prepared for reporting and downstream consumption.

The `Gold` directory contains the corresponding Gold-layer implementation.

### 4. Calendar Table

The `Calendar table.ipynb` notebook is used to create a calendar/date dimension that supports time-based analysis and reporting.

## 🧱 Medallion Architecture

The project follows the following layer responsibilities:

| Layer      | Purpose                                 |
| ---------- | --------------------------------------- |
| **Bronze** | Raw/ingested source data                |
| **Silver** | Cleaned, validated and transformed data |
| **Gold**   | Business-ready and analytical data      |

This layered approach separates raw ingestion from transformation and business-level data modeling.

## ⚙️ Technologies Used

* **Azure Databricks**
* **Apache Spark**
* **PySpark**
* **Spark SQL**
* **Delta Lake**
* **Python**
* **SQL**
* **Medallion Architecture**

## 🔍 Key Data Engineering Concepts

This project demonstrates practical implementation of:

* Medallion Architecture
* Bronze, Silver and Gold layers
* PySpark transformations
* Spark SQL
* Data cleansing and validation
* Data transformation
* Date/Calendar dimension
* Delta Lake based data processing
* Databricks notebooks
* Layered data architecture

## 🔗 Integration with Azure Data Factory

Azure Data Factory is used as the **orchestration layer** for the overall CareFlow data engineering workflow, while Azure Databricks is used for data processing and transformation.

```text
                Azure Data Factory
                       │
                       │ Orchestration
                       ▼
                Azure Databricks
                       │
                       ▼
                  Bronze Layer
                       │
                       ▼
                  Silver Layer
                       │
                       ▼
                   Gold Layer
```

The ADF implementation is maintained separately in the CareFlow ADF repository.

## 🎯 Project Objective

The objective of this project is to build a scalable data engineering workflow using **Azure Data Factory and Azure Databricks**, following a Medallion Architecture.

ADF handles pipeline orchestration and data movement, while Databricks performs scalable data processing and transformation.

## 🔐 Security

No passwords, access keys, connection strings, tokens, or other sensitive credentials should be committed to this repository.

Credentials and environment-specific configuration should be managed using appropriate Azure security mechanisms.

## 👤 Author

**Vishal Chandra**

Data Engineering | Azure Databricks | Azure Data Factory | PySpark | SQL
