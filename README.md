# Azure-Based-Sales-Insights-Pipeline

This project implements an automated data pipeline for processing and validating orders data using Azure services. It ensures data quality and generates actionable sales insights for reporting.

Here's how it worked:

![folders](https://github.com/user-attachments/assets/376eb2b9-dcf1-44a3-a8dc-4c46a70d9244)

📁 𝗧𝗿𝗶𝗴𝗴𝗲𝗿𝗶𝗻𝗴 𝗔𝘂𝘁𝗼𝗺𝗮𝘁𝗶𝗼𝗻
 Whenever an Orders file landed in the Landing folder, an Azure Storage Event Trigger kicked off a pipeline.

 ![Event_trigger](https://github.com/user-attachments/assets/c8a7629d-91de-4439-998c-c4b9db1a8b9c)


🚀 𝗗𝗮𝘁𝗮 𝗜𝗻𝗴𝗲𝘀𝘁𝗶𝗼𝗻 & 𝗩𝗮𝗹𝗶𝗱𝗮𝘁𝗶𝗼𝗻
Pulled the Order Items file from Amazon S3 to ADLS Gen2.

Ran validation checks in Azure Databricks:
Checked for duplicate order_id (discarded if found).
Validated order_status dynamically against an Azure SQL DB table.

Used KEY VAULT for storing all the sensitive information


![keys](https://github.com/user-attachments/assets/ec5aa77b-1a1b-455a-9fc2-f287d3800d33)



✅ 𝗗𝗮𝘁𝗮 𝗧𝗿𝗮𝗻𝘀𝗳𝗼𝗿𝗺𝗮𝘁𝗶𝗼𝗻
Valid files moved to the Staging folder, others to the Discarded folder.

Read customer data from Azure SQL DB and created TempViews for Orders, Order Items, and Customers.
Performed a join to calculate total orders and total spend per customer.


💾 𝗙𝗶𝗻𝗮𝗹 𝗢𝘂𝘁𝗽𝘂𝘁
 The results were written into the Sales Reporting Table in Azure SQL DB for insights.

📌 𝗧𝗲𝗰𝗵 𝗦𝘁𝗮𝗰𝗸: Azure Data Factory, ADLS Gen2, Key Vault, Azure Databricks, PySpark, and Azure SQL DB.

![Notebook_1](https://github.com/user-attachments/assets/b0b998df-d207-475f-a81e-fc93a5d53976)
![Notebook_2](https://github.com/user-attachments/assets/d88e3368-84df-4ae2-8b2f-c04e3984bd2e)
![Notebook_3](https://github.com/user-attachments/assets/c4583bd8-287b-4c23-ba29-b946408329a7)
![Notebook_4](https://github.com/user-attachments/assets/285f0f92-05b5-4b51-884c-eb4fddcd1faa)
![Notebook_5](https://github.com/user-attachments/assets/4923622e-33d6-43d2-98b2-e476e2561f5e)
![Notebook_6](https://github.com/user-attachments/assets/286d1d02-828e-4a00-8eff-c4240fcb5044)

