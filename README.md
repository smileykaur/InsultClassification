# Insult Classification in a Social Media Comment

### Problem Definition:
__________________
Objective of this project is to detect if a comment from an online conversation can be considered insulting to another participant in the conversation. The idea is to create a generalizable single-class classifier which could operate in a near real-time mode. In this project I build a system that can detect whether or not any given comment is insulting by building a machine learning system.

In addition to just building a classifier this project also test different classifier - **Linear & Non-Linear** and decide which might be the best classifier for the purpose.


Ref: https://www.kaggle.com/c/detecting-insults-in-social-commentary

**Note:** This project is based around *Detecting Insults in Social Commentary* hosted on Kaggle by Imperium.
Ref: http://scikit-learn.org/stable/tutorial/text_analytics/working_with_text_data.html


### Methodology
__________________
This project has been built in 6 stages. Each stage is part of an end-to-end machine learning pipeline for sentiment classification.

#### Stage 1: Data Ingestion
__________________
In this stage data for training and testing is obtained from Kaggle. Training dataset contains **3947** examples, each of which consists of the text of a particular post and its desired label. Test dataset contains **2235** examples. Data is also inspected for shape and features.

A label of 1 represents an insulting post, while a label of 0 represents a non-insulting post. For Example, 

**Text:** “You’re a moron, truth is beyond your reach”, **Label: 1**

**Text:** “I’ll take that temp…I really hate the heat”, **Label: 0**

#### Stage 2: Data Wrangling
__________________
Once the data is loaded, data wrangling pipeline is created to clean data prepare it to be fed to the classifer in later stages. Following steps are taken: 

- Text Cleansing.
- Tokenization
- Stemming
- Lemmatization
- Stop words removal

#### Stage 3: Model Building
__________________
I started with linear classification models **Naïve Bayes, SVMs, and Logistic Regression** for building the classifier as they are very common and easy models for classification. Following this I built Non-Linear classifiers like **Random Forest Classifier, Decision Tree Classifier**. Evnetually, I compare how these classifiers perform.

In later, I perform **K-fold cross validation** which helped to standardize the results.

Each of these classifiers have been implemented with only unigrams features, followed by basic preprocessing (such as lowercasing all letters, removing punctuation and stemming)in Stage 2.

#### Stage 4. Model Evaluation
__________________
Once the models have been created, I am evaluating all the models. Basic metrics I am using to carry out these evaluation are - 
1. Precision - Recall 
2. Accuracy
3. AUC Score

I am using **10-fold cross validation** to check training accuracy and determine how well the model is fitting in training data. This also checks for any possible overfitting. The cross validation accuracy was more significant because it was more generalized.

#### Stage 5. Results 
This section evaluates the results obtained during training. I check the **Normal Accuracy**, **Cross Validatio Accuracy**, **precision-recall Scores**. I also build bar graphs to visually represent these results. 

#### Stage 6. Predicting Test Data
In this section I predict values for test data using the model built on Stage 4. Finally I present my conclusion which will be based on following parameters -
1. Classification Accuracy
2. AUC Score
3. Balance of Precision & Recall
__________________
__________________
