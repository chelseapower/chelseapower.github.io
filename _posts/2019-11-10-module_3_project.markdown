---
layout: post
title:      "Classification Machine Learning Project"
date:       2019-11-10 18:34:54 -0500
permalink:  module_3_project
---


For my Module 3 project, I spent over a week before I landed on using a Spotify dataset to build a deep neural network and predict whether a song would be played or not played/skipped. My biggest challenge for two other topics of interest was finding an appropriate dataset.

My first choice was using the [Barcelona](https://www.kaggle.com/xvivancos/barcelona-data-sets) dataset from Kaggle to determine if you would have an accident based on your neighborhood. Unfortunately, this dataset didn’t have enough continuous features and/or the minimum amount of rows (50,000). The second dataset I was excited about (also from Kaggle) was about accidents in [France](https://www.kaggle.com/ahmedlahlou/accidents-in-france-from-2005-to-2016#places.csv) but I had the same issue where it didn’t have enough continuous features. So onto the project dataset I ended up working on as my Machine Learning Classification project. 

The 2018 Spotify dataset consisted of user streaming session data and track information for a total of 51 features and over 100,000 rows. It required merging two CSV files together into a single set and then closely analyzing the feature set to reduce it down to 33 features in order to determine if a track will be played or skipped using the predictor variable **not_skipped**. 

## Observe

After reading the CSV files through pandas, I immedinately renamed and reordered columns so they could be merged with an inner join into a single dataset with 167,880 rows and 50 columns.

![MergeCSV](https://drive.google.com/uc?export=view&id=1bEB9XnyLGFeZiY2IkhGfqsuOsMY1pQP5)


Based on the [Spotify documentation](https://developer.spotify.com/documentation/web-api/reference/object-model/), I was able to quickly identify 16 unnecessary / categorical features and dropped them.

## Scrub

After removing the unnecessary / categorical features, I then verified that there weren't any null values in the remaining columns.

![Drop](https://drive.google.com/uc?export=view&id=1abDOQCfR5sT9LDXIFma4T7-4mw4dQWxK)

![LambdaCheckNulls](https://drive.google.com/uc?export=view&id=1PT_j_wFQi6fmzqdAjWV4G6NIA5p0H-Lt)

I also checked to see how the data looked with my predictor variable **not_skipped**.

![ValueCounts](https://drive.google.com/uc?export=view&id=1TThk0gIzmtu0MXKO31GPgvJHKCYsgGHZ)

This showed that the data was unbalanced but I proceeded in exploring the data further knowing that I would need to come back and balance the data out.

## Explore

From the continuous dataset, I reviewed the distrubutions of the data and confirmed that there were only about nine features with normal distributions.

![Heatmap](https://drive.google.com/uc?export=view&id=1RvJqrEBYH-0qgPps4W4GKqoyLVsUwb1x)

The heatmap below showed multicolinarity for `beat_strength` and `bounciness` so `bounciness` is dropped before I test and train the data. 

![Normalize](https://drive.google.com/uc?export=view&id=1zyaQouKUm9wEYiZqpzs7hV8cxbCv6SEG)

## Model

Because I know that my data is unbalanced (and in my first jupiter notebook I modeled my project without resampling that resulted in poor results - 50% accuracy), I tried SMOTE and nothing changed. I got stumped here and had to reach out to my instructor who lead me to the following steps to resample the data and balance it.

![resample](https://drive.google.com/uc?export=view&id=1R4K-kIqSue4h8Lx5REzgxl7xPnoVTKiD)
![resample2](https://drive.google.com/uc?export=view&id=1WIltT8pr05B3UU4t_u0jRzlhVF_NLS1Y)

So now that everything looked good, I was able to:

* run another logistic regression model with resampled data,
* validate my model with a confusion matrix, ROC Graph, random forest classifier, 
* and hyperparameter tune with GridSearchCV

After all of these models were run, I was able to conclude that the model that provided best results was the first **Random Forest Classifier with 91% accuracy and precision**. This project was challenging but fun and I'm looking forward to the next one!




