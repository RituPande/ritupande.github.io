---
layout: post
title: Direct and Semidirect Products of Groups
permalink: /blog/direct-semidirect-products-groups/
published: true
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
Generation of group $$D_4$$ from two normal subgroups $$H = \{e, r, r^3, f, rf, r^2f, r^3f \},  K=\{e, r^2 \}$$, where $$r$$ representes rotation by 90 degrees and $$f$$ represents flipping operation.

The internal directproduct  $$H \times K = \{ e,  r,r^2, r^3, f, rf, r^2f, r^3,f \}=D_4 $$   

### 1.3 Difference between external and internal direct product

A completely new group $$G$$  can be constructed using external direct product by taking ordered pairs of the component groups . The component groups of an external direct product can be completely unrelated. On the other hand, the components involved in internal direct product are normal subgroups of the group created after internal direct product.

## 2. Semidirect Product
Semidirect product is a generalization of direct product. While operation on the elements of the direct product has to be performed component-wise, elements of the semidirect product are constructed by interaction between the component groups. Just like the direct product, the semidirect product can be external or internal. There is a possibility to create a completely new group by applying external semi-direct product. However, in case of internal semidirect product, the resultant group is isomorphic to the group of which one of the components is a subgroup.

### 2.1 Indirect Semidirect product

Let $$N$$ and $$H$$ be two subgroups of a $$G$$ such that $$N$$ is normal. Also, let $$\phi_h(n)$$ be the conjugate action of subgroup $$H$$ on $$N$$, where $$h \in H,n \in N$$. Since $$H$$ is a subgroup of $$G$$ , we know that  $$hNh^{-1} \in N$$. This implies that $$\phi$$ is a group homophormism from $$H$$ to $$Aut(N)$$. More formally,  
  
$$\phi: H \Rightarrow Aut(N)$$  

Now, the inner semidirect product $$G'  = N \rtimes H$$ is constructed as pairs $$(n, h)$$ where $$n \in N, h \in H$$.  Also, the group operation of this newly generated group can be found as follows:  
    
Let $$(n_1, h_1) , (n_2, h_2) \in G$$    
Then $$(n_1, h_1) . (n_2, h_2) = n_1.h_1.n_2.h_2 $$  
  
Adding $$h_1^{-1}.h_1$$ to the R.H.S of equation as it is same as $$e$$  
$$(n_1, h_1) . (n_2, h_2) = n_1.h_1.n_2.h_1^{-1}.h_1.h_2$$  
  
Using group associativity:  
$$(n_1, h_1) . (n_2, h_2) = n_1.(h_1.n_2.h_1^{-1}).h_1.h_2$$  
  
Using definition of $$\phi_h(n)$$:  
$$(n_1, h_1) . (n_2, h_2) = n_1.\phi_{h_1}(n_2)).h_1.h_2$$  
  
This can be written as:  
$$(n_1, h_1) . (n_2, h_2) = (n_1.\phi_{h_1}(n_2)), (h_1.h_2)$$  

This can be summarized into a formal **definition**:  

Let $$N$$ and $$H$$ be two subgroups of $$G$$, with $$N$$ normal to $$G$$ and $$\phi_h(n)$$ be group action of $$H$$ on $$N$$, such that,  $$\phi_h(n) : H \Rightarrow N$$, then the semidirect product $$G'= N \rtimes H$$ is the set of pairs  $$G' = \{ (n,h), n \in N , h \in H \} $$, such that,    

- Group operation: $$(n_1, h_1) . (n_2, h_2) = (n_1.\phi_{h_1}(n_2)), (h_1.h_2)$$
    
- Identity element = $$(e,e)$$
    
- Inverse of $$(n,h) = (\phi_{h^{-1}}(n^{-1}, h^{-1})$$
    
- $$G'$$ is isomorphic to $$G$$ 

### 2.1.1 Example: $$D_n = R \rtimes T$$
Let $$G = D_n$$, be the diheral group, $$R$$ = group of rotations , and $$T$$ the group of relections.   
  
It can be seen that,
- $$R$$ is normal to $$D_n$$
     
- $$R$$ is isomorphic  to $$Z_n$$ :$$R \cong Z_n$$
    
- $$T$$ is isomorphic  to $$Z_2$$ : $$T \cong Z_2$$  
  
  
Also we know that:  
- Every element $$g \in G$$ can be represented as $$g=r^i. t^j$$ where $$r^i \in R, t^j \in T, i \in Z_n, j \in Z_2$$
    
- Every element g has a property $$t.r = r^{-1}.t$$
  
To find the function that constitutes group homomorphism from $$T \Rightarrow R$$, we consider the action of group $$T$$ on $$R$$ via conjugation.  The conjugation operation can be written as:   
$$t.r^k.t^{-1}, $$  
$$r^{-k}.t.t^{-1} = r^{-k}$$
   
This gives us:  
- Group homomorphism $$\phi_t(R): T \Rightarrow Aut(R)$$
    
- Represented as $$\phi_t(R) = (-1)^t.R$$  
  
Therefore, $$D_n = R \rtimes T$$  


### 2.2 External Semidirect product

Let $$(H,o)$$ and $$(K,.)$$ be be any two groups and given $$\phi_h(K) : H \Rightarrow K$$, then the semidirect product $$G'= H \rtimes K$$ is the set of pairs  $$G' = \{ (h,k), k \in K , h \in H \} $$, such that,    
- Group operation: $$(h_1, k_1) . (h_2, k_2) = (h_1 \hspace{2pt} o \hspace{2pt} \phi_{k_1}(h_2)), (k_1.k_2)$$
  
- Identity element = $$(e,e)$$
    
- Inverse of $$(n,h) = (\phi_{h^{-1}}.(k^{-1}), h^{-1})$$

### 2.2.1 Example: Group of Affine Transformations
Let $$H = (V, +), K = GL(V, .)$$  
$$\phi_k(h):GL(V) \Rightarrow Aut(V)$$  
$$\phi_k(h) = A.v$$ where $$A, B \in GL(V)$$ and $$v,w \in V$$  
  
By definition of semidirect product:  
$$(v, A).(w, B) =  (v + A.w, A.B)$$
  
This group, $$T = V \rtimes GL(V)$$ constructed out of semidirect product of $$V$$ and $$GL(V)$$ is called a  **group of affine transformations**.

## 3. References
1.[Yuly Billig: Direct and Semidirect Products of Groups](https://youtu.be/Vog1Kvr-u4A?si=U1CXIzbE1XcoUsyZ)  
2.[Kimberly Brehm: Abstract Algebra - 8.1 External Direct Products](https://youtu.be/v11oJwBxZpM?si=3BiH_MdoRkTbc7JM)  
3.[Kimberly Brehm: Abstract Algebra - 9.3 Internal Direct Products](https://youtu.be/ZoPbDDuQTi4?si=EvgsaaYIGq2HqIjr)  
4.[Wikipedia: Semidirect Product](https://en.wikipedia.org/wiki/Semidirect_product)  







