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
![Q1](https://github.com/user-attachments/assets/777bc307-35e9-43d0-9d25-04068ba1bf4f)


![Q4](https://github.com/user-attachments/assets/4895e66b-f8c6-47b3-be92-e40573135f04)


![Q2a](https://github.com/user-attachments/assets/a5434a25-9fc3-430c-9d13-14999467b103)


   
![Q2b](https://github.com/user-attachments/assets/e509e14c-a732-4e87-a067-67f1248db59b)



![Q3](https://github.com/user-attachments/assets/f5bebaa7-3d75-455f-8849-dedc08f7bf01)


![Q5](https://github.com/user-attachments/assets/9c02cc16-62a0-4aec-949e-6ce0a1f5bc1d)


![Q6a](https://github.com/user-attachments/assets/01cbaf90-2c75-43e6-8637-838e1943ed9b)


![Q6b](https://github.com/user-attachments/assets/9b7a5940-3fe1-4cfe-9377-5c34f0d5933d)


![Q7](https://github.com/user-attachments/assets/7fcb2c4e-216f-4c6f-9d30-0ee76f321007)


![Q8](https://github.com/user-attachments/assets/c9927aec-6c9d-4b7f-962e-4324867090be)



![Q9](https://github.com/user-attachments/assets/c224bdf3-f11d-4c90-ba2a-278b3f33ac9d)


![Q10](https://github.com/user-attachments/assets/89a130a6-411f-4158-b4e3-c62688dd5f9b)


![Q11](https://github.com/user-attachments/assets/5fea6651-c385-4fa9-87bf-ff9a9b3278f0)














