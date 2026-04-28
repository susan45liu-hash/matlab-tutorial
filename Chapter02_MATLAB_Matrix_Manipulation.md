# Chapter 2: MATLAB Matrix Manipulation
## 2.1 Special Matrices
Special matrices fall into two major categories: one consists of general-purpose special matrices—such as the zero matrix, the identity matrix, and so forth.  
Another category consists of special matrices used in specialized disciplines—such as magic square matrices, Vandermonde matrices, Hilbert matrices, and so on.
### 2.1.1 General-Purpose Special Matrices
①`zeros` function: Generates a matrix consisting entirely of zeros (a zero matrix).  
②`ones` function: Generates a matrix consisting entirely of ones.  
③`eye` function: Generates a matrix with ones along its main diagonal. When the matrix is ​​square, this results in an identity matrix.  
④`rand` function: Generates a random matrix with elements uniformly distributed within the interval (0, 1).  
⑤`randn` function: Generates a random matrix with elements following a standard normal distribution (mean = 0, variance = 1).  

The five function call formats listed above are consistent.

Let's take the `zero` function as an example:  
Format:

$$
zeros(m)
$$

Generates an m×m zero matrix.

$$
zeros(m,n)
$$

Generates an m×n zero matrix.

$$
zeros(size(A))
$$

Generate a zero matrix of the same size as matrix A.




### 2.1.2 Special Matrices for Specific Disciplines


### 2.1.3 Magic Square Matrices


### 2.1.4 Vandermonde Matrices


### 2.1.5 Hilbert Matrices


### 2.1.6 Adjugate Matrices
















## 2.2 Matrix Transformations
## 2.3 Matrix Evaluation
## 2.4 Eigenvalues ​​and Eigenvectors
## 2.5 Sparse Matrices
