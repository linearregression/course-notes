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
