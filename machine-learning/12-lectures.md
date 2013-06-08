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

# Kernels
Non-linear classifiers in SVM: Kernels
One option for a complex NLC: polynomial features
* THETA0 + THETA1 * f1 + THETA2 * f2, etc.
* Is there a better / different choice for the features?

Pick a few landmark points in space of possible X
Define features as similarity between x and a given landmark:
f1 = k(x, l1) = similarity(x, l1) = exp(- (|| x - l1 ||) / 2 * SIGMA^2) 
this similarity function is a kernel; the exp() one is called the Gaussian kernel

Intuition:
* if x ~= l1, then the numerator will be close to 0, so f1 will be close to 1
* if x is far from l1, then the numerator will be large and f1 will be close to 0

Each landmark point computes a new feature
SIGMA^2 is a variable parameter; it controls how "spiky" the model is (how close X has to be to the landmark point to give a result of 11)

Intution: y ~= 1 whenever you're close to one of the landmarks, so you get a complex non-linear boundary

How do you choose landmarks? Each training example becomes a landmark [ danger of overfitting? ]
That gives you a feature vector: f = [f0; f1; f2]  (f0 = 1)
That vector can be applied to x^i to get the vector for that point

Hypothesis:
* Given x, compute feature vector; predict y=1 if THETA^T * f >= 0
* Train with the SVM equation (but with f^i instead of x^i)
* note that the number of features n = number of examples m in this case
* also: the trailing term (sum(THETAj^2)) can be rewritten THETA^T * THETA (without THETA0) == ||THETA||^2

Kernels can be very slow with other algos (e.g., logistic regression)

SVM parameters
* large C = lower bias, higher variance
* small C = higher bias, lower variance
* large SIGMA^2 = features vary smoothly = higher bias, lower variance
* small SIGMA^2 = features vary abruptly = lower bias, higher variance

# Using an SVM
Use an SVM package to solve for THETA
* need to specify C and choice of kernel (or no / linear kernel)
* might want a linear kernal if n and m are large and you don't want a complicated, non-linear boundary (risk of overfitting)
* Gaussian kernel - you have to choose SIGMA^2 - choose if number of features is small and m is large
  * scale features before using the kernel (otherwise the norm for some Xs will be huge and those will dominate the equation)
* not all similarity functions make valid kernels - Mercer's theorem
* other kernels
  * polynomial kernel k(x,l) = (x^T * l + constant)^degree
  * string kernel, chi-square kernel, histogram intersection kernel

Multi-class classification
* many packages build it in
* otherwise, use one-vs-all method

Logistic regression vs SVMs
* if n is large relative to m (10k vs 1k), use logistic regression or SVM with a linear kernel
* if n is small and m is biggish (10k), use SVM with a Gaussian kernel
* if n is small and m is large, create/add more features manually and use logistic regression or SVM with a linear kernel (Gaussian kernel would be slow)

Logistic regression basically equal SVM without a kernel (linear kernel)
Neural networks may work well for all of these, but may be slower to train
Local optima are not a problem for SVMs, but may be for networks