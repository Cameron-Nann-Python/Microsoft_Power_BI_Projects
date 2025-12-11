# 🟨 ETL: Extract, Transform, Load

## 📘 Overview
This is a guided project under the Microsoft Power BI Analyst Certificate Program. This project reviews order data for a fictitious company, Adventure Works, and performs the process of extracting, transforming, and loading data in Power BI by leveraging Power Query. The goal of this project is to provide a clean, consolidated dataset for a product sales review.

There are three data sources to work with: 

- OrderData2022.xlsx
- OrderData2023.xlsx
- OrderDetails.xlsx

The order data spreadsheets contain general information on product sales and the order details data contains sales records. An analysis on company sales has been requested, and these datasets need to be reviewed for incomplete and irrelevant data. Below is a breakdown of the necessary data transformations:

1. Retain fields **SalesOrderID**, **ProductID**, **OrderQuantity** and **UnitPrice** from the **OrderDetails** spreadsheet. Remove all other columns.
2. Remove any rows with missing data or outliers from each dataset to ensure data integrity.
3. Append the **OrderData2023** spreadsheet to the **OrderData2022** spreadsheet. Merge the combined dataset with the **OrderDetails** spreadsheet for a unified sales dataset.

The Power BI report file is included as an exemplar of the project workflow and screenshots from the file provide clarity in transformation procedures.

## 📘 Getting Started
1. Download Power BI Desktop or open a Power BI service account to access Power BI.
2. Download the .xlsx files in the project "data" folder. 

## 🛠️Extract
Create a new project in Power BI (The one in this branch is called "ETL_project"). Use the **Get Data** icon and choose the excel spreasheet option to import the spreadsheets into the BI project. Click on the **Transform** button on the Navigator window to access Power Query. The Power Query editor should appear like this:

<img width="1917" height="1015" alt="image" src="https://github.com/user-attachments/assets/198ac980-e797-4169-8213-b56323e6c50c" />

## 🛠️ Transform
**Remove irrelevant columns from the OrderDetails Spreadsheet** 

Navigate to the **Order Details** query. Hold the ctrl key and select all other columns excluding those mentioned in the **Overview**. Right-click and select remove columns. The Power Query editor should appear like this:

<img width="1918" height="1016" alt="image" src="https://github.com/user-attachments/assets/408e892d-1aa7-4625-b860-a032c1b19f24" />

**Remove outliers and missing data**

Navigate to the View tab and check the box for "Column Quality" to check for the percentage of missing data and errors. Check the box for "Column Distribution" to verify the amount of distinct and unique values for each column. Check the box for "Column profile" to see statistics of a selected column.

Select the UnitPrice column. The "Column profile" shows that the maximum value is $1,500,000.60 while the average price is $4831.11. Select the filter icon on the right of the column tab. Scroll down to view three outliers where the third to last price is $1,000,000.50. Uncheck these three values so these prices do not inflate future calculations. The revised column should appear like this:

<img width="1918" height="1017" alt="image" src="https://github.com/user-attachments/assets/14d08023-48ff-4fe2-85eb-9e8b9087323a" />

**Append queries**
Select the **Order2022** query. Choose the **Append Queries as New** option from the **Append Queries** option on the Home tab. Select the **Order2023** query as the second table and create the new query. Name this query "Orders". The new query should appear like this:

<img width="1913" height="1017" alt="image" src="https://github.com/user-attachments/assets/a3e09310-8bc5-4def-afab-a33462874e7f" />

Verify that the new query "Orders" has 1000 rows by navigating to the Transform tab and selecting **Count Rows** in the **Table** ribbon. 

**Merge queries**
Select the **OrderDetail** query and choose **Merge Queries** from the Combine ribbon on the Home tab. Select the **Orders** query as the second table and click on "SalesOrderID" as the common key to merge the sets on. Select "Inner Join" for the **Join Kind** selection to merge existing entries between both queries.

Click on the Expand icon of the newly added "Orders" column added to the **OrderDetail** query. Unselect every column except the **OrderDate** column.

<img width="1918" height="1013" alt="image" src="https://github.com/user-attachments/assets/9603a2cb-3210-4e35-b50c-f5356dbc8879" />

The "Orders" column will be renamed to "Orders.OrderDate". Rename this column to "OrderDate" after double-clicking the column name. The merged dataset should appear like this:

<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/8600f148-1809-4d89-a005-06969db44f6d" />

## 🛠️Load
Click on **Close & Apply** in the home tab. The dataset has now been prepared for visualizations and data analysis.

## 📂 Files Included
- `OrderData2022.xlsx`: 2022 sales data for AdventureWorks
- `OrderData2023.xlsx`: 2023 sales data for AdventureWorks
- `OrderDetails.xlsx`: sales records for AdventureWorks
- `ETL_project.pbix`: Power BI report containing full project transformations
