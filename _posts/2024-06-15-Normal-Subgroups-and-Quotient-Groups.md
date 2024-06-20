---
layout: post
title: Normal Subgroups and Quotient Groups
permalink: /blog/normal-subgroups-quotient-groups/
published: true
---

Groups, just like composite numbers, can be composed from other simpler groups. These simpler groups are easier to study and reveal wealth of information about the structure of the original group.  
  
Normal subgroups of a group allow partioning of the group into a smaller group, called the quotient group. In this post, we shall delve into normal groups and quotient groups in detail.

## 1. Cosets
To understand normal subgroups and quotient groups, we first need to understand the concept of *Cosets*. Cosets are one of the basic tools to study groups. Informally, if there is a subgroup $$(H,.)$$ of a group $$(G,.)$$, the subgroup $$H$$ divides the group $$G$$ into disjoint sets of cardinality equal to the size of the subgroup H.
  
More formally,      
Let there be a Group $$(G,.)$$ which contains a subgroup $$(H,.)$$. Then for every element $$g \in G$$, the left coset is defined $$g.H$$ and the right coset is defined as $$H.g$$.  
  
Note, that :
- Subgroup H is also a left coset and right coset wherein  $$g $$ is the identity element of the subgroup G.
- A coset (barring the subgroup H), is not a group, as it does not contain the identity element. The identity element is only part of the subgroup H.  
- The cardinality of a coset is same as  the cardinality of the subgroup H.
  
## 2. Normal Subgroups and Quotient Groups

Let $$(N,.)$$ be a subgroup of a group $$(G,.)$$, then $$N$$ is called a ***normal subgroup*** if the cosets it creates also form a group, called the ***quotient group***, $$(Q,.)$$ such that,  
  
- $$N$$ is the identity element of the group $$Q$$.  
- $$x.N * y.N = x.y.N$$, where $$x.N $$ and $$y.N$$ are two elements of the quotient group and $$x,y\in G$$.
    
Note, that the quotient group is not a subgroup of G but an entirely different group. A quotient group is denoted as $$G/N$$. 

### 2.1 Conditions for a subgroup to be normal

Every subgroup is not a normal group. There are certain conditions that must be met for a subgroup to divide its group into a quotient group. Let us try to derive these conditions:  
  
Let there be two cosets of the group $$G$$, $$x.N$$ and $$y.N$$. if these two are elements of a group $$(Q,.)$$, then,  
it should be that $$x.N . y.N = x.y.N$$  
    
Let $$n_1, n_2 \in N$$, then 
$$x.n_1 . y.n_2 = x.y.n_1.n_2$$
  
Since $$N$$ is a subgroup $$n_1.n_2$$ is also in N. Let us call it $$n_3$$
$$x.n_1 . y.n_2 = x.y.n_3$$
    
Multiplying the equation on both sides by $$x^{-1}$$
$$x^{-1}.x.n_1 . y.n_2 = x^{-1}.x.y.n_3$$
  
Since $$x^{-1}.x = e $$  
$$n_1.y.n_2 = y.n_3$$
  
Multiplying the equation on both sides by $$y^{-1}$$  
$$y^{-1}.n_1.y.n_2 = y^{-1}.y.n_3$$
  
Since $$y^{-1}.y = e $$  
$$y^{-1}.n_1.y.n_2 = n_3$$
  
Multiplying the equation on both sides by $$n_2^{-1}$$  
$$y^{-1}.n_1.y.n_2.n_2^{-1} = n_3.n_2^{-1}$$

Since $$n_2^{-1}.n_2 = e $$  
$$y^{-1}.n_1.y = n_3.n_2^{-1}$$
  
Since $$N$$ is a subgroup $$n_3.n_2^{-1}$$ is also in N. Let us call it $$n_4$$
$$y^{-1}.n_1.y = n_4$$
  
This implies that $$y^{-1}.n_1.y \in N$$
$$\implies y^{-1}.N.y \in N$$ .  
  
This operation called a ***conjugate*** and is the condition that must be satisfied if a subgroup is  normal. 

The reverse can also be proven i.e. if $$y^{-1}.N.y \in N$$, then $$N$$ must be a subgroup.[2]

More formally, it can be stated that a subgroup is normal, if and only if, it is  invariant under conjugation by members of the group of which it is a part. 

### 2.2 Properties of a Normal Subgroup

if a subgroup $$(N,.)$$ of $$(G,.)$$ is normal, then:  
- The Left coset $$g.N$$ is equal to the right coset N.g, for $$g \in G$$
- $$(g.N)^{-1} = g^{-1}N$$

## 3. Simple Groups

Every group $$(G,.)$$ has atleast two normal subgroups, the identity element $$e$$, and the group $$G$$ itself. If a group has only these two normal subgroups, then such a group is called a ***simple group***. Such groups form the building blocks of other groups.

## 4. References
1. [Wikipedia-Normal Subgroup](https://en.wikipedia.org/wiki/Normal_subgroup)  
2. [Socratica-Normal Subgroups and Quotient Groups](https://youtu.be/vYKdh5oQ4Zw?si=Ec1FyITRZ1mOmois)  
3. [Michael Penn-Normal Subgroups](https://www.youtube.com/watch?v=eK0lc7cOBkY)

  
    

