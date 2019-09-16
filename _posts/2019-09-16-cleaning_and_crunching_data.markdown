---
layout: post
title:      "Cleaning and Crunching Data "
date:       2019-09-16 18:40:15 +0000
permalink:  cleaning_and_crunching_data
---


For my Module 4 project, I was faced with cleaning and combining three separate CSV files where they grew from 11.6 million to over 17 million records. Knowing the starting size of each file, my approach was to start by cleaning the smallest dataset before joining it with the next most smallest dataset (in terms of columns). I focused on reducing noise (removing unnecessary columns, replacing important null columns with zeros, and remvoing rows with null values) and making business decisions about scaling down the data by setting rules like:


> **Remove tracks that were played less than 50 times**

This helped me quickly remove 12.4 million records before I moved to the final CSV file that included the detailed Spotify content track information. After cleaning it and then concatnating it with the previously cleaned dataset, I was able to quickly move to creating a predictor column and one-hot encode a valudable categorical column.


> **Final MVP Datase: 2,267,492 records!!!**


### Data Exploration

I always like to start by generating histograms for the data.

![Histogram](https://drive.google.com/file/d/1cNHampIv4grkqfBjcsqY_YCX3oyIafUX/view?usp=sharing)

Most of the data is skewed and has outliers. So then I checked for multicollinarity by generating a heatmap.

![Multicollinearity](https://drive.google.com/file/d/1YEdMJZMkF3syB6iBmwSicRjNwocUqtXa/view?usp=sharing)

Two variables showed to be correlated to each other but I leave them in for now. My next challenge is dealing with the data being imbalanced. After upsampling and scaling the data, I end up with a balanced dataset!

![Balanced Predictor Column](https://drive.google.com/file/d/1uRTvOdAiIXgQjX88SIItWu8Nbqi-aLKr/view?usp=sharing)

### Summary

After all of the data cleaning and reducing effort, my final results paid off. The final sequential neural network model predicts with **100% accuracy**!




