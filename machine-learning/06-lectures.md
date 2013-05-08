# Logistic regression: classification
Simplest: binary classification (negative/positive)

Linear regression can fit the data, but poorly
Add a threshold to make the function discontinuous? can be misleading or incorrect, depending on the training set

classification: y = 0 or 1
linear regression: predictions can be >1 or <0

Logistic regression: 0 <= hTHETA(x) <= 1

# Hypothesis representation
hTHETA(x) =  g(THETA^T * X)
where g(z) = 1 / (1 + e^-z) <= sigmoid / logistic function
==> hTHETA(x) = 1 / (1 + e^(-THETA^T * X))
sigmoid function has asymptotes at 0 and 1, so it's appropriate for binary classification

interpretation: hTHETA(x) = estimated probability that y=1 on input x
hTHETA(x) = P(y=1|x;THETA) -- probability that y = 1, given x, parameterized by THETA

# Decision boundary
Intuitions about the function
Sigmoid function >= 0.5 when z >= 0 (so whenever THETA^T * x >= 0)
Decision boundary: the plane formed by a binary-classification logistic regression
Some boundaries can be non-linear (e.g., a circle generated from polynomial features)

# Cost function
How do we choose the parameters for THETA?
alternative formulation of old cost function:
J(THETA) = 1/m * SUM( cost(hTHETA(x^i, y) )
where cost == 1/2 (hTHETA(x) - y)^2
=> non-convex function when you just plug the sigmoid function into this formulation - not guaranteed to converge (local optima)

alternative that will be convex:
cost(hTHETA(x), y) = 
  -log(hTHETA(x))     if y = 1
  -log(1 - hTHETA(x)) if y = 0

for the y=1 function
* cost = 0 if y = 1 and hTHETA(x) = 1, but as hTHETA(x) => 0, the cost goes to infinity -- dramatically punish misses

for the y=0 function
* reversed - dramatically punish false positives

# Simplified cost function and gradient descent
Unify the y=0/1 cost functions:
cost(hTHETA(x),y) = -y * log(hTHETA(x)) - (1-y) * log(1-hTHETA(x))
so:
J(THETA) = -1/m * SUM( y^i * log(hTHETA(x^i)) + (1-y^i) * log(1 - hTHETA(x^i)))
To fit THETA params, minimize J(THETA)

To make prediction given new x:
hTHETA(x) = 1 / (1 + e^(-THETA^T * x)))

Gradient descent: identical to linear regression GD (cosmetic identity; hTHETA(x) is different)

vectorized implementation to update all THETA params simultaneously

feature scaling still helps

# Advanced optimization
Gradient descent is one algorithm
Alternatives:
* conjugate gradient
* BFGS
* L-BFGS

Advantages:
* no need to select ALPHA (learning rate)
* often faster than GD

Disadvantages:
* more complex

To use: write (Octave) function that returns j(THETA) and the gradient vector

# Multiclass classification: one-vs-all (one-vs-rest)
Assign numbers to classes (y=1,2,3,4,etc.) so that we have discrete classes to work on
Treat as a series of binary classification problems: 1 vs 2+3, 2 vs 1+3, and 3 vs 1+2
generates:
hTHETA^i(x) = P(y=i|x;THETA) (where i = class)

on a new input; run all three classifiers and pick the one that maximizes hTHETA^i(x)
