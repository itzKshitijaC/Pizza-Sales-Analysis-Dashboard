# Pizza Sales Analysis Dashboard 📊

# Demo-Preview 🗺️

<img src="https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/0fc036bd-a722-49d4-90eb-cd223c12d206" width="800" height="400" />

# The business Problem 🔍
The Pizza shop's sales team aims to scrutinize historical sales data to extract actionable insights that will help optimize future marketing strategies, improve inventory management, and enhance customer satisfaction. This analysis seeks to identify trends, seasonal patterns, and key performance indicators, enabling the business to make data-driven decisions that boost overall profitability and operational efficiency.

# Data Cleaning 🧹

1. Rename Pizza Sizes
   
![img1](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/c5d63197-e2fa-4965-84cb-bbafaa3a22f6)
Replace - 
L - Large

M - Medium

Small - Regular

XLarge - X-Large

XXLarge - XX-Large

![img2](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/964bfff9-cecd-42a4-9daf-bacbae42d3a9)


# Data Preprocessing 👩🏻‍💻
1. Create a new column "order_day" from "order_date" column

           =TEXT([@[order_date]],"dddd")

![img3](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/6b4f6534-73f7-44d9-9599-81d51a04b07e)

2. Create a "total orders" column to count the total number of orders given by a particular customer

           =1/COUNTIF(B:B,[@[order_id]])

![img4](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/7e8a7059-9422-47d4-b128-54724b9ce099)

# SQL Queries 👩🏻‍💻
1. Total Revenue:

         SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;
 
![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/a06fab95-25df-4f86-9d5a-04464237527c)

2. Average Order Value

         SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/15bac363-e21a-4bbb-8cf5-24b592ad8ffc)

3. . Total Pizzas Sold

         SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/243b9fdf-1330-43cc-9ed5-223a83984330)

4. Total Orders

         SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/63994d7a-d3a4-4fde-bad0-2f2263736adc)

5. Average Pizzas Per Order

         SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / 
         CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2))
         AS Avg_Pizzas_per_order
         FROM pizza_sales

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/ca9bfd38-5ec7-4497-a3fe-799c9cb95693)

6. Daily Trend for Total Orders

         SELECT DATENAME(DW, order_date) AS order_day, COUNT(DISTINCT order_id) AS total_orders 
         FROM pizza_sales
         GROUP BY DATENAME(DW, order_date)

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/cb90ecb1-d2db-4e66-ac9c-84251817cf08)

7. Hourly Trend for Orders

         SELECT DATEPART(HOUR, order_time) as order_hours, COUNT(DISTINCT order_id) as total_orders
         from pizza_sales
         group by DATEPART(HOUR, order_time)
         order by DATEPART(HOUR, order_time)

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/29727b51-b6e6-4a47-b650-f0ed8c9a0210)

8. % of Sales by Pizza Category

         SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
         CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
         FROM pizza_sales
         GROUP BY pizza_category

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/81f6fcab-14e2-49de-b862-17b2fd804110)

9. % of Sales by Pizza Size

         SELECT pizza_size, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
         CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
         FROM pizza_sales
         GROUP BY pizza_size
         ORDER BY pizza_size

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/92d42be2-d7be-4022-afb9-54d8f1f32481)


10. Total Pizzas Sold by Pizza Category

         SELECT pizza_category, SUM(quantity) as Total_Quantity_Sold
         FROM pizza_sales
         WHERE MONTH(order_date) = 2
         GROUP BY pizza_category
         ORDER BY Total_Quantity_Sold DESC

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/711ce62e-b900-43ac-aaf2-823266438d4f)

11. Top 5 Best Sellers by Total Pizzas Sold

         SELECT Top 5 pizza_name, SUM(quantity) AS Total_Pizza_Sold
         FROM pizza_sales
         GROUP BY pizza_name
         ORDER BY Total_Pizza_Sold DESC

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/bb751d81-f08e-49f2-a338-7bc83ef78e3d)

12. Bottom 5 Best Sellers by Total Pizzas Sold

         SELECT TOP 5 pizza_name, SUM(quantity) AS Total_Pizza_Sold
         FROM pizza_sales
         GROUP BY pizza_name
         ORDER BY Total_Pizza_Sold ASC

![image](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/f65731d8-04dd-4c52-9115-0c019ebcffcc)

# Dashboarding 📊

![Dashboard](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/1df7061f-1e2f-4b5d-89f9-9b9924fa37d4)

### KPI's Requirements 

We analyzed key indicators for our pizza sales data to gain insights into our business performance. 

<b>1. Total Revenue: </b> The sum of the total price of all the pizza orders 

<b>2. Average order value: </b> The average amount spent per order, calculated by dividing the total revenue by the total number of orders 

<b>3. Total Pizza Sold: </b> The sum of quantities of all the pizza sold 

<b>4. Total Orders: </b> The total number of orders placed

<b>5. Average pizza per order: </b> The average number of pizzas sold per order, calculated by dividing the total number of pizzas sold by total number of orders

### Visualizations
1.  Daily Trend for Total Orders
   
![v1](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/0d54c6b0-7142-4fad-8b44-d441c8204eac)

This bar chart displays the daily trend of total orders over a specific period. This chart helps us to identify any patterns or fluctuations in order volumes daily. 

2. Hourly Trend for Total Orders

![v2](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/e1413958-aa21-4e93-8560-ec576028817b)

This line chart visualization illustrates the hourly trend of daily orders. This chart allows us to identify peak hours or periods of high-order activity. 

3. Percentage of sales by Pizza category
   
![v3](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/8ba62eb4-69dc-418a-9fab-7af2191e0681)

This pie chart visualization shows the distribution of sales across different pizza categories. This chart helps to provide insights into the popularity of various pizza categories and their contribution to overall sales

4. Percentage of sales by Pizza size
   
![v4](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/c49aad39-4dcd-44ec-8abb-f9122e94d74e)

This Pie Chart represents the percentage of sales attributed to different pizza sizes. This chart helps us understand customer preferences for pizza sizes and their impact on sales.

5. Total pizzas sold by Pizza category

![v5](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/6ebcafaa-bcdb-4e6a-8aab-d822699ffb2b)

This Pie Chart represents the percent of total number of pizzas sold for each pizza category. This chart allows us to compare the sales performance of different pizza categories.

6. Top 5 best sellers by Total Pizzas sold
   
![v6](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/10435b62-39fc-46e3-99e7-2f3a77b028c7)

A bar chart highlighting the top 5 best-selling pizzas based on the total number of pizzas sold. This chart will help us identify the most popular pizza options.

7. Bottom 5 worst sellers by Total Pizza sold

![v7](https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/2958ef05-ea6c-47a1-a37a-43fe6b79f624)

This is a bar chart showcasing the bottom 5 worst-selling pizzas based on the total number of pizzas sold. This chart enables us to identify underperforming or less popular pizzas options. 

