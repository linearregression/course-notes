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


