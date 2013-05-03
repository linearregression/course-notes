# Multiple features
Already seen single-feature regression
name features x(sub)
n = number of features
x^i = input (features) for the ith training example; IS A VECTOR
x^i(sub j) = value of feature j in the ith training example

hypothesis was hTHETA(x) = THETA0 + THETA1 * x
now it is hTHETA(x) = THETA0 + THETA1 * x1 + THETA2 * x2 + ...
[ assumes features are independent? or is that covered in the THETAs? ]

assume x0 == 1
x = 0-indexed vector of n+1 dimensionality
THETA is also a 0-indexed vector of n+1 dimensionality
which makes hTHETA(x) = THETA^T * x (transpose THETA into a row vector and multiply it by the features)

# Gradient descent for multiple variables
cost function remains the same:
J(THETA) = 1/2m * SUM(hTHETA(x^i) - y^i)^2

Gradient descent:
THETAj := THETAj - ALPHA(DELTA/DELTA * THETAj) * J(THETA)
again, solve for all THETAs simultaneously
- partial derivative of cost function J(THETA)

# Gradient descent in practice 1: feature scaling
Normalize features (put them on the same scale)
e.g., size of house and number of bedrooms
different scales make for oddly-shaped contour functions, which makes gradient descent take a very long time

Ideally: get all features to -1 <= x <= 1 (avoid too large a range and too small a range)

Mean normalization: Replace x0 with x0 - u0 (size - 1000 / 2000)
u = average value; s = maximum value - minimum value (or std dev)
x0 = (x0 - u0) / s0

# Gradient descent in practice 2: learning rate
debugging: make sure GD is working correctly
watch progress towards minimzing J(THETA) over # of iterations that GD runs
J(THETA) should decrease after every iteration (when GD is solid); declare converge if decrease < 10^-3 in one iteration

if J(THETA) is increasing, maybe ALPHA is too big?
if it's cyclical, use smaller ALPHA
- for sufficiently small ALPHA, GD should work on every iteration (but it can be too slow to converge)

To choose ALPHA
..., 0.001, 0.003, 0.01, 0.03, 0.1, 0.3, 1, ...

# Features and polynomial regression
choosing features:
ex: house price, two features (frontage and depth)
create a new feature: area (frontage * depth)

polynomial regression:
add new feature to change the model function (cubic vs quadratic vs linear, etc.) - don't forget to scale the features!
square a feature, square root it, cube it

# Normal equation
Method to solve for THETA analytically (vs. gradient descent)
m = 4
x1, x2, x3, x4, + x0
matrix X = all training data features (m x (n+1) dimensional) = design matrix
vector Y = data values (m-dimensional)
THETA = (X^T * X)^-1 * X^T(y)
training examples are transposed into the design matrix
Octave: pinv(X'*X)\*X'\*y

no need to scale features in the normal equation

- use gradient descent when you need to choose ALPHA/can use many iterations
- use normal equation - no need to choose ALPHA, no need to iterate
- GD works well with large ns
* NE needs to compute the inverse matrix, slow with large ns (1,000+)

NE doesn't work for classification problems

# Normal equation and non-invertability
What if X^T * X is non-invertible?
Octave will handle it regardless - use pinv (inv wouldn't work)

What if non-invertible? 
- probably redundant features (size in feet2 / m2) => eliminate dupes
- too many features for the number of training examples (m <= n) => delete features or regularize




