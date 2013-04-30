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
Choose params such that hθ(x) is close to y for training examples (x,y) - minimization problem over θ0,θ1 - potentially minimize average square of sum of differences between prediction and actual price (average = 1/2m)

cost function = J(θ0, θ1) = 1/2m * sum(1..m)(hθ(x(i)) - y(i))^2
squared error function

## Cost function intuition 1
simplified: hθ(x) = θ1 * x ==> θ0 = 0
if θ1 == 1, then J(θ1) = 0 (for x==y training set)
if θ1 == 0.5, then J(θ1) ~= 0.58 (for x == 0.5y)
computing range of θ1, you get a parabolic function with the minimum at θ1 == 1 (where it's 0)

## Cost function intuition 2
!: Contour plots/figures may be confusing
Single parameter cost function == parabolic function
Double parameter cost function == parabolic function in 3d

## Gradient descent
Algorithm for minimizing cost function: 
1. Start with some value for params
2. Keep changing params to reduce cost function, hope to find a minimum

Stepwise descent in direction of steepest descent, results depend on starting point (e.g., local minima traps)

Gradient descent algorithm:
Repeat until convergence: assign θj to θj - ALPHA[(DELTA/DELTA * θj)J(θ0,θ1)] for j = 0 and j = 1 *simultaneously*
ALPHA == learning rate
[DELTA....] == derivative term; will be explained in next lecture

## Gradient descent intuition
Ex: single parameter, set of real numbers -- parabolic function
partial derivative == derivative with additional variables
positive deriviative (slope) ==> θ1 decreases, moves closer to minimum
negative derivative (slope) => θ1 increases, moves closer to minimum

effects of ALPHA
too small == gradient descent is too slow
too large == GD can overshoot the minimum, may fail to converge or even diverge
if θ1 is already at a local minimum, what happens? derivative term is 0, so ALPHA * 0, so gradient descent doesn't move you
- so even with a fixed ALPHA, GD takes smaller steps as you get closer to a local minimum (because the derivative term gets smaller with each step)

## Gradient descent for linear regression
! Multivariate calculus to expand the partial derivatives
Linear regressions always have a convex function (bowl-shaped), so a single global minimum/optimum

"batch" gradient descent -- each step of GD uses all the training examples (the sum of square of diffs)
some alternatives use subsets of the training examples

normal equations method == you can solve for the solution numerically, but GD scales better

## What's next
1. minimize the cost function without iteration (much faster)
2. learning with a larger number of features (not just x => y)
- linear algebra provides best notation for matrices and vectors (matrix for x's, vector for y's)


