---
layout: post
title:      "Classification Machine Learning Project"
date:       2019-11-10 18:34:54 -0500
permalink:  module_3_project
---


For my Module 3 project, I spent over a week before I landed on using a Spotify dataset to build a deep neural network and predict whether a song would be played or not played/skipped. My biggest challenge for two different project topics of interest was finding an appropriate dataset.

My first choice was using the [Barcelona](https://www.kaggle.com/xvivancos/barcelona-data-sets) dataset from Kaggle to determine how if you would have an accident based on your neighborhood. Unfortunately, this dataset didn’t have enough continuous features and/or the minimum amount of rows (50,000). The second dataset I was excited about (also from Kaggle) was about accidents in [France](https://www.kaggle.com/ahmedlahlou/accidents-in-france-from-2005-to-2016#places.csv) but I had the same issue where it didn’t have enough continuous features. 

So back to the project dataset I ended up working on as my Machine Learning Classification project. 

The 2018 Spotify user streaming session and track information required merging two CSV files, closely analyzing the feature set and reducing the amount of features from 51 to 33 to determine if a track will be played or skipped using the predictor variable **not_skipped**. 

## Observe

I read in each of the Spotify CSV files, renamed and reordered columns so they could be merged with an inner join into a single dataset with 167,880 rows and 50 columns.

![MergeCSV](https://drive.google.com/uc?export=view&id=1bEB9XnyLGFeZiY2IkhGfqsuOsMY1pQP5)


Based on the [documentation](https://developer.spotify.com/documentation/web-api/reference/object-model/) provided by Spotify, I was able to quickly identify 16 unnecessary / categorical features.

## Scrub

After removing the unnecessary / categorical features, I then verified that there weren't any null values in the remaining columns.

![Drop](https://drive.google.com/uc?export=view&id=1abDOQCfR5sT9LDXIFma4T7-4mw4dQWxK)

![LambdaCheckNulls](https://drive.google.com/uc?export=view&id=1PT_j_wFQi6fmzqdAjWV4G6NIA5p0H-Lt)

I also checked to see how the data looked with my predictor variable **not_skipped**.

![ValueCounts](https://drive.google.com/uc?export=view&id=1TThk0gIzmtu0MXKO31GPgvJHKCYsgGHZ)

This showed that the data was unbalanced but I proceed with exploring the data further.

## Explore

From the continuous dataset, I reviewed the distrubutions of the data and confirmed that there are only about nine features with normal distributions.

![Heatmap](https://drive.google.com/uc?export=view&id=1RvJqrEBYH-0qgPps4W4GKqoyLVsUwb1x)

The heatmap below showed multicolinarity for `beat_strength` and `bounciness` so `bounciness` is dropped before I test and train the data. 

![Normalize](https://drive.google.com/uc?export=view&id=1zyaQouKUm9wEYiZqpzs7hV8cxbCv6SEG)

## Model

Because I know that my data is unbalanced (and in my first jupiter notebook I modeled my project without resampling that resulted in poor results), I run through the following steps to resample the data to balance it.

![resample](https://drive.google.com/uc?export=view&id=1R4K-kIqSue4h8Lx5REzgxl7xPnoVTKiD)
![resample2](https://drive.google.com/uc?export=view&id=1WIltT8pr05B3UU4t_u0jRzlhVF_NLS1Y)

Finally, I run another Logistic Regression Model with resampled data and continue to validate my model with a confusion matrix, ROC Graph, random forest classifier, and hyperparameter tune with GridSearchCV. After all of these steps, I conclude that the model with the best accuracy is the first **Random Forest Classifier with 91% accuracy and precision**.




