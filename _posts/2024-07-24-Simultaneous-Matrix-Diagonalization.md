---
layout: post
title: Simultaneous Matrix Diagonalization
permalink: /blog/simultaneous-matrix-diagonalization/
published: true
---

Simultaneous diagonalization of a group of matrices plays an important role in identifying irreducible representations of a group from its regular representation. But before delving into simultaneous diagnolization of regular matrix represenation of all elements of a group, we briefly discuss how a single matrix can be diagnonalized.  
  
## Diagnonalization of a Single Matrix
Let  matrix $$A$$ be a $$n \times n$$ matrix, which has following eigenvalues:  
-  $$m$$ distinct real eignevalues, $$\lambda_1, \lambda_2, \lambda_3, .... , \lambda_m$$  
-  One complex conjugate pair, $$\lambda + i\omega, \lambda - i\omega$$  
-  $$\mu$$ with algebraic and geometric mutiplicity  2, $$s.t. (A- \mu I)$$ has a 2-D NULL space.  
-  $$\gamma$$ with algebraic multiplicity 2 and geometric mutiplicity  1, $$s.t. (A- \gamma I)$$ has a 1-D NULL space.

Then $$A$$ can be block diagnonalized as follows [1]:  

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

This is called ***Jordan canonical form*** of a square matrix.

This implies that the a square matrix is fully diagonalizable, if the direct sum of its eigenspaces spans the whole vector space. i.e algeriac multiplicty of each eignevalue is equal to its geometric multiplicity. In cases where this condition is not met, the matrix is still block diagnonalizable 

## Simultaneous Diagnonalization of Matrices and Irreducible Representations
A question begs answering: Given a class of square matrices or operators, is it possible that one could find a transformation, a change of basis, in which their matrix representations all have the same structure such as diagonal or block diagonal?
The answer is, yes. Based on our discussion of diagnonalizing a single square matrix, we know that eignevectors can be used to diagnonalize a matrix. So if a group of matrices share a full set of eignevectors they can be simultaneously diagonalized/block diagnoalized. 

A group of square matrices can be simulataneously diagonalized if they are individually diagonalizable and mutually commute. To understand this intuituvely, we must appretiate that diagnonal matrices always commute. Hence, they would commute in any basis.

Simulataneous diagonalization of matrix represenatation of group elements can be used to find irreducible representations of a group. This approach might work with groups having few elements with simple matrix represenations. However, this approach is not viable for any practical purposes.

This is where *Character Theory* steps in, and is the topic on our next post.


## References
1. [Block Diagnozalization](https://www.youtube.com/watch?v=SsCiQym5yQU)
  
2. [Discovering Transforms: A Tutorial on Circulant Matrices, Circular Convolution, and the Discrete Fourier Transform](https://arxiv.org/abs/1805.05533)


