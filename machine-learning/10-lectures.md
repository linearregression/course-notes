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

# Model selection and validation
How do you decide what degree polynomial to use?
* treat degree as an extra parameter
* goal: fit model and estimate accuracy of fit to new examples
* calculate THETA for each hypothesis and pick the best cost function
* problem: THETA is overly optimistic (because degree is fit to the test set)
* solution: divide training examples into three sets (training, cross-validation, and test set - 60/20/20%)
  * calculate training, CV, and test error for each hypothesis
  * select model based on CV error minimization, not test set error

# Diagnosing bias v variance
High bias == underfitting
High variance == overfitting

* Training error tends to decrease with increasing degree of polynomial
* CV error is a U-shaped curve when plotted against degree of polynomial (underfitting == high error, overfitting == high error)

High bias is the case when both training and CV error are high
High variance is the case when training error is low and CV error is high

# Regularization and bias/variance
Large lambda (regularization) => underfitting, high bias
Small lambda => overfitting, high variance

Choosing lambda:
* define J(THETA) = cost function without regularization (for train, CV, and test)
* define a range of possible lambdas
* minimize J(THETA) based on possible lambdas to define various THETAs
* evaluate Jcv(THETA) for each THETA (minimize it)
* evaluate chosen Jtest(THETA) for selected THETA

lambda is too large if Jcv(THETA) is high and Jtrain(THETA) is high
lambda is too small if Jcv(THETA) is high and Jtrain(THETA) is low
