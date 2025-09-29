---
layout: post
title: Basics of Character Theory
permalink: /blog/character-theory/
published: false
---

## 1. Introduction
Character theory is a tool in  representation theory that allows study group representations using functions rather than matrices. These functions called  ***characters***, are much easier to handle but still encode a large amount of structural information about the group and its representations. A character is a function that maps each element of a group to a real/complex number, such that, group elements that perform same action ( under different perspectives) are assigned the same value, allowing similar elements to be identified easily. This  set of similar elements is called a ***conjugacy class***.

A conjugacy class is the group of elements that produce the SAME tranformation under differnet group perepectives (relabling of group elements) from group theoretic perepective,  or a different basis, from representation theoretic perspective.  In other words, a permutation (12) and (23) are same if the labeling of the elements in the group are changed. The permutation just swaps two numbers next to each other. Mathematically,  
  
$$g$$ and $$h^{-1}gh$$ belong to the same conjugacy class for every $$g , h \in G$$ , where $$h^{-1}gh$$ is a similarity transform of $$g$$ within the group $$G$$  

## 2. Character Table

A character table of a finite group $$G$$  is a square matrix where

- Rows = the distinct irreducible characters of $$G$$  
- Columns = the conjugacy classes of $$G$$  
  
It is a grid collecting all irreducible characters of a group against its conjugacy classes. A character $$X_i(g)$$ is the *trace* of the irreducible representation $$\rho_i$$ in row $$i$$, of conjugacy class $$g$$

The character table encodes deep information:

- The number of irreducible characters = number of conjugacy classes.  
- Dimensions of irreducible representations.
- Whether the group is abelian (all irreps are 1-dimensional).  
- Helps decompose any representation into irreducibles.

### 2.1 Properties of the Character Table

- The rows of a character table are orthogonal to each other. Mathematically:  
   $$\frac{1}{|G|} \sum_{i=0}^{ncols} m_i*X_i^a * \overline{X_i^b} = 0$$                                                  (1)
  
   where $$s_i$$ is the size of the conjugacy class corresponding to column $$i$$ , $$X_a , X_b$$ are two rows of the table and $$|G|$$ is the size of the group

- The above relation provides a mechanism to calculate the multiplicity of an irreduicle representation in any given representation of a group element i.e.  
  $$m_i = \frac{\sum_{i=0}^{ncols} X_i^a * \overline{X_i^b}}{|G|}$$                                                       (2)

 
- The columns of a character table are also orthogonal to each other.

- The first column of the character table, corresponds to the identity element and represents the dimensions of the irreducible representation in the corresponding row.
    
- Characters of two representations are same iff they are equivalent.
    
- The character table is a square matrix. The number of equivalence classes of a group is equal to the number of its irreducible represenatations

- $$\sum d_i^2 = |G|$$ where $$d_i$$ is the dimension of an irreducible representation, $$\rho_i$$ of group G            (3)

## 3. Finding Irreducible Representations

As discussed in the preivous post, finding irreducible representations by simultaneous diagnonalization/ block diagonalization of matrices, is not possible for large groups with complex matrices. Character theory comes to the rescue here. Character theory can be used in two scenarios:  

- We already know all the irreducible represenations of the group. We use the character table to decompose a reducible representation into its irreducible representations.

- We do not know the irreducible represenations of a group and need to find them.

### 3.1 Decompose a Reducible Representation

Let us assume we are given a reducible representation of a group and we wish to decompose it to its irreducible represenattion. If we already know the irreducible representations of the group:  

1. We build the character table from the known irreducible representations  
2. Use the formula from equation (2) to find the multiplicities of each irreducible representation in the given representation.  

### 3.2 Finding charater table of a group

If we do not know irreducible represenatations of a group before hand,  we start by finding its charcter table
  
1. Understand the properties of the group: order, congugacy classes, and whether or not it is an abelian group.  
2. Find all 1-D represenatations of the group. ( refer Appendix for details). An abelian group has only 1-D represenatations. However, if the group in non-abelian we proceed to calculate characters of irreducible representations of higher dimensions.
3. Use the sum of dimension squares formula ( eq 3) to find dimensions of other irreducible represenattions.    
4. Use orthoganality to find characters for those irreducible representations, with the first character always being equal to the dimensions of the representation  

### 3.3 Finding irredicble representation matrix from the character table

The matrix entries of an irreducible represenatation $$\rho(g)$$  can be extracted from the characters as follows:

1. Find the permutation matrices $$M$$ of the group elements
2. Build projection operator for a character $$\alpha$$ using permutation matrices $$M$$ as below:

   $$P^{(\alpha)} = \frac{d_{\alpha}}{G} \sum_{g \in G}\chi^{(\alpha)} (g^{-1}) M(g)$$

3. Find basis vectors for the image of $$P^{(\alpha)}$$ by applying it to standard basis vectors. Choose $$d_{\alpha}$$ vectors from them for further processing.
   
4. Project $$M(g)$$ to the $$d_{\alpha}$$ dimensional matrix formed using the basis vectors obtained in the previous step to get the irreducible matrix representation for each group element for character $$\alpha$$


# 4. Appendix

## 4.1 Finding Character Table of Finite Abelian Groups
It should be noted that every irreducible representation of a finite abelian group is 1-dimensional.  To find its chaarcter table:

1. Every abelian group is a direct product of cylic groups. So as a first step we decompose a albelian group to its cyclic factors
2. Assign roots of unity as generators of each cyclic factor.
3. The 1-D representation of group elements are then calculated using these generators
4. All combinations of  the characters of cyclic factors are taken to get the chactacer table of the original abelian group 

Example:  
1. $$Z_6 = Z_2 \times Z_3$$
2. Generator for $$Z_2$$ can be mapped to 1 or -1, resulting in two possible characters, using each of these three generators
3. Generator for $$Z_3$$ can be mapped to $$1, e^{2 *pi/3}, e^{4 *pi/3}$$ , resulting in three possible characters, using each of these three generators
4. All characters for $$Z_6$$ can be found by taking direct product of chacters of $$Z_2$$ and $$Z_3$$

## 4.2 Finding 1-D Characters of Finite Non-Abelian Groups

 Finite Non-Abelian Groups have higer dimensional represenatations than just 1-D representations. As stated above, to find all the characters, first we need to find the 1-D chaarcters and then use orthogonality and other properties of a character table to find the characters of higher dimensional representations.  
  
First, It must be understood that finding a 1-D group is same as finding all homomorphisms of the group, since for a 1-D character $$\chi$$,  
$$\chi(gh) = \chi(g).\chi(h)$$  
This is because a 1-D chaarcter is a scalar.  
  
Second, because a 1-D chaarcter is a scalar,  $$\chi(g).\chi(h)=\chi(h).\chi(g)$$ i.e. they always commute.  For a non-abelian group, 1-D characters only see those parts of the group that are ableian in nature.  

Therefore to find 1-D characters of a non-abelian group, we must remove those aspects of the group that make the group non-commutative. if a group is communtiative, then for every element $$g$,h$$, $$ghg^{-1}h^{-1} = e$$. However, if they are  non-commutiative $$ghg^{-1}h^{-1}$$ gives a measure of the distance from commutativity. Therefore, to get 1-D characters of a non-ablelen group:  
  
1. Calculate the commutative subgroup  [G, G] = $$ghg^{-1}h^{-1}$$, for $$g,h \in G $$
2. Calculate abelianization of $$G$$ as $$G_{ab}= G/[G, G]$$ i.e. quotient of G with commutator subgroup. This only keeps the information in G that is commutiative in nature.
3. Note that $$G_{ab}$$ contains cosets of [G,G] in G as its member elements. All the memeber elements are commutiative to each other.
4. Calculate the 1-D characters of $$G_{ab}$$, as for any abelian group
5. Each 1-D character of $$G_{ab}$$ gives a 1-D character of the original group.

# 5. References
