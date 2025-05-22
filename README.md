
**Azure Data Factory ETL Pipeline for Data Migration**

Overview

This project showcases a fully functional ETL (Extract, Transform, Load) pipeline built with Azure Data Factory (ADF) for migrating customer, product, and order datasets from Azure Data Lake Storage Gen2 (blob storage) to an Azure SQL Database. The original datasets were generated using Python’s pandas library. The pipeline features parallel copy activities for efficient data ingestion, with table schemas designed and created using Azure Data Studio. This solution demonstrates practical skills in data engineering, cloud integration, pipeline orchestration, and SQL database management within the Azure ecosystem



**Architecture**

Source: CSV files stored in Azure Data Lake Storage Gen2(blob storage containing the data(customer_expanded, product_expanded, order_expanded files)).
ETL Pipeline: Azure Data Factory Copy Activity moves data from Data Lake to SQL database
Sink: Sink: Azure SQL Database(relational database for structured data)


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

**Tools & Technologies**

**Azure Data Factory (ADF)**


Azure Data Factory served as the central orchestration tool for automating and managing the ETL pipeline. It was used to:

Ingest data (CSV files) from Azure Blob Storage.
Perform schema mapping to align source and destination structures.
Load the transformed data into target (Azure SQL Database).
Integrate with GitHub for version control of pipeline definitions and configurations.


**Azure Blob Storage**

Used primarily to store datasets in containers (customer_expanded.csv, product_expanded.csv, order_expanded.csv). These files serve as the source for the ETL pipeline in ADF. After processing, ADF writes the transformed data back into Blob Storage containers, acting as the sink. Blob Storage’s scalability and easy integration with ADF made it the perfect place to hold and move files during the data migration.



**Pandas (Python Library)**


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





![workflow_schema](https://github.com/user-attachments/assets/4e879f2b-1af6-4d68-b74a-29debab57af5)






