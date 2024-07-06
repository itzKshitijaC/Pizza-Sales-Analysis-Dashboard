# Pizza Sales Analysis Dashboard 📊

# The business Problem 🔍

### KPI's Requirements 

We need to analyze key indicators for our pizza sales data to gain insights into our business performance. Specifically, we want to calculate the following metrics

<b>1. Total Revenue: </b> The sum of the total price of all the pizza orders 

<b>2. Average order value: </b> The average amount spent per order, calculated by dividing the total revenue by the total number of orders 

<b>3. Total Pizza Sold: </b> The sum of quantities of all the pizza sold 

<b>4. Total Orders: </b> The total number of orders placed

<b>5. Average pizza per order: </b> The average number of pizzas sold per order, calculated by dividing the total number of pizzas sold by total number of orders

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


