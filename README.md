
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

## Ordinal Variables

An ordinal variable is similar to a categorical variable. However, the key difference between the two is that there is a clear ordering of the categories. For example, suppose you have a variable, economic status, with three categories (low, medium and high). In addition to being able to classify people into these three categories, you can order the categories as low, medium and high.

Now, our yelp review's star ratings range from 1 to 5.
A reviewer can assign a star rating from integers 1 to 5, which makes it discrete. However, the business that receives the rating shows the aggregated average of the total star ratings, which then makes it continuous.


## Classification Models
First, I chose to explore the following multi-class classification algorithms, and used the following metrics for comparison:

* **Models:** KNN, Decision Tree, Random Forest, Gradient Boosting and Multilayer Perceptron

* **Comparison Metrics:** Accuracy, Precision, Recall and F1 Score. 
  Below are the results scored in Accuracy:

  - KNN: 37.0%
  - Decision Tree: 37.7 %
  - Random Forest: 46%
  - Gradient Boosting: 46.8%
  - Multi Layer Perceptron: 47.75%

* Comparison Metrics

* 
## Classification into 3 Categories: Positive, Neutral, Negative
