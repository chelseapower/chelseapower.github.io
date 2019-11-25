---
layout: post
title:      "Artist Recommendation System"
date:       2019-11-14 21:27:47 -0500
permalink:  recommendations
---

**Background**

For my capstone project, I reached out to a CEO of [AXS.com](http://axs.com) (whom I had worked for at [Live Nation](http://https://livenation.com) from 2006 - 2008) with the idea that I could gain access to anonymized proprietary AEG data. My original idea was seeking out Coachella Festival data where I wanted to connect festival online advertising with Twitter sentiment and coachella sales from 2015-2018 to predict if a user would attend coachella 2019 based on the artist lineup. (I was inspired after watching this [video](https://www.vox.com/2019/8/13/20801974/we-charted-pop-music-falsetto).) I quickly found out that this data wasn’t going to be easy to get access to but I did end up working with the lead of AXS’s data team to find a mutually beneficial data set to analyze for my final project.
 
So I set out to build a recommender system based on 100,000 rows (169 MB) of proprietary but anonymized demographic, ticket purchase, genre and [mosaic](https://www.experian.com/assets/marketing-services/product-sheets/mosaic-usa.pdf) data. This data set included 15 rows of mostly categorical variables and required that I one hot encide, frequency encode and label encode many of the columns. (This [article](https://towardsdatascience.com/all-about-categorical-variable-encoding-305f3361fd02) was really helpful in breaking down all of my options for converting categorical variables.) I also had to a bit of clean up like removing unnecessary columns, removing null values, and reducing results to get a dataframe that was ready to be run through some models.
 
**Supervised Models**

In my Logistic Regression test where I used **gender** as the predictor, my results only came to **52-54%** accuracy and precision, which isn’t great. So, I proceeded to a Random Forest Classifier and my model increased to **100%**!

![Random Forest Model Classification Report](http://drive.google.com/uc?export=view&id=1imfK5yOUjcJ67UZongdQshoByK8B-g2E)

I also plotted a feature importance chart:

![Features](http://drive.google.com/uc?export=view&id=133OnChK5XQSSlAh3xRdR0TKiy1n2fbdw)

The top features are: `headline`, `revenue_2018`, and `venue_name`.

**Recommender Systems**

So then I moved on to:

* Fit a recommender system model to a set of data
* Create a function that will return the top recommendations for a user
* Introduce a new user to a rating matrix and make recommendations for them

The model with the best results was **SVD** with `n_factors=20, reg_all=0.02`.

**Next Steps**

* Merge an artist ranking dataset and re-run the recommendation model.
* Try and chain all of the steps together into one function that asks users for ratings for a certain number of artists, then all of the above steps are performed to return the top n recommendations.
* Make a recommender system that only returns items that come from a specified genre.




