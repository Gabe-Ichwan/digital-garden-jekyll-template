---
tags:
  - published
---
LU Factorization is a process formulated by [[Alan Turing]] that involves decomposing a matrix $A$ into the product of a lower triangular matrix $L$ and an upper triangular matrix $U$, in order to solve a system of equations in the form $Ax=b$. The steps are as follows:

1. Put a square and invertible matrix into upper [[Triangular Matrix|Triangular]] form by zeroing out all entries below the first pivot. Do this only by replacing those rows with a multiple of the top. (Multipliers equal lower divided by upper)
2. Repeat this process on the newly created square submatrix. 
3. Construct $L$ by filling an empty matrix with ones along the diagonal, and the multiples used previously in the spots where they created zero. 

### Efficiency

This factorization allows a system to be cheaply solved for a large number of right-hand-sides: The initial factorization cost is $\frac{2N^3}{3}$ [[Flops]], after which any number of additional right-hand sides can be solved  for only $2N^2$ [[Flops]] in the following steps. 

$$LUx=b$$
$$Ly=b \quad(N^2)$$
$$Ux=y \quad(N^2)$$

Note that no computation is needed for $Ux=y$ because $x$ is simply the vector of coefficients, and we trivially know the answer.

LU Factorization is also efficient storage-wise, because you can store all needed information in what used to be $A$. 

