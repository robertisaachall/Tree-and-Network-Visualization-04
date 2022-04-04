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
  From viewing the produced visualizations above, one can see where the Tree classifier decided to take the splits based on certain values. For Figure 1.1 since the tree was not pruned and used a different criteria it makes many splits to create the classifier. From the first figure it creates four initial splits for the classifier based on the age, cholesterol, and blood pressure and proceeds to create the sub-leafs such as where it has a branch specifically for ages above 70.5 and cholesterol levels above 347.5. The accuracy of this created classifier was reported at: 0.5737 from no prior adjustments to the hyper parameters of the model and it shows in the graph. When moving onto Figure 1.2 where the tree has a max depth of 2 and uses the Entropy criterion the tree is cut down in size to a maximum of two initial nodes that bases the classifier on ages above 56.5 and cholesterol levels above 245.5. Considering this classifier was the best one created thus far with an accuracy of : 0.6885 it goes to show that these values the classifier is considering the split for are closely related to the actual outcome class we were trying to classify (high-risk vs. not high risk). From what is shown between the two visualizations it shows that when changing hyper parameters on the Decision Tree Classifier model from sklearn it has an actual effect on both the outcome accuracy and the number of respective nodes the classifier creates to attempt to classify the target variable.
 
# Dataset 2: Astro Physics Collaboration Network
## Description
  The dataset used for this analysis is a collaboration
network from arXiv which is the scientific collaboration
between authors papers submitted to the respective
category, where if an author collaborated with another the
graph contains an undirected edge and creates a connected
graph if the paper is co-authored. The data covers the
period from January 1993 to April 2003. The dataset can be
sourced and found from:
https://snap.stanford.edu/data/ca-AstroPh.html

## Dataset Format, Type, Attribute Types and Semantics
  The data-set format consists of individual network
piece data meaning that each entry in the set
corresponds to a collaboration between two paper
authors. From this set of entries, each individual set can
stand on its own since each entry corresponds to two
authors collaborating. Each data point is an integer that
corresponds to an author. It is important to note as well
that this data-set does not contain any metadata about
the collaboration rather this is just a collaboration
network to show undirected connections.

## Preprocessing
  The dataset is set up as a .txt file containing no
methods of parsing the data set such as a .csv file so a
script was created in order to parse this data to be ported
into our dataframe for transformation and to be used in the
network visualizer. Each point in the dataset appears as:
                      84424 276
                      84424 1662
From this format whenever the dataset was read in
from the file it was parsed from the spaces giving us an
array of each value where each of the values was placed
into the respective array (Source array for first part,
destination array for the second part). A counter was
placed inside the preprocessing script in order to cut down
on processing time. Whenever the initial visualization was
created the time it took to produce said visualization was
taking much time considering the data-set consisted of
over 300,000 entries. For this reason I decided to cut down
the size of the initial data read to 1000 entries to help cut
down on processing time. After the dataset was read and a
pandas dataframe created from the two sets, we created a
graph network using the networkx package in Python to
create a graph type to use in our visualization packages.
This graph
type object can be used for multiple packages for
visualization. No other preprocessing techniques were used
for this dataset considering there are no missing or
erroneous values.

## Visualization
Figure 2.1: Initial Visualization with Networkx Package

Figure 2.2: Visualization with PyVis Package

## Analysis
From viewing the produced visualizations above
the first thing you can see is the initial visualization in
Figure 2.1 is that the included visualizer in the networkx
package does not show us good information about the
clustering and close details about the collaborations.
We can definitely see there are instances of clustering
but details are lost in the blobs. Due to this lack of
information it was decided to use another graph
visualization package which was the PyVis package
which produced Figure 2.2. Figure 2.2 shows us much
more information that we can use and in the included
Jupyter Notebook produces visualizations that can be
moved around and zoomed in and is highly
recommended to run the code to see further details as I
will describe them here. Two of the biggest clusters is in
the southeast of the visualization where authors: 60471
and 106274 have a large number of connecting edges
indicating that these authors have collaborated with
many other authors on papers. Another large cluster
appears northeast to the previously mentioned cluster
with author 94138 connecting to quite a bit of other
authors. Looking at the outer sections of the
visualization shows small leaf sections with few
collaborations such as in the southwest corner with
author 5412 connecting to three other authors. Overall
this graph shows that there are many instances of
authors collaborating with others on papers. One of the
more interesting pieces that has been learned from this
is that the packages used for visualizations matter
much where important details such as individual
clusters and small instances of clustering is lost in the
blob of connections.
