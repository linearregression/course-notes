# Anomaly detection
Example of unsupervised learning

Flag as anomaly if result of the model is <= some EPSILON

* Fraud detection
* Manufacturing
* Server monitoring

# Gaussian distribution
Gaussian distribution == normal distribution

`x ~ N(MU, SIGMA^2)`
x is distributed with mean MU, variance SIGMA

`p(x; MU, SIGMA^2)`

## Parameter estimation problem
Given a dataset, estimate MU and SIGMA

`MU = 1/m * sum(x^i)`

`SIGMA^2 = 1/m * sum(x^i - MU)^2`

# Algorithm
Density estimation

Assume unlabeled training set

`p(x) = p(x1;MU1,SIG1^2) * p(x2;MU2,SIG2^2) * … p(xn;MUN,SIGN^2)`

`p(x) = prod( p(xj;MUj,SIGMAj^2) )`

1. Choose features that may show an anomaly
2. Fit params `MU` and `SIGMA`
3. Given new `x`, compute `p(x)`; anomaly if `p(x) < EPSILON`

# Developing and evaluating a system
* Assume some labeled data
* Train on (mostly) non-anomalous data
* CV and test sets may have anomalous data

10,000 good / 20 bad = 6000 train, 2000/10 CV, 2000/10 test

## Evaluation

* Fit model on Xtrain
* Evaluate against CV / test set
    * precision / recall
    * F1 score
    * true pos, false pos, true neg, false neg
    * *can also use CV to choose param* `EPSILON`

# Anomaly detection vs supervised learning
Anomaly detection may be superior if you have: 

* very small # of positive examples
* large # of negative examples
* many "types" of anomalies; future anomalies may be totally different than anything seen so far

# What features to use?
* Plot the data first to confirm that it's Gaussian (`hist()`)
* Manipulate the data to make it more Gaussian (`log(x)`, for example)

## Error analysis
Want `p(x)` large for normal examples and small for anomalies

* Problem: `p(x)` is large for both normal and anomalies
* Find a new feature that would detect the anomalies

