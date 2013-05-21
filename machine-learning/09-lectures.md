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

# Backpropagation intuitions
Run the calculations backward to see how much each hidden layer node contributes to the next layer's activation

# Implementation: Unrolling parameters
Unroll matrices into vectors (so we can use optimization algorithms)
In octave, use (:) to unroll a matrix (so you can pass it to fminunc)
Use reshape with (elements, n, m) to get the matrix back

costFunction in Octave - pass in the unrolled vector, reconstruct the matrices, use forward and backward propagation to get D1, D2, etc., then unroll those to output gradientVec

# Gradient checking
How do you confirm that you've got the optimal learned weighting?
approximate derivative of J(THETA) with (J(THETA+EPSILON) - J(THETA-EPSILON))/(2 * EPSILON) # two-sided difference / when THETA is a real number

When THETA is a vector, partial derivatives reappear; code example in slides
calculate the approximate gradient, then compare to DVec (derivatives from back propagation)

Process:
1. backprop to compute DVec
2. numerical gradient check to compute gradApprox
3. confirm they're similar
4. turn off gradient checking (too expensive to run constantly)

# Random initialization
Need some initial THETA
* could use zeroes; works for logistic regression but not for neural networks (no differential activation, so you're basically only calculating one feature per node)
* breaking symmetry by random initialization between -EPSILON and EPSILON

# Putting it together
Steps to train a NN:
* pick an architecture (layers, nodes)
  * input units defined by dimension of features
  * output units defined by classes
  * reasonable default: single hidden layer; if more than one, use the same number of units in each hidden layer
  * more hidden units the better (1-4x input units)
* randomly initialize weights
* implement forward propagation to get hTHETA(x)
* implement cost function
* implement backprop to compute partial derivatives
  * usually done with a for loop over the training examples to get activations and deltas for each layer
    * perform forward and back prop using the example
    * calculate activations and delta terms
    * compute the DELTAs
* use gradient checking to validate the code
  * then disable gradient checking
* use gradient descent or advanced optimization with backprop to minimze J(THETA) wrt THETA
  * J(THETA) is non-convex (so you can get stuck in local optima, occasionally)

# Autonomous driving
Neural network!
