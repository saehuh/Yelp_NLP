
# NLP with Yelp
![Yelp_logo](/IMG/unnamed.png)

## About the Project
Develop a model to correctly classify or predict yelp review comments' star rating ranging from 1 to 5 stars.

## Data
The dataset came from Yelp's dataset page, https://www.yelp.com/dataset/, which has a subset of their businesses, reviews, and user data. 
It holds 8,021,122 reviews, 209,393 businesses, 200,000 pictures for 10 metropolitan areas.

Here is a word cloud generated using the review data:

![Yelp_wordcloud](/IMG/wordcloud.png)

### Distribution of Star Ratings in Review Dataset

A reviewer can assign a star rating from integers 1 to 5. However, the business data shows the aggregated average of the total star ratings. Below, you can see how star ratings are differently distributed in the two differnt datasets:

![Yelp_review_stars](/IMG/yelp_stars.png)

### Distribution of Star Ratings in Business Dataset
![Yelp_review_stars](/IMG/yelp_stars_business.png)


## Pipeline
### Preparing the Data
* Cleaning: Stop-words, punctuation, and non-alpha characters were removed from the data.

* Lmmatization: Lemmatization (nltk.wordnet.Lemmatizer) was used to reduce each each word to its meaning and consolidate like-meaning words.

* N-grams: were explored to see how it changes the results of top 30 n-grams used in the review texts.

![Yelp_unigrams](/IMG/unigrams.png)

![Yelp_bigrams](/IMG/bigrams.png)

![Yelp_trigrams](/IMG/trigrams.png)

* Count/TF-IDF Vectorization: were both explored to vectorize the words and weight their importance. 

     
## Model Comparison

* Models

* Comparison Metrics

* 
