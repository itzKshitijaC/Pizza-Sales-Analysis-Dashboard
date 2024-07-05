# Pizza Sales Analysis Dashboard 📊

# The business Problem 🔍

### KPI's Requirements 

We need to analyze key indicators for our pizza sales data to gain insights into our business performance. Specifically, we want to calculate the following metrics

<b>1. Total Revenue: </b> The sum of the total price of all the pizza orders 

<b>2. Average order value: </b> The average amount spent per order, calculated by dividing the total revenue by the total number of orders 

<b>3. Total Pizza Sold: </b> The sum of quantities of all the pizza sold 

<b>4. Total Orders: </b> The total number of orders placed

<b>5. Average pizza per order: </b> The average number of pizzas sold per order, calculated by dividing the total number of pizzas sold by total number of orders

# Pizza Sales SQL Queries 👩🏻‍💻

1. Total Revenue:

        SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;
   
2. Average Order Value

        SELECT (SUM(total_price) / COUNT(DISTINCT order_id)) AS Avg_order_Value FROM pizza_sales

3. Total Pizzas Sold

        SELECT SUM(quantity) AS Total_pizza_sold FROM pizza_sales

4. Total Orders

        SELECT COUNT(DISTINCT order_id) AS Total_Orders FROM pizza_sales

5. Average Pizzas Per Order

        SELECT CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / 
        CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) AS DECIMAL(10,2))
        AS Avg_Pizzas_per_order
        FROM pizza_sales

6. Daily Trend for Total Orders

        SELECT DATENAME(DW, order_date) AS order_day, COUNT(DISTINCT order_id) AS total_orders 
        FROM pizza_sales
        GROUP BY DATENAME(DW, order_date)

7. Hourly Trend for Orders

        SELECT DATEPART(HOUR, order_time) as order_hours, COUNT(DISTINCT order_id) as total_orders
        from pizza_sales
        group by DATEPART(HOUR, order_time)
        order by DATEPART(HOUR, order_time)

8. % of Sales by Pizza Category

        SELECT pizza_category, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
        CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
        FROM pizza_sales
        GROUP BY pizza_category

9. % of Sales by Pizza Size

        SELECT pizza_size, CAST(SUM(total_price) AS DECIMAL(10,2)) as total_revenue,
        CAST(SUM(total_price) * 100 / (SELECT SUM(total_price) from pizza_sales) AS DECIMAL(10,2)) AS PCT
        FROM pizza_sales
        GROUP BY pizza_size
        ORDER BY pizza_size

10. Total Pizzas Sold by Pizza Category

        SELECT pizza_category, SUM(quantity) as Total_Quantity_Sold
        FROM pizza_sales
        WHERE MONTH(order_date) = 2
        GROUP BY pizza_category
        ORDER BY Total_Quantity_Sold DESC

11. Top 5 Best Sellers by Total Pizzas Sold

        SELECT Top 5 pizza_name, SUM(quantity) AS Total_Pizza_Sold
        FROM pizza_sales
        GROUP BY pizza_name
        ORDER BY Total_Pizza_Sold DESC

12. Bottom 5 Best Sellers by Total Pizzas Sold

        SELECT TOP 5 pizza_name, SUM(quantity) AS Total_Pizza_Sold
        FROM pizza_sales
        GROUP BY pizza_name
        ORDER BY Total_Pizza_Sold ASC









