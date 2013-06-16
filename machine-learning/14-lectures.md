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
