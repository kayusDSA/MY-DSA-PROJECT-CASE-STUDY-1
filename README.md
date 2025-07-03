![Q1](https://github.com/user-attachments/assets/0aec355d-5152-4bb1-8241-ee8e20d0c851)
# MY-DSA-PROJECT-CASE-STUDY-1
This is one of my projects, in Digital SkillUp Africa (DSA) through The IncubatorNG, which focuses on Sales Performance and Inventory Utilization of Kultra Mega Stores (KMS), Lagos, Nigeria. An Excel file containing order data from 2009 to 2012 was analyzed to provide key insights and findings for management use.

### Project Topic 
Sales Performance and Inventory Utilization of Kultra Mega Stores (KMS) from 2009 – 2012, Lagos.

### Project Overview
This project aims to generate insight into the sales performance and inventory utilization of Kultra Mega Stores (KMS) from 2009 – 2012, focusing on identifying sales, growth opportunities, customer segments, operational efficiencies, and optimize inventory management for improved business efficiency.

### Data Source
The Data Source used for this project is an *CSV file*, which is a secondary data and it is provided by the Business Manager of the Abuja division of Kultra Mega Stores Inventory.

### Project Scope
Sales and inventory data relevant to KMS operations in Lagos, but the analysis is focused on the Abuja division

### Tool Used
SQL Server is used for this project for querying and analysis. It can be [downloaded here](https://www.microsoft.com/en/sql-server/sql-server-downloads)

### Data Cleaning and Preparation
Under this project, data cleaning and preparation are done by changing the data type of
Row_ID from smallint to int
Order_ID from smallint to int
Click on Allow Nulls for Unit_Price and Profit

Sales from float
Discount from float

### Exploratory Data Analysis for Kultra Mega Stores (2009–2012)
### Understanding the Dataset
- Order ID
- Order Date
- Product Name
- Category (Furniture, Office Supplies)
- Sub-Category
- Quantity
- Sales
- Discount
- Profit
- Customer Type
- Region or City
- Order Priority
- Shipping Cost
- Ship Mode
### Project Reqiurement
#### Case Scenario I
1. Which product category had the highest sales?
2. What are the Top 3 and Bottom 3 regions in terms of sales?
3. What were the total sales of appliances in Ontario?
4. Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers
5. KMS incurred the most shipping cost using which shipping method?

#### Case Scenario II
6. Who are the most valuable customers, and what products or services do they typically purchase?
7. Which small business customer had the highest sales?
8. Which Corporate Customer placed the most number of orders in 2009 – 2012?
9. Which consumer customer was the most profi table one?
10. Which customer returned items, and what segment do they belong to?
11. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer

### Data Cleaning and Preparation
i. Import the data: The Data is loaded into the SQL Server

ii. Explore the data: The structure of the data such as columns, data types were carefully examined and missing values were identified.

iii. Data Cleaning:
- Data Type was changed for Row_ID and Order_ID from smallint to int
- Allow Nulls was done for Unit_Price and Profit

### Data Analysis
Data analyses were performed under two case scenarios
#### Case Scenario I 
1.	Which product category had the highest sales
Sequel Query
~~~~ Sequel Query
select Product_Category, SUM(distinct Row_ID) as TotalSales
from Inventory
group by Product_category
order by TotalSales desc
~~~~~

   




