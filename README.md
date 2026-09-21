# Azure NYC Taxi Data Engineering Project

End-to-end Azure Data Engineering project using Azure Data Factory, ADLS Gen2, Azure Databricks, PySpark, Delta Lake, and Power BI.

## Architecture

The project follows a Medallion Architecture:

**Bronze → Silver → Gold → Power BI**

### Bronze Layer

- Raw NYC Taxi data is ingested using Azure Data Factory.
- Data is stored in Azure Data Lake Storage Gen2.
- Raw data is kept with minimal transformation.
- Bronze acts as the source layer for further processing.

### Silver Layer

- Bronze data is processed using Azure Databricks and PySpark.
- Data cleaning and transformation are performed.
- Data types are corrected.
- Null and invalid values are handled.
- Transformed data is stored in Parquet format.

### Gold Layer

- Silver data is read and processed using Azure Databricks.
- Parquet data is converted into Delta format.
- Delta tables are created for analytics and reporting.
- Delta Lake features are demonstrated, including:
  - Update
  - Delete
  - Time Travel
  - Version History
  - Restore

### Power BI

Power BI is used as the reporting and visualization layer.

The Gold layer provides analytics-ready data for creating reports and dashboards.

The dashboard includes analysis such as:

- Total Trips
- Trip Trends
- Revenue
- Average Fare
- Trip Types
- Payment Types
- Pickup and Drop-off Locations

## Azure Services & Technologies

- **Azure Data Factory** – Data ingestion and pipeline orchestration
- **Azure Data Lake Storage Gen2** – Data storage
- **Azure Databricks** – Data processing and transformation
- **PySpark** – Data cleaning and transformation
- **Parquet** – Silver layer storage format
- **Delta Lake** – Gold layer storage and version management
- **Power BI** – Reporting and visualization
- **Microsoft Entra ID / Managed Identity** – Authentication and access

## Data Flow

```text
NYC Taxi Data
      ↓
Azure Data Factory
      ↓
ADLS Gen2 - Bronze
      ↓
Azure Databricks + PySpark
      ↓
ADLS Gen2 - Silver
      ↓
Delta Lake - Gold
      ↓
Power BI

```
## ADLS Gen2 Structure


```text
ADLS Gen2
│
├── bronze/
│   └── Raw Data
│
├── silver/
│   └── Cleaned & Transformed Data
│
├── gold/
│   └── Analytics-Ready Delta Data
│
└── logs/
    └── Pipeline Logs
```
## Project Structure


```text
azure-nyc-taxi-data-engineering/
│
├── README.md
├── .gitignore
│
├── Raw Data/
│
├── notebooks/
│   ├── silver_Notebook.ipynb
│   └── Gold_Notebook.ipynb
│
├── Data/
│   ├── taxi_zone_lookup.csv
│   └── trip_type.csv
│
└── screenshots/
    ├── architecture.png
    ├── azure-resources.png
    ├── adls-containers.png
    ├── databricks-catalog-explorer.png
    └── powerbi-dashboard.png
```
## Databricks Notebooks

### Silver Notebook

The Silver notebook uses PySpark to clean and transform the raw NYC Taxi data before storing it in the Silver layer.

### Gold Notebook

The Gold notebook reads the Silver data and creates Delta tables in the Gold layer.

It also demonstrates Delta Lake operations such as:

- Update
- Delete
- Time Travel
- Version History
- Restore

## Key Learning Outcomes

Through this project, I worked with:

- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- PySpark
- Parquet
- Delta Lake
- Medallion Architecture
- Delta Tables
- Time Travel
- Data Version History
- Power BI

## Screenshots

Project screenshots are available in the `screenshots` folder, including:

- Azure Architecture
- Azure Resources
- ADLS Gen2 Containers
- Databricks Catalog Explorer
- Power BI Dashboard
