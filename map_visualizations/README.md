# 🗺️ Adventure Works US Sales Map

<img width="1266" height="717" alt="aw_us_sales_shape_map" src="https://github.com/user-attachments/assets/33ede8bb-f8ec-4972-8e65-5f7ef170e2af" />

## 📧 Overview
A fictional project manager at Adventure Works wants a visualization of sales across the United States. The best course of action was to implement a shape map within a Power BI report to show sales across the states with zoom features for closer inspection.

## 📓 Getting Started

Ensure that the shape map feature box is checked by navigating to **File -> Options and Settings -> Options -> Preview Features**. This will trigger a restart for the Power BI Desktop application.

<img width="1223" height="976" alt="enable_shape_map" src="https://github.com/user-attachments/assets/2019f898-2b91-4acb-8c89-2fc3e4683cf4" />

Navigate to the **Security** tab. Ensure that map visuals are allowed by checking the "use map and filled map visuals" box.

<img width="1217" height="982" alt="enable_map_visuals" src="https://github.com/user-attachments/assets/5e3e2b71-266e-4f77-99f8-097d0b39967c" />

Exit the **Options** menu and return to the report. Navigate to the **table view** tab in the left sidebar. Verify that the `State` column is of data category "state or province" to ensure proper map functionality. A globe icon should be visible to the left of the column name in the Data panel.

<img width="1910" height="1013" alt="validate_state_column" src="https://github.com/user-attachments/assets/ad3115d1-51c1-4e13-a657-b2914987a64a" />

Select the `Sales` column. Verify that the format is `Currency` and there are 2 digits following the decimal. This is necessary for tooltips to display accurate sales data for each state.

<img width="1918" height="996" alt="validate_sales_column" src="https://github.com/user-attachments/assets/e7a68567-198a-4a92-89da-be26c8c99b6a" />

## 🗒️ Configure the Shape Map
The shape map takes the `State` column as its location and the `Sum of Sales` calculation for its color saturation. A city park theme was used for accessibility and a gradient was used to provide more variance in saturation. Green states have higher sales, red states have lower sales and yellow states have sales that fall in between.

To set up the zoom feature, navigate to the **Format Visual** tab of the **Visualizations** pane and expand the **Zoom** tab. Select the **Zoom on selection** toggle to "on" so for a close up view of a state when it is selected.

<img width="1914" height="1020" alt="zoom_on_kentucky" src="https://github.com/user-attachments/assets/737c1ee5-bd3f-421e-94a0-135ee6e62f32" />

## 💡 Data Insights
By observing the shape map, it can be seen that the highest overall sales are in Kentucky with most vibrant green color and a sales figure of $400,000.00. The lowest sales can be observed in Oregon with the most vibrant red color and a sales figure of $81,000.00.

<img width="1919" height="1020" alt="lowest_sales_oregon" src="https://github.com/user-attachments/assets/72d872ac-9700-48de-99b5-fa51b715f4b1" />


## 💻 Technologies Used
- Power BI Desktop

## 📁 Files Included 
Provided by the Microsoft Power BI Data Analyst Professional Certificate Program
- `aw-sales-by-geo.pbix`: a Power BI report containing a table of 50 states and the total sales per state.
