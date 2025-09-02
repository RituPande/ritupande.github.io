---
layout: post
title: Basics of Character Theory
permalink: /blog/character-theory/
published: false
---

Character theory is a tool in  representation theory that allows study group representations using functions rather than matrices. These functions called  ***characters***, are much easier to handle but still encode a large amount of structural information about the group and its representations. A character is a function that maps each element of a group to a real/complex number, such that, group elements that perform same action ( under different perspectives) are assigned the same value, allowing similar elements to be identified easily. This  set of similar elements is called a ***conjugacy class***.

A conjugacy class is the group of elements that produce the SAME tranformation under differnet group perepectives (relabling of group elements) from group theoretic perepective,  or a different basis, from representation theoretic perspective.  In other words, a permutation (12) and (23) are same if the labeling of the elements in the group are changed. The permutation just swaps two numbers next to each other. Mathematically,  
  
$$g$$ and $$h^{-1}gh$$ belong to the same conjugacy class for every $$g , h \in G$$ , where $$h^{-1}gh$$ is a similarity transform of $$g$$ within the group $$G$$  

## 1. Character Table

A character table of a finite group $$G$$  is a square matrix where

- Rows = the distinct irreducible characters of $$G$$  
- Columns = the conjugacy classes of $$G$$  
  
It is a grid collecting all irreducible characters of a group against its conjugacy classes. A character $$X_i(g)$$ is the *trace* of the irreducible representation $$\rho_i$$ in row $$i$$, of conjugacy class $$g$$

The character table encodes deep information:

- The number of irreducible characters = number of conjugacy classes.  
- Dimensions of irreducible representations.
- Whether the group is abelian (all irreps are 1-dimensional).  
- Helps decompose any representation into irreducibles.

### 1.1 Properties of the Character Table

- The rows of a character table are orthogonal to each other. Mathematically:  
   $$\frac{1}{|G|} \sum_{i=0}^{ncols} s_i*X_i^a * \overline{X_i^b} = 0$$
  
   where $$s_i$$ is the size of the conjugacy class corresponding to column $$i$$ and $$X_a , X_b$$ are two rows of the table.

- The columns of a character table are also orthogonal to each other.

- The first column of the character table, corresponds to the identity element and represents the dimensions of the irreducible representation in the corresponding row. 
