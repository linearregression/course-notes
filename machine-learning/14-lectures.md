# Dimensionality reduction
Motivation 1: data compression
* save disk space
* speed up algorithms

Example: reduce data from 2d to 1d (measures in inches and cm)
* approximate all measures by projecting examples onto a single line
* similarly for 3d to 2d -- project the data onto a 2d plane

# Visualization
Another motivation for dimensionality reduction: better understanding through visualization

Condense many dimensions to 2 (example: 50 => 2 for country data)
* plot country size (economy) vs per person GDP

# Principal component analysis
PCA tries to find a surface that minimizes the projection distance/error
* actually, it finds a vector
* reduce from n-dimensions to k-dimensions / vectors (u1, u2, etc.)

PCA is not linear regression - minimize projection dist vs dist from line

# PCA algorithm
Steps:
1. Preprocessing: mean normalization (and possibly feature scaling, as well)
  * compute mean of each feature (uj), then replace each xj with xj-uj
  * scale if necessary
2. Calculate uk by
  * computing covariance matrix
  SIGMA = 1/m * sum( (xi)(xi)^T )
  * compute eigenvectors of matrix SIGMA
  [U,S,V] = svd(Sigma); # singular value decomposition, or eig(Sigma)
  U matrix is n x n matrix; columns are the vectors that we want
3. Ureduce = n x k matrix of u1...uk, then transpose and multiply by X to get reduced Z
  Ureduce^T * X

Vectorized 2 = Sigma = (1/m) * X' * X
Ureduce = U(:, 1:k)
z = Ureduce' * x

# Choosing the number of principal components
Selecting k - the target, reduced dimensionality

Concepts:
* average squared projection error (goal of PCA)
* total variation in the data = average length, squared, of training examples (how far from the all-0 vector?)

Choose k so that the ratio between avg squared projection error and total variation <= 0.01 (1%)
"99% of the variance is retained"

5%, 10%, 15% are also (relatively) common, but 95-99% is *most* common

Process:
* try PCA with k=1, check ratio
* repeat with increasing k until ratio <= 0.01

[U,S,V] = svd(Sigma)
S = square matrix (n x n), diagonal values; for given value of k, the ratio can be computed as:
(sum(1..k) Sii) / (sum(1..n) Sii) >= 0.99

# Reconstruction from compressed representation
Xapprox = Ureduce * Z    # (n x k * k x 1 matrices == n x 1)

# Advice for applying PCA
PCA can speed up learning algorithms

Supervised learning problem:
* high-dimensional training examples (e.g., 10,000 features per example)
* extract inputs (giving us an unlabeled training set)
* apply PCA
* push PCA z back into the labels, giving a new labelled training set
* generate hTHETA(z) based on the new set
* for new example x, run it through PCA and apply the hTHETA hypothesis

Mapping of x -> z should be defined by running PCA only on the training set

Bad use of PCA: preventing overfitting by reducing number of features. BAD BAD BAD! Regularization is better.

Questionable use: using it before trying without PCA. Only fall back to PCA if you have to (speed, memory usage, etc.)
