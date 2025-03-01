# PowerBIproject
# E-Commerce Retail Sales Report

# Problem Statement
This dashboard provides comprehensive insights into e-commerce retail sales performance, enabling businesses to better understand customer behavior, sales trends, and areas for improvement. By leveraging historical data from 2020 to 2025, the dashboard can forecast sales, profit, and other key metrics up to 2030. With 49,782 rows of data, it includes detailed columns such as Country, Customer ID, Description, Discount, Exchange Rate, Invoice Time, Date, Return Status, Sales, Payment Method, Shipping Cost, and more. A currency converter table ensures all values are standardized to USD, while a date table ensures continuous date ranges for accurate analysis. The analysis reveals that nearly 57% of customers are neutral or dissatisfied with their purchase experience, while only 43% are satisfied. This highlights the need for the business to focus on improving customer satisfaction by addressing issues such as product quality, delivery times, or return policies. Additionally, the dashboard identifies opportunities to optimize shipping costs and discount strategies to enhance profitability. By leveraging this dashboard, the e-commerce business can:

*Identify trends and forecast future sales and profit up to 2030.

*Improve customer satisfaction by addressing areas of concern.

*Optimize pricing, discounts, and shipping strategies to maximize profitability.

*Enhance decision-making by understanding customer preferences and purchasing behavior.

# Steps followed
Step 1: Import the CSV dataset into Power BI Desktop.

Step 2:Handle null values (if any) in key columns like "Sales" or "Shipping Cost".Ignore nulls for calculations (e.g., average discount or shipping cost).

Step 3:In Report View, Apply a Theme from the View tab for consistent formatting.Add Slicers for interactive filtering (e.g., Country, Year, Month, Return Status).

Step 4:Use Cards for key metrics such as Total Sales, Total Quantity, Total Profit, and Average Shipping Cost.

Step 5 : Create a Bar Chart to show sales by product category or customer segment.

Step 6 : In the report view, under the view tab, theme was selected.

Step 7 : Add a Donut Chart to visualize payment method distribution.

Step 8 :Use a Map Chart to display sales by country.

Step 9 : Visuals(ResetButtons)Interact with slicers and filters in the report.

Step 10 : Create the Sales Forecasting Channel for next 5 years from the current year to view the time-series Forecasting

Step 11 : In the report view, under the insert tab, one text boxes were added to the canvas, in that name of the report was mentioned.

Step 12 : In the report view, under the insert tab, using shapes option from elements group a rectangle was inserted was added to the report design area.

Step 13 : Create a Newcolumn named currency Exchange Rate Table

for creating NewColumn following DAX expression was written;

    Sales in USD =
    SUMX(
            'online_sales_dataset',
            IF('online_sales_dataset'[ExchangeRate]>1,
            ('online_sales_dataset'[TotalSales]/'online_sales_dataset'[ExchangeRate]),
            ('online_sales_dataset'[TotalSales]*'online_sales_dataset'[ExchangeRate]))
    ) 

    ![Image](https://github.com/user-attachments/assets/8a8de106-51cf-4565-a35d-5620026df406)![Sales_column](https://github.com/user-attachments/assets/522f65af-79ca-46df-8433-9e7dfaa20110)

    
