# Tweet Sentiment Using Natural Language Processing (NLP)

![Image Description](Image/Twitter1.png)

![Image Description](Image/Twitter.png)

### Contributers
* Sean Evans
* Jonnie Brown
* Ansel Vallejo

For an in depth analysis please review our [jupyter notebook](./Final_Logistic_Regression_Model_6.23.2023_-_SE.ipynb) and [presentation slides.](path_to_slide_deck)

## Business Understanding
We were tasked with building a NLP model that can rate the sentiment of a tweet based on its contents. Our target audience is a team of business executives that wants to understand how to engage its customers and to provide a better experience with their products.

## Data Understanding
The dataset comes from CrowdFlower via [data.world](https://data.world/crowdflower/brands-and-product-emotions) and contains over 9,000 tweets that were rated as positive, negative, neutral, or unknown. The tweets were generally about Apple and Google products.

We decided to go with a binary target by removing the tweets that were not positive or negative in order to better aid us in our business problem. Here is a distribution of the target variable...

## Data Preparation
To prepare the data we made a function that would preprocess our data for us. It takes in a the list of strings to be processed, a tokenizer, and two stopwords lists and it will change the case to lowercase, apply the tokenizer, remove all stopwords, and apply a lemmatizer.

We decided to use TweetTokenizer because it is designed for handling tweet text.

## Modeling
We designed a pipeline that 

## Evaluation

