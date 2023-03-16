# Sales Insights

#### Powerpoint Presentation Link:-
https://docs.google.com/presentation/d/1U61qH5c8lxyvJ9pNvYJTSZBQzVkjwKdc/edit?usp=sharing&ouid=105751002311733246477&rtpof=true&sd=true

#### Data Analysis using SQL  
  ##### 1.Show all customer records
  ```SELECT * FROM customers;```
  ##### 2.Show total number of customers  
      SELECT count(*) FROM customers;

  ##### 3.Show transactions for Chennai market (market code for Mumbai is Mark002 
      SELECT * FROM transactions where market_code='Mark002';

  ##### 4.Show distrinct product codes that were sold in Mumbai
         SELECT distinct product_code FROM transactions where market_code='Mark002';

  ##### 5.Show transactions where currency is US dollars  
      SELECT * from transactions where currency="USD"

  ##### 6.Show transactions in 2018 join by date table  
      SELECT transactions., date. FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

  ##### 7.Show total revenue in year 2020,  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

  ##### 8.Show total revenue in year 2020, February Month,  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="February" and (transactions.currency="INR\r" or transactions.currency="USD\r");

  ##### 9.Show total revenue in year 2020 in Bengaluru  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark002";

#### Data Analysis using Power Bi  
  ##### Formula to create norm_sales_amount column  
      = Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*82.40 else [sales_amount], type any)

## **Power BI User Interface: (Whole Years Report)**
![image](https://user-images.githubusercontent.com/91029423/225554771-6f54a75a-b25b-4ebd-a593-d66c68b371b7.png)
## **Power BI User Interface: (Specific Year 2020 Report)**
![image](https://user-images.githubusercontent.com/91029423/225555286-e2b63df5-885c-4878-b482-b218b2487941.png)
## **Power BI User Interface: (Mumbai for year 2020 Report)**
![image](https://user-images.githubusercontent.com/91029423/225555857-f66205c6-7a1e-40b2-933b-6b2c886cf788.png)
