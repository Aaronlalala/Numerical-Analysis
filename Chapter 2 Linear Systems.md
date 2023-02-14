[toc]

# System of Linear Equations

## Non-singular Matrix

A matrix is non-singular if it satisfies one of the following statements:

1. Matrix has an inverse.
2. Determinant of the matrix is non-zero.
3. Matrix has full rank (columns are independent)
   - Vectors are linearly independent when linear combination of vectors is 0 if and only if all parameters are zero
4. Matrix's null space only have 0 vector. It means for any $x \neq 0$, $Ax \neq 0$.

**If matrix $A$ is non-singular**, then $A$ always has an inverse $\implies x = A^{-1}b$  always exists regardless value of b.

**If matrix $A$ is singular**, $b$ determines whether the system has solutions. If there is a solution $Ax = b$, then exist $z$ such that $A(x + \gamma z) = b$, where $Az = 0$ and $\gamma$ is any scalar. (according to the 4-th bullet point). Thus, the solution cannot be unique.

Thus, for a linear system, there are only three cases: unique solution (A is non-singular), no solution (A is singular) and infinitely solution  (A is singular) .



## Orthogonal

### Orthogonal Matrix

An orthogonal matrix is a square matrix whose columns are mutually orthogonal unit vectors and the dot product of the columns equal to zero.

Some properties of orthogonal matrix:

- It must be square matrix
- Columns of an orthogonal matrix are mutually orthogonal and has length 1.
- $A^TA = I$
- It preserves inner product: $<Av, Aq> = (Av)^T (Aq) = v^T (A^T A) q = v^T I q = v^T q = <v, q>$
- It preserves the length of vectors: $||Av|| = ||v||$.

### Orthogonal Vector

Two vector are orthogonal if their inner product is zero. Projection of one onto the other is zero. If vectors are orthogonal. They are linearly independent.



## Matrix Norm

$\|A\|_1$ is the maximum absolute column sum of the matrix.

$\|A\|_{\infin}$ is the maximum absolute row sum of the matrix.

**Induced matrix norm:** $\|A\| = max_{x \neq0} \dfrac{\|Ax\|}{\|x\|}$, where $\|\cdot\|$ is 2-norm by default. It could be intuitively understood as the largest proportion that a matrix could stretch a vector. $\|y\| = \|Ax\|$ is the length of the transformed vector.

**Properties of matrix norm:**

1. cond(A) $\geq 1$. 
2. For any non-zero scalar $\gamma$, $cond(\gamma A) = cond(A)$. 
3. For any diagonal matrix, condition number is the maximum diagonal term over minimum diagonal term.



## Matrix Condition Number

The condition number of a matrix is a measure of the sensitivity of the solution of a linear system to small perturbations in the data. A high condition number indicates the solutionis highly sensitive to small perturbations in the data.

$$\kappa(A) = \|A\|_2 \|A^{-1}\|_2 = \frac{\sigma_{\max}(A)}{\sigma_{\min}(A)}$$, where $\sigma$ denotes the singular value of matrix A. If matrix A is singular, then $\kappa(A) = \infin$. Thus, condition number is also a measure of how a matrix is close to singular.

However, determinant of a matrix is not a good indicator of near singularity: although a matrix A is singular if det(A) = 0, the magnitude of a nonzero determinant, large or small, gives no information on how close to singular the matrix may be.



==Why $\|A^{-1}\|_2 = \frac{1}{\sigma_{min}(A)}$?==

Given a matrix $A$, its SVD can be written as $A = U\Sigma V^T$, where $U$ and $V$ are orthogonal matrices and $\Sigma$ is a diagonal matrix whose diagonal entries are the singular values of $A$. The singular values of $A$ are positive real numbers that measure the magnitude of the stretches that $A$ applies to the unit vectors.

If $A$ is invertible, then its inverse $A^{-1}$ can be written as $A^{-1} = V \Sigma^{-1} U^T$, where $\Sigma^{-1}$ is a diagonal matrix whose diagonal entries are the reciprocals of the singular values of $A$. The operator norm of $A^{-1}$ is equal to the reciprocal of the smallest non-zero singular value of $A$, that is, $\|A^{-1}\| = \frac{1}{\sigma_{\min}}$, where $\sigma_{\min}$ is the smallest non-zero singular value of $A$.



### Perturbation to the output coefficient

It also provides a **upper bound** for the relative error $\frac{
|\delta_x|}{|x|}$. Define error of solution $\delta_x = \hat{x} - x$, where $\hat{x}$ is the  estimated solution. This solution not equals to x due to perturbations of b. $A\hat{x} = b + \delta_b$.  Then we have $A\hat{x} = A(x + \delta_x) = Ax + A\delta_x = b + \delta_b \implies A\delta_x = \delta_b \implies \delta_x = A^{-1}\delta_b$. Take the norm at both sides, we have $\|\delta_x\| = \|A^{-1}\delta_b\| \leq \|A^{-1}\|\|\delta_b\|$. Use similar method, we have $\|b\| \leq \|A\|\|x\| \implies \|x\| \geq \|b\| / \|A\|$. Divide two norms $\frac{\|\delta_x\|}{\|x\|} \leq \|A\|\|A^{-1}\|\frac{\|\delta_b\|}{\|b\|}$. 

### Perturbation to the input coefficient

I am also confused what the exactly the norm is used in matrix condition number? If the condition number of a matrix measures the ratio of the maximum relative stretching to the maximum relative shrinking that the matrix does to any nonzero vectors. I believe p=2, because this norm represents the length. However, in the picture, it also mentioned something related to $\|A\|_{\infin}$ and $\|A\|_0$. That really confused me.

## Complexity to Solve a Linear System

orthogonal:

Triangular:

## LU Decomposition

[Gaussian Elimination](https://www.youtube.com/watch?v=RgnWMBpQPXk)

[Use Gaussian Ellimination to solve LU factorization.](https://www.youtube.com/watch?v=BFYFkn-eOQk)

[Partial Pivoting](https://www.youtube.com/watch?v=RgnWMBpQPXk): for each row of elimination, we want to make sure the leading element is non-zero (is max at that column.)

Check Strang's Textbook at chapter 2. Very good explanation.

## Complexity to Solve a Linear System

Solve a triangular matrix linear system requires only $n^2$.

Computing the LU factorization by Gaussian eliminatino requires about $n^3/3$ floating-ponit multiplications and additions.

Thus, using LU factorization method to solve linear system is dominanty by the factoriazation part.

### Cholesky Factorization Properties

Cholesky factorization can decompose a symmetric (Hermitian) positive definite matrix into a product of a lower triangular matrix and its transpose. $A = LL^T$. Once the factorization is computed, it could be used to solve the linear system, compute the determinant of matrix and compute the inverse of the matrix.

The diagonal entries of L are the square roots of the corresponding diagonal entries of A.

