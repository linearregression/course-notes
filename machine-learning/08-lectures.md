# Non-linear hypotheses
Neural networks!
Alternative to linear and logistic regression

Example: 
* non-linear classification, avoiding massively polynomial equations (or situations with many features)
* computer vision

# Neurons and the brain
Attempts to mimic the brain - popular from the 80s to the mid-90s, before fading in the late 90s (but coming back now)
Computationally expensive, but modern neural networks run well
Evidence for "one learning algorithm": neural plasticity / rewiring

# Model representation I
Neural networks are meant to simulate neurons in the brain

Neurons are (simplified) computational units that receive inputs, perform a computation, and create an output
* logistic unit, accepts x1...xn => hTHETA(x) (1/(1 + e^-THETA^T * x))
X0 is the bias unit/neuron, always = 1
Each node has a sigmoid (logistic) activation function
THETAs are sometimes called "weights" == parameters

Neural networks are groups of these logistic units
First layer == input layer, accepts training set
Final layer == output layer, outputs answer
Middle layer(s) == hidden layer(s)

ai^j == activation of unit i in layer j
THETA^j == matrix of weights controlling function mapping from layer j to layer j + 1

If a network has sj units in layer j, s(j+1) units in layer j+1, then THETA^j will be of dimension s(j+1) x sj + 1

# Model representation II
a1^2 = g(z1^2), a2^2 = g(z2^2), etc.
zX^2 = THETA1 * x (matrix)
x = vector of x0, etc.
z^2 = vector of zx^2
a^1 = activations into the input layer
add a0^2 = 1 to make a^2 a 4d vector
z^3 = THETA^2 * a^2
hTHETA(x) = a^3 = g(z^3)

all of that == forward propagation
the relationship of the last hidden layer to the output layer == basic logistic regression
* the main difference is that the features in that level are themselves learned -- not pre-set

Network architecture == how neurons are connected to each other

# Examples and intuitions I
Example: XOR/XNOR
* starting with AND
  hTHETA(x) = g(-30 + 20\*x1 + 20\*x2)
* added OR
* added NOT
* added (NOT a) AND (NOT b)

# Examples and intutions II
* Combine AND and (NOT a) AND (NOT b) into hidden layer
* Combine activations from hidden layer with weights from OR to give (a AND b) OR ((NOT a) AND (NOT b)) == XNOR (both false or both true)

# Multi-class classification
Extension of one-vs-all method
* have one output unit for each class
* hTHETA(x) = vector with 1/0 for each output unit; ideally, only one output unit will be active for a given set of inputs
* y is vector of 1/0 for each output unit)
