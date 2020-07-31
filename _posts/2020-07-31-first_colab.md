---
layout: post
title: First Notebook on Google Colab with Text and Sentiment Analyzing
date: 2020-07-31
---
In the first two weeks of July, I have completed my research in text analyzing by prototyping the American Data Scientist Job Market on Kaggle and tried to create one reinforcement ML model to analyzing text to regconize the sentiment of the comment of the dataset of MyAnimeList.

You can find my works here:

[First notebook](https://colab.research.google.com/drive/1q95p4tj_-IM3PZ4xg5NFTZsD_M6vvyqN?usp=sharing)

[Second notebook](https://colab.research.google.com/drive/1XDkETaNYf_V8AhFBXsxZeeu5vPBdc4dh?usp=sharing)

From my works with two datasets above, there are some notes for the further intepreting the raw dataset which the shape is unknown for analyzing text:

## 1. You have to figure out how to labeling the data you want to analyze
The method that I used in the first notebook is not based from the original version of the notebook that I prototyped. I used WordCloud library for find out the most used keywords and then determined how the data will be categorized by creating labels from the wordcloud you plotted. After creating the WC, I divided the data scientist jobs in the dataset to four labels and 'other' label: 'Data Scientist', 'Data Engineer', 'Data Analyst' and 'Data Manager'.

In the second notebook, I divided the labels of the comments based on the rate of the anime of each comment in the dataset. The method I used in this notebook is not totally perfect because I did not intepret too much into each element of the tags like storyRating or animationRating. 

## 2. The data is not clean enough
The main problem in the second notebook is my model is not precise enough since the loss still high and converge at the rate of 0,45. This was caused by the careless data cleaning process when I did not have the best way to analyze the comment section. This should be checked again in the next work.

## 3. The problem of the 'sigmoid' layer
The sigmoid layer of the model was not work properly. There are two problems:

The input data is not clean.
The sigmoid layer is not too good with 3 or more categorize analyzing when it returns negative loss.

## 4. The process of text analyzing
There are some approachs used from my works above. In the first notebook, I used the approachs with the nltk library. The code could be found in the notebook. In the second notebook, I used the Tensorflow library to analyzing the comment section. Both of the notebooks have the same process of text analyzing:

First, tokenize the whole text.
Second, lemmertize with the whole token we created.
Third, remove all the special charracters.

Because of different goals of two datasets so we have two ways to use the token that we had. In the first notebook, the token will be used for searching the patterns to answer our research questions. In the second notebook, we have to create the word vectors, then embedding the word vectors by change every vector to the same size for training. 

There are still lots of mistakes and bugs in my code of two notebooks and these are problems I approached while studying how to analyzing text. 