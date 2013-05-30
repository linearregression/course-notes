# Applying ML
How do you choose which algorithm / model to apply?

Debugging a learning algo:
* on testing, you find huge errors with your existing hypothesis - what next?
  * more training examples
  * try fewer features
  * try more features
  * try polynomial features
  * increase or decrease lambda

Diagnostic: a test you can run to find out what is and isn't working with a given algo

# Evaluating a hypothesis
How can you tell if a hypothesis is overfitting the training data?
* plot the hypothesis, if possible
* if not plottable, split the data into 70%/30% training / test sets
  * learn THETA from new training set, then compute test set error
  * for logistic regression, test set error may be calculated as misclassification error


