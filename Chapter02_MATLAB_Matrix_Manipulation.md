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

```matlab
>>A=zeros(2,3)
A	=
  0  0  0
  0  0  0

>>zeros(size(reshape(A,3,2)))
ans =
  0	0	
  0	0	
  0	0
```
---
Example: First, generate a 5x5 matrix A consisting of two-digit random integers; next, generate a 5x5 random matrix B with a normal distribution having a mean of 0.6 and a variance of 0.1; finally, verify the identity (A+B)I = IA+BI (where I is the identity matrix).
`rand` function: Generates a random number *x* with a uniform distribution over the open interval (0, 1).
`fix(a+(b-a+1)*x)`: Generates a random integer with a uniform distribution over the interval [a, b].
`randn` function: Generates a random number *x* with a standard normal distribution (mean = 0, variance = 1). `μ + σ*x`: Yields a random number with a mean of μ and a variance of σ².

```matlab
>>A=fix(10+(99-10+1)*rand(5));	
>>B=0.6+sqrt(0.1)*randn(5);
>>C=eye(5);
>>(A+B)*C==C*A+B*C
ans =
  1  1  1  1  1
  1  1  1  1  1
  1  1  1  1  1
  1  1  1  1  1
  1  1  1  1  1
```
---

### 2.1.2 Special Matrices for Specific Disciplines

#### Magic Square Matrices
The turtles retrieved from the Luo River have some markings on their backs, forming a matrix.
<img width="516" height="264" alt="image" src="https://github.com/user-attachments/assets/74a053c5-586e-4ab3-b3b4-cb3abbf8bf1e" />

* An n-order magic square consists of n² integers: 1, 2, 3, ..., n².  
* The sum of the n elements in each row, column, and main and secondary diagonals is equal.  
* The sum of the elements in each row and column of an n-order magic square is (1 + 2 + 3 + ... + n²) / n = (n + n³) / 2.  
* The MATLAB function `magic(n)` generates a specific magic square.

---
Example generates an 8x8 magic square. Find the sum of the elements in each row and column.
```matlab
>> M=magic(8);
>>sum(M(1,:))
ans=
  260
>> sum(M(:,1))
ans=
  260
```
---

#### Vandermonde Matrices
For a vector \( v = [v_1, v_2, \cdots, v_n] \),  
the Vandermonde matrix is defined as:

$$
V =
\begin{bmatrix}
v_1^{n-1} & \cdots & v_1^2 & v_1^1 & v_1^0 \\
v_2^{n-1} & \cdots & v_2^2 & v_2^1 & v_2^0 \\
v_3^{n-1} & \cdots & v_3^2 & v_3^1 & v_3^0 \\
\vdots    & \ddots & \vdots & \vdots & \vdots \\
v_n^{n-1} & \cdots & v_n^2 & v_n^1 & v_n^0
\end{bmatrix}
$$

<details>
<summary>Chinese tips</summary>
\begin{bmatrix} + & 对齐 + \\ 换行
</details>

#### Hilbert Matrices


#### Adjugate Matrices
















## 2.2 Matrix Transformations
## 2.3 Matrix Evaluation
## 2.4 Eigenvalues ​​and Eigenvectors
## 2.5 Sparse Matrices
