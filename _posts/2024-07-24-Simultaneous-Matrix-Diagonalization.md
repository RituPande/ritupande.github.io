---
layout: post
title: Simultaneous Matrix Diagonalization
permalink: /blog/simultaneous-matrix-/
published: false
---

Matrix diagonalization plays an important role in identifying irreducible representations of a group its from regular representation. But before delving into simultaneous diagnolization of regular matrix represenation of all elements of a group to find its irreducible representations, we briefly discuss how a single matrix can be diagnonalized, and when complete diagnozalization is not possible, then block-diagnonalized.
  
Let  matrix $$A$$ be a $$n x n$$ matrix, which has following eigenvalues:  
-  $$m$$ Distinct real eignevalues, $$\lambda_1, \lambda_2, \lambda_3, .... , \lambda_m$$  
-  $$\lambda + i\omega, \lambda - i\omega$$  
-  $$\mu$$ times 2, s.t. $$(A- \lambda I)$$ has a 2D NULL space.  
-  $$\gamma$$ times 2, s.t. $$(A- \lambda I)$$ has a 1D NULL space.

Then A can be block diagnonalized as follows:  




 


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


https://www.youtube.com/watch?v=SsCiQym5yQU&t=664s

https://www.youtube.com/watch?v=SsCiQym5yQU&t=664s
