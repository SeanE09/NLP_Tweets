# NLP_Tweets
Natural Language Processing of Tweets

Current working document in Google Sheets:
https://docs.google.com/document/d/1L8DDtaTEgJddz7V3nkQzFKCeaDRefA6EnF6kcuzsHVo/edit

![Image Description](Image/Twitter1.png)

![Image Description](Image/Twitter.png)


Cleaning:
Lowercase
Tokenizer = Tweet Tokenizer
Stopwords = stopwords_list 
Remove words = 'sxsw', 'rt', 'mention', 'link', 'ipad', 'google', 'apple', '2', 'iphone', 'austin', 'android', 'sxswi'

Pipeline:
ensemble_pipeline = Pipeline([
    ('preprocessor', FunctionTransformer(clean_text, kw_args={'tokenizer': tokenizer, 'stopwords_list': stopwords_list, 'remove_words': remove_words})),
    ('tfidf', TfidfVectorizer()),
    ('classifier', VotingClassifier(
        estimators=[
            ('nb', GridSearchCV(MultinomialNB(),
                               param_grid={'alpha': [0.1, 0.5, 1.0]},
                               scoring='accuracy',
                               cv=5)),
            ('svm', GridSearchCV(SVC(probability=True),
                                 param_grid={'kernel': ['linear', 'rbf'], 'C': [1, 10]},
                                 scoring='accuracy',
                                 cv=5)),
            ('rf', GridSearchCV(RandomForestClassifier(),
                                param_grid={'n_estimators': [50, 100, 200]},
                                scoring='accuracy',
                                cv=5)),
            ('xgb', GridSearchCV(XGBClassifier(),
                                 param_grid={'n_estimators': [100, 200, 300], 'learning_rate': [0.01, 0.1, 1.0]},
                                 scoring='accuracy',
                                 cv=5)),
            ('rf2', GridSearchCV(RandomForestClassifier(),
                                 param_grid={'n_estimators': [40, 90, 125, 150], 'max_depth': [None, 10, 20]},
                                 scoring='accuracy',
                                 cv=5))
        ],
        voting='soft'


