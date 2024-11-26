# Azure Data Pipeline and Analytics Solution for Customer Insights
## Business Requirement:
 A company XYZ, operating in the Cycling and Outdoor Sports Retail sector, aims to gain
 deeper insights into customer demographics and their purchasing patterns. Specifically,
 stakeholders are interested in understanding the gender distribution of customers and its
 impact on sales across various product categories. The company’s product portfolio includes a
 diverse range of cycling-related items, from bikes and accessories to clothing and
 components.
 
Key requirements include:
1. KPI Dashboard: Insights into sales by gender and product category, highlighting:
   - Total products sold.
   - Total sales revenue.
   - Gendersplit of customers.
2. Dynamic Filtering:
   - Allow stakeholders to filter data by product category, gender, and date range.
3. Real-time Access:
   - Provide up-to-date data through an automated and scalable pipeline.
The company’s existing data resides in an on-premises SQL database, requiring a robust and
efficient system to process, analyze, and visualize the information.
## Solution:
To address these business requirements, I proposed the following solution:
 1. Data Extraction and Ingestion:
    - Extract sales and customer data from the on-premises SQL database using Azure Data Factory (ADF).
    - Store the raw data securely in Azure Data Lake Storage (ADLS) for centralized processing.
 2. Data Transformation:
    - Use Azure Databricks with PySpark to cleanse and transform the data.
    - Key transformations include:
         - Mapping product categories (e.g., Bikes, Accessories, Clothing, Components).
         - Aggregating KPIs such as:
               - Total products sold by gender and category.
               - Total revenue by gender and category.
               - Percentage breakdown of gender distribution.
  3. Data Modeling and Architecture:
     - Implement the Medallion Architecture:
         - Bronze Layer: Raw data directly extracted from the SQL database.
         - Silver Layer: Cleansed and structured data with enriched product and customer details.
         - Gold Layer: Aggregated KPI data, ready for reporting and dashboarding.
  4. KPI Dashboard Development:
     - Build a Power BI dashboard with:
          - Visualizations for total sales, products sold, and gender distribution.
          - Interactive slicers for filtering by gender, product category, and date.
          - Linecharts and bar graphs showing trends over time.
          - Piecharts for gender distribution within product categories.
  5. Pipeline Automation:
     - Schedule daily pipeline runs using ADF triggers to ensure real-time data updates.
  6. Governance and Security:
     - Secure credentials using Azure Key Vault.
     - Manage access with Azure Active Directory to ensure data confidentiality and integrity.
## Architecture Diagram

![architecture drawio](https://github.com/user-attachments/assets/046e27c4-cd69-46e7-a51c-f65ce4f31d93)

## Azure Services
- Azure Data Factory (ADF): For orchestrating data extraction and pipeline automation.
- Azure Data Lake Storage (ADLS): Centralized storage for raw, transformed, and aggregated data.
- Azure Databricks: For data transformations using PySpark and SQL.
- Azure Synapse Analytics: For querying the Gold layer and enabling analytics.
- Power BI: For interactive dashboards and visualizations.
- Azure Key Vault: For managing secrets securely.
- Azure Active Directory (AAD): For managing secure access to resources.

## Features
1. Automated ETL Pipeline:
   - Extracts data from an on-premises SQL database using Azure Data Factory.
   - Transforms data in Azure Databricks following Medallion Architecture principles.
   - Stores data in Delta Lake format for optimized analytics.
2. Interactive Dashboard:
   - Includes dynamic filtering by gender, product category, and date range.
   - Visualizes sales trends, gender distributions, and revenue metrics.
3. Secure and Scalable:
   - Credentials stored in Azure Key Vault.
   - Fine-grained access controls using Azure Active Directory.
4. Real-Time Updates:
   - Daily scheduled pipeline runs ensure up-to-date data.
## Pipleine Implementation

1. Data Extraction:
   - Data ingested from an on-premises SQL Server into the Bronze Layer using ADF.
   - Secure integration with Azure Key Vault for managing database credentials.
2. Data Transformation:
   - Performed in Azure Databricks
     - Cleaned and enriched data for the Silver Layer.
     - Aggregated metrics and standardized formats for the Gold Layer.
   - Used PySpark and SQL for efficient processing.
3. Data Visualization:
   - Interactive dashboard in Power BI connected to Azure Synapse Analytics.
   - Enabled real-time KPI tracking.
## KPI Dashboard

The Power BI dashboard includes:
- Sales by Gender and Product Category:
    - Pie charts and bar graphs for total revenue and gender splits.
- Filters:
    - Product category, gender, and date range filters for granular insights.
<img width="504" alt="image" src="https://github.com/user-attachments/assets/80fe41b3-adcc-4c51-956f-e09dd409b8e1">

## Future Scope
Enhancements:
1. Real-Time Streaming:
     - Integrate Azure Stream Analytics for live data processing.
2. Predictive Analytics:
     - Use Azure Machine Learning for sales forecasting and personalized recommendations.
3. Multi-Region Scalability:
     - Expand the pipeline for multi-region sales data.
4. Enhanced Visualizations:
     - Add geographic and demographic insights to Power BI dashboards.
5. Incremental Data Loads:
     - Transition to Delta Lake's time-travel features for efficient historical analysis.
