CouponFollow  
40 Triangle Center 
Suite 203  
Yorktown Heights, NY 10598   

# Senior Data Engineer Code Exercise

## About CouponFollow

Established in 2010, CouponFollow is a fast-growing, international company with  headquarters in New York. With 10 million monthly users, our two primary savings tools, CouponFollow and our Cently browser extension, have helped save shoppers over $400 million dollars by intelligently finding coupons, discovering deals and earning rewards. 

## Introduction to the Exercise

The exercises below are designed to confirm your skills and give you an idea of what some of the work you will encounter on the job might look like. At CouponFollow, a data engineer spends some of their time developing the data transformation layer (cleaning and modeling data using business logic to empower our clients to make better decisions) and some of their time writing code to solve various problems. We hire data engineers who seek to understand business processes, employ engineering best practices, are comfortable writing code tests, and who appreciate really good documentation. Should you have clarifying questions while you work on it, please don’t hesitate to reach out.

## Rubric

What we’ll be evaluating submissions on:

Code

- The code is accurate (produces what it intends to produce, without errors).
- The code is easy to read and interpret, including commenting where warranted.
- The code shows an eye for reusability and maintainability (DRY).
- The approach is valid (any math, aggregation, or other analysis).

Communications
- Comments are clearly written and suited to their audience.
- Communications demonstrate professionalism and are suited to the audience.
- Comments and communications demonstrate clarity of thought.

### Business Background

CouponFollow is a coupons and deals business which is primarily driven by anonymous traffic through Google. We have millions of site visitors each year, and most of the visitors have arrived to our site by searching for a specific retailer coupon (e.g.-- “ebay coupon”). Once a visitor reaches the CouponFollow site page, they are presented with a set of coupons and associated discount codes. After clicking out to a retailer from these coupon codes, the visitor is tracked using an affiliate link. We partner with many affiliate networks who enable us to collect commissions on orders completed on the retailer page (cost per acquisition) or commissions per click (CPC). 

### Requirements

Imagine you are working with a product manager to redesign our data warehouse, and as a proof of concept you are given a set of raw data files (attached with this exercise), and you’d like to create a data warehouse with the following schema:

![alt text](https://github.com/smiechom/sde_exercise/blob/main/db_schema.jpg?raw=true)

Using the files and schema provided, please build out your prototype data warehouse.

Your task will be to build a pipeline from Azure data source to database engine that you choose. You can use the database of your choice (SQL, NoSQL, Graph). However, it is worth noting that CouponFollow uses Snowflake. A free trial of Snowflake can be created here. 


### Files
You should be able to find the necessary files here: 
https://couponfollowrecruitment.blob.core.windows.net/dataenginer/Data.zip?st=2022-03-11T15%3A15%3A06Z&se=2022-03-25T15%3A15%3A00Z&sp=rl&sv=2018-03-28&sr=b&sig=%2BELWIrXbqH3F95zqrPjA3z%2F40JRCaBGTDaXC6H%2FOl3U%3D

To confirm, the files should include:

- Affiliate_Network.csv -
- Clicks.csv (Warning 1GB)
- CouponCodes.csv
- DomainNames.csv
- Orders.csv
- PageViews.csv (Warning 4GB)
- PartnerWebsites.csv
- Promotions.csv

Please note that the large CSV files will not fit into memory.

### Queries

Once you’ve created your database, we’d like you to showcase some work by running the following queries. Extra points will be given for minimizing the total number of queries used to solve these requirements.


- Top 3 retailers/advertisers by revenue  
- Top 3 retailers/advertisers by page views
- Average Commission Rate (Commission Rate = commissions/sale amount)
- Number of unique page views
- Rolling sum of order count
- Month-over-month comparison of revenue broken down by affiliate network (is revenue going up or down for the various affiliate networks?)


### Expected Output
- GitHub or zip file containing any code you used
- File with queries and output 
- Database diagram (from the data engine that you choose)

### Considerations
You can use any method to ingest data to the database (excluding SQL Server Integration Services) to import the data. However, your solution should specify:
- How you will schedule the data ingestion (either with a build-in scheduler or a trigger mechanism)
- How you will implement a trigger to process the arrival of new data in Azure Storage
- How you will host your solution

### Hints 
- CouponFollow works with Snowflake and dbt
- We process large amounts of data in regularly scheduled jobs to ensure that the data in our Snowflake data warehouse is as up-to-date as possible
- We connect to the warehouse with a variety of BI tools, like Tableau, PowerBI, or Sisense in order to visualize the data
- We highly value accurate and error-free data
- We work in a number of currencies, but we assess the performance of our business in US dollars
- We use GitHub internally to share and track code
- We believe that code is to be read and we should be able to understand the programmer's intent from the comments in the code
