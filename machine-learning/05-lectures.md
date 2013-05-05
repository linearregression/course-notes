# Basic operations
Octave!
~= for not-equal
PS1 for prompts
disp, sprintf
format long/short

A = [ 1 2; 3 4; 5 6 ]
v = [ 1; 2; 3 ]

v = 1:0.1:2 % => [ 1 1.1 1.2 1.3 ... 2 ]
v = 1:6 % => [1 2 3 4 5 6]

ones(2,3) % => 2x3 matrix of 1s

zeroes(1,3) % => 1x3 matrix of 0s

rand(x,y) % => matrix of random numbers

randn(x,y) % => gaussian distribution of random numbers

hist(matrix, categories=10) % => histogram of data

eye(4) % => 4x4 identity matrix

# Moving data around
size(matrix) % => 1x2 matrix of [rows, columns]

length(vec) % => size of longest dimension

pwd, cd, ls all work

load [filename] OR load('filename')
- loads file data into var named according to filename (e.g., feature.dat => feature)

who % => shows current variables
whos % => variables + metadata

clear [var] % => no arg, everything gets cleared

save [filename] [var] % => saves contents of var into filename in working dir
= filetypes: .mat is compressed, .txt -ascii is human-readable

vector(1:10) % => elements 1-10 of the vector
matrix(2,:) % => entire second row

A([1 3],:) % => 1st and 3rd rows, all columns
can reassign into matrix with these indexers (A(1,2) = whatever=> replace 2 with whatever) or add a column (column vector)
- A = [A; (COLUMN VECTOR)]
A(:) % => all elements in a single column vector

C = [A B] % => adds B to A as additional columns
C = [A; B] % => adds B to A as additional rows

# Computing on data
A .\* B is element-wise multiplication of matrices
A .^ 2 is element-wise squaring
1 ./ A is inverse of each element

magic(x) % => x x x magic square

# Plotting data


