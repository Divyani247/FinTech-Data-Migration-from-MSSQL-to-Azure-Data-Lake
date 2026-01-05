# FinTech Data Migration from MSSQL to Azure Data Lake (Delta Architecture)

## 📌 Project Overview
This project demonstrates an end-to-end industrial **FinTech data migration pipeline** that modernizes legacy **MSSQL-based financial systems** into a **Delta Lake architecture on Azure Data Lake Storage (ADLS)**.  
The solution ensures scalable ingestion, reliable transformations, automated orchestration, and operational monitoring using Azure-native services.

---

## 🛠 Tech Stack
- **Programming:** Python, PySpark, SQL  
- **Data Storage:** Azure SQL Database, Azure Data Lake Storage (ADLS)  
- **Processing & Analytics:** Azure Synapse Analytics  
- **Data Format:** Delta Tables  
- **Orchestration & Automation:** Azure Synapse Pipelines, Azure Logic Apps  

---

## 🏗 Architecture Overview
The project follows the **Medallion Architecture (Bronze–Silver–Gold)**.
Azure SQL Database
|
v
Bronze Layer (ADLS)
|
v
Silver Layer (Delta Tables)
|
v
Gold Layer (Delta Tables)
|
v
Analytics & Reporting


---

## 🔄 Data Pipeline Workflow

### 1️⃣ Source System Setup
- Historical financial data stored in **Azure SQL Database**
- Multiple normalized tables with referential integrity
- Acts as the source system for migration

---

### 2️⃣ Bronze Layer – Dynamic Ingestion
- Azure Synapse Pipeline extracts data from Azure SQL Database
- Parameterized and dynamic linked services used
- Raw data loaded into **ADLS Bronze Layer**
- Supports scalable ingestion for multiple tables

---

### 3️⃣ Silver Layer – Data Transformation
- PySpark notebook processes Bronze data
- Performs:
  - Data cleansing  
  - Standardization  
  - Enrichment  
- Writes transformed data to **Silver Delta Tables**

---

### 4️⃣ Gold Layer – Business Aggregations
- PySpark notebook applies business logic
- Aggregations prepared for analytics
- Outputs stored as **Gold Delta Tables**

---

### 5️⃣ Operational Workflow
- Synapse Web Activity triggers Azure Logic App
- HTTP POST sends pipeline execution status

---

### 6️⃣ Automated Notifications
- Logic App parses pipeline response
- Sends success/failure email alerts to FinTech operations teams

---

## ⚙️ Orchestration & Error Handling
- Fully automated sequential pipeline execution
- Built-in error handling and monitoring
- Ensures reliable data migration and processing

---

## ✅ Outcome
- Modernized FinTech data infrastructure
- Migration from MSSQL to Delta Lake on ADLS
- Faster analytics with optimized Delta Tables
- Automated operational monitoring and alerts

---

## 🚀 Future Enhancements
- CI/CD using Azure DevOps  
- Data quality checks using Delta constraints  
- Power BI integration for reporting  
- Role-based access control (RBAC)



