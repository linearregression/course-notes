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

