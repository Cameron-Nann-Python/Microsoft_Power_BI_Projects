# Converting Unstructured Data with an Index Column

## Overview
At times, data will be in a format that is not suited for analysis. In this project, I will examine an unstructured dataset that 

## Getting Started
The dataset is intially loaded into Power BI Desktop. There is only one column that stores all of the data, which appears to have three distinct sections:

<img width="1051" height="836" alt="load-unstructured-data" src="https://github.com/user-attachments/assets/d0200bd0-8214-4ef8-9b72-08c017653b45" />

To adjust the format, the data must be transformed using PowerQuery.

### Create an Index Column

The first step is to add an index column. This column will serve as a basis for future columns representations. For this project, navigate to the **Add Column** tab and select **Index Column** from the **General** tab. Select **From 0** from the dropdown to make the column:

<img width="737" height="760" alt="make-index-column" src="https://github.com/user-attachments/assets/7a7399ee-a7c9-4aa1-9949-3b7297fa4cae" />

### Create a Modulo Column

The next stage is to make a modulo column. The data has three groups: Month, Order Quantity, and Order Total. The modulo column will take the remainder of values from the index column. To access the modulo column, select **Standard** and choose **Modulo** as the mathematical operation. Choose three to represent the groups. The resulting column will have remainders of 0, 1, and 2 that repeating corresponding to the initial groups:

<img width="863" height="630" alt="make-modulo-column" src="https://github.com/user-attachments/assets/149461b8-cc27-4887-bd54-f44cc64d8c3c" />

### Create an Integer Division Column

The final column to create is the integer division column. This column will designate row-level values for each data entry in the unstructured column as each quotient represents a row. Select the index column and choose **Division (Integer)** from the **Standard** dropdown. Use three as an input to generate the column:

<img width="1072" height="768" alt="create-integer-division-column" src="https://github.com/user-attachments/assets/00ade713-d55d-4c4b-a2cf-a2b4640131d0" />

With the modulo and integer division columns complete, the index column can be removed.

### Pivot the Data

To transform that unstructured data, the modulo column must be pivoted. The modulo column will become columns and the integer division column will become an index. Navigate to the **Transform** tab and select **Pivot Column**. Select the "Data" column as the Values Column. Under the Advanced options, select "Don't Aggregate" to maintain the original values. The following transformation should appear as follows:

<img width="1091" height="452" alt="pivot-data" src="https://github.com/user-attachments/assets/324cb087-9a7d-4782-b3fa-fd987894e321" />

### Finishing Touches

To finalize the table, unnecessary columns should be removed and the first row should appear as column headers. Remove the integer division index as it is not needed as a primary key. To shift the first row to the column headers, select the **Use First Row as Headers** option from the **Use First Row as Headers** icon. The final table should appear as follows:

<img width="677" height="431" alt="final-structured-data" src="https://github.com/user-attachments/assets/de0e904d-f775-45cb-b4b6-adf5d97220fa" />

## Technologies Used
- Power BI Desktop

## Files Included
- `create-an-index-column.pbix`: a Power BI report containing the full data transformation process on the unstructured data
Provided by the Microsoft Power BI Data Analyst Professional Certificate Program
- `Activity-Index-Column.xlsx`: excel spreadsheet containing unstructured order data
