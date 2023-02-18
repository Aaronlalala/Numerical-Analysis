[toc]

# Space

## Row Space

## Column Space

## Null Space



# Residual

Residual vector is orthogonal to the span of A. 

Know how to compute the projection

# SVD

## How to solve a SVD

## Partial SVD

![image-20230214130434425](Pictures/partialSVD.png)

If we inverse a non-square matrix (usually we do this to compute the pseudo inverse matrix A), we could drop the columns after n-th column of U. Because those columns will multiply zero vectors in the $\Sigma $ matrix.

# Pseudo Inverse

SVD allows to generalize to nonsquare matrix A. $A = U\Sigma V^T$ is the SVD factorization. Then we have $U\Sigma V^Tx = b \implies x = V\Sigma^{-1}U^Tb$. In this case, $A^\dagger = V\Sigma^{-1}U^T$. In most cases, matrix A is non-square. However, we could still compute the economic SVD for A and the some of the diagonal terms of $\Sigma$ are zeros. It does not matter since we could use this matrix to compute $A^{\dagger}$, which finally result in a square matrix.

Then we can use the pseudo inverse of A to compute the condition nubmer of singular matrix A.

# Least Square

## Uniqueness of Least Square Solution







## Orghogonality

## Conditioning

### Normal Equations Method

## QR Factorization

We want to change the matrix A into triangular systems, so that it's much easier to solve. QR factorization is such a transformation $A = Q \left(
\begin{array}{rr} 
R  \\
O 
\end{array}
\right)$, where R is an n\*n upper triangular matrix and Q is an m\*m orthogonal matrix. Then, 

$\|r\|^2_2 = \|b - Ax\| = \|b - Q \left(
\begin{array}{rr} 
R  \\
O 
\end{array}
\right)\|^2_2$. Multiply the residual by the orthogonal matrix won't change its Euclidean norm. So $\|Q^Tb -  \left(
\begin{array}{rr} 
R  \\
O 
\end{array}
\right)\|^2_2 = \|c_1-Rx\|^2_2 + \|c_2\|^2_2$, where $Q^Tb = [c_1, c_2]^T$. 















