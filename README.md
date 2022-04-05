<h2  style="color:#03396c";><center>Project 3 - SubReddit Classification</center></h2>



<h3 style="color:#6497b1";> Problem Statement: </h3>
<p><strong>
This project aims through the use of NLP to discover the most distinguishing features of 2 subreddits. Through the use of these features, posts will be classified using differnt models, seeking to make predictions within a 10% margin of error. 
    </strong></p>

<h3 style="color:#6497b1";> Data Dictionary: </h3>

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**title**|*str*|reddit_posts_clean.csv|Title of Reddit post| 
|**selftext**|*str*|reddit_posts_clean.csv|Text body of Reddit post|
|**subreddit**|*str*|reddit_posts_clean.csv|Subreddit the post was posted to|
|**created_utc**|*numpy.int64*|reddit_posts_clean.csv|Date and time the reddit post was created|
|**target**|*int*|reddit_posts_clean.csv|Binarized version of subreddit column (0 being askscience and 1 being unpopularopinion)|
|**all_text**|*str*|reddit_posts_clean.csv|Text from title and selftext columns combined to one string|
|**word_count**|*integer*|reddit_posts_clean.csv|Total number of words in the post (both title and selftext)|
|**sentiment**|*float*|reddit_posts_clean.csv|The sentiment of the text in a given post, ranging from 1 to -1 (most positive and most negative respectivly)|

<h3 style="color:#6497b1";> Methods: </h3>

After the data was scraped from the subreddits using the pushshift API, word counts and sentiment analysis was run on the data. Following this, the text was run through a count vectorizer. Through a process of trial and comparison, it was determined that a Logistic Regression model is the best choice for the prediction of this target. While the a Random Forest model both with and without stemming and lemitization performed above the null model (the mean of the target), it fell short of the accuracy of Logistic Regression. 



<h3 style="color:#6497b1";> Executive Summary: </h3>
<p>Through the use of a Logistic Regression model, the added features of sentiment analysis and word count, and the count vectorization of the text, the price of a house can be predicted within a 10% margin of error. This fulfills the projected goal, and performs well above the null model, which predicts with only 52.31% accuracy. This analysis also allowed for discovery of key features such as which words act as the best predictors of each subreddit, the distribution of sentiment by subreddit, and the distribution of word count. </p>
