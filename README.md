## SubReddit Classification

### Background:
As the internet solidifies itself as the primary forum for discussions of virtually every topic, it has become increasingly difficult to differentiate fact and opinion. As the largest online forum and aptly named "front page of the internet", there seems no better canidate for studying this than Reddit.
<br>
### Problem Statement:
__This project aims to determine what features make a Reddit post likely to be objective, and what features are characteristic of an opinion post.__
<br>
 The impact of these features may be gauged though using them as features for a model to classify Subreddits, and measuring the accuracy of this model. To ensure that any flaws in classification are due to the features rather than shortcomings of the model, both random forest and logistic regression models will be tested. Through careful consideration, the Subreddits selected for analysis and classification were r/AskScience, a forum where science related questions are discussed and answered, and r/UnpopularOpinion, ostensibly a hotbed for hot takes.  As both of these Subreddits are fairly large (AskScience having upwards of 22 million members), obtaining enough data to analyze and train a model should be fairly straightforward.

### Data Dictionary:

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**title**|*str*|reddit_posts_clean.csv|Title of Reddit post|
|**selftext**|*str*|reddit_posts_clean.csv|Text body of Reddit post|
|**subreddit**|*str*|reddit_posts_clean.csv|Subreddit the post was posted to|
|**created_utc**|*numpy.int64*|reddit_posts_clean.csv|Date and time the reddit post was created|
|**target**|*int*|reddit_posts_clean.csv|Binarized version of Subreddit column (0 being askscience and 1 being unpopularopinion)|
|**all_text**|*str*|reddit_posts_clean.csv|Text from title and selftext columns combined to one string|
|**word_count**|*integer*|reddit_posts_clean.csv|Total number of words in the post (both title and selftext)|
|**sentiment**|*float*|reddit_posts_clean.csv|The sentiment of the text in a given post, ranging from 1 to -1 (most positive and most negative respectivly)|




### Executive Summary:

#### Methods (change to notebooks):
After the data was scraped from the Subreddits using the pushshift API, word counts and sentiment analysis was run on the data. Following this, the text was run through a count vectorizer. Through a process of trial and comparison, it was determined that a Logistic Regression model is the best choice for the prediction of this target. While the a Random Forest model both with and without stemming and lemitization performed above the null model (the mean of the target), it fell short of the accuracy of Logistic Regression.

Through the use of a Logistic Regression model, the added features of sentiment analysis and word count, and the count vectorization of the text, the price of a house can be predicted within a 10% margin of error. This fulfills the projected goal, and performs well above the null model, which predicts with only 52.31% accuracy. This analysis also allowed for discovery of key features such as which words act as the best predictors of each Subreddit, the distribution of sentiment by Subreddit, and the distribution of word count. 

### conclusions and recommendations
