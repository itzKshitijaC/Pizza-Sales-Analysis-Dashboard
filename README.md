# Pizza Sales Analysis Dashboard 📊

# Demo-Preview 🗺️

<img src="https://github.com/itzKshitijaC/Pizza-Sales-Analysis-Dashboard/assets/168798073/0fc036bd-a722-49d4-90eb-cd223c12d206" width="800" height="400" />

# The business Problem 🔍



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

