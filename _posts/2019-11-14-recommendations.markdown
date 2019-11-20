---
layout: post
title:      "Artist Recommendation System"
date:       2019-11-14 21:27:47 -0500
permalink:  recommendations
---

**Background**

For my capstone project, I reached out to a CEO of [AXS.com](http://axs.com) (whom I had worked for at [Live Nation](http://https://livenation.com) from 2006 - 2008) with the idea that I could gain access to anonymized proprietary AEG data. My original idea was seeking out Coachella Festival data where I wanted to connect festival online advertising with twitter sentiment and coachella sales from 2015-2018 to predict if a user would attend coachella 2019 based on the artist lineup. (I was inspired after watching this [video](https://www.vox.com/2019/8/13/20801974/we-charted-pop-music-falsetto).) However, as it turned out, this data wasn’t going to be easy to get access to but I did end up working with the lead of AXS’s data team to find a mutually beneficial data set to analyze for my final project.
 
So I set out to build a recommender system based on 100,000 rows (169 MB) of proprietary but anonymized demographic, ticket purchase, genre and [mosaic](https://www.experian.com/assets/marketing-services/product-sheets/mosaic-usa.pdf) data. This data set included 15 rows of mostly categorical variables and required that I one hot encide, frequency encode and label encode many of the columns. (This [article](https://towardsdatascience.com/all-about-categorical-variable-encoding-305f3361fd02) was really helpful in breaking down all of my options for converting categorical variables.) I also had to a bit of clean up like removing unnecessary columns, removing null values, and reducing results to get a dataframe that was ready to be run through some models.
 
**Supervised Models**

In my Logistic Regression test where I used **gender** as the predictor, my results only came to **52-54%** accuracy and precision, which isn’t great. So, I proceeded to a Random Forest Classifier and my model increased to **100%**!


