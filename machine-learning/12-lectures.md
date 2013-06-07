# Optimization objective
Support vector machines - sometimes cleaner and more powerful for complex non-linear functions
For logistic regression:
* if y = 1, we want hTHETA(x) ~= 1, which means THETA^T * x >> 0
* if y = 0, we want hTHETA(X) ~= 0, which means THETA^T * X << 0

SVM: take the logistic regression cost function and manipulate it
come up with Cost1(z) and Cost0(z) (for y = 1 and y = 0)
SVM equation in slides/official notes

Regularizing on the first term: C = 1/LAMBDA

SVM does not output probability -- it just outputs 1 or 0

# Large margin intution
SVMs as large margin classifiers
If y = 1, we want THETA^T * X >= 1 (not >= 0), and similarly for y = 0 (<= -1) -- eliminate the middleground

if C is huge, we'll want to set the first term (the sum of the costs) to 0, so you end up solving for 1/2 * sum(THETAj^2)

linearly-separable: there are one or more straight lines that separate the classes
SVM will select a better decision boundary when there are many options
it attempts to maximize the margin - distance from training examples
(this is a simplification; it's more complicated, esp when you factor in outliers; changing C can affect the behavior)

# Math behind large margin classification
Vector inner product; take two two element vectors u and v
u^T * v = ?
||u|| = length of vector u (aka norm of u)
plot u and v on a graph
projection p = vector v projected onto vector u
p = length of projection
u^T * v = p * ||u|| = u1v1 + u2v2 = v^T * u
p is signed

sqrt(THETA1^2 + THETA2^2) = ||THETA||