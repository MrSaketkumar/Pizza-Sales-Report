# Pizza-Sales-Report
This pizza sales dashboard is to deliver a comprehensive and data-driven view of business performance for a pizza outlet or chain. Specifically, it aims to:

Summarize key performance indicators (KPIs) such as total revenue, total orders, average order value, and average pizzas per order in a single glance.

Identify best- and worst-performing pizzas by:

Revenue

Order count

Quantity sold

Analyze customer behavior and preferences, including:

Most popular days and months for pizza orders

Preferred pizza categories (Classic, Supreme, Veggie, Chicken)

Preferred pizza sizes (Large, Medium, Regular, etc.)

Enable interactive exploration via filters (Pizza category, time period) for actionable insights by managers, marketers, or stakeholders.

Support decision-making in areas like promotions, inventory planning, and menu optimization.

I analyzed the Pizza_Sales data by using MySql_Server querry to gain insights into our business performance, 
for this i have calculated following metrics :-

1) Total Revenue

        SELECT.SUM(total_price) AS Total Revenue
         FROM pizza_sales;
2) Average Order Value

       SELECT SUM(total_price)/COUNT(DISTINCT(order_id)) AS Avg order value
        FROM pizza_sales;
3) Total Pizza Sales

       SELECT SUM(quantity) AS Total Pizza Sold
        FROM pizza_sales;
5) Total orders

       SELECT COUNT(DISTINCT(order_id)) AS Total Orders
        FROM pizza_sales;
6) Average Pizzas per order

         SELECT SUM(quantity)/COUNT(DISTINCT(order_id)) AS Avg order value
          FROM pizza_sales;
7) Daily Trend for total order

        SELECT DATENAME(DW, order_id) AS order_day COUNT(DISTINCT(order_id)) AS total_orders
         FROM pizza_sales
          GROUP BY DATENAME(DW,order_id);
8) Monthly Trend for Orders

       SELECT DATENAME(MONTH, order_date) AS Month_Name COUNT(DISTINCT(order_id)) AS total_orders
        FROM pizza_sales
         GROUP BY DATENAME(MONTH,order_id);;
   
9) % of sales by Pizza Category

        SELECT pizza_category, SUM(total_price) AS total_revenue,
         SUM(total_price)*100/(SELECT.SUM(total_price) FROM pizza_sales)
          FROM pizza_sales
            GROUP BY pizza_category;
10) % of sales by Pizza Size

        SELECT pizza_size, SUM(total_price) AS total_revenue,
         SUM(total_price)*100/(SELECT.SUM(total_price) FROM pizza_sales)
          FROM pizza_sales
            GROUP BY pizza_size ;
            
11) Total pizzas sold by Category
    
        SELECT pizza_category, SUM(quantity) AS Total Quantity Sold
         FROM pizza_sales
          GROUP BY pizza_category;
       
11) TOP 5 Pizzas by Revenue
   
        SELECT TOP 5 pizza_name, sum(total_price) AS Total_Revenue
         FROM pizza_sales
           GROUP BY pizza_name
            ORDER BY pizza_name DESC;
            
12) Bottom 5 Pizzas By Revenue
   
        SELECT TOP 5 pizza_name, sum(total_price) AS Total_Revenue
         FROM pizza_sales
          GROUP BY pizza_name
           ORDER BY pizza_name ASC;

From all this metrics, I visualize various aspects of pizza_sales data to gain insights and understands key trends.

Based on the visual analysis and data provided in the dashboard:

The business has generated a strong revenue of $817.86K, selling 50K pizzas across 21K orders, with an average order value of $38.31 and 2.32 pizzas per order.

Classic Deluxe pizza emerged as a consistent top-performer across revenue, quantity sold, and number of orders.

Thai Chicken and Barbecue Chicken pizzas are also top earners in terms of revenue, suggesting premium pricing or popularity.

Spinach Supreme, Green Garden, and Brie Caramelized Onion pizzas rank lowest across revenue and order metrics, signaling underperformance that may require promotional support or menu reevaluation.

Large-size pizzas dominate revenue (45.89%), while XX-Large sizes contribute almost nothing, suggesting a potential phase-out or repositioning opportunity.

Classic category leads in total pizzas sold (15K units), but other categories like Supreme, Veggie, and Chicken are not far behind, indicating balanced customer interest.

Friday is the busiest day of the week (3.5K orders), followed by Thursday and Saturday—ideal days for running high-impact promotions.

August records the highest monthly orders (1.9K), likely due to seasonal demand, while October shows a noticeable dip.
 
I Upload mysql data to POWER BI to create dashbords.
 
<img width="1291" height="723" alt="Screenshot 2025-07-17 013206" src="https://github.com/user-attachments/assets/9ae5dce5-549c-4f75-aa45-f5dd0aada497" />
<img width="1290" height="722" alt="Screenshot 2025-07-17 013143" src="https://github.com/user-attachments/assets/178db069-c1f3-4eef-a12e-d189cbdfff94" />
