# Josh Galloway Portfolio
Selected projects from my work in data science, statistics, and numerical analysis.

## RNN Application: Predicting VIX Ticker Volatility from Headlines

Working from publicly available data sources, the student trained a recursive neural network (RNN) implemented in Python (pandas, sklearn, keras) to predict the Chicago Board Options Exchange (CBOE) Volatility Index (VIX). An ad hoc method of sentiment quantification was applied to datasets containing Reddit and ABC headlines spanning several years. The result was a trained RNN that was able to predict the Delta VIX closing day over day based on the headlines from the previous 20 trading days.
<br>
Once  trained,  the  network  was  scored  against  a  test  set  to  root-mean-squared  error (RSME),  and  evaluated  again  by  graphing  the  results  of  the  prediction  against  the recorded  data  set.   The  RMSE  was  1.87  for  the  ABC  dataset  against  the  segregated test set, and 2.07 for the Reddit.  The predictions graphed against the ABC datase is shown below, and the full writeup pdf is available [here](https://github.com/jgalloway42/MS-Applied-Mathematics-Projects/blob/master/Math_7243_Machine_Learning_Final_Project_r3.pdf).

![](/images/VIX%20Prediction%20ABC%20Headlines%20Results.png)

## Unsupervised Learning: Clustering of News Headlines for Sentiment Analysis
The goal of the project was to analyze a collection of news headlines to identify reoccurring sentiment themes. The dataset was comprised of roughly 1.25 million headlines and is the synthesis of two datasets publicly available on Kaggle. The news sources from which the headlines were pulled were Reddit’s WorldNews channel and ABC which is an Australian news organization. The time span for the collective dataset was roughly from 2003 to 2019. This project utilized skills in natural language processing (NLP) and unsupervised machine learning techniques in clustering analysis.  
![](/images/TF%20and%20TFIDF%20Wordcloud.png)

The K-means LDA-based model performed best based on Silhouette coefficient and CH score metrics.  In fact, the LDA-based models performed better in all cases with the exception of DBSCAN.  This is likely due to the additional sophistication in the LDA algorithm from the inclusion of extra latent variables versus the non-negative matrix factorization.

![](/images/KMeans%20LDA%203d%204%20views.png)

Comparing the models in a confusion matrix shows only a few labels were in disagreement. Inspecting these disagreements on a PCA-reduced two dimensional graphing of the LDA dataset clarifies the region of disagreement for all the algorithms is generally between the boundary of cluster 0 and 3.  Inspecting the topics closest to the Cluster 0 and 3 centroids shows that the two topics are slightly similar with the words ‘fear’ and ‘warns’ and other vaguely worrisome words associated with each topic.

![](in/images/confusion_matrtix.png)

The reserved test set was utilized to measure the performance of the model. Using only words from the model’s 2000 term vocabulary, the headlines in the test set were scored for sentiment; following which, the K-Means model was used to predict a label for each headline. Each randomly selected 50-point testing fold was scored on Silhouette coefficient and CH score.  The CH score distribution was very tail heavy showing high levels of clustering performance for a significant portion of the folds.  The box plot for the CH score distribution shows many outliers to the higher performing side of the interquartile range.  The Silhouette coefficient distribution was shown to be roughly normal with a mean score of 0.66 and 95% confidence interval from 0.55 to 0.76.

![](/main/images/Bootstrapping%20Results.png)

In both cases, the scoring was improved on the test set over the training score. This is likely due to duplication of topics between headlines creating tighter clusters with more distance between them, as this would improve either metric.PDF of the presentation may be found [here](https://github.com/jgalloway42/MS-Applied-Mathematics-Projects/blob/master/DS%205230%20Unsupervised%20ML/Galloway-DS5230-Final%20Project%20Report.pdf). 

