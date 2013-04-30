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

hθ(x) = θ0 + (θ1)x
linear function
== linear regression with one variable; univariate linear regression

## Cost function
m = 47
θi = parameters
How do we choose θi's?
Choose params such that hθ(x) is close to y for training examples (x,y) - minimization problem over θ0 θ1 - potentially minimize average square of sum of differences between prediction and actual price (average = 1/2m)

cost function = J(θ0, θ1) = 1/2m * sum(1..m)(hθ(x(i)) - y(i))^2
squared error function
