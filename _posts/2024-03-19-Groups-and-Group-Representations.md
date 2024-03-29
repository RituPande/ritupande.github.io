---
layout: post
title: Groups and Group Representations
permalink: /blog/group-representations/
published: false
---

## 1. Introduction
The natural world around us is rife with examples of transformations applied to objects that retain some underlying property of the object before and after the transformation. For example, rigid motions in 3D-space that preserve a particular molecule.   A simple example is rotation of a 2-D square ( in XY plane ) about the Z axis. A 0, 90, 180 and 270 and 360 degree rotation has no impact on the square shape and orientation.  Such transformations are called ***symmetries***.Two symmetries can be combined to form another symmetry and every symmetry has an opposite or inverse symmetry. For instance,  90 and 180 degree rotation can be combined to produce a 270 degree rotation that does not change a square. Also,a  rotation counterclockwise by 90 degrees can be undone by rotation clockwise by 90 degrees. ***Groups*** are a collection of transformations that preserve some underlying structure of a set to  which they are applied.

Historically, the groups were not separate from their ***representation*** as a set of transformations. However, in the late nineteenth century Cayley formulated an ***abstract*** definition of a group that separated it from it from its representation as a group of transformations or ***tranformation groups*** . This enabled effective study of transformations which might drastically differ in how they are represented but in essence have the same underlying properties.  Representation theory aims to understand different ways in which abstract groups can be realized as transformation groups.

## 2. How is group theory relevant in machine learning

## 3. Groups

### 3.1 Abstract Groups
A ***Group*** is a set G which is closed under an operation ∗ (i.e., for any $$x, y \in  G, x ∗ y \in G $$) and satisfies the following properties:
-  Identity: There is an element e in G, such that for every $$x \in G, e ∗ x = x ∗ e = x$$.    
- Inverse: For every x in G there is an element y ∈ G such that $$x ∗ y = y ∗ x = e$$ , where again e is the identity.
- Associativity: he following identity holds for every $$x, y, z \in G:x ∗ (y ∗ z) = (x ∗ y) ∗ z$$.  


### 3.2 Transformation Groups

## 4 Homomorphism and Isomorphism

## 5 Group Actions

## 6. Group Represenations

## 7. References
1. [The Very Basics of Group, Rings and Fields](https://www-users.cse.umn.edu/~brubaker/docs/152/152groups.pdf)



