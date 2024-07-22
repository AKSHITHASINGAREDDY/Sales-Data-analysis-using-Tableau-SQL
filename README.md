# Sales-Data-analysis-using-Tableau-SQL

## Requirements
01. download and setup MySQL
   import - sales.sql and perform EDA
    download tableau desktop to connect to MySQL and import above file
3. write sql queries to know about data and perform Explorative data analysis to identify missing values, null values, duplicates, date format and
    know avg, total, top 5 and other deatils using joins, date functions, string functions to convert date from string to date, joins
    the db contains transactions, customers, products, markets, date
   Show all customer records
# below are some of the queries

(i)Show total number of customers

SELECT count(*) FROM customers;

(ii)Show transactions for Chennai market (market code for chennai is Mark001)

SELECT * FROM transactions where market_code='Mark001';

(iii)Show distrinct product codes that were sold in chennai.

SELECT distinct product_code FROM transactions where market_code='Mark001';

(iv)Show transactions where currency is US dollars.

SELECT * from transactions where currency="USD"

(v)Show transactions in 2020 join by date table.

SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

(vi)Show total revenue in year 2020.

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

(vii)Show total revenue in year 2020, January Month.

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

(viii)Show total revenue in year 2020 in Chennai.

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020and transactions.market_code="Mark001";

03. Now open tableau and connect to MySQL and connect relationship between fact table to dimension tables (STAR Schema)
    transaction-fact table
    order,date, markets, products, customers- dimension tables
    also remove and null values
    normalize sales amount by using calculated field
    remove any negative values sales quantity(make sure data is cleaned and preprocessed before visualization)
    
5. create sheets and visualize data and combine to create and show in 1 dashboard and apply filters to all to get better understanding of by yearly or monthly selection.
