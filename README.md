# Sales-Insights-Project

## Abstract
In this project I will be conducting a basic sales analysis using MySQL and Tableau.
## Introduction
This project will show how you can download data from MySQL, perform preliminary data analysis, extract, transform and load data into Tableau.

Next, we will build 2 different dashboards on Tableau showing the revenue and profit of various sales.

At the end of the project, we will visualize the revenue and profit trends for various years starting from 2017 to 2020.
## Purpose 
To unlock sales insights that are not visible to the  sales team  in order to enable decision support and automate them in order to reduce the time spent in data gathering.
## Stakeholders
The results obtained in this project can be used by various stakeholders such as 
* Sales director
* Marketing team
* Customer service team
* Data and analytics team
* IT
## Objective
An automated dashboard providing quick and latest sales in order to support data driven decision making.
## Code and Resources used

**MySQL workbench Version**:8.0

**Tableau Version**:2022.3.1.

**Data Source**:https://github.com/codebasics/DataAnalysisProjects/blob/master/1_SalesInsights/db_dump.sql (part 1) 

** Data Source**:https://github.com/codebasics/DataAnalysisProjects/blob/master/1_SalesInsights/db_dump_version_2.sql (part 2)
## Data Collection
The data used in this project was downloaded from  [https://ourworldindata.org/coronavirus](https://github.com/codebasics/DataAnalysisProjects/blob/master/1_SalesInsights/db_dump.sql) for part 1 and (https://github.com/codebasics/DataAnalysisProjects/blob/master/1_SalesInsights/db_dump_version_2.sql) for part 2. I then read the sql files using the using MySQL workbench.

## Data Analysis using MySQL
* Show all customer records

`SELECT * FROM customers();`
* Show total number of customers

`SELECT count(*) FROM customers;`

* Show transactions for the Mumbai market (market code for mumbai is Mark002)

`SELECT * FROM transactions where market_code='Mark002';`

* Show distinct product codes that were sold in mumbai

`SELECT distinct product_code FROM transactions where market_code='Mark002';`

* Show transactions where currency is US dollars

`SELECT * from transactions where currency="USD";`

* Show transactions in 2020 join by date table

`SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

* Show total revenue in year 2020

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`

* Show total revenue in year 2020, January Month

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

* Show total revenue in year 2020 in Mumbai

`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark002";`

## Data Analysis using Tableau
