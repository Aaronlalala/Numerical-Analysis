In this problem, we consider the Fiedler algorithm, which partitions graphs by finding eigenvectors of a matrix associated with the graph. Your main task will be to implement Lanczos to find a particular eigenvector.
Given a graph $G$, we can partition elements into groups by calculating the Fiedler vector of its Laplacian matrix $\boldsymbol{L}$ :
- if $i \neq j$,
- $l_{i j}=-1$ if the $i^{t h}$ vertex of $G$ is connected to the $j^{\text {th }}$ vertex
- $l_{i j}=0$ otherwise
- $l_{i i}=$ number of connections from vertex $i$ (degree of vertex $i$ )
The row-sums of the symmetric matrix $\boldsymbol{L}$ are zero, so it has a 1-dimensional null-space, which corresponds to its smallest eigenvalue, zero. The Fiedler vector of a graph $G$ is the eigenvector with the second smallest eigenvalue. From this vector, the graph can be partitioned by taking vertices corresponding to eigenvector elements with an less than the median in one partition and placing the remaining vertices in the other partition. As an intuition for why the Fiedler vector provides a partitioning with a small cut, we can consder a graph that has two disjoint partitions. The Fiedler eigenvector then contains ones for all vertices in one partition, and zeros for all vertices in the other partition, with an eigenvalue of zero (in this case the null space of $\boldsymbol{L}$ is 2 -dimensional).
Since we are interested in an extremal eigenvalue (second smallest) of a symmetric matrix, we will employ the Lanczos algorithm. Since we are not interested in the trivial 1dimensional null-space of $\boldsymbol{L}$, we will orthogonalize the starting Krylov vector to the vector of ones.

Your task is to implement the Lanczos algorithm in a function called lanczos and to extract the vector with the smallest Ritz value in the function fiedler_ritz. The lanczos function takes three arguments:

- L : Laplacian $\boldsymbol{L}$ of the dual graph (scipy. sparse matrix of shape: $n \times n$ )
- $x 0$ : Starting vector for Lanczos iteration (numpy. array of length $n$ )
- $\mathrm{k}$ : number of Lanczos iterations to be performed.
Your completed lanczos function should implement the Lanczos algorithm after removing the components of the $\mathbf{1}$ vector (vector of ones) from the initial guess $x 0$ via orthogonalization. It should return two matrices:
- Q : Contains first $\mathrm{k}$ orthogonal Lanczos vectors (numpy . array of shape: $n \times k$ )
- $\mathrm{T}$ : Tridiagonal matrix having eigenvalues and eigenvectors similar to the original Laplacian matrix $(\mathrm{L})$ provided. (numpy. array of shape: $(k \times k)$ )
These matrices are then given as arguments to the fiedler_ritz function, which should return an approximation to the Fiedler eigenvector:
- fiedlerVec: vector of dimension $n$ corresponding to the Ritz vector (i.e., approximate eigenvector) with the smallest Ritz value