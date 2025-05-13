# Azure End-to-End ETL Pipeline using Data Factory, Databricks, MongoDB & Synapse

## 🚀 Project Overview

This project demonstrates an **end-to-end ETL data pipeline** using various Azure services. The pipeline ingests raw data from external sources, processes and enriches it using Azure Databricks, stores intermediate data in Azure Data Lake, and ultimately loads it into Synapse Analytics for reporting and visualization using Power BI. MongoDB Atlas is integrated for additional data enrichment.

---

## 🧱 Architecture Diagram


![Architecture Diagram](https://github.com/user-attachments/assets/524577c4-9266-4827-bde1-1c9f4b6d6de7)

---

## 🔧 Technologies Used

- **Azure Data Factory** – Data ingestion from external sources
- **Azure Data Lake Storage Gen2** – Raw and processed data storage
- **Azure Databricks** – Data cleaning, transformation, enrichment
- **MongoDB Atlas** – Used for lookup/enrichment table
- **Azure Synapse Analytics** – Data warehousing and integration with Power BI
- **Power BI / Tableau / Fabric** – Visualization layer

---

## 📌 Key Features

- Ingest data from **GitHub HTTP source** and **SQL Tables** using Azure Data Factory
- Store raw data in **ADLS Gen2**
- Perform data transformation, cleaning, and aggregation using **PySpark in Azure Databricks**
- Enrich data using **MongoDB Atlas lookup**
- Save transformed data back to **ADLS Gen2**
- Load clean data into **Azure Synapse Analytics**
- Visualize data insights using **Power BI / Tableau / Microsoft Fabric**

---

## 🛠️ Setup Instructions

### 1. Azure Resources Setup
- Create a resource group
- Create a storage account (ADLS Gen2) with containers: `landing`, `staging`, `curated`
- Create Azure Data Factory and Databricks Workspace
- Set up Synapse Analytics workspace
- Setup MongoDB Atlas cluster (free tier)

### 2. Data Ingestion
- Use Azure Data Factory to move raw CSV from external source (e.g., GitHub) into `landing`
- Create linked services and datasets in ADF
- Build and trigger the Copy pipeline

### 3. Data Transformation in Databricks
- Mount the ADLS Gen2 storage
- Read raw data using PySpark
- Perform schema cleanup, null handling, type casting
- Add computed columns (e.g., Total Sales)
- Join with MongoDB data for enrichment (e.g., product details)
- Save output in curated layer

### 4. Load into Synapse
- Use Databricks Spark JDBC to write the curated data into Synapse SQL pool
- Create Synapse table beforehand for target schema

### 5. Visualization
- Connect Power BI to Synapse SQL pool
- Build visuals: sales by region, top customers, time trends, etc.

---


