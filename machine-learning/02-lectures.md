# Linear regression with one variable

## Model representation
Ex: housing prices, how much could my friend sell her 1250 sqft house for?
Supervised learning - given answer for each example
Training set: size in sqft => price in 1ks
m = # of training examples
x = input variable/feature
y = output/target variable
(x,y) = one example
(x^(i), y^(i)) => the ith training example (not exponentiation)

Supervised learning => 
- feed training set to learning algorithm
- learning algorithm outputs function *h*, which takes input (x; size of house) and produces output (y; estimated value of house)
- h is "hypothesis" function, maps from x's to y's

How do we represent h? for this class, initial choice is:

h(x) = THETA0 + THETA1x
linear function
== linear regression with one variable; univariate linear regression
