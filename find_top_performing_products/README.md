# Finding Top Performing Products with PowerQuery

## Overview

In this Power BI report, I leveraged PowerQuery to perform data transformations that revealed the top performing products for each region and product category for the ficitional Adventure Works company. The data has been processed, so data cleaning is not necessary for this project.

## Getting Started
I have listed the methodology I used to showcase the top performing products. The following sections will serve as a guide to repeat the workflow.

### Update the Data Source 
The `FindTopPerformingProducts.pbix` report initially was linked to a file stored in Power BI Service. The data source must be adjusted to the Excel spreadsheet `AdventureWorks-FactSale.xlsx`. After downloading both , go to **File** and select **Options and Settings**. Click on **Data Source Settings** and change the data source appropriately. 

The data source should reference the Excel file as seen here:
<img width="961" height="728" alt="change-data-source" src="https://github.com/user-attachments/assets/73b83e49-2f2b-41ca-bc12-82cef3f4c12d" />

After the data source is updated, open PowerQuery by clicking **Transform data** from the **Queries** pane in the **Report View**.

### Group Columns
To find the top performing products based on region and product category, a Group by operation must be performed. Navigate to the **Sales** table and scroll to the right to find the **Category** and **Country-Region** columns. These columns that will be used for grouping. To determine the most successful products, calculations on the **Sales Amount** column will be used as criteria. 

To start grouping, select **Group by** from the **Transform** pane in the **Home** tab. Check the "Advanced" radio button to group by multiple columns, namely the **Category** and **Country-Region** columns mentioned before by clicking on "add grouping". A new column named "Total Amount" can be made using a sum operation on the **Sales Amount** column, which is important for a future calculation. Another column named "Order Quantity" can be made by clicking "add aggregation" and using "Count Rows" as the operation. The final new column named "All Rows" can be made by clicking "add aggregation" and using "All Rows" as the operation. This final column will contain tabular data for each group.

The operation panel should appear as follows:
<p align="center">
  <img width="852" height="667" alt="group-by-pane" src="https://github.com/user-attachments/assets/f425a7cd-e907-499b-a691-e0fcea8deec8" />
</p>


### Create the Top Performing Products Column

After finishing the grouping, a new column can be added to store the top performing products. Navigate to the **Add Column** tab and select **Custom Column** from the **General** pane. This will start a DAX query. 

To start the query, the best products will have the highest sales, so a Max function needs to performed based on the grouping sales amounts by products. Use Table.Max() to compute the highest product sales value. Pass Table.Group() as the first comparison parameter and "Total Sales" as the second.. Within Table.Group(), use the **All Rows** as the table and select "Product" as the grouping key. The final parameters needs to be a list with brackets {}. Compute the sales for each product by using the "Total Sales" column and representing each of the sums of the "Sales Amount" column with the List.Sum() method calling **Sales Amount** as the parameter. 

The final column logic appears as follows:
<p align="center">
  <img width="857" height="513" alt="top-perform-custom-column" src="https://github.com/user-attachments/assets/124e97b4-11b3-4e34-aacc-91a291494652" />
</p>

After completing the expression, the new column is generated. Use the expand column icon in the top right of the column and ensure only the product box is checked:
<img width="1295" height="737" alt="expand-product-column" src="https://github.com/user-attachments/assets/67ce19b9-e0bb-4b7b-a43d-a88790db45ae" />

The top performing product for each region and category is now displayed (renamed the column as needed):
<img width="1297" height="741" alt="final-product-column" src="https://github.com/user-attachments/assets/26eec28d-917c-483f-940b-9bfb364b4f8a" />


## Technologies Used

- Power BI Desktop

## Files Included

Provided by the Microsoft Power BI Data Analyst Professional Certificate Program
- `AdventureWorks-FactSale.xlsx`: Excel spreadsheet containing tables of sales and customer data for Adventure Works
- `FindTopPerformingProducts.pbix`: Power BI report with loaded data before transformations occur
