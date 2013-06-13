# Machine learning
Statistics vs machine learning
* stats try to model the world through a stochastic process
* ML discards accuracy of the model in favor of accuracy of prediction 
[ strong vs weak AI ]

Classification vs regression (discrete classes vs numeric ranges)
Supervised vs unsupervised learning

Learning components:
* representation (what is the classifier?)
* evaluation (is it good or bad, and how do we know?)
* optimization (how do you search among the alternatives?)

# Rules
Inspect the data (visualization)

Rote classifier: if there's an exact match to a training set, use its output; else guess
Inspect for matches on a particular trait, take a vote (most females survive => assume all females survive)

Confusion matrix: reality vs prediction

Searching for the appropriate model:
* 1-rule (try them all)
* Sequential covering (look for increasing coverage across rule combinations)

Search: increasing specificity (add constraints) OR increasing generality (remove constraints)

# Decision trees
Rules based directly on attributes:
* Grouping redudant conditions => decision tree
* Every path from the root is a rule

Entropy = expected information = -1 * sum( px * log2(px))
I(X) = -log2(px)

Back to decision trees: at each level, pick the attribute that reduces entropy the most (has the highest information gain)

# Information gain
Example calculations for minimizing entropy

ID3 algorithm for building a tree:
* assume attributes are discrete
* choose the attr with the highest information gain
* create branches for each value
* partition examples based on selected attributes
* repeat with remaining attributes
* stop when:
  * all examples have the same label
  * no examples are left

Problems:
* expensive to train
* prone to overfitting (pruning low-value subtrees can help)

Splitting continuous attributes
* sort data set
* evaluate each choice based on information gain

# Overfitting
Great on training data, poor on test data
Test on hold-out data (cross-validation sets)

Overfitting: low bias / high variance
Underfitting: high bias / low variance

bias ~= accuracy (low bias == high accuracy)
variance ~= precision (low variance == high precision)

# Evaluation
Dividing training and test sets
* fixed - leave out a random X%
* k-fold cross-validation - select k-folds without replace (10-fold, for example)
* leave-one-out cross-validation - C-V against a single datapoint, repeatedly
* bootstrap - generate new training sets through sampling with replacement

LOOCV
* train on all but one value, test accuracy for it; do that leaving each one out
* accuracy == average of all n accuracies

Accuracy
* Confusion matrix; accuracy = correct predictions / all predictions
* how do you interpret the accuracy percentage?
* need a baseline 
  * base rate = trivial prediction of most-frequent class
  * random rate = completely random assignment or prior knowledge
  * naive rate = accuracy of some simple/pre-existing model

ROC plot
* receiver operator characteristic
* sensitivity = % of true examples correct
* specificity = % of false examples correct

# Bootstrap
* Given m examples
* draw n samples WITH REPLACEMENT to create a new dataset
* repeat 1000x
* compute sample statistics on these cases

# Ensembles
Ensembles == combining classifiers
* average results from different models
* pros: better classification performance, increased noise resistance
* cons: time consuming, more challenging models

Bagging
* draw n bootstrap samples
* retrain for each sample
* average the results (regression = average, classification = majority vote)
* decreases variance without changing bias

Boosting
* favor misclassified points when sampling
* con: inherently sequential, so large datasets can be problematic

# Random forests
* Repeat k times:
  * draw bootstrap sample
  * train decision tree
    * until tree is max-size
    * choose next leaf node
    * select m attributes at random from those available
    * pick best atrribute / split as usual
  * measure out-of-bag error (evaluate samples that weren't in the bootstrap)
* prediction by majority vote among the trees

Variable importance
* if you scramble the values of a variable and the tree's accuracy doesn't change much, then the variable isn't very important
* measure the error increase
* random forests are more difficult to understand than single trees; variable importance helps to clarify what's happening

Gini coefficient
* measures inequality 
* somewhat similar concept to entropy
  Gini(T) = 1 - sum(p^2)

Random forests are easy to parallelize
Handles small n / big p problems easily

# k-nearest neighbors
[ relationship to SVM? ]
How do you choose k?
* small = fast
* large = ignores outliers; bias towards popular labels

Similarity function
* Euclidian distance con: sensitive to # of dimensions
* Cosine similaity con: favors dominant labels
