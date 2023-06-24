# Tweet Sentiment Using Natural Language Processing (NLP)

![Image Description](Image/Twitter1.png)

![Image Description](Image/Twitter.png)

### Contributors
* Sean Evans
* Jonnie Brown
* Ansel Vallejo

For an in depth analysis please review our [jupyter notebook](./Final_Logistic_Regression_Model_6.23.2023_-_SE.ipynb) and [presentation slides.](.presentation_deck.pdf)

## Business Understanding
We were tasked with building a NLP model that can rate the sentiment of a tweet based on its contents. Our target audience is a team of business executives that wants to understand how to engage its customers and to provide a better experience with their products.

## Data Understanding
The dataset comes from CrowdFlower via [data.world](https://data.world/crowdflower/brands-and-product-emotions) and contains over 9,000 tweets that were rated as positive, negative, neutral, or unknown. The tweets were generally about Apple and Google products.

Since neutral tweets don't provide any business value we decided to go with a binary target by removing the tweets that were not positive or negative in order to better aid us in our business problem. Here is a distribution of the target variable after making it binary.

![Emotion Distribution](https://github.com/SeanE09/NLP_Tweets/assets/116228715/1d7fb201-915b-469a-86e4-fb9df27db3ee)


## Data Preparation
To prepare the data we made a function that would preprocess our data for us. It takes in a the list of strings to be processed, a tokenizer, and two stopwords lists and it will change the case to lowercase, apply the tokenizer, remove all stopwords, and apply a lemmatizer.

We decided to use TweetTokenizer because it is designed for handling tweet text.

## Modeling
From there we designed a pipeline that included our preprocessing function, a TfidfVectorizer, and a classifier. First we ran a dummy model so we could have something to compare our results with, and that scored 83% in accuracy. We chose to use a logistic regression model for the sake of easy interpretability. After performing a gridsearch trying out different n_grams and C values, we ended up with a model that had these results:

Accuracy: 0.8774647887323944 \
Precision: 0.8687812929946244 \
Recall: 0.8774647887323944 \
F1-score: 0.8555468276811696

![confusion](https://github.com/SeanE09/NLP_Tweets/assets/116228715/a76f71a2-8e7d-48b2-a0f5-bfa8fdf9728a)


## Evaluation
We first looked at the top 10 words that drove our model to predict if the tweet was a negative sentiment or positive sentiment.
![feature_analysis1](https://github.com/SeanE09/NLP_Tweets/assets/116228715/6d3e04b5-0cb0-42ee-99a1-507c638de535)
![feature_analysis2](https://github.com/SeanE09/NLP_Tweets/assets/116228715/b3b46b0b-b3d5-4e4c-b995-da08da49dbc0)

And we also wanted to see the frequency of the words being used in both positive and negative sentiments.
![pos](https://github.com/SeanE09/NLP_Tweets/assets/116228715/8eefe0fb-d04a-4ea4-bce0-4ad61cbc24d0)
![neg](https://github.com/SeanE09/NLP_Tweets/assets/116228715/907d317d-46f9-4a10-a836-217a65db7d82)

We noticed links and mentions were prominent in positive sentiment along with "free" and "win". So we suggest having customers share the company's link to the product mentioning someone else as a friendly competition where the company gives something away for free. 
