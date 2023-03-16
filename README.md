# Sales Insights

#### Powerpoint Presentation Link:-
https://docs.google.com/presentation/d/1U61qH5c8lxyvJ9pNvYJTSZBQzVkjwKdc/edit?usp=sharing&ouid=105751002311733246477&rtpof=true&sd=true

#### Data Analysis using SQL  
  ##### 1.Show all customer records
  ```SELECT * FROM customers;```
  ##### 2.Show total number of customers  
      SELECT count(*) FROM customers;

  ##### 3.Show transactions for Chennai market (market code for Bengaluru is Mark006 
      SELECT * FROM transactions where market_code='Mark006';

  ##### 4.Show distrinct product codes that were sold in Bengaluru
         SELECT distinct product_code FROM transactions where market_code='Mark006';

  ##### 5.Show transactions where currency is US dollars  
      SELECT * from transactions where currency="USD"

  ##### 6.Show transactions in 2018 join by date table  
      SELECT transactions., date. FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018;

  ##### 7.Show total revenue in year 2018,  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and transactions.currency="INR\r" or transactions.currency="USD\r";

  ##### 8.Show total revenue in year 2018, February Month,  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and and date.month_name="February" and (transactions.currency="INR\r" or transactions.currency="USD\r");

  ##### 9.Show total revenue in year 2018 in Bengaluru  
      SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2018 and transactions.market_code="Mark006";

#### Data Analysis using Power Bi  
  ##### Formula to create norm_sales_amount column  
      = Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*82.40 else [sales_amount], type any)

## *Power BI User Interface: (Whole Years Report)*
