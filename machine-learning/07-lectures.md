# The problem of overfitting
Underfitting / high bias -- the algorithm has a very strong bias to, e.g., linear predictions
Overfitting / high variance -- too-high an order polynomial function is not constrained enough, and could fit anything
* too many features can result in a very good fit to the training set but fail to generalize to new examples

Addressing overfitting:
* plot hypotheses -- may not always work (esp when there are immensely many features)
* reduce # of features
  * manual selection
  * model selection algorithms to automate it
* regularization
  * keep all features but reduce magnitude of the parameters
  * works best with lots of features that each contribute a little bit

# Cost function for regularization
Minimize the impact of *all* parameters
Small values for parameters basically equivalent to a simpler hypothesis => less prone to overfitting

J(THETA) = 1/(2 * m) * (SUM(hTHETA(x^i) - y^i)^2 + LAMBDA * SUM(THETA(J)^2))
LAMBDA = regularization parameter

linear regression: if LAMBDA is high, all params approach 0 => underfitting

# Regularized linear regression
## Gradient descent
Remember: THETA0 does not get penalized/regularized

add LAMBDA/m * THETAj to the gradient descent equation
this == 
THETAj := THETAj(1 - ALPHA * LAMBDA/m) - ALPHA/m * SUM((hTHETA(x^i) - y^i) * x-j^i

1 - ALPHA * LAMBDA/m < 1 a bit (so shrinking the parameter a little bit)

## Normal equation
THETA = (X^T * X)^-1 * X^T * y

with regularization:

THETA = (X^T * X + LAMBDA[identity matrix with 0 in 1,1])^-1 * X^T * y

Non-inversability:
m <= n then this (X^T * X) is non-invertible/singular/degenerate (though pinv in octave will still work)
regularization fixes it!

# Regularized logistic regression
## Gradient descent
Take cost function and add 
LAMBDA / 2 * m * SUM(THETA-j^2) <= minimizes parameters
REMEMBER: don't regularize THETA0

## Optimized algorithms
pass costFunction to fminunc; calculates
* jVal (with new cost function)
* gradient vector (1 => partial derivitave of J(THETA) wrt THETA0, etc)
