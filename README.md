# Healthcare Revenue Cycle Management (RCM) – End-to-End Data Engineering Project

## 📖 Project Overview
This project is an end-to-end **Healthcare Revenue Cycle Management (RCM)** data engineering solution built using **Azure Data Factory, Azure Data Lake Gen2, Azure Databricks, and Delta Lake**.

The project focuses on designing **production-style data pipelines** that ingest data from multiple hospital branches, standardize it using a **Common Data Model**, and prepare reliable datasets for downstream analytics and reporting teams..

---

## 🏥 Business Context
In healthcare organizations, revenue is mainly driven by two components:
- **Accounts Receivable (AR)** – money to be collected from patients and insurance
- **Accounts Payable (AP)** – payments made to providers and vendors

Hospitals often operate multiple branches, each having its own EMR database.

Because of this:
- Reporting teams struggle with inconsistent schemas
- Finance teams face delays in AR tracking
- Historical changes are difficult to maintain

This project solves these problems by building a **centralized healthcare data platform**.

---

## 🛠️ Tech Stack
- **Azure Data Factory (ADF)** – Pipeline orchestration
- **Azure Data Lake Gen2** – Centralized storage
- **Azure Databricks** – Data transformation
- **Delta Lake** – SCD handling
- **SQL / PySpark** – Transformations
- **Parquet** – Storage format

---

## 🏗️ Solution Architecture (Medallion)

This diagram represents the end-to-end data flow across Bronze, Silver, and Gold layers.

![Architecture Diagram](https://github.com/alpesh502/azure-healthcare-rcm-pipeline/blob/main/Architecture-Diagram.png)

The solution follows **Bronze–Silver–Gold architecture**, ensuring scalability, data quality, and analytics readiness.

---

### 🥉 Bronze Layer 
- Ingests raw data from multiple EMR databases (different hospital branches)
- Uses **config-driven ADF pipelines**
- Supports **full and incremental loads**
- Stores raw data in **Parquet format**
- Handles dynamic file paths and partitioning
- Maintains basic audit and logging information

---

## 🔄 Azure Data Factory Pipeline (Bronze Layer)

The following image shows the **ADF pipeline used for ingesting EMR data into the Bronze layer**.

![ADF Pipeline](https://github.com/alpesh502/azure-healthcare-rcm-pipeline/blob/main/adf/adf-pipeline.png)



### 🥈 Silver Layer
- Applies **Common Data Model (CDM)** across hospital branches
- Performs data cleansing and standardization
- Implements **Slowly Changing Dimension (SCD Type 2)**
- Uses **Delta Lake MERGE operations** to maintain history

![Silver Layer Merge](https://github.com/alpesh502/azure-healthcare-rcm-pipeline/blob/main/Silver_Layer(Merge).png)

---

### 🥇 Gold Layer
- Builds business-ready datasets
- Supports **Accounts Receivable and Claims analytics**
- Designed for BI and reporting use cases

---

## 🔁 Data Sources
- **EMR Databases**
  - Patients
  - Providers
  - Departments
  - Encounters
  - Transactions
- **Claims Data** (Insurance)
- **NPI Data** (Doctor identifiers)
- **ICD Codes** (Diagnosis reference)



---

## 📈 Business Value
- Faster and reliable Accounts Receivable reporting
- Consistent data across multiple hospital branches
- Historical visibility into patient and claim changes
- Reduced manual effort for reporting teams



---

## 👤 Author
**Alpesh Singh**  
Aspiring Data Engineer | ADF | Databricks | SQL

