https://relate.cs.illinois.edu/course/cs450-s23/page/midterm-1-study-guide/

## Scientific Computing

- [ ] What is posedness and conditioning of problems?

- [ ] What are absolute and relative errors?
- [ ] What are forward and backward errors?
- [ ] What are the categories of sources of error in numerical methods?
- [ ] What does it mean for a result to have n accurate digits?
- [ ] How does the number of accurate digits relate to rounding?
- [ ] What is the relative and absolute condition number of evaluating a function for a given input? over a domain of inputs?
- [ ] What are the main components of floating point numbers?
- [ ] What is the typical relative accuracy in a floating point representation of a real number?
- [ ] What are normalized floating point numbers?
- [ ] Why are subnormal numbers used?
- [ ] How many digits can be lost during addition and multiplication of floating point numbers?

## Linear Systems

- [x] What is a vector norm? a normalized vector? a unit ball?
- [x] What defined a matrix norm? what are induced vector norms? what is the Frobenius norm?
- [x] What is the matrix condition number?
- [x] What is the conditioning of solving a linear system? of matrix-vector multiplication?
- [ ] How are the propagated data error, forward error, and backward error related? in terms of conditioning?
- [x] How does one solve a triangular linear system? What is the cost?
- [ ] What is LU factorization, when does it exist and when is it unique?
- [x] Why is pivoting necessary and what type of pivoting strategies are possible?
- [x] What is the cost of Gaussian elimination?
- [x] How can Gaussian elimination be done with elementary elimination and permutation matrices?
- [x] How do you solve a linear system given a pivoted LU factorization?
- [x] What is the SVD of a matrix? What are the properties of the 3 matrices obtained from SVD of a matrix?
- [x] What are the Cholesky and $LDL^T$ factorizations? When can they be used and what are their advantages?
- [ ] How can we solve a rank-1 perturbed problem via the Sherman Morrison formula?
- [ ] How can we take advantage of tridiagonal or banded structure in solving a linear system?

# Least Square System

- [x] How can you solve a least-squares problem using the SVD?

- [x] Given an SVD of the matrix and a right-hand side, how would you find the 2-norm of the residual of a least-squares problem?
- [x] How can least squares problems be solved via the normal equations? What are the advantages and disadvantages of that?
  - Let the gradient equal zero could derive the normal equations.
  - Disadvantages: 1. Information might lost in matrix multiplication. 2. Condition number is square making computation much more sensitive.
- [x] On what factors does the conditioning of a linear least-squares problem depend on?
- [x] What is QR factorization, when does it exist and is it unique?
  - QR factorization 
- [x] What is an orthogonal matrix?
- [x] What is a projection matrix?
- [x] What are the classical and modified Gram-Schmidt processes? What can you say about their stability?
- [x] What is a Householder reflector matrix, what properties does it have?



