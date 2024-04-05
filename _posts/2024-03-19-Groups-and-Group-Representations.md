---
layout: post
title: Groups and Group Representations
permalink: /blog/group-representations/
published: false
---

## 1. Introduction
The natural world around us is rife with examples of transformations applied to objects that retain some underlying property of the object before and after the transformation. For example, rigid motions in 3D-space that preserve a particular molecule.   A simple example is rotation of a 2-D square ( in XY plane ) about the Z axis. A 0, 90, 180 and 270  degree rotation has no impact on the square shape and orientation.  Such transformations are called ***symmetries***.Two symmetries can be combined to form another symmetry and every symmetry has an opposite or inverse symmetry. For instance,  90 and 180 degree rotation can be combined to produce a 270 degree rotation that does not change a square. Also,a  rotation counterclockwise by 90 degrees can be undone by rotation clockwise by 90 degrees. ***Groups*** are a collection of transformations that preserve some underlying structure of a set to  which they are applied.

Historically, the groups were not separate from their ***representation*** as a set of transformations. However, in the late nineteenth century Cayley formulated an ***abstract*** definition of a group that separated it from it from its representation as a group of transformations or ***tranformation groups*** . This enabled effective study of transformations which might drastically differ in how they are represented but in essence can be defined as the same generic abstract objects.  Representation theory aims to understand different ways in which abstract groups can be realized as transformation groups.

## 2. How is group theory relevant in machine learning


## 3 Abstract Groups
A ***Group*** is a set G which is closed under an operation ∗ (i.e., for any $$x, y \in  G, x ∗ y \in G $$) and satisfies the following properties:
-  Identity: There is an element e in G, such that for every $$x \in G, e ∗ x = x ∗ e = x$$.    
- Inverse: For every x in G there is an element y ∈ G such that $$x ∗ y = y ∗ x = e$$ , where again e is the identity.
- Associativity: he following identity holds for every $$x, y, z \in G:x ∗ (y ∗ z) = (x ∗ y) ∗ z$$.  

  A group that is also commutative i.e.  for every $$x, y \in G: x ∗ y  = y ∗ z $$ is called an ***abelian*** group.

A ***Subgroup*** is a subset of a group that also a group in its own right.

A ***Field*** is a set $$\cal{F}$$ which is closed under two operations + and * such that:    
- $$\cal{F}$$ is an abelian group under + and  
- $$\cal{F}$$ − {0} (the set F without the additive identity 0) is an abelian group under *.  


### 3.1 Quotient Groups

The Quotient group $$(\cal{Z}_n; +)$$ is the set of all congruence classes of $$\cal{Z}$$ modulo n where a congruence class $$a \in \cal{Z}$$  modulo n is defined as:
$$\bar{a}$$ = a + nk where $$k \in \cal{Z}$$

There are always n-1 congruence classes for $$\cal{Z}_n$$. For example, 
$$\cal{Z}_7 = \{ 1, 2, 3, 4,5 , 6 \} $$

### 3.2 General Linear Groups and Special Linear Groups 

General Linear Group $$GL(n,\cal{F})$$ or $$GL_n(\cal{F})$$, is a non-abelian group of inveritible n X n matrices under the operation * where * represents matrix multiplcation. Since the matrices in this group are invertible, the determinant of the matrices in the group is non-zero. The entries of the matrices can come from real the field of real numbers $$\cal{R}$$, rational numbers $$\cal{Q}$$, complex numbers $$\cal{C}$$ and quotitent group $$\cal{Z_p}$$

Special Linear Group $$SL(n,\cal{F})$$ or $$SL_n(\cal{F})$$ is a subgroup of  $$GL(n,\cal{F})$$ with the diterminant of the matrices being  one.

## 4. Transformation Groups

To understand what a transformation group is, we need to clearly define a transformation
A ***transformation*** of a set X is a bijective self-map $$f : X \rightarrow X$$. i.e it is a function that when applied on a set returns the same set. A transformation is also  called a *permutation* a set X.

Two transformations can be composed to produce a third, and every transformation has an inverse transformation (this is essentially the meaning of bijection"). In other words, the collection of all transformations of X forms a group under composition, whose identity element is the identity transformation ***e*** fixing every element. Such a group is called **Aut X** or Automorphism of set X

A ***transformation group*** is any subgroup of Aut X for some set X

## 5. Homomorphism and Isomorphism

***Homomorphism*** is a mathematical tool to compare two groups. it is used to identify whether two groups are similar, identical or completely dissimilar. Let us consider two groups:  

G(Z, +): Infinite group of all integers  
H(Z/2Z, +): Finite group of integers mod 2-{0, 1}   

At the surface, these two groups seem to be complely different with no similarities. However, notice that:  
G = { odd } U { even }  
  
even + even = even  
even + odd  = odd  
odd + even  = odd  
odd + odd   = even 
  
Shifting the focus to group H: 
  
0 + 0 =  0 mod 2  
0 + 1 =  1 mod 2  
1 + 0 =  1 mod 2  
1 + 1 =  0 mod 2   

Dividing two group G into two sets of even and odd integers, one can see that its behavior is similar to that of group H.   More formally, Let us consider a function ***f***:  
     
$$f: Z /rightarrow Z/2Z$$  
  
that maps each *even* element of G to $$0 \in H$$ and each *odd* element of G to $$1 \in H$$     
  
if we apply ***f*** to every element of G, we are able to see similarity between G and H.  

***f*** ,in general, is a mathematical tool that given two groups (G,*) and (H,o) maps every element of G to an element in H i.e. 
$$f: G \right arrow H$$  
such that, f(x*y) = f(x) o f(y), where $$x,y \in G$$  

if such a function exists, this implies that the two group have some underlying structural similarity. Such a function ***f*** is called ***group homomorphism*** or ***homomorphism*** in short.  Note, that the function  ***f*** is not required to be bijective and the direction of mapping from one group to another matters.

if ***f**** is bijective then the groups are not just similar but identical. Such a function is called ***group isomorphism*** or ***isomorphism***, in short.


## 6 Group Actions

## 6. Group Represenations

## 7. References
1. [The Very Basics of Group, Rings and Fields](https://www-users.cse.umn.edu/~brubaker/docs/152/152groups.pdf)



