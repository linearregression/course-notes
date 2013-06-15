# Gradient descent
Optimization method, minimizing cost function step by step

# Logistic regression, SVM
also optimizable by gradient descent

# Regularization
Tweak preference for simpler/complex models when data points are highly correlated

# Stochastic & minibatch gradient descent
Stochastic GD: run gradient descent on a single, random data point at each step
Minibatch GD: run GD on a small subset of data points chosen fresh each step
Stochastic GD is (somewhat) parallelizable

# Unsupervised learning
No feedback (compared to all other ML types)
Used for:
* outlier detection
* classification / clustering
* compression

# K-means
Clustering algorithm
You have to know how many clusters you're looking for upfront

Start with guessed centroid points for each cluster; assign points; find average point based on distances to points; repeat
Parallelizable via map-reduce

Answer depends on starting points

# DBSCAN
Finds non-linearly-separable clusters
Does not require assumption of # of clusters upfront
No dependence on starting conditions
Only two parameters

Sensitive to Euclidean distance measure problems (so is k-means)
Variable density can be a problem (tight vs. loose clusters in the same dataset)
