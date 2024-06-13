Implementing a basic decision tree algorithm to classify instances of the Iris dataset into
their respective classes.


DATASET:

The Iris dataset is a well-known and commonly used dataset in machine learning. It is relatively small,
containing 150 samples with 4 features each, making it easy to work with and analyze.
The dataset is well-balanced, so it did not require much preprocessing and it contains an equal number of
samples for each of the three classes (setosa, versicolor, and virginica). This balance can help the classifier learn
effectively from the data.

The data set has numerical values for the species:
0 = setosa
1 = cersicolor
2 = virginica

We calculate the gini which measures the impurity of the node and the entropy which is the disorder of the
node. Through this, we will calculate the information gain and we decide the root node of each sub-tree. Each
subtree is defined by calculating the information gain and the tree is built.

I have created two classes for this algorithm. Which are the node class and the tree class.
NODE class:

The node class defines the nodes of our decision tree. Each time it called to create a node for the tree. I have
defined several attributes in the node class. Those are:
• main_index
• weight
• left
• right
• gain_info
• and value


The decision tree contains two kinds of nodes decision nodes and leaf nodes.


The decision node contains a condition that is defined by the main_index and the weight for that particular
feature. The left and right are for accessing the left node and the right node. These are imagined as the edges of
the tree. it helps us to move from the parent node to the child node.

Decision_tree class:
This class represents the decision tree itself and contains methods for building, printing, fitting, and predicting
the tree.

__init__ function:
Initializes a Decision_tree object with default or user-specified parameters. Parameters include
minimum_samples_split and maximum_depth.

building_tree function:
Recursively builds the decision tree. Takes data (features and labels) and current_depth as input. It recursively
constructs the decision tree by selecting the best split at each node until a stopping criterion is met (minimum
samples or maximum depth).

get_good_split function:
Finds the best split for a given set of data. It iterates over all features and their possible values to find the split
that maximizes the information gain. Returns a dictionary containing information about the best split, including
the main index, weight, data for the left and right child nodes, and the gain in information.

split function:
Splits the data into left and right child nodes based on a given feature index and threshold value. Returns the
subsets of data for the left and right child nodes.

information_gain function:
Calculates the information gain for a split using either entropy or Gini impurity as the measure. It takes the
parent node and its children as input and returns the information gain.

entropy function:
Calculates the entropy of a given set of labels. It measures the impurity or randomness in the data.

gini_index function:
Calculates the Gini impurity of a given set of labels. It measures the probability of misclassifying an item.

cal_leaf_val function:
Calculates the predicted value for a leaf node based on the majority class in the node's data.

fit function:
Fits the decision tree to the training data. It concatenates the features and labels and then calls the building_tree
method to construct the tree.

predict function:
Predicts the labels for input features using the fitted decision tree. It takes input features (X) and returns the
predicted labels.

testing function:
Recursively traverses the decision tree to predict the label for a single input instance (x). After creating the
algorithm, I split the dataset into train and test datasets. I then calculated the accuracy using test data.

CONCLUSION:
Using the test dataset I have calculated the accuracy. For accuracy, I have used sklearns.metrics.From which I
have got 0.93 accuracy. An accuracy score of 0.93 (or 93%) indicates that the decision tree classifier achieved a
high level of accuracy in predicting the species of iris plants in the test dataset.
Overall, the combination of a high-quality dataset, an effective algorithm like decision trees, appropriate data
splitting, and carefully chosen hyperparameters contributes to achieving a high accuracy score of 0.93 using the
Iris dataset.
