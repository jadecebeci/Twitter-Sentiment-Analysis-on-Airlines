# Twitter-Sentiment-Analysis-on-Airlines

<img src="images/akshar-dave-mkTqZN1NzhY-unsplash.jpg" width="800">

## Table of Contents

* [Business Understanding](#business-understanding)
* [Data Understanding](#data-understanding)
* [Modeling](#modeling)
* [Best Performing Model](#best-performing-model)
* [Conclusion and recommendation](#conclusion-and-recommendation)

## Business Understanding

Airline companies wants to use model to identify customers that are having a negative experience and direct tweets with negative sentiment towards the proper channel.

One way this might be accomplished would be to set up a bot that uses sentiment analysis to automatically identify tweets with negative sentiment, and then direct those tweets to the appropriate customer service representative or department for further assistance.

By implementing this system, the airline company can improve customer satisfaction by addressing negative experiences more quickly and efficiently, increase brand loyalty by showing that they value and take action on customer feedback.

## Data Understanding

The dataset used in this project is provided on Kaggle and originally collected by Crowdflower’s Data for Everyone library.

This Twitter data was scraped on **February 2015**. It contains tweets on six major United States (US) airlines: 
United, Us Airways, American, Soutwest, Delta and Virgin America.

Dataset has **14,640 entries** and **15 columns**.

We have three different target categories as **positive, neutral** or **negative** depend on tweet.

### Data Preparation and Exploration

- Duplicated rows were dropped and rows that had missing values were dropped

- Links, punctuation and stopwords were removed from the data prior to modeling. '#' was removed from twitter hashtags.
The data was small enough that lemmatization was usable to reduce the dimensionality of the data.

- To get a general idea of both the word frequencies and twitter sentiments several data visualizations were made:

<img src="images/WordCloud Positive.png" width="800">

- The meaningful words that can be spotted in the positive sentiments’ word cloud directly include **“thank”, “flight”** and **“great”**. This shows people tend to appreciate the airline on social media when they have positive flight experience.

<img src="images/WordCloud Negative.png" width="800">

- We observe from the word cloud that tweets related to **"flight"** and **"hour"** are causing the most negative tweets. And also **"cancelled","delayed", "customer"** and **"service"** have higher frequencies than other words.

<img src="images/EDA1.png" width="800">

- we can clearly see that these tweets are overwhelmingly **negative**.

<img src="images/EDA2.png" width="800">

- Most of the tweets belongs to **United Airlines** and followed by **US Airways , American**.

<img src="images/EDA3.png" width="800">

- Looking at the number of negative sentiments, **United Airline** ranks the first, followed by **US Airways Airline** and **American Airline**.

## Modeling
- Throughout the project, our goal was reducing False Negatives and False Positives

  -**False Positive:** Model predicts negative tweet but it's actually positive, leading to wrong customer service response and wasting company time/money.
  
  -**False Negative:** Model predicts positive tweet but it's actually negative, leading to lack of proper customer service and potential loss of customer.

- To balance the downsides of False Positive and False Negative, F1-score is used to find maximum negative sentiment tweets while avoiding incorrect customer service actions.

<img src="images/Comparing F1 Score.png" width="800">

<img src="images/Comparing Accuracy.png" width="800">

## Best Performing Model

-  Best accuracy and F1 score were achieved through parameter tuning with GridSearch on **Support Vector Classifier.**

<img src="images/Best Model CM.png" width="800">




