# NLP_Tweets
Natural Language Processing of Tweets

### Source
Data World (data.world) - Brands and Product Emotions
https://data.world/crowdflower/brands-and-product-emotions


Current working document in Google Sheets:
https://docs.google.com/document/d/1L8DDtaTEgJddz7V3nkQzFKCeaDRefA6EnF6kcuzsHVo/edit

## Overview
To apply Natural Language Processing (NLP) and predict sentiment in tweets. Having an understanding of the sentiments of consumers gives companies the ability to make formal decisions on their products, or services. With NLP, it provides classification to the data, such as postitive emotion and negative emotion, as for the scope of the analysis limited to binary. To get a better understanding of consumer sentiment, the model is able to understand sentiment on a word by word basis, as Lemmatization was considered. As the cleaning progresses, its obvious the dataset suffers from a massive imbalance which can be resolved in our Moving Forward phase. On that note, the model does not take into account figure of speech, such as sarcasm. With all the challenges, the model has resulted with an 87% accuracy whhen applying a Logistic Regression model. This can be further tuned and improved.

## Business Objective
To provide a better understanding of consumer sentiment thats extracted from the tweets, to then help predict and make better formal business decisions.

## Data Classification
The data was transformed into a Binary Classification model, with classification labeled as Positive and Negative. The Positive classification insists the words extracted from the tweet were of positive meaning, whereas the Negative classification is intended for negative meaning. The class imbalance is massive between both Positive (~84%) and Negative (~16%) 
Below, you can see a pie chart that shows how the data is classified, by ratio.


![alt text](https://github.com/SeanE09/NLP_Tweets/blob/Ansel/Image/pie_chart_binary.png)


## Model
The models implemented on this data were Random Forests, Logistic Regression and Naive Bayes. The model found most effective was the Logistic Regression that scored 87% accuracy, considering a huge imbalance.

## Moving Forward
For the next steps, the model will need further improvements to capture human figure of speech that is not easy for a machine to understand, which will require modification to define such speech recognition. Also, the data will need to be better balanced and thoroughly cleaned so that the model can better predict and classify sentiment. 


### Contact us for more information!
Sean (sean.evans009@gmail.com)
Jonnie (jonnie.brown4@gmail.com)
Ansel (ansel.vallejo@gmail.com)

### Link to our presentation
via Google Docs (requires permission) - (https://docs.google.com/presentation/d/1Lm0a2KJ_F7GKdpQ-P8YPc23MdE3zIl3IFZbvkmFhnTk/edit#slide=id.g2542d76265b_0_289)


