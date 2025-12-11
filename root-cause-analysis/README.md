# 🚗 Root Cause Analysis: Vehicle CO2 Emissions

## 📓 Overview
CO2 emissions are a major environmental concern, especially those emitted by cars. This project undergoes a root cause analysis to reveal which vechicular attributes are most represented in the largest CO2 emissions, and to break down the data to locate specific instances of vehicles with low CO2 emissions.

<img width="1285" height="722" alt="co2_emissions_dashboard" src="https://github.com/user-attachments/assets/786dbeb4-444a-44cd-be2d-c22e725b0529" />

## 💡 Data Insights

This report is split into two pages: a key indicator page that explores features that contribute to high CO2 emissions and a decomposition tree breaking down specific vehicle groups by average CO2 emissions. 

### 📂 Vehicle Analyzed Card

This visual shows that 22 million vehicles were analyzed in this study. 

### 📊 Key Indicators

There are three distinct segments that indicated when the average CO2 emissions are likely to be high.

<img width="1732" height="766" alt="top3_co2_segments" src="https://github.com/user-attachments/assets/5c322643-88b1-46d2-b919-1ef3f5a3373c" />

The largest top segment reveals that CO2 emissions are most likely to high when the engine size is greater than 2494 $cm^3$. A safe assumption is larger engines lead to higher CO2 emissions.

<img width="1717" height="691" alt="first_co2_segment" src="https://github.com/user-attachments/assets/668df9e7-2de4-4dda-b309-aec4ec1b5001" />

The other two segments show that internal combustion engine (ICE) powertrains and automatic transmissions are also likely to see high CO2 emissions.

<img width="1715" height="678" alt="second_co2_segment" src="https://github.com/user-attachments/assets/90c0c74d-3d8e-4943-a7c2-9a1a06cb9a23" />

<img width="1712" height="631" alt="third_co2_segment" src="https://github.com/user-attachments/assets/bc2b1c45-6c42-4ba1-b5b5-ccddc774a333" />

### 📈 Average CO2 Emissions by Engine Size

A scatterplot of CO2 emissions with various engine sizes is given. A general positive correlation can be seen between a rise in CO2 emissions and an increase in engine size. The largest engine size observed was  6749 $cm^3$ with an average CO2 emission of 360.33.

<img width="1366" height="752" alt="CO2_engine_scatterplot" src="https://github.com/user-attachments/assets/9318c805-269e-44a4-a278-7b8380e3d2c1" />

### 📊 Powertrain by Transmission

The other two factors of the top segments, powertrain and transmission, appeared to be correlated as they had repeated featured across two segments. This column chart illustrates powertrain types and the frequency of the transmission per category. It can be seen that over 4000 vehicles of this dataset had a internal combustion engine powertrain with 2677 having an automatic transmission. The trend may influence the average emission seen.

<img width="1367" height="767" alt="powertrain_by_transmission_column_chart" src="https://github.com/user-attachments/assets/adde9c0c-13a1-4f21-9cbd-4fb99b4e7385" />

### 🥧 CO2 Emissions by Fuel Type

Although fuel type was not represented in a top segment, it is a feature that contributes a rise in CO2 emissions. A pie chart illustrates the total CO2 emissions by fuel type. The fuel type that leads in the highest CO2 emissions by 52.1% is Petrol.

<img width="1733" height="762" alt="co2_emissions_by_fuel_type" src="https://github.com/user-attachments/assets/31bcd6e8-9e45-423b-8860-58b81776f25c" />

### 📓 Decomposition Tree

The decomposition tree is a granular analysis of vehicular groups by the highest average CO2 emissions. In order to accomodate the style of the tree, an engine size group of 5 bins was formed from the engine size column. The tree uses AI insights to gather information about the groups and an example of the hybrid electric vehicle with the lowest CO2 emissions is provided below:

<img width="947" height="588" alt="decomposition_tree_hybrid_eletric_lowest_co2" src="https://github.com/user-attachments/assets/e0b84777-4fb7-478c-9510-e235a6b31d31" />

## 📂 Technologies Used
- Power BI Desktop

## Files Included
Provided by the Microsoft Power BI Data Analyst Professional Certificate Program
- `CO2-emissions-by-vehicle.pbix`: Power BI report containing vehicle data and emissions


