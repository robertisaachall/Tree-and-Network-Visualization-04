# Tree and Network Visualization 04

# Dataset 1: Heart Attack Analysis & Prediction - Tree Visualization
## Description
The original dataset is from Kaggle and consists of information regarding the outcome of a heart attack prediction. The data is broken down into individual features such as blood pressure, cholesterol, and age to predict whether or not a heart attack is more likely or not. This dataset is not in a tree format but the classifier built with the data will be a tree visualization. Two Decision Tree classifiers are created using an 80 - 20 split for training and test respectively with the first classifier not using hyper parameters and the second using different criteria. The dataset can be sourced from: https://www.kaggle.com/datasets/rashikrahmanpritom/heart-attack-analysis-prediction-dataset

## Dataset Format, Type, Attribute Types and Semantics
The dataset is a table consisting of multiple rows that correspond to that certain person’s features. The features we are using to build our classifier to visualize the decision tree will be: Age , Resting Blood Pressure (“trtbps”) , Cholesterol (“chol”) , and maximum heart rate achieved (“thalach”). There are other features in the dataset that are not used for this analysis such as the fasting blood sugar, exercise induced angina, and resting electrocardiographic results. The aforementioned features that will be used are all floating point numbers for their respective values. Whenever the classifier is fitted and a visualization is created the tree values correspond to where the tree marks the criterion to split where the individual nodes correspond to the leaf of that split. 

## Preprocessing
The dataset is in a .csv format where it was read with python and imported for use. There were no missing values in the feature columns that were used for the classifier. The specified feature column names were selected and used to filter the dataset to get those specific ones into a variable to be stored. The target variable (‘output’) column was stored in its own set as well to build our test - train split. Since we are using a classifier it is important to split and train our data separately to reinforce the learning of the algorithm. We use the built in functionality from the Sklearn package to create the test - train split at an 80% and 20% respectively. Whenever the sets were created the classifier was then created and trained with no further hyper-parameters tuned. The first model achieved an accuracy of : 0.5737 where then the visualization was created of our Decision Tree Classifier to view the criterion splits (FIGURE 1.1). After the first model was created we did a similar step above but instead of leaving the hyper-parameters untouched we changed the criterion from the default Gini Index to Entropy and trimmed our decision tree to a maximum depth of 2 which boosts the accuracy of : 0.6885 . The visualization for this classifier was (FIGURE 1.2). 

## Visualization
Figure 1.1: Classifier Tree No Hyper Parameters | Accuracy: 0.5737

Figure 1.2: Classifier Tree Entropy Criterion with Max Depth at 2 | Accuracy: 0.6885

## Analysis
