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
    
$$G \times H: (g,h)$$
where  $$g \in G, h\in H$$  
  
i.e an ordered pair of every element of G and every element of H.  
  
Such a direct product itself forms a group whose operator $$.$$ is defined as:
    
$$ (g,h).(g',h') = (g*g', h \circ h') $$  
  
where $$(g,h),(g',h') \in G \times H$$  
    
It should be noted that group products are not just limited to two groups. Products can be performed on more than two groups or even infinite groups.   
    
Group created by a group product is abelian if all the participating groups in the product are abelian. If even a single participating group is non-abelian the group resuting from their product is non-abelian.
  
 **Examples:**     
- Group of vector of real numbers $$(R^n, +) = (R,+) \times (R, +) \times ....\times (R,+)$$
- Group of complex numbers $$(C, * )=(R_+, *) \times S^1$$, where $$R_+$$= positive real numbers and  $$S^1$$ = unit circle

### 1.2. Internal Direct Product

We say  a group $$G$$ in the internal direct product of $$H$$ and $$K$$ i.e $$G = H \times K$$, if:  
- $$H$$ and $$K$$ are normal subgroups of G
- Every element of $$G$$ is composed by multiplication of an element of $$H$$ with and element of H i.e. $$G= HK$$
- $$H$$ and $$K$$ have no common elements other than identity element. 

As in case of external direct product, internal direct product can be extended to more than two subgroups.  
Note, that an internal direct product  is isomorphic to the external direct product, whenever it is possible to construct the internal direct product.  
  
**Examples:**  
Generation of group $$D_4$$ from two normal subgroups $$H = \{e, r, r^3, f, rf, r^2f, r3^f \},  K={e, r^2 }$$, where $$r$$ representes rotation by 90 degrees and $$f$$ represents flipping operation.

The internal directproduct  $$H \times K = \{ e,  r,r^2, r^3, f, rf, r^2f, r^3,f \}=D_4 $$   

### 1.3 Difference between external and internal direct product

A completely new group $$G$$  can be constructed using external direct product by taking ordered pairs of the component groups . The component groups of an external direct product can be completely unrelated. On the other hand, the components involved in internal direct product are normal subgroups of the group created after internal direct product.

## 2. Semidirect Product
Semidirect product is a generalization of direct product.Just like the direct product, there is an external semidirect product and internal semidirect product. 

### 2.1 External Semidirect product
### 2.2 Indirect Semidirect product

Let $$N$$ and $$H$$ be two subgroups of a $$G$$ such that $$N$$ is normal. Also, let $$\phi_h(n) be the conjugate action of subgroup $$H$$ on $$N$$, where $$h \in H,n in N$$. Since $$H$$ is a subgroup of $$G$$ , we know that  $$hNh^{-1} \in N$$. This implies that $$ phi$$ is a group homophormism from $$H$$ to $$Aut(N)$$. More formally,    
$$\phi: H \implies Aut(N)$$  

Now, the inner semidirect product $$G'  = N \rtimes H$$ is constructed as pairs $$(n, h)$$ where $$n \in N, h \in H$$.  Also, the group operation of this newly generated group can be found as follows:  
  
Let $$(n_1, h_1) , (n_2, h_2) \in G$$    
$$Then (n_1, h_1) . (n_2, h_2) = n_1.h_1.n_2.h_2 $$  

Adding $$h_1^{-1}.h_1$$ to the R.H.S of equation as it is same as $$e$$  
$$Then (n_1, h_1) . (n_2, h_2) = n_1.h_1.n_2.h_1^{-1}.h_1.h_2$$  

Using group associativity:  
$$Then (n_1, h_1) . (n_2, h_2) = n_1.(h_1.n_2.h_1^{-1}).h_1.h_2$$  

Using definition of $$\phi_h(n)$$:  
$$Then (n_1, h_1) . (n_2, h_2) = n_1.\phi_{h_1}(n_2)).h_1.h_2$$  

This can be written as:  
$$(n_1, h_1) . (n_2, h_2) = (n_1.\phi_{h_1}(n_2)), (h_1.h_2)$$  

This can be summarized into a formal definition:  

Let $$N$$ and $$H$$ be two subgroups of $$G$$, with $$N$$ normal to $$G$$ and $$\phi_h(n)$$ be group action of $$H$$ on $$N$$, such that,  $$\phi_h(n) : H \implies N$$, then the semidirect product $$G= N \rtimes$$ is the set of pairs  $$G' = \{ (n,h), n\in N , h \in H \} $$, such that,    
- Group operation: $$(n_1, h_1) . (n_2, h_2) = (n_1.\phi_{h_1}(n_2)), (h_1.h_2)$$   
- Identity element = $$(e,e)$$
- Inverse of $$(n,h) = (\phi_{h^{-1}}(n^{-1}, h^{-1})$$












