---
layout: post
title:      "Using Histograms to Problem Solve"
date:       2019-11-10 21:18:47 -0500
permalink:  using_histograms_to_problem_solve
---


For my first data science project, I used histograms several times in this assignment to evaluate the detailed distributions of my dataset. A histogram shows the underlying frequency distribution (shape) of a set of continuous data. These visualizations are especially useful for taking an early look at data distributions to check and see which variables are normal or skewed. In the image below, you can see how obvious it is that this project data is very skewed.

![Histogram1](http://drive.google.com/uc?export=view&id=1AATSW8F2gDRgx3TJir6JiNKActI6UpOD)

After doing quite a bit of work to properly classify the data types, clean the rows, and remove the outliers per variable, the revised histogram below shows the updates.

![Histogram2](http://drive.google.com/uc?export=view&id=1nPBFAoes2vJd2Pn1b2qiIyXYiR0UqWYW)

Even though many of the variables are still skewed, the distributions are starting to look better.  The next step in my process was to log transform the dataset to look at normalized data that may help to balance the distributions further. Below are the log transformed results.

![Histogram2](http://drive.google.com/uc?export=view&id=1HRp4RZduX9Mit0FSfp_jiOtkYqCuRcw0)

These distributions look the best of all! 

The key thing to remember about histograms is that even though they look like a bar chart, they can only plot the frequency of occurrences for **continuous data** that has been divided into classes or bins. Bar charts on the other hand can be used to represent a number of other types of variables.

So in conclusion, histograms are very valuable to use and I recommend including them in every data science project. However, they do have limitations that are based on the type of data you are trying to model.
