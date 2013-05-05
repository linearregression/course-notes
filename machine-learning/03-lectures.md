# Matrices and vectors
Matrix: rectangular array of numbers written in square brackets
Dimension is rows x cols
A(sub ij) = row i, col j member of matrix A

Vector is an n x 1 matrix
n-dimensional vector (n == number of elements)
y(sub i) = ith element of the vector y
inconsistency between 0- and 1-indexed vectors (in math, tend towards 1; in programming, tend towards 0; assume 1-indexed)

usually, matrices are upper-cased (A,B,C) and vectors are lower-cased (a,b,c)

# Addition and scalar multiplication
addition: add corresponding elements 
- you can only add matrices of the same dimensionality

scalar multiplication: multiply each element by the scalar

# Matrix-vector multiplication
Multiply each row of the matrix by the elements of the vector and sum them, resulting in a vector
m x n matrix * n-dimensional vector == m-dimensional vector

Trick to use linear algebra to compute predictions from the hTHETA(x) function for a data set
- construct a matrix of [1 value, 2 value, etc.] and a vector of [h0 h1] and multiply them out
- prediction = data matrix * parameters
- more computationally efficient than looping over the data set

# Matrix-matrix multiplication
example: 3x2 * 2x3
1. multiple 3x2 by first column of 2x3 (matrix-vector multiplication)
2. multiple 3x2 by second column of 2x3 (m-v mult)
3. end result is 2x2 of first result and second result (1 => first column, 2 => second column)

You can only multiply matrices where the cols from the 1st matrix == rows from the 2nd matrix; result is # of rows from first matrix x # of cols from second

Neat trick: view competing hypotheses' predictions against data set
- construct matrix [1 value, 1 value]
- construct matrix [h0 h0 h0, h1 h1 h1]
- result orders predictions in columns

# Matrix multiplication properties
Scalar multiplication is commutative
Matrix multiplcation is *not* cumulative
Example: A is m x n; B is n x m A x B gives m x m; multiply B x A and you get n x n

Scalar multiplcation is associative
so is matrix multiplication

Identity matrix == different identity matrix for each dimension nxn
1x1 = [1]
2x2 = [1 0, 0 1]
etc. (basically, all 0 except for 1,1, 2,2, 3,3, etc. members which are 1

A (m x n) * I == I * A (but the first I is n x n and the second is m x m)

# Inverse and transpose
3 and 1/3 == inverses of each other (3 and 3^-1)
not all numbers have inverses (0)

If A is an m x m matrix (square matrix) and has an inverse, then A * A^-1 == I
- inverses usually computed by libraries (e.g., Octave)

no inverse == singular / degenerate matrix

Transpose: m x n => n x m (columns become rows)
so A is m x n, and B = A^T
then B is n x m, and Bij = Aji

