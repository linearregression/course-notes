# Neural networks learning - Cost function
Binary classification = 1 output unit (y == 0 or 1)
Multiclass classification for K classes = K output units (y is a member of R^K, e.g., [1; 0; 0; 0], [0; 1; 0; 0])

Cost function for NN is a generalization of logistic regression
... look in course notes for equation (too complicated to render in markdown)

# Backpropagation algorithm
Need code that takes J(THETA) and computes the partial derivative of THETA wrt J(THETA)

Intuition: deltaJ^l = "error" of node j in layer l
Calculate delta^l for each layer (after input layer) in reverse

Ignoring regularization, the partial derivative of J(THETA) = activation^l * delta^(l+1)

Algorithm:
* for i = 1 to m
  * set a^1 = x^i
  * forward propagate to compute all layer activations
  * using y^i, computer delta^L = a^L - y^i
  * compute delta^l for all lower layers
  * set DELTA := DELTA^l + delta^(l+1) * (a^l)^T

Again, check course notes for equations

# 
