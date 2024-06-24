---
layout: post
title: Direct and Semidirect Products of Groups
permalink: /blog/direct-semidirect-products-groups/
published: False
---

Direct and Semidirect products are techniques to construct larger, more complex groups from simpler, smaller ones. In this post we shall understand how direct and semidirect products on groups are performed and what is the relation between these two operations.

## 1. Direct Product

### 1.1. External Direct Product

The external direct products of two groups $$(G,*)$$ and $$(H, \circ )$$ is a cartesian product, such that:  
    
$$ G \times H: (g,h)$$
where  $$g \in G, h\in H$$  
  
i.e an ordered pair of every element of G and every element of H.  
  
Such a direct product itself forms a group whose operator $$.$$ is defined as:
    
$$ (g,h).(g',h') = (g*g', h \circ h') $$  
  
where $$(g,h),(g',h') \in G \times H$$  
    
It should be noted that group products are not just limited to two groups. Products can be performed on more than two groups or even infinite groups.   
    
Group created by a group product is abelian if all the participating groups in the product are abelian. If even a single participating group is non-abelian the group resuting from their product is non-abelian.
 

### 1.2. Internal Direct Product

We say  a group $$G$$ in the internal direct product of $$H$$ and $$K$$ i.e $$G = H \times K$$, if:  
- $$H$$ and $$K$$ are normal subgroups of G
- Every element of $$G$$ is composed by multiplication of an element of $$H$$ with and element of H i.e. $$G= HK$$
- $$H$$ and $$K$$ have no common elements other than identity element. 

### 1.3 Examples   
- Group of vector of real numbers $$(R^n, +) = (R,+) \times (R, +) \times ....\times (R,+)$$
- Group of complex numbers $$(C, * )=(R_+, *) \times S^1$$, where $$R_+$$= positive real numbers and  $$S^1$$ = unit circle

## 2. Semidirect Product

