![workflow_schema drawio](https://github.com/user-attachments/assets/9883f603-225a-49da-b5af-e4d60cb9d0c8)
**Azure Data Factory ETL Pipeline for Data Migration**

Overview


This project showcases a fully functional ETL (Extract, Transform, Load) pipeline built with Azure Data Factory (ADF) for migrating customer, product, and order datasets between Azure Blob Storage containers. The data was generated using Python’s pandas library and processed in parallel pipelines. The solution demonstrates skills in data engineering, cloud integration, pipeline orchestration, and troubleshooting within the Azure ecosystem.
Architecture

Source: Azure Blob Storage (customer_data, product_data, order_data files).
ETL Pipeline: Three parallel Copy Activities in ADF handling customer, product, and order data migration.
Sink: Azure Blob Storage containers (v_activity, activity, copy_ac_tivity folders).

**Repository Structure**


<pre><code> AzureDataEngineering/
├── dataset/                 # Dataset JSON configurations
├── factory/                 # ADF factory configuration
├── linked_service/          # Linked Service JSONs (Blob Storage configs)
├── pipeline/                # Main pipeline JSON with Copy Activities
├── docs/                    # Screenshots and visuals
│   ├── pipeline-overview.png
│   ├── blob-storage-config.png
│   └── pipeline-run.png
├── publish_config.json      # ADF publishing config
└── README.md                # Project documentation
</code></pre>

Tools & Technologies

**Azure Data Factory (ADF)**


Role in the Project:
Azure Data Factory served as the central orchestration tool for automating and managing the ETL pipeline. It was used to:

Ingest data (CSV files) from Azure Blob Storage.
Perform schema mapping to align source and destination structures.
Load the transformed data into target Blob Storage containers (or optionally into Azure SQL Database).
Support parallel execution of three copy activities for customer, product, and order data.
Integrate with GitHub for version control of pipeline definitions and configurations.


**Azure Blob Storage**


Role in the Project:
Azure Blob Storage was used as both the source and sink for the ETL pipeline.

Source: Stored raw datasets (customer_data.csv, product_data.csv, order_data.csv) that were ingested by ADF.
Sink: Target containers received the transformed data after schema mapping via ADF copy activities.
Blob Storage’s scalability and seamless integration with ADF made it ideal for staging and persisting files during the data migration process.

**Pandas (Python Library)**


Role in the Project:
Pandas was used for the initial data generation and preprocessing before the files were uploaded to Azure Blob Storage.

Created structured data for customer, product, and order datasets.
Applied custom logic and formatting to simulate realistic business data for ETL processing.
Exported the final DataFrames as .csv files which were later ingested by ADF.

**Azure SQL Database**


Overview: Azure SQL Database is a fully managed relational database service built on SQL Server. It provides high performance, scalability, and built-in intelligence, making it a preferred choice for storing structured data in the cloud.

Role in the Project:
While the current pipeline loads data into Blob Storage, it can be extended to load transformed datasets into an Azure SQL Database for better querying, analytics, and reporting.
Potential use cases include:

Storing normalized customer, product, and order data.
Running complex SQL queries for business insights.
Connecting BI tools (e.g., Power BI) for dashboarding.
Future Integration Plans:

Create staging tables in Azure SQL for each dataset.
Add new Copy Activities in ADF to move data from Blob Storage to SQL tables.
Use Stored Procedures or Mapping Data Flows for transformation.

**Azure Data Studio**


Overview: Azure Data Studio is a cross-platform, lightweight SQL editor developed by Microsoft. It supports connections to Azure SQL Database and comes with features like:

IntelliSense for SQL queries.
Rich visualizations for query results.
Git integration for version control of SQL scripts.
Notebooks for documenting your workflows with markdown + code.
Role in the Project:
Azure Data Studio can be used to:

Inspect the data after it's loaded into Azure SQL.
Write, run, and save SQL queries.
Monitor and troubleshoot ETL runs through query performance stats.
Version SQL scripts alongside your pipeline JSONs.



