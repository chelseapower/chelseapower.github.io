---
layout: post
title:      "Classification Machine Learning Project"
date:       2019-11-10 18:34:54 -0500
permalink:  module_3_project
---


For a Machine Learning Classification project, I used 2018 Spotify user streaming session and track information. This project required merging two CSV files, closely analyzing the feature set and reducing the amount of features from 51 to 33 to determine if a track will be played or skipped using the predictor variable **not_skipped**. 

## Observe

I read in each of the Spotify CSV files, renamed and reordered columns so they could be merged with an inner join in a single dataset with 167,880 rows and 50 columns.

![CSV Merge](<https://drive.google.com/uc?export=view&id=1bEB9XnyLGFeZiY2IkhGfqsuOsMY1pQP5)

Based on the [documentation](https://developer.spotify.com/documentation/web-api/reference/object-model/) provided by Spotify I was able to quickly identify 16 unnecessary / categorical features.

## Scrub

After removing the unnecessary / categorical features, I then verified that there weren't any null values in the remaining columns.

![Drop](<https://drive.google.com/uc?export=view&id=1abDOQCfR5sT9LDXIFma4T7-4mw4dQWxK)

![LambdaCheckNulls](https://drive.google.com/uc?export=view&id=1PT_j_wFQi6fmzqdAjWV4G6NIA5p0H-Lt)

I also check to see how the data looks with my predictor variable **not_skipped**.

![ValueCounts](https://drive.google.com/uc?export=view&id=1TThk0gIzmtu0MXKO31GPgvJHKCYsgGHZ)

This showed that the data is unbalanced.

## Explore

So I then create continuous dataset and take a quick look at the distrubutions of the data and confirm that there are only about nine features with normal distributions.

The heatmap below shows multicolinarity for `beat_strength`, and then `dyn_range_mean` so these two additional features are dropped before I test and train the data.

![Heatmap](https://drive.google.com/uc?export=view&id=1RvJqrEBYH-0qgPps4W4GKqoyLVsUwb1x)

But since this is a classification project, I have to normalize the data prior to fitting the model.

![Normalize](https://drive.google.com/uc?export=view&id=1zyaQouKUm9wEYiZqpzs7hV8cxbCv6SEG)

## Model

Because I know that my data is unbalanced (and in my first jupiter notebook I modeled my project without resampling that resulted in poor results), I run through the following steps to resample the data to balance it.

![resample](https://drive.google.com/uc?export=view&id=1R4K-kIqSue4h8Lx5REzgxl7xPnoVTKiD)

After running Train-Test Split, Predicting, Interperting, I created a Confusion Matrix and ROC / AOC Curve.




