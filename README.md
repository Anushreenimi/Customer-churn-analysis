# Customer-Churn-Analysis
## Tools used- SQL, Power BI, Python
### Table of Contents:
1. [Project Overview](#project-overview)
2. [ETL Framework](#etl-framework)
3. [Dataset Description](#dataset-description)
4. [Project Workflow](#project-workflow)
5. [Power BI Dashboard](#power-bi-dashboard)
## Project Overview
The primary objective of this project is to analyze customer behavior, identify the reasons behind customer churn, and provide actionable recommendations to reduce churn rates. By combining SQL for data extraction and preprocessing, Python for in-depth data analysis and machine learning, and Power BI for visualizing insights, this project aims to help the business improve customer retention and satisfaction.

Churn occurs when customers stop using a service or discontinue their subscription. Understanding the factors leading to churn can help the company implement targeted retention strategies to minimize customer losses and enhance long-term loyalty.
## ETL Framework
Our framework uses below components-
1. CSV/Excel File: Customer churn dataset stored in a local file.
2. SQL: Clean and preprocess data at the database level using SQL queries.
3. Power BI: Import the data for dashboard creation and visualization.
## Dataset Description
No. of rows- 7044, no. of columns-21. The dataset consists of customer information of a company like customerID,	gender,	SeniorCitizen,	Partner,	Dependents,	tenure,	PhoneService,	MultipleLines,	InternetService,	OnlineSecurity,	OnlineBackup,	DeviceProtection,	TechSupport,	StreamingTV,	StreamingMovies,	Contract,	PaperlessBilling,	PaymentMethod,	MonthlyCharges,	TotalCharges,	Churn.
### Note: Dataset in the above Dataset Folder.
## Project Workflow
### SQL(MySQL Workbench)
1. Created new database `Churn2` in mysql workbench, after connecting to server.
2. After creating the database, imported CSV file in MySQL workbench.
3. After importing, performed data analysis using SQL queries.
4. Created a new table `Final_Churn` from our previous table `Customer_Data` by replacing NULL values by 'None' or 'No' values.
  ### Note: For Steps 3 and 4 please refer to SQL Queries file above for all the queries used in data analysis.
### Power BI
5. Connected Power BI to our SQL Server and imported `Final_Churn` table into our Power Query Editor using Transform Data option.
6. Created a new custom column `Churn_Status` and changed the datatype to Whole Number.
7. Created a new custom column Churn_Status and changed the datatype to Whole Number.
   ```bash
   = IF([Customer_Status] = "Churned", 1, 0)
   
8. Created a new custom column `Monthly_Charge_Status`.
   ```bash
   Charge_Category = IF([Monthly_Charge] < 20, 
   "<20", 
   IF([Monthly_Charge] < 50, 
      "20-50", 
      IF([Monthly_Charge] < 100, 
         "50-100", 
         ">100"
      )))
9. Created a new table named `mapping_AgeGrp` by referencing the `Final_Churn` table, keeping only the Age column, and removing duplicate values from it.


  
   







