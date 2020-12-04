
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

* **Models:** KNN, Decision Tree, Random Forest, Gradient Boosting and Multilayer Perceptron, MultinomialNB

* **Comparison Metrics:** Accuracy, Precision, Recall and F1 Score. 
  Below are the results scored in Accuracy:

  - MultinomialNB: 0.32
  - KNN: 37.0%
  - Decision Tree: 37.7 %
  - Random Forest: 46%
  - Gradient Boosting: 46.8%
  - Multi Layer Perceptron: 47.75%

### Classification into 3 Categories: Positive, Neutral, Negative

The multi-class classification with 5 different ratings didn't perform well. So I bucketed the star ratings into 3 groups of Positive, Neutral and Negative to see how the performance improved. It had improved a little bit but it seemed like it was struggling to predict negative reviews from looking at the confusion matrix.

## Regression Models with Cross Validations
In exploration with regression models, cross validation was used in both tuning of hyper parameters and the training of the best resulting models. The scores reported are based on the predictions from unseen test data that were excluded from the training set.

* **Models:** Random Forest Regressor, Gradient Boosting Regressor, AdaBoost Regressor

* **Comparison Metrics:** RMSE, R2 
  Below are the results scored in MSE:
  - Random Forest Regressor: 1.002
  - Gradient Boosting Regressor: 1.018
  - AdaBoost Regressor: 1.081

### Comparing Different Models at Different Learning Rates
![GDB](/IMG/GB.png)
![GDB_RF](/IMG/GB_RF.png)
![ADB_RF](/IMG/Ada_RF.png)

With Gradient Boosting Model, I used Grid Search method to further tune hyperparameters and was able to get MSE down to 0.822.

## Tensor Flow Regression

### Balancing the Data

Before I start training a Tensor Flow model. I thought it would be a better idea to balance the data since the distribution of star ratings in our data wasn't even. 

![rating_og](/IMG/star_count_org.png)
![rating_bl](/IMG/star_count_bal.png)

With Tensor Flow and larger data, I could get the RMSE down to 0.53.



