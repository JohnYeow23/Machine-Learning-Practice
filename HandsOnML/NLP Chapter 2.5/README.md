# Project Name

"Spam or ham?" Natural Language Processing project in identifying whether emails are spam or ham.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Results](#results)
- [Conclusion](#conclusion)
- [Contributing](#contributing)
- [License](#license)

## Introduction

The project's goal is to demonstrate my grasp of the Natural Language Processing (NLP) framework learned through Derek Jedamski's LinkedIn course. We aim to apply NLP lifecycle concepts into our project, gaining proficiency in tokenising, vectorising, and understanding the rationale behind each process. Specifically, use a machine learning model to classify emails as either 'spam' or 'ham.' This real-world application provides insights on how NLP can actively enhance email security and combat spam, hence deepening my understanding of NLP's practical applications. 

## Installation

To install and set up this project, you need to follow these steps:

1. Install Visual Studio Code (VSCode), our main development tool.
2. Set up a GitHub repository for version control and to practice Git commands.

## Lifecycle

The main goal of this project is to convert text data into a format that a computer can understand and process efficiently. While doing so, we kept in mind the complexity of the data and its potential impact on processing time and space.

We started with feature engineering to enhance our model's prediction capabilities. We appended these key features to our dataframe:

1. Punctuation percentage in the document.
2.  Misspelled words percentage in the document.
3.  Count of lowercase words in the document.
4.  Count of uppercase words in the document.

Following this, we converted textual data into a machine-readable format. In this process, we leveraged a function for data cleaning that can be reused in future tasks. The function specifics include:

1. Removing punctuation.
2. Tokenizing the text.
3. Removing stopwords and applying stemming (we opted for stemming due to its faster processing speed).

We then split the data frame, designating 20% for our test set and the remaining 80% for training. The test set was kept aside until we made decisions concerning the vectorizer, hyperparameters, and model selection.

Two main vectorizers―the count vectorizer for its simplicity, and the tfidf vectorizer for its complexity handling via word weightage―were considered for text data transformation. Both were employed to compare performance, resulting in two separate data frames.

Our model selection was primarily focused on ensemble models, namely, the RandomForestClassifier and GradientBoostingClassifier. We used grid search and 5-fold cross-validation to determine the optimal hyperparameters for each model.

To gauge performance, we used nltk's score function to measure precision and recall. We also considered the processing time for fitting different vectorizers and prediction in our final evaluation. The tfidf vectorizer showed  better performance across both models, and due to its time efficiency, we chose the RandomForestClassifier as our final model, despite it slightly underperforming in comparison to GradientBoostingClassifier.

## Results

Using the RandomForestClassifier with tfidf vectorizer we were able to achieve the following results:
Fit time: 1.094 / Predict time: 0.082 ---- Precision: 1.0 / Recall: 0.813 / Accuracy: 0.975

## Conclusion

Reflecting on this NLP project, main purpose is to understood the processes and reasons behind data transformations and model selection. One area of potential improvement is feature scaling, especially for the punctuation percentage feature, which displayed a significant left-skew; a Box-Cox transformation might have helped to normalize it.

## License

Credits to Derek Jedamski for the insightful walkthrough tutorial which can be found on LinkedIn learn.
