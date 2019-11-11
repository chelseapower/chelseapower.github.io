---
layout: post
title:      "Working with SQLAlchemy"
date:       2019-11-11 02:16:31 -0500
permalink:  working_with_sqlalchemy
---


For my second data science project, I started by closely examining the Northwind database schema in order to come up with the hypothesis statements and tests I would run. The three project hypothesis questions that I set out to prove were:

1. Discounts have an effect on the number of products ordered.
2. Revenue per order varies by different regions.
3. There is a regional difference in quantity of Chai sold from North America.

So to get started, I decided to use SQLAlchemy to query the project database and constantly referred to this [site](https://www.pythonsheets.com/notes/python-sqlalchemy.html). 
 
![SQLAlchmey](http://drive.google.com/uc?export=view&id=1JxKwSRP2iH5fsU3A_77DV9bWdzDm1W0O)
 
As you can see I started by bringing in the Order Detail table as it contains all of the fields I need for the first question. From here, I split the data into two separate groups to test the difference.
![Split1](http://drive.google.com/uc?export=view&id=1PJNEk-8kfiGYH0k2GBSQjjw5WeeU5J0K)
 
Then I plotted the data, ran a normality test, created a sample distribution of the sample mean (because the data is skewed), and performed an ANOVA test that resulted with **p (4.7e-09) < α** where I could reject the null hypothesis.

For my second question, I brought in a new set of fields that focused on the customer orders by region. 

![Query2](http://drive.google.com/uc?export=view&id=1ZJQA7Hxj9v5asafyelWAUg0kW5yvpvds)

As you can see, I also left joined order and order details so I could work with all of the fields and information needed for this question's analysis. Here is a another [site](https://www.diffen.com/difference/Inner_Join_vs_Outer_Join) that I used to clarify the type of join that was needed.

This is the section where I was challenged working with `groupby` for the first time in order to manipulate the data (as you would in a tool like excel) and output bar charts. Luckily, my instructor directed me to this [site](https://chrisalbon.com/python/data_wrangling/pandas_apply_operations_to_groups/) that helped me figure things out.

![chart1](http://drive.google.com/uc?export=view&id=1rJ0MTAyVPhQA19gRhmEBBjXDDeXv45I-)

I proceeded with the same tests (as noted above in Question 1) and ended up with the result **p (1.0) < α** where I again rejected the null hypothesis.

For my final question, I pulled in the supplier and product tables in order to answer the question about chai sales by region. 

![query3](http://drive.google.com/uc?export=view&id=1MG_1bXhivPnJK8oNJTlUXf5w44v0bpi8)

At this point, I was finally getting the hang of how to use groupby to display my data and it was very straightforward in creating the chai by region chart.

![chart2](http://drive.google.com/uc?export=view&id=1VCWAhBzZjr0e_syt8JwsrW_xkXO2tOXm)

After a normality test, create a sample distribution of the sample mean, and performing an ANOVA test, the result again was **p (1.0) > α**, so the null hypothesis was rejected again. The amount of Chai sold is different between the supplier sources of North America vs. other regions.

To wrap things up, I added a final question.

> Do customers in North America purchase the same quantity as other regions?














