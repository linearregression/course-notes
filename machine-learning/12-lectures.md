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