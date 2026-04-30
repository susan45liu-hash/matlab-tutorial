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

In MATLAB, the function `vander(v)` generates a Vandermonde matrix based on the vector \( v \).

```matlab
A = vander(1:5)

A =
     1     1     1     1     1
    16     8     4     2     1
    81    27     9     3     1
   256    64    16     4     1
   625   125    25     5     1
```

#### Hilbert Matrices
The Hilbert matrix is ​​a well-known ill-conditioned matrix, meaning that a small change in any element will significantly alter the value and inverse of the entire matrix. The degree of ill-conditioning is related to the matrix order.

The \( n \)-th order Hilbert matrix is defined as:

$$
H =
\begin{bmatrix}
\frac{1}{1} & \frac{1}{2} & \cdots & \frac{1}{n} \\
\frac{1}{2} & \frac{1}{3} & \cdots & \frac{1}{n+1} \\
\vdots      & \vdots      & \ddots & \vdots \\
\frac{1}{n} & \frac{1}{n+1} & \cdots & \frac{1}{2n-1}
\end{bmatrix}
$$

Each element of the Hilbert matrix is defined as:

$$
H(i,j) = \frac{1}{i + j - 1}
$$

In MATLAB, the function to generate an n-order Hilbert matrix is ​​hilb(n).
```matlab
>>format rat
>>H=hilb(4)
H=
   1     1/2    1/3    1/4
   1/2   1/3    1/4    1/5
   1/3   1/4    1/5    1/6
   1/4   1/5    1/6    1/7
```
#### Adjugate Matrices
Let the polynomial be:

$$
p(x) = a_n x^n + a_{n-1} x^{n-1} + \cdots + a_1 x + a_0
$$

The companion matrix（伴随矩阵） associated with this polynomial is:

$$
A =
\begin{bmatrix}
-\frac{a_{n-1}}{a_n} & -\frac{a_{n-2}}{a_n} & \cdots & -\frac{a_1}{a_n} & -\frac{a_0}{a_n} \\
1 & 0 & \cdots & 0 & 0 \\
0 & 1 & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & 1 & 0
\end{bmatrix}
$$

The polynomial \( p(x) \) is the characteristic polynomial（特征多项式） of matrix \( A \),  and the roots of \( p(x) = 0 \) are the eigenvalues（特征值） of \( A \).

The MATLAB function to generate the adjoint matrix is ​​`compan(p)`, where `p` is a vector of coefficients of a polynomial, with higher-order coefficients listed first and lower-order coefficients last. For example, to generate the adjoint matrix of the polynomial x³ - 2x² - 5x + 6:

```matlab
>>p=[1,-2,-5,6];
>>A=compan(p)
 A=
2  5 -6
1  0  0
0  1  0
```
#### Pascal Matrix

According to the binomial theorem（二项式定理）, the coefficients of \( (x + y)^n \) form Pascal's triangle（杨辉三角）.  
The Pascal matrix（帕斯卡矩阵） is constructed by placing these coefficients along the left diagonals.  
Generate an n-order Pascal matrix: 

$$
P = pascal(n)
$$

```text
          1
        1   1
      1   2   1
    1   3   3   1
  1   4   6   4   1
1   5  10  10   5   1
```

Each element satisfies:

$$
P(i,j) = P(i-1,j) + P(i,j-1)
$$

with:

$$
P(1,j) = 1,\quad P(i,1) = 1
$$

---
```matlab
P = pascal(5)

P =
     1     1     1     1     1
     1     2     3     4     5
     1     3     6    10    15
     1     4    10    20    35
     1     5    15    35    70
```
---

Each element of the Pascal matrix is a binomial coefficient（组合数）.

## 2.2 Matrix Transformations


### Diagonal matrix
### matrix construction
### triangular matrix
### matrix transpose
### left-right flip
### top-bottom flip













## 2.3 Matrix Evaluation
## 2.4 Eigenvalues ​​and Eigenvectors
## 2.5 Sparse Matrices
