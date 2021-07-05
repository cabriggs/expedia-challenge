## Background

Expedia is an online travel shopping company. Expedia offers travel solutions to customers by facilitating airline, hotel, and rental car bookings, among other services. The mission of any such operation should be to optimize customer satisfaction by directing them to options of maximal value to the customer with as little effort as possible on the part of the customer.

## Problem statement

The following challenge was presented as a Kaggle [competition](https://www.kaggle.com/c/expedia-hotel-recommendations). Given a set of information that Expedia can realistically collect about a customer at the point of hotel browsing, predict with maximal accuracy the hotel group (out of 100) that the customer will ultimately book.

## What data

The data set consists of some 7.6 million records. Some of the features include

- a timestamp
- the user's continent and country
- the hotel continent and country
- whether the user is on a mobile device
- the number of rooms booked
- whether the booking was completed

## What methods

A prediction consists of five guesses. The accuracy of the prediction is scored by nearness of the actual result to the top of the predicted list. 

First, a naive model was attempted. This model selected the top five (by sheer number of bookings) hotel clusters in the user's search destination.

A suite of machine learning models were applied. These models are

- logistic regression
- linear discriminant analysis
- KNN
- decision tree
- Gaussian naive Bayes
- neural network
- support vector machine

The decision tree model was most successful. The approach was then further refined by training a decision tree model _per destination ID_. The result is a network of over 20,000 decision tree classifiers which, together, achieve good prediction accuracy.

### Technology

The analysis was performed in a Jupyter notebook, leveraging the pandas, numpy, and sklearn libraries.

## What conclusions

The nature of the model structure means that a human-interpretable explanation of the form "a user with these properties tends to book here" is not possible. Rather, the conclusion is that a successful model for predicting hotel bookings can be assembled out of a network of decision trees. 

## What questions remain

The results achieved here are good enough to get to 13th place on the Kaggle competiton leaderboard, so some improvement is possible. It is unclear whether further significant improvements can be made through modifications to the presented method, or if a much different approach would be needed.

