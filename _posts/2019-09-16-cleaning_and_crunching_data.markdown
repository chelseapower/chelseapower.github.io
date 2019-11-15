---
layout: post
title:      "Cleaning and Crunching Data "
date:       2019-09-16 14:40:16 -0400
permalink:  cleaning_and_crunching_data
---


For my Module 4 project, I decided to continue to work with Spotify streaming music data but took inspiration from next steps in a 2018 published paper and the nowplaying-RS dataset. By incorporating mood related hashtags and timestamps in a neural network to predict the emotion variation of the user based on the track they are playing, can this improve the **next song recommendation model**?

This project was the most difficult one yet. I was faced with cleaning and combining three separate CSV files where they grew from **11.6 million to over 17 million records** when joined. Because I knew the starting size of each file, my approach was to begin by cleaning the smallest dataset before joining it with the next most smallest dataset (in terms of columns). I focused on reducing noise (removing unnecessary columns, replacing important null columns with zeros, and remvoing rows with null values) and making business decisions about scaling down the data by setting rules like:

> **Remove tracks that were played less than 50 times**

This helped me quickly remove 12.4 million records before I moved to the final CSV file that included the detailed Spotify content track information. After cleaning it and then concatnating it with the previously cleaned dataset, I was able to quickly move to creating a predictor column and one-hot encode a valudable categorical column. 

> **Final MVP Datase: only 2,267,492 records!!!**

It took me about two weeks to get my dataset down to this size. Some of the time spent was due to the time that it takes to process this volumn of data. But the critical thinking and decision making is what really took most of the time. Because I'm not an experience python programmer, I spent a fair amount of type looking up ways to query the data in different ways to help me get to the decisions about how to manage it.

### Data Exploration

I always like to start by generating histograms for the data.

![Histogram](https://drive.google.com/uc?export=view&id=1eRoEaBKmyrwhpsvDXdpIXgRV6SVAXmNP)

Most of the data was skewed and had outliers. So then I checked for multicollinarity by generating a heatmap.

![Multicollinearity](https://drive.google.com/uc?export=view&id=1l_Ayu6ps5Ace4WMdK5qQ21LyTFMBSk6v)

Two variables showed to be highly correlated to each other (`loudness` and `energy`) but I decided to leave them in. 

My next challenge is dealing with the data being imbalanced which was similar to my Module 3 project. I immediately moved to upsampling and scaling the data to end up with a balanced dataset.

![Predictor scaled](https://drive.google.com/uc?export=view&id=1pSQ5RvFloq8Is650rj84LKVw_y1CFzG1)

### Summary

After all of the data cleaning and reduction efforts, my final results paid off. The final sequential neural network model predicts with **99% accuracy!** But then I went back and timed the processing time and my **supervised model** ran in 2 seconds with 99% accuracy vs. the neural network at 81 seconds.

You can view my jupyter notebook and presentation in my [Git Hub.](https://github.com/chelseapower/dsc-4-final-project-online-ds-pt-011419/) or try to build your own kernal on [Kaggle](https://www.kaggle.com/chelseapower/nowplayingrs).




