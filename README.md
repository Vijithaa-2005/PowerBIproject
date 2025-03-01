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

   # Images
   ![Sales_column](https://github.com/user-attachments/assets/8152965c-3be4-4a74-9bdf-6030e73fb92b)

  Step 15 : NewTable was created to find Currency Conversion for each Country.

  ![Currency_Conversion_Table](https://github.com/user-attachments/assets/84fde81c-7a5c-4ec3-9606-95ba66202664)

  Step 15 : NewTable was created to find Currency Conversion for each Country.

  DateTable = 
VAR StartDate = DATE(2020, 1, 1)  // Start date of your date range
VAR EndDate = DATE(2025, 12, 31)  // End date of your date range
VAR DateRange = CALENDAR(StartDate, EndDate)  // Generates a continuous date range
RETURN
ADDCOLUMNS(
    DateRange,
    "Year", YEAR([Date]),
    "Month", MONTH([Date]),
    "Day", DAY([Date]),
    "Quarter", QUARTER([Date]),
    "Month Name", FORMAT([Date], "MMMM"),
    "Weekday", WEEKDAY([Date]),
    "Weekday Name", FORMAT([Date], "dddd"),
    "Week of Year", WEEKNUM([Date]),
    "Is Weekend", IF(WEEKDAY([Date], 2) > 5, TRUE(), FALSE())
)

![DateTable](https://github.com/user-attachments/assets/ec3310cc-f9ab-4202-a1db-82883dffb032)





    
