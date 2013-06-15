# Unsupervised learning
Clustering! (one type of unsupervised learning)
unsupervised learning = learning from unlabelled data; finding structure in the data

# K-means algorithm
Most popular option
1. Randomly initialize cluster centroids (# depends on desired # of clusters)
2. Assign each point to a cluster based on which centroid is closer
3. Move the centroids to the average of the points in their cluster
4. Repeat until the centroids stop moving

Inputs:
* K = number of clusters
* training set {x1, x2, ..., xM} (no x0)

Calculate:
* ci := index from 1 to K of cluster centroid closest to xi
* MUk := average (mean) of points assigned to cluster k

If there's a centroid with no points, then you usually just drop that centroid

## Non-separated clusters
e.g., t-shirt sizing (cluster within a continuous range)
K-means may work

# Optimization objective
K-means also has a cost function that is minimizable

MUci = cluster centroid of cluster to which example xi has been assigned

Optimization objective:
J(c1...cM, MU1...MUK) = 1/m * sum( (|| xi - MUci ||)^2 )

The cluster assignment step is minimizing the cost function (for c1...cM, holding the MUs constant)
The move-centroid step is minimizing the cost function with respect to MU1...MUK

# Random initialization
Initialization:
* should have K < m
* randomly pick K training examples
* set MU1...MUK equal to these K examples

K-means can converge on different solutions based on how it is initialized; specifically, you can hit a local optimum
Increase the odds of avoiding local optima:
* run the algorithm multiple times with different initializations (e.g. 50-1000 times)
* pick the clustering that gives the lowest cost
* usually works for K = 2-10; much higher K makes this less effective

# Choosing the number of clusters
No great answer for setting K; most commonly, you just look at the data and make your best guess / intuitive call

The Elbow method:
* compute cost function across multiple K values
* look for the elbow in the plot (where increasing K doesn't improve distortion as much as it did previously)
* often, there's no elbow

Alternative:
Evaluate K-means based on a downstream metric
Example: t-shirt sizing; compare S-M-L to XS-S-M-L-XL clustering by running both, then check to see how the sizes would fit the customers in each cluster, etc.
