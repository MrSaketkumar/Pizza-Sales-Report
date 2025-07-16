# Pizza-Sales-Report
I analyzed the Pizza_Sales data by using MySql_Server querry to gain insights into our business performance, 
for this i have calculated following metrics :-
1) Total Revenue

   SELECT.SUM(total_price) AS Total Revenue
       FROM pizza_sales;
2) Average Order Value

   SELECT SUM(total_price)/COUNT(DISTINCT(order_id)) AS Avg order value
       FROM pizza_sales;
3) Total Pizza Sales

   SELECT SUM(quantity) AS Total Pizza Sold FROM pizza_sales;
4) Total orders

   SELECT COUNT(DISTINCT(order_id)) AS Total Orders
       FROM pizza_sales;
5) Average Pizzas per order

     SELECT SUM(quantity)/COUNT(DISTINCT(order_id)) AS Avg order value
         FROM pizza_sales;
6) Daily Trend for total order

    SELECT DATENAME(DW, order_id) AS order_day COUNT(DISTINCT(order_id)) AS total_orders
        FROM pizza_sales
         GROUP BY DATENAME(DW,order_id);
7) Monthly Trend for Orders

    SELECT DATENAME(MONTH, order_date) AS Month_Name COUNT(DISTINCT(order_id)) AS total_orders
       FROM pizza_sales
        GROUP BY DATENAME(MONTH,order_id);;
   
8) % of sales by Pizza Category

  SELECT pizza_category, SUM(total_price) AS total_revenue,
    SUM(total_price)*100/(SELECT.SUM(total_price) FROM pizza_sales)
     FROM pizza_sales
       GROUP BY pizza_category;
9) % of sales by Pizza Size
    
   SELECT pizza_size, SUM(total_price) AS total_revenue,
      SUM(total_price)*100/(SELECT.SUM(total_price) FROM pizza_sales)
         FROM pizza_sales
            GROUP BY pizza_size ;
            
10) Total pizzas sold by Category
    
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

# From all this metrics, I visualize various aspects of pizza_sales data to gain insights and understands key trends.
# I Upload mysql data to POWER BI to create dashbords.
<img width="1291" height="723" alt="Screenshot 2025-07-17 013206" src="https://github.com/user-attachments/assets/9ae5dce5-549c-4f75-aa45-f5dd0aada497" />
<img width="1290" height="722" alt="Screenshot 2025-07-17 013143" src="https://github.com/user-attachments/assets/178db069-c1f3-4eef-a12e-d189cbdfff94" />
