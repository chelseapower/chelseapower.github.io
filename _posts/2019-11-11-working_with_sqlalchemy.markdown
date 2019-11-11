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
 
Then I plot the data, run a normality test, create a sample distribution of the sample mean (because the data is skewed), perform an ANOVA test and I end up with a the result **p (4.7e-09) < α**, and rejected the null hypothesis.

For my second question, I bring in a new set of fields that focus on the customer orders by region. 

![Query2](http://drive.google.com/uc?export=view&id=1ZJQA7Hxj9v5asafyelWAUg0kW5yvpvds)

This is the section where I had a challenge working with `groupby` for the first time in order to manipulate the data (as you would in a tool like excel) and output bar charts. Luckily, my instructor directed me to this [site](https://chrisalbon.com/python/data_wrangling/pandas_apply_operations_to_groups/) that helped me figure things out.

![chart1](http://drive.google.com/uc?export=view&id=1rJ0MTAyVPhQA19gRhmEBBjXDDeXv45I)

I proceeded with the same tests as noted above in Question 1 and ended up with the result **p (1.0) < α**, and rejected the null hypothesis again.

For my final question, I pulled in the supplier and product tables in order to answer the question about chai sales by region. 

![Query3](http://drive.google.com/uc?export=view&id=1MG_1bXhivPnJK8oNJTlUXf5w44v0bpi8)








