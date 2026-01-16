## Overview

The goal of this project is to detect credit card fraud using an unsupervised Gaussian Estimation algorithm. The data consists of information from credit card transactions during the course of 48 hours, including amount of purchase, time of purchase, and other propietary (unlabeled) parameters. 

## Business Problem

Credit card fraud is a significant issue to both CC issuers and consumers. Consumers may have to pay back fraudulent charges if not properly detected. Likewise, CC issuers may have to refund large transactions if not properly detected. 

## Data Source:

The data used in this project contains transactions made by credit cards in September 2013 by European cardholders. The dataset presents transactions that occurred in two days, where there are 492 frauds out of 284,807 transactions. The dataset is not directly hosted in this repository. Instead, you can find it [HERE.](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

![Histogram of Data Features](/images/cc_features_histograms.png)

## Methods

The goal of this project is to use the unsupervised Gaussian Estimation algorithm. Specifically, the data is split into three sets: training, validation, and test. The model is initially trained on the training set which includes non-anomalous transactions to show the model what 'normal' looks like. The model is then trained on the validation set (which includes normal and anomalous transactions) using the F1 score to determine the best threshold, i.e. to detect anomalies. 

It is significant to note that standard scikit-learn libraries were not used for the algorithm. Instead, I manually coded the formulas needed to make predictions. 

### Libraries / Languages Used

* Python
* Pandas
* Numpy

## Analysis

The model has a 99.42% accuracy rate. The baseline accuracy of assuming all normal transactions (i.e. no fraud) is 99.57%. Despite performing below the baseline, the model is still able to determine instances of fraud that the baseline model misses. 

It is also important to note that this dataset is from 2013. Fraud patterns change over time. Though this model worked for our current data, it might not work given current fraud patterns. Other models could also potentially work well for this data such as a random forest supervised learning algorithm.
