# Super Store Analysis

### Dashboard Link : https://app.powerbi.com/groups/me/apps/20c2b009-2ed4-4052-8425-5e0ed4dde25d/reports/0b321c7a-a568-42d9-96a9-f27a5ec6d847/c36f25b0035043002614?experience=power-bi

## Problem Statement

This dashboard analyzes Super Store data by region, country, and city etc. It shows important details like profit, sales, and which products sell the most. This information helps identify strong areas and points for improvement, making it easier to plan for growth and better service.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options they help us to identfy health of column ,errors,etc.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : If the any errors and you need to changed datatypes and another settings then changed them and finalized the proper set a data then close load and applay.
- Step 5 : In the report view, under the view tab, theme was selected like Electric,Classic theme.
- Step 6 : To start make a report add visuals ,kpi and make meaningful report. 
- Step 7 : Visual filters (Slicers) were added for two fields named "Year" and "Segment".
- Step 8 : Three card visuals were added to the canvas, one representing Total Sales  & other representing Total Profit, 
           Using visual level filter display Top 1 Product Name those higher sales.
           
- Step 10 : In this report first page  added a Five charts like stacked bar chart,stacked column chart,treemap,area chart,pie chart.

        Dax query
        Total Profit = SUM(Global_Superstore2[Profit])
        Total Sales = SUM(Global_Superstore2[Sales])

![image](https://github.com/user-attachments/assets/1281400f-3aa2-4d9f-a595-68687cbeb834)

## Time intelligence
- Step 11 :The second page is Time intelligence we can find date related functions like MTD,QTD,YTD using Dax query created a measure and used in visuals. 
- Step 12 :Dax quey MTD ,QTD,YTD

for creating new measure following DAX expression was written;
       
        MTD = TOTALMTD([Total Sales],Dates[Date].[Date])
        QTD = TOTALQTD([Total Sales],Dates[Date].[Date])
        YTD = TOTALYTD([Total Sales],Dates[Date].[Date])
        All Total Sales = CALCULATE([Total Sales],ALL(Global_Superstore2))
        All Profit = CALCULATE([Total Profit],ALL(Global_Superstore2))
        Contribution Regionwise % Profit = [Total Profit]/[All Profit]
        Contribution Regionwise % TS = [Total Sales]/[All Total Sales]
     
- Step 13 : In this page apply drill through functionality they help us to higher level page to visit detail page.

![Screenshot 2024-10-25 205730](https://github.com/user-attachments/assets/7cc2afcf-229c-4b57-bcb2-3d2babf23e0f)

![image](https://github.com/user-attachments/assets/c4d98d3e-625d-4c75-8c87-25098f761ea5)

![image](https://github.com/user-attachments/assets/d1490cb0-91ed-4b67-9919-1d87a00c13fe)

 ## Compare       
 - Step 13 : In this page compare Toatal sale vs previous year sale as well as Profit using a drill down functionality and Bookmark method,and compare country wise and market wise sales and profit,also predict target value after 20% increase sales and profit using Gauge Chart.

![image](https://github.com/user-attachments/assets/59dcd8f2-2ae2-4a9e-93fe-87772cc8ac0e)
 
 
- Step 14 : This all report upload in power bi service and create a workspace and connect gateways personal mode and applay applay shedule referesh as well as creating a app.
