# Azure End-to-End Data Engineering Real-Time Project: 

This project is designed as a data engineering pipeline solution to address a simulated business challenge, providing hands-on experience in data pipelining and analytics.

## Project Overview :

The goal of this project is to build a comprehensive data pipeline on Azure, enabling the extraction of customer and sales data from an on-premises SQL database, transforming it in the cloud, and generating insightful reports through a Power BI dashboard. The dashboard will offer key performance indicators (KPIs) related to gender distribution and product category sales, allowing stakeholders to filter and analyze data based on date, product category, and gender.

## Business Requirements:

The business aims to gain a deeper understanding of customer demographics—particularly gender distribution—and its influence on purchasing behavior. The primary requirements include:

1) **Sales Analysis by Gender and Product Category** – A dashboard displaying total products sold, total sales revenue, and a 
    breakdown of customers by gender.
2) **Data Filtering Capabilities** – Users should be able to filter sales data by product category, gender, and date.
3) **User-Friendly Interface** – A simple and intuitive interface that allows stakeholders to interact with data easily.

## Solution Overview :

To fulfill these requirements, the solution is structured into the following components:

1. **Data Ingestion** :
* Extract customer and sales data from an on-premises SQL Server database.
* Load the extracted data into Azure Data Lake Storage (ADLS) using Azure Data Factory (ADF).
2. **Data Transformation** :
* Use Azure Databricks to clean and transform raw data.
* Implement a Bronze-Silver-Gold data architecture: 
      * Bronze Layer – Stores raw ingested data.
      * Silver Layer – Contains cleansed and structured data.
      * Gold Layer – Holds aggregated data for analytics and reporting.
3. **Data Storage and Reporting** :
* Load the processed data into Azure Datalake Gen2 Gold Container for analysis.
* Develop a Power BI dashboard to visualize insights and enable data-driven decision-making.
4. **Automation** :
Schedule pipeline execution to run daily, ensuring data and reports remain up to date.

## Technology Stack :

* **Azure Data Factory (ADF)** – Orchestrates data ingestion and movement.
* **Azure Data Lake Storage (ADLS)** – Stores raw and processed data.
* **Azure Databricks** – Handles data transformation and processing.
* **Azure Synapse Analytics** – Provides data warehousing and analytics capabilities.
* **Power BI** – Visualizes insights for business stakeholders.
* **Azure Key Vault** – Secures credentials and access keys.
* **SQL Server (On-Premises)** – Serves as the source of customer and sales data.

## Setup Instructions :

### Prerequisites :

* An active Azure account with sufficient credits.
* Access to an on-premises SQL Server database.

### Step 1: Set Up Azure Environment :

1) Create a Resource Group to organize all Azure services.
2) Provision Required Services:
   * Deploy an Azure Data Factory instance.
   * Set up Azure Data Lake Storage with bronze, silver, and gold containers.
   * Configure Azure Databricks and Azure Synapse Analytics.
   * Enable Azure Key Vault for secure credentials management.

### Step 2: Data Ingestion :

1) **Prepare SQL Server** – Install SQL Server and SQL Server Management Studio (SSMS). Restore the AdventureWorks database.
2) **Extract and Load Data** – Use ADF pipelines to copy data from SQL Server to the Bronze layer in ADLS.

### Step 3: Data Transformation :

1) **Mount ADLS in Databricks** – Configure Databricks to read and write to Data Lake Storage.
2) **Transform Data** – Use Databricks notebooks to clean, aggregate, and move data across Bronze → Silver → Gold layers.

### Step 4: Data Loading and Reporting :

1) **Load Data into Synapse Analytics** – Set up a Synapse SQL pool and store transformed data for querying.
2) **Create a Power BI Dashboard** – Connect Power BI to Synapse and develop visualizations aligned with business needs.

### Step 5: Automation and Monitoring :

1) **Schedule Pipeline Execution** – Use ADF triggers to automate daily pipeline runs.
2) **Monitor Data Pipelines** – Track execution status in ADF and Synapse monitoring tools.

### Step 6: Security and Governance :

1) **Manage Access Control** – Implement Role-Based Access Control (RBAC) using Azure Entra ID (formerly Active Directory).

### Step 7: End-to-End Testing :

1) **Run Test Scenarios** – Insert new records into SQL Server and verify the pipeline execution.
2) **Validate Power BI Dashboards** – Ensure reports reflect the latest data updates.

## Conclusion :

This project provides a scalable and automated data pipeline for gaining insights into customer demographics and sales trends. By leveraging Azure services, the solution ensures efficient data processing, real-time analytics, and seamless reporting, empowering stakeholders with valuable business intelligence.
