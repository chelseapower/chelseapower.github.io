---
layout: post
title:      "Using Histograms to Problem Solve"
date:       2019-11-10 21:18:47 -0500
permalink:  using_histograms_to_problem_solve
---


For my first data science project, I used histograms several times in this assignment to evaluate the detailed distributions of my dataset. These visualizations are especially useful for taking an early look at data distributions to check to see which variables are normal or skewed. In the image below, you can see how obvious it is that this project data is very skewed.

![Histogram1](http://drive.google.com/uc?export=view&id=1AATSW8F2gDRgx3TJir6JiNKActI6UpOD)

After doing quite a bit of work to properly classify the data types, clean the rows, and remove the outliers per variable.

![Histogram2](http://drive.google.com/uc?export=view&id=1nPBFAoes2vJd2Pn1b2qiIyXYiR0UqWYW)

Even though many of the variables are still skewed, the distributions look a lot better.  The next step in this process was to log transform the dataset to them to see if normalizing the data would help to balance the data distributions further. Below are the log transformed results.

![Histogram2](http://drive.google.com/uc?export=view&id=1HRp4RZduX9Mit0FSfp_jiOtkYqCuRcw0)
