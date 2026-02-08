# 2021 Olympics in Tokyo  
## End-to-End Azure Data & Analytics Architecture

---

## Project Overview
This project implements an **end-to-end Azure cloud architecture** to ingest, process, store, analyze, and visualize data from the **2021 Tokyo Olympics**.

The solution demonstrates a **modern data engineering and analytics pipeline** using Microsoft Azure services, following best practices for **scalability, security, automation, and governance**.

The architecture covers the full lifecycle:
**Data ingestion → Data storage → Data transformation → Analytics → Visualization → Monitoring**

---

## Project Objectives
- Build a complete **Azure-based data pipeline**
- Ingest Olympic data from structured sources (CSV/Excel/API)
- Store raw and curated data using Azure data services
- Transform data for analytics and reporting
- Visualize insights using **Power BI**
- Implement DevOps and monitoring practices
- Demonstrate real-world cloud architecture skills

---

## End-to-End Architecture

### 🔹 Architecture Flow
`Data Source
↓
Azure Data Factory
↓
Azure Data Lake Storage Gen2
↓
Azure Databricks / Azure Synapse
↓
Azure SQL Database / Synapse Analytics
↓
Power BI Service`

---

## Azure Services Used

### Data Ingestion
- **Azure Data Factory (ADF)**
  - Pipeline orchestration
  - Data extraction from source files or APIs
  - Scheduled and automated ingestion

### Data Storage
- **Azure Data Lake Storage Gen2**
  - Raw (Bronze), Cleansed (Silver), and Curated (Gold) layers
  - Scalable and secure cloud storage

### Data Processing & Transformation
- **Azure Databricks / Azure Synapse Analytics**
  - Data cleaning and transformation
  - Business logic implementation
  - Optimized analytical datasets

### Data Serving
- **Azure SQL Database / Synapse Dedicated Pool**
  - Structured data for reporting
  - Optimized queries for BI tools

### Data Visualization
- **Power BI Desktop & Power BI Service**
  - Interactive dashboards and reports
  - Olympic insights: medals, countries, sports, trends

### DevOps & Monitoring
- **GitHub / Azure DevOps**
  - Source control
  - CI/CD pipelines
- **Azure Monitor & Log Analytics**
  - Pipeline and performance monitoring
 
---

## Repository Structure
2021-Olympics-in-Tokyo/
│
├── architecture/
│ └── azure_architecture_diagram.png
│
├── data/
│ ├── raw/
│ ├── processed/
│ └── curated/
│
├── adf/
│ └── pipelines/
│
├── databricks/
│ └── notebooks/
│
├── database/
│ └── schema.sql
│
├── powerbi/
│ └── tokyo_olympics_dashboard.pbix
│
├── devops/
│ └── ci-cd-pipeline.yml
│
└── README.md


---

## Analytics & Insights
The Power BI dashboards provide insights such as:
- Medal distribution by country and continent
- Top-performing athletes and sports
- Gender participation analysis
- Event-wise medal trends
- Country performance comparisons

---

## How to Run the Project
1. Deploy Azure resources using the defined architecture
2. Configure Azure Data Factory pipelines
3. Upload Olympic datasets to Data Lake (Raw layer)
4. Run Databricks/Synapse transformations
5. Load curated data into SQL/Synapse
6. Connect Power BI to the analytical layer
7. Publish dashboards to Power BI Service

---

## Security & Governance
- Azure Active Directory (AAD) for access control
- Role-Based Access Control (RBAC)
- Secure secrets using Azure Key Vault
- Data access policies applied at storage and database levels

---

## Monitoring & Optimization
- Pipeline execution monitoring via Azure Monitor
- Performance tuning in Synapse/SQL
- Cost management and optimization strategies applied

---

## Use Case
This project is suitable for:
- Cloud data engineering portfolios
- Azure architecture demonstrations
- Power BI analytics projects
- Academic or professional cloud case studies

---

## License
This project is intended for **educational and demonstration purposes**.

---

## Acknowledgements
- International Olympic Committee (IOC)
- Microsoft Azure Documentation
- Open-source data contributors

