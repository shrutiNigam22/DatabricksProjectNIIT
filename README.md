# DatabricksProjectNIIT
Road Infrastructure and Traffic Analysis Project
This project implements a data pipeline using the Medallion Architecture, designed to process and analyze data related to road infrastructure and traffic patterns. The project ingests two types of CSV files—Raw_Roads and Road_Traffic—and processes them through bronze, silver, and gold layers. The entire workflow is triggered automatically when new files are placed in a designated landing folder in Azure Data Lake Storage Gen2 (ADLS Gen2).

<h>Project Structure<h>

Data Sources
Raw_Roads CSV Files:

Description: Contains data on roads, including IDs, categories, regions, link lengths, and the number of motor vehicles.
Business Importance: Provides essential information on road infrastructure, enabling analysis of road conditions, traffic patterns, and aiding in transportation planning. This data is critical for making informed decisions on road maintenance, expansion, and optimization.

Road_Traffic CSV Files:

Description: Contains traffic count data at various locations, including details like count point ID, direction, date, time, region, road name, vehicle types, and traffic volume.
Business Importance: Valuable for analyzing traffic patterns, identifying congestion hotspots, and making data-driven decisions related to transportation infrastructure and planning.
Medallion Architecture Layers
Bronze Layer:

Purpose: Raw ingestion of the data from the CSV files into the data lake.
Processing: Data is read from the landing folder in ADLS Gen2 and stored in its raw format without any transformations or filtering.
Silver Layer:

Purpose: Cleansed and structured data.
Processing: Data from the bronze layer is cleaned, filtered, and transformed into a more structured format, making it suitable for analysis. This step includes handling missing values, correcting data types, and aligning data into a consistent format.
Gold Layer:

Purpose: Aggregated and enriched data ready for reporting and analytics.
Processing: Data from the silver layer is aggregated and enriched with additional calculations and metrics. This final layer provides a high-level view of the data, optimized for queries and dashboards.

Workflow Automation
<img width="751" alt="image" src="https://github.com/user-attachments/assets/1f4c0e88-b482-4cfc-b12e-502e2b336e86">

Trigger: The workflow is automatically triggered when a new file is placed in the landing folder within ADLS Gen2.
Process: The new file is ingested into the bronze layer, then cleaned and processed into the silver layer, and finally aggregated into the gold layer.
Storage: Processed data is stored back into ADLS Gen2 in respective folders for bronze, silver, and gold layers.


Notebooks
<img width="504" alt="image" src="https://github.com/user-attachments/assets/d539ef26-ff65-4014-9f03-394c428a71ee">

To run the project, follow these steps:

Setup ADLS Gen2: Ensure that the landing folder and corresponding bronze, silver, and gold folders are set up in your ADLS Gen2 storage account.

Upload CSV Files: Place the Raw_Roads and Road_Traffic CSV files into the landing folder in ADLS Gen2. This will automatically trigger the workflow.

Run the Notebooks: The bronze, silver, and gold notebooks will be executed in sequence, processing the data through each layer.

Analyze the Results: Once processing is complete, the aggregated and enriched data in the gold layer can be used for reporting and analysis.

Conclusion
This project demonstrates a robust data pipeline using the Medallion Architecture, facilitating the ingestion, processing, and analysis of road infrastructure and traffic data. By following the structured layers, the project ensures data quality and readiness for high-level decision-making.

