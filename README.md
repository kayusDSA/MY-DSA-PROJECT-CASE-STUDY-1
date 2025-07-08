### Table of Contents
1. Project Topic
2. Description
3. Project Overview
4. Data Source
5. Project Scope
6. Tool Used
7. Data Cleaning and Preparation
8. Exploratory Data Analysis for Kultra Mega Stores (2009–2012)
- Understanding the Dataset
- Project Reqiurement
  Case Scenario I
  Case Scenario II
- Data Cleaning and Preparation
9. Data Analyses
10. Finding of the study
11. Recommendations
  
### Project Topic 
Sales Performance and Inventory Utilization of Kultra Mega Stores (KMS) from 2009 – 2012, Lagos.

# Description 
This is one of my projects in Digital SkillUp Africa (DSA) through The IncubatorNG. It focuses on Sales Performance and Inventory Utilization of Kultra Mega Stores (KMS), Lagos, Nigeria. An Excel file containing order data from 2009 to 2012 was analyzed to provide key insights and findings for management use.

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

### Exploratory Data Analysis for Kultra Mega Stores (2009–2012)
### Understanding the Dataset

- Order_ID
- Order_Date
- Product_Name
- Product_Category
- Product_Sub-Category
- Order_Quantity
- Sales
- Discount
- Profit
- Customer Segments
- Region or City
- Order_Priority
- Shipping_Cost
- Ship_Mode
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

### Case Scenario I 

#### 1.	Product Category that had the Highest Sales

**SQL Query**
~~~sql
select Product_Category, SUM(distinct Row_ID) as TotalSales
from Inventory
group by Product_category
order by TotalSales desc
~~~
**Table 1: Product Category with The Highest Sales**

![Q1](https://github.com/user-attachments/assets/777bc307-35e9-43d0-9d25-04068ba1bf4f)

The result feom Table 1 above shows that Office Supplies had the highest sales of $19,468,739.

### 2.	The Top 3 and Bottom 3 Regions in Terms of Sales
a.	Top 3 regions by sales

**SQL Query**
~~~sql
Select top 3 Region, SUM(Sales) AS TotalSales
from Inventory
group by Region
order by TotalSales desc
~~~
**Table 2a: Top Three (3) Regions by Sales**

![Q2a](https://github.com/user-attachments/assets/4ddfa4b9-1cd5-4024-b8e0-44faa0fcabd0)

Statistics from Table 2a above reveals that West, Ontario and Prarie are the top 3 regions that have highest sales as $3,597,549, $3,063,212 and $2,837,305 respectively.

### 2b. Bottom 3 Regions in Terms of Sales

**SQL Query**
~~~sql
Select top 3 Region, SUM(Sales) AS TotalSales
from Inventory
group by Region
order by TotalSales asc
~~~
**Table 2b: Bottom Three (3) Regions in Terms of Sales**

![Q2b](https://github.com/user-attachments/assets/99adb31f-e3f2-4ba9-a748-0c2f6ef96617)

Table 2b above reveals that Nunavut, Northwest Territories and Yukon are the bottom 3 regions by sales as $116,376, $800,847 and $975,867 respectively.


### 3.	The Total Sales of Appliances in Ontario

**Sequel Query**
~~~sql
SELECT Region,  Product_Sub_Category, SUM(Sales) AS TotalSales
FROM Inventory
WHERE Region = 'Ontario'
AND Product_Sub_Category = 'Appliances' 
GROUP BY Region,  Product_Sub_Category
ORDER BY TotalSales desc
~~~               
**Table 3: Total Sales of Appliances in Ontario**

![Q3](https://github.com/user-attachments/assets/474f76af-5286-488e-b2ea-60e2c75eae6a)

Table 3 above shows the total sales of appliances in Ontario. Statistics shows that the total sales of appliances in Ontaria were N202,347.

### 4.	Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers

**SQL Query**
~~~sql
Select top 10 Customer_Name, SUM(Sales) AS TotalSales
from Inventory
group by Customer_Name
order by TotalSales asc
~~~
**Table 4: The Bottom Ten (10) Customers**

![Q4](https://github.com/user-attachments/assets/393f81d5-56cf-44ff-b0d9-a587e3681d27)

The result from Table 4 above reveals the bottom 10 customers of Kultra Mega Stores (KMS). As a Business Intelligence Analyst, based on this result, I therefore advise the management of KMS on how to increase the revenue from their bottom 10 customers based on customers’ behavior, preferences, and value potential. My advice will take a structural approach as follows

1.	Understand the Bottom Customers: 
There is a need to segment these bottom 10 customers. That is, are they small businesses, one-time buyers, or price-sensitive clients? The management needs to analyze the purchase patterns of these customers. In other words, what do they buy? How often? What’s their average spend? Also, there is a need to identify friction points: Are there service, pricing, or product issues reducing their engagement?
2.	Personalize Marketing and Communication: That is, 
- Use personalized promotions: Offer tailored discounts, bundles, or loyalty points to encourage repeat purchases.
- Engage with personalized email campaigns: Highlight relevant products based on their past purchases.
- Assign account managers: For B2B clients, personal engagement can foster trust and loyalty.

3.	Offer Incentives to Increase Spend. In other words, the management needs to
- Cross-sell and upsell: Suggest complementary or premium products.
- Loyalty programs: Reward repeat purchases or long-term commitment.
- Minimum spend rewards: E.g., "Get 10% off when you spend $100 or more.

4.	Improve Customers’ Experience
- Simplify ordering: Reduce barriers in the sales or checkout process.
- Enhance service quality: Ensure fast response, delivery, and support.
- Request feedback: Understand why they’re not spending more and use insights to make changes.

5. Reevaluate Product-Market Fit: Are the right products being offered? Adjust product mix based on their needs.
- Review pricing strategy: Is pricing a barrier? Consider tailored pricing or financing options.

6.	Monitor Progress and Adjust: Track the Key Performance Indicators (KPIs) like order frequency, average order value, and lifetime value for these customers and set SMART goals for revenue growth from this segment and review performance quarterly.

### 5. The Most Shipping Cost Incurred By KMS Using which shipping Method

**SQL Query**

~~~sql
Select top 5 Ship_Mode, SUM(Shipping_Cost) AS TotalShipping_Cost
from Inventory
group by Ship_Mode
order by TotalShipping_Cost desc
~~~
**Table 5: The Most Shipping Cost Incurred by shipping method**

![Q5](https://github.com/user-attachments/assets/ffe3194c-d8e2-4844-9511-4ba666381fe4)

Statistics from Table 5 above shows that KMS incurred the most shipping cost ($51,972) on Delivery Truck.

### Case Scenario II
 
### 6. The most Valuable Customers, and What Products or Services They Typically Purchase 
a. The Most Valuable Customers

**SQL Query**
~~~sql
SELECT top 5 Customer_Name, SUM(Order_Quantity*Unit_Price) AS TotalRevenue
FROM Inventory
GROUP BY Customer_Name
ORDER BY TotalRevenue DESC
~~~
**Table 6a: The Most Valuable Customers by Total Revenue Generated**

![Q6a](https://github.com/user-attachments/assets/e47da9d3-ec1d-4a0e-a27d-6314cd601052)

Table 6a above depicts the top 5 most valuable customers by the total revenue generated. Statistics from the above table 7a reveals that Emily Phan, Deborah Bunmifield, Sylvia Foulston, Roy Skaria and Alejandro Grove are the most valuable customers by their total revenue at N118,906, N100,784, N95,458 N90,956 and N86,448 respectively.

### 6b. Products or Services The Most Valuable Typically Purchase

**SQL Query**
~~~sql
SELECT top 5 Customer_Name, Product_Sub_Category, SUM(Order_Quantity*Unit_Price) AS TotalRevenue
FROM Inventory
GROUP BY Customer_Name, Product_Sub_Category
ORDER BY TotalRevenue DESC
~~~
**Table 6b: Products or Services do the Most Valuable Typically Purchase**

![Q6b](https://github.com/user-attachments/assets/e7a9a11b-8528-474c-a19b-4b54c9ae0998)

Table 6b above shows that Office Machines and Copiers and Fax are the products that customers typically purchased.

### 7. Small Business Customer With Highest Sales
 
**SQL Query**
~~~sql
SELECT TOP 1 Customer_Segment, Customer_Name, SUM(Sales) AS TotalSales
FROM Inventory
WHERE Customer_Segment = 'Small Business'
GROUP BY Customer_Segment, Customer_Name
ORDER BY TotalSales desc
~~~
**Table 7: Small Business Customer with The Highest Sales**

![Q7](https://github.com/user-attachments/assets/be1f4d9e-3f09-4d6f-93a6-75c8416435a8)

Table 7 above depicts the small business customer with the highest sales. The result shows that Corporate has the highest sales, N5,498,905.

### 8. Corporate Customer Who Placed the Most Number of Orders Between 2009 – 2012

**SQL Query**
~~~sql
SELECT top 1 Customer_Name, Customer_Segment,
Count(Order_ID) AS TotalOrders
FROM Inventory
WHERE Customer_Segment = 'Corporate'
AND Year (Order_Date) BETWEEN 2009 AND 2012
GROUP BY Customer_Name, Customer_Segment
ORDER BY TotalOrders desc;
~~~
**Table 8: Corporate Customer who Placed the Most Number of Orders in 2009 – 2012**

![Q8](https://github.com/user-attachments/assets/bc92dd32-202d-4d68-b582-cfb1f47568f9)

Table 8 above reveals that Adam Hart who is a corporate customer place the greatest number of orders (27) between 2009 and 2012.

### 9. The Most Profitable Consumer Customer 

**SQL Query**
~~~sql
SELECT top 1 Customer_Segment, Customer_Name, SUM(Profit) AS TotalProfit
FROM Inventory
Where Customer_Segment = 'Consumer'
GROUP BY Customer_Name, Customer_segment
ORDER BY TotalProfit DESC
~~~                   
**Table 9: The Most Profitable Consumer Customer**

![Q9](https://github.com/user-attachments/assets/40a81214-8c2b-43e4-ac8b-887ac8a20cf3)

Table 9 above depicts that Emily Phan was the most profitable customer at $34,005

### 10. Customer who Returned Items, and The segment they belong to

**SQL Query**
~~~sql
SELECT DISTINCT o.[Order_ID], o.[Customer_Name], o.[Customer_Segment]
FROM Inventory o
JOIN [dbo].[Order_Status] r 
ON o.[Order_ID] = r.[Order_ID]
WHERE r.Status = 'Returned';
~~~
**Table 10: Customer who Returned Items, and The segment they belong to**

![Q10](https://github.com/user-attachments/assets/89f7a9b0-1eac-42d9-a591-e83a36678c82)

Statistics from Table 10 above shows that a large number of customers returned their items and these belong to customer segments such as Corporate Customers, Consumer Customers, Home Office Customers and Small Business Customers.

### 11. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer

**Explanations:**
If the Delivery Truck of Kultra Mega Stores (KMS) is the most economical but slowest shipping method, and the Express Air is the fastest but most expensive, then shipping decisions should ideally align with the Order Priority of each order.

High-priority orders (like "Critical" or "High") should use Express Air, even though it is expensive, to ensure fast delivery.
Low-priority orders (like "Low", "Medium" or Regular) should use the Delivery Truck to save costs, since speed is less important.
To determine if Kultra Mega Stores (KMS) appropriately spent shipping costs based on the Order Priority, there is a need to examine whether there is a match between
shipping methods and order priorities:
 If most Critical/High orders were shipped via Express Air and most Low/Medium priority orders were shipped via Delivery Truck. Then the company is appropriately managing its shipping costs, balancing speed for urgent orders and cost savings for non-urgent orders.
However, if many Low-priority orders were sent via Express Air, and many Critical orders were delayed using Delivery Truck. Then the company may be wasting money or failing to meet delivery expectations, showing a misalignment between cost and urgency.

**SQL Query**
~~~sql
SELECT 
    Order_Priority,
    Ship_Mode,
    COUNT(Order_ID) AS orderCount,
    Round(SUM(Sales - Profit), 2) AS Estimatedshippingcost,
   AVG(DATEDIFF(day, [Order_Date], [Ship_Date])) AS AvgShipDays
   FROM Inventory
  GROUP BY Order_Priority, Ship_Mode
 ORDER BY Order_Priority, Ship_Mode desc
~~~                                
**Table 11: Whether Kultra Mega Stores (KMS) Appropriately Spent Shipping Costs Based on the Order Priority**

![Q11](https://github.com/user-attachments/assets/fc62f940-2cf8-47a6-85f1-26a5e8c986ca)

Statistics from Table 11 above shows a clear pattern that shows a match between shipping methods and order priorities, although it is not perfectly strict. Here's the analysis from the table:
1. Critical Priority Orders: Here, cost
Express Air: 200 orders, $198,005 (1 day)
Delivery Truck: 228 orders, $1,221,313 (1 day)
Analysis: This category uses the two methods. Though both achieved 1-day delivery. However, Delivery Truck is far more expensive than Express Air. For critical orders, using Express Air is both faster and cheaper. It can be concluded that, Kultra Mega Stores inappropriately spent shipping costs. In other words, the company overpaid for Trucks when Express Air was better.
2. High Priority Orders:
Express Air: 212 orders, $206,125 (1 day)
Delivery Truck: 248 orders, $1,338,508 (1 day)
Analysis: Similarly, this category shares the same issue with the Critical Priority Orders: Delivery Truck is unnecessarily expensive. This resulted into inefficiency. That is, the company could have relied more Express Air.
3. Low Priority Orders: Here, it is expected that shipping costs should be minimized and speed should not be considered as important.
Express Air: 190 orders, $191,312 (1 day)
Delivery Truck: 250 orders, $1,332,956 (4 days)
The issue here is that Express Air was too fast and expensive for low-priority products. At least, Delivery Truck here was slower (4 days), but still very costly. It can be concluded that there was an inappropriate spending by using premium method for low-priority delivery.
3. Medium Priority Orders:
Express Air: 201 orders, $247,152 (1 day)
Delivery Truck: 205 orders, $976,999 (1 day)
Analysis: Both shipping modes delivered fast, but Delivery Truck was significantly more expensive. Conclusively, the company could optimize costs better by favoring Express Air.
5. Not Specified:
Express Air: 180 orders, $194,394 (1 day)
Delivery Truck: 215 orders, $1,085,457
Analysis: Orders without stated priority were still shipped using Express Air significantly, which is not logical without urgency justification. Hence, the company Inappropriately spent shipping cost with unclear priority classification.
Conclusion:
The company, Kultra Mega Stores (KMS) did not appropriately spend shipping costs based on order priority.

### Findings from the Study
Based on the full analysis of the Kultra Mega Stores (KMS) sales and inventory utilization data from 2009–2012, here are the key findings.
Study shows that the top troduct category, Office Supplies generated the highest total sales of $19,468,739, indicating strong demand and market penetration in this category.

In terms of regional performance, the study shows that West, Ontario, and Prarie are the top 3 regions with highest sales $3.6M, $3.06M and $2.83M respectively whereas the 
bottom 3 regions with low sales (all under $1M) are Nunavut, Northwest Territories, and Yukon , indicating weak market engagement or logistical challenges in those areas.
Appliances in Ontario sold $202,347, highlighting a niche opportunity in regional product targeting
The bottom customers had sales below $500. These are potential revenue growth segments if approached with strategic engagement.
Delivery Truck incurred the highest shipping cost ($51,972), despite being the slowest method.

Furthermore, study reveals that Express Air, although faster, had a lower total cost ($7,851), suggesting possible inefficiencies in logistics decisions. Emily Phan with revenue of $118,906 is the Top customer. The top products purchased are Office Machines, Copiers, and Fax equipment.
The most profitable consumer, Emily Phan generated  $34,005 profit.

Moreover, findings shows that a large number of customers who are Corporate Customers, Consumer Customers, Home Office Customers and Small Business Customers returned their items for quality control and service improvement tracking. There is no consistent alignment between order priority and shipping methods.
For instance, Critical orders used both Express Air and Delivery Truck, but the Truck was more expensive despite similar delivery speed. Low-priority orders were unnecessarily shipped using Express Air.

### Recommendations

Based on the findings, the following recommendations are provided for Kultra Mega Stores (KMS) management:
Optimize Shipping Decisions:
- Strengthen High-Value Customer Relationships
- Improve buying experience of customers and gather feedback to address pain points.
- For customers like Emily Phan, build long-term loyalty programs and explore exclusive service tiers.
- Bundle frequently purchased items (e.g., office machines) into business packages.
- Target Underperforming Regions
- Investigate barriers in Nunavut, Yukon, etc.
- Run localized promotions or campaigns to test interest in specific product categories.
- Review Product-Market Fit
- Evaluate if the right products are available to each segment and region.
- Adjust inventory strategies to meet regional and segment demand better.
- Track KPIs for Low-Performing Segments
- Improve Data Practices
- Enforce proper Order Priority labeling to avoid misuse of expensive shipping methods.
- Regularly audit shipping and delivery metrics to ensure performance aligns with cost.
- Monitor order frequency, value, and customer lifetime value regularly.
- Use Express Air only for Critical and High Priority orders.
- Use Delivery Truck only for Low Priority, and only if cost-effective.
- Audit Delivery Truck usage: it's consistently costlier than needed.
- Engage Low-Value Customers and understand who they are (e.g., small businesses, price-sensitive individuals).
- Personalize communication with offers, loyalty programs, and email campaigns.
- Cross-sell and upsell related products.










                               








