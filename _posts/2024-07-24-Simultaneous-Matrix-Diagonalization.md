---
layout: post
title: Simultaneous Matrix Diagonalization
permalink: /blog/simultaneous-matrix-/
published: false
---

Matrix diagonalization plays an important role in identifying irreducible representations of a group its from regular representation. But before delving into simultaneous diagnolization of regular matrix represenation of all elements of a group, to find its irreducible representations, we briefly discuss how a single matrix can be diagnonalized. When complete diagonalization is not possible, then a matrix can still be block-diagnonalized.

## Diagnonalization of a Single Matrix
Let  matrix $$A$$ be a $$n X n$$ matrix, which has following eigenvalues:  
-  $$m$$ distinct real eignevalues, $$\lambda_1, \lambda_2, \lambda_3, .... , \lambda_m$$  
-  One complex conjugate pair, $$\lambda + i\omega, \lambda - i\omega$$  
-  $$\mu$$ with algebraic and geometric mutiplicity  2, $$s.t. (A- \mu I)$$ has a 2-D NULL space.  
-  $$\gamma$$ with algebraic multiplicity 2 and geometric mutiplicity  1, $$s.t. (A- \gamma I)$$ has a 1-D NULL space.

Then A can be block diagnonalized as follows [1]:  

$$A =
\begin{bmatrix}
\begin{bmatrix}
\lambda_1 & 0 & \cdots & 0 \\
0 & \lambda_2 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & \lambda_m
\end{bmatrix} & 0 & 0 & 0 \\
0 & 
\begin{bmatrix}
\lambda & \omega \\
-\omega & \lambda
\end{bmatrix} & 0 & 0 \\
0 & 0 & 
\begin{bmatrix}
\mu & 0 \\
0 & \mu
\end{bmatrix} & 0 \\
0 & 0 & 0 & 
\begin{bmatrix}
\gamma & 1 \\
0 & \gamma
\end{bmatrix}
\end{bmatrix}$$

## Simultaneous Diagnonalization of Matrices
- A matrix is diagonalizable if it has full set of eignevectors i.e. an n x n eigenvector has n linearly independent eignevectors.
- A group of matrices are simultaneouly diagnonalizable if they are individually diagonalizable and mutually commute.
- The shift operator and its adjoint commute with ciruclant matrices. Rather it can be said that a matrix is circulant iff it communtes with the shift operator
- The shift operator is in some sense the most fundamental circulant matrix
- Circular convolution of two vectors a , v is defined as:
  a * v = circulant matrix(a) *v
  -  Circular convolution is associative and commutative
  -  i.e a * x = C_a  x = C_x a.
  -  C_ab =  C_a * C_b
  -  C_a C_b = C_b C_a

Schur's Lemma
- The only relationship that can exist between who irredicuble repressentation is similarity
  XR=R'X i.e. $$XRX^{-1} = R'$$  
- If a matrix X commutes with all the matrices of a collection of irreducible matrices, i.e XR = RX, for all R's in the
-  collection then it has to be a scalar multiple if identity matix I


## References
1. [Block Diagnozalization](https://www.youtube.com/watch?v=SsCiQym5yQU)
2. [Discovering Transforms: A Tutorial on Circulant Matrices, Circular Convolution, and the Discrete Fourier Transform] (https://arxiv.org/abs/1805.05533)


