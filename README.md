
# Super Store Sales Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/040a33ff-214e-42ef-982c-b9874ec76dd7/4717246556cc05c3e563?experience=power-bi

## Problem Statement

This dashboard helps the Super Store gain a deeper understanding of its sales performance and customer segments. It provides insights into how different regions, customer segments, and product categories contribute to overall sales and profits. By analyzing the data, the store can identify areas of underperformance, such as regions or product categories with lower sales, and focus on strategies for improvement. The dashboard also highlights the effectiveness of various shipping and payment methods, offering a clear picture of customer preferences and satisfaction levels. Additionally, the average delivery time metric enables the store to identify delays, allowing for operational improvements in logistics. 

Moreover, the Data Anaysistechniques are used ,specially focusing on Time Series Analysis,to provide valuable insights and accurate sales forcasting of 1-month, offering valuable foresight into expected sales trends and enabling the business to make data-driven decisions for future planning. 


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a excel file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that there were 2 empty columns named "ind1" and "ind2",removed them.
- Step 5 : There was a column named "Returns" containing "#N/A" values. By going to the Transform button and selecting Replace Value, the "#N/A" values were replaced with "0" .
- Step 6 : Select all columns, navigate to the Transform tab, and click on Detect Data Type to automatically assign the appropriate data types for each column.
- Step 7 :After cleaning and formatting the data, go to the Home tab and click Close & Apply. 
- Step 8 : Go on Report View tab,a blank canvas appeared.
- Step 9 : Go to the Visualization tab, click on the Format Page icon, and under the Canvas Background section, add a background.
- Step 10 : Calculated measure was created in which total delivery time was calculated . 

for creating new measure following DAX expression was written;
       
        Average delivery Time = DATEDIFF('Sheet1'[Order Date],'Sheet1'[Ship Date],DAY)

 
- Step 11 : Add Card Visuals to display total sales, total quantity, total profit, and average delivery time.The report was then published to Power BI Service.
- Step 12 : Created a Pie Chart to represent sales by segment (e.g., Corporate, Home Office, Consumer). Used another pie chart to show sales distribution by region.
- Step 13 : A Line Chart was added to show Monthly Sales YOY (Year-Over-Year) for the years 2019 and 2020. Similarly, a line chart was created for Monthly Profit YOY.
- Step 14 : A Bar Chart was used to represent sales by ship mode. Another bar chart was created to represent Sales by Category.
- Step 15 : A Map Visual was inserted to display the Sum of Sales and Profit by State, allowing users to visualize sales performance across different states.
- Step 16 : Added Visual Filters (Slicers) for fields such as "Region," "Year," "Segment," and "Ship Mode" to allow users to filter the dashboard interactively.
- Step 17 : The dashboard was customized by adjusting the colors, fonts, and labels. The visuals were aligned for a clean and professional appearance.
- Step 18 : Labels and titles were added to each visual for clarity. For example, "Sales by Region," "Monthly Sales by YOY," and "Sales by Ship Mode" were used as titles.
- Step 19 : Added Text Box from Insert tab to the canvas for giving Title to the dashboard.
- Step 20 : Added another canvas for sales forcasting .
- Step 21 : Used line chart for Time Series analysis. 
- Step 22 : Formated the chart by using Formating tab and zoom slicer.
- Step 23 : Calculated new table, for summarizing sales by date.

for creating new measure following DAX expression was written;
       
        Sales Forecast = SUMMARIZE('Sheet1',Sheet1[Order Date],"Total Sales", SUM(Sheet1[Sales]))

 snap of new calculated column ,

 ![Screenshot (290)](https://github.com/user-attachments/assets/8fbed381-2099-4173-bf50-bf56b14c57a2)
- Step 24 : Added a Stacked Bar Graph for showing sales by state.
- Step 25 :  Finally, the dashboard was published by clicking Publish from Power BI Desktop.

  ![Publish Message](https://github.com/user-attachments/assets/546fac85-2b1a-4768-8a09-c0200e41237e)

# Snapshot of Dashboard (Power BI Service)
![Dashboard snap](https://github.com/user-attachments/assets/d2c5255c-4728-4cc2-875b-2ec590d547d3)

![Sales Forcasting Dashboard Snap](https://github.com/user-attachments/assets/9659ce49-0f66-4f13-9f7e-48559d730686)

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Key metrics
Total Sales = 2M 
Total Quantity Sold = 22K 
Total Profit Earned = 175K 
Average Time Taken for Delivery = 4 DAY

            thus,these key metrics provide a high-level overview of the overall performance of the store.

### [2] Sales Insights
Sales by Segment = Consumers lead with 48% of sales, followed by Corporate at 33%.

Sales by Region = The West region contributes the most, with 33% of total sales, followed by the East at 29%.

Sales by Payment Mode = Cash on Delivery (COD) is the most preferred, accounting for 43% of all transactions.

Sales by Ship Mode = Standard delivery dominates, making up 0.50M of total sales.

Sales by Category = Office Supplies lead sales with 0.64M, followed by Technology and Furniture.

Sales by Sub-Category = Phones are the top-selling sub-category, generating 0.20M in sales.

### [3] Year to year Comparison 
Monthly Sales YOY = The line chart shows a general upward trend in monthly sales from January to December in both 2019 and 2020.

            thus,shows sales growth throughout both 2019 and 2020, with sales performing slightly better in 2020 compared to 2019. This shows an overall improvement in performance year-over-year.

Monthly Profit YOY = Profits were higher in the second half of the year in both 2019 and 2020.

            thus,shows consitent growth throughout the year.


Key Indicator: The second half of the year, in both sales and profit, shows the highest performance, highlighting an opportunity to capitalize on this period for maximum growth.

### [4] Sales Forcasting 
Daily Forcasted sales = 5k 
