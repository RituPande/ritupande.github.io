---
layout: post
title: Basics of Groups and Group Representations
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

### 3.1 Examples of Abstract groups
#### 3.1.1 Quotient Groups

The Quotient group $$(\cal{Z}_n; +)$$ is the set of all congruence classes of $$\cal{Z}$$ modulo n where a congruence class $$a \in \cal{Z}$$  modulo n is defined as:
$$\bar{a}$$ = a + nk where $$k \in \cal{Z}$$

There are always n-1 congruence classes for $$\cal{Z}_n$$. For example, 
$$\cal{Z}_7 = \{ 1, 2, 3, 4,5 , 6 \} $$

#### 3.1.2 General Linear Groups and Special Linear Groups 

General Linear Group $$GL_n(\cal{F})$$, is a non-abelian group of inveritible n X n matrices under the operation * where * represents matrix multiplcation. Since the matrices in this group are invertible, the determinant of the matrices in the group is non-zero. The entries of the matrices can come from real the field of real numbers $$\cal{R}$$, rational numbers $$\cal{Q}$$, complex numbers $$\cal{C}$$ and quotitent group $$\cal{Z_p}$$

Special Linear Group $$SL_n(\cal{F})$$ is a subgroup of  $$GL_n(\cal{F})$$ with the diterminant of the matrices being  one.

### 3.2 Group Homomorphism and Isomorphism

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
     
$$f: Z \rightarrow Z/2Z$$  
  
that maps each *even* element of G to $$0 \in H$$ and each *odd* element of G to $$1 \in H$$     
  
if we apply ***f*** to every element of G, we are able to see similarity between G and H.  

***f*** ,in general, is a mathematical tool that given two groups (G,*) and (H,o) maps every element of G to an element in H i.e. 
$$f: G \rightarrow H$$  
such that, f(x*y) = f(x) o f(y), where $$x,y \in G$$  

if such a function exists, this implies that the two group have some underlying structural similarity. Such a function ***f*** is called ***group homomorphism*** or ***homomorphism*** in short.  Note, that the function  ***f*** is not required to be bijective and the direction of mapping from one group to another matters.

if ***f**** is bijective then the groups are not just similar but identical. Such a function is called ***group isomorphism*** or ***isomorphism***, in short.

## 4. Transformation Groups

To understand what a transformation group is, we need to clearly define a transformation
A ***transformation*** of a set X is a bijective self-map $$f : X \rightarrow X$$. i.e it is a function that when applied on a set returns the same set. A transformation is also  called a *permutation* a set X.

Two transformations can be composed to produce a third, and every transformation has an inverse transformation (this is essentially the meaning of bijection"). In other words, the collection of all transformations of X forms a group under composition, whose identity element is the identity transformation *e* fixing every element. Such a group is called **Aut X** or Automorphism of set X

A ***transformation group*** is any subgroup of Aut X for some set X.

It should be understood that every abstract groups is isomorphic to a transformation group.

### 4.1 Examples of Transformation Groups

#### 4.1.1. Dihedral group
A Diheral group $$D_n$$ is a collection of symmetries of a regular n-gon (for any n > 3) forms the dihedral group $$D_n$$ under composition. It is easy to check that this group has exactly 2n elements: n rotations and n reflections. $$D_n$$ is non-abelian.  
  
For example, $$D_4$$, a group of all possible transformations of a square that ensures the same orientation and structure before and after the tranformations includes 6 elements: rotation by 0, 90, 180 and 270 dgrees, a horizontal flip ( or reflection ) and a vertical flip.   

$$D_4$$ is isomorphic to $$Z/nZ$$.
#### 4.1.2. Groups of Linear tranformation

A vector $$V \in R^n$$ can be written as a column vector with n-elements. A linear transformation:  
$$T: R^n \rightarrow R^n$$   
is a linear map defines where it sends the basis of V. The group of such linear maps that preserves the vector space of a vector for a given basis is called the group of linear transformation as is defined as $$GL(R^n)$$.This transformation is achieved by left multiplying an n x n matrix with the vector V. This implies that:  
$$GL_n(R)$$ is isomorphic to $$GL(R^n)$$ for a given choice of basis. 
  
This is true for complex numbers as well.

#### 4.1.3.Symmetric Groups
A symmetric group $$S_n$$ is the group of permutations of a set with n elements. No matter how one permutes the elements of a set, the set still remains the same. Hence, a symmetric group $$S_n$$ is a finite transformation group with n! elements.
There are many notations for describing a permutation, but the most convinient and compact is the *cycle notation*. A transposition(swapping ) of elements of a set is represented as a tuple (s,d), where s is the element's source index and d is the destination index. A cycle is represented as a tuple of more than two elements.    
  
For example, Let $$S_3$$ = {1,2,3,4}  
1. Swapping the first two elements of the set is denoted as **(1,2)** which transforms $$S_3$$ to {2,1,3,4}.  
2. Next is we wish to move the resultant set such that element at indexes move as follows:  $$1 \rightarrow 2, 2 \rightarrow 3 , 3 \rightarrow 4, 4 \rightarrow 1$$, the transform  is denoted as **(1,2,3,4)** which transforms the set resulting from transform in the first step to {4,2,1,3}.  
3. Permutations can also be disjoint, for example (1,2)(3,4) transforms the resultant set from step 2 to {2,4,1,3}. The notation (1,2)(3,4), denotes that first transposition (1,2) is performed and then (3,4).  
  
Two permutations and be combined under the composition operator * to create a new permulation. The permutation are composed right to left. For example,  
  
Let $$S_4$$ = {1,2,3,4} , f = (1,2) and g=(2,3)  
Then f * g applied to $$S_4$$ results in { 3,1,2,4}

The identity element of $$S_n$$, is a fixed ordering of its element. Except for $$S_1$$ and $$S_2$$, all symmetric groups are non-abelien. Disjoint permutation however commute.

## 5 Direct Product of Groups
The direct products of two groups (G,*) and (H,o) is a cartesian product, such that:  
G X H: (g,h), where  $$g \in G, h\in H$$  
i.e an ordered pair of every element of G and every element of H.  
  
Such a direct product itself forms a group whose operator . is defined as:
(g,h).(g',h') = (g*g', h o h') where (g,h),(g',h') $$\in$$ G X H  

It should be noted that group products are not just limited to two groups. Products can be performed on more than two groups or even infinite groups.   
  
Group created by a group product is abelian if all the participating groups in the product are abelian. If even a single participating group is non-abelian the group resuting from their product is non-abelian.


## 6 Group Actions

## 7. Group Representations

## 8. References
1. [The Very Basics of Group, Rings and Fields](https://www-users.cse.umn.edu/~brubaker/docs/152/152groups.pdf)  
2. [Groups and their Representations](https://dept.math.lsa.umich.edu/~kesmith/rep.pdf)
3. [Socratica-Abstract Algebra Playlist](https://www.youtube.com/playlist?list=PLi01XoE8jYoi3SgnnGorR_XOW3IcK-TP6)



