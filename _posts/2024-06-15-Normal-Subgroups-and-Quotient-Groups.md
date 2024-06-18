---
layout: post
title: Normal Subgroups and Quotient Groups
permalink: /blog/normal-subgroups-quotient-groups/
published: false
---

Groups, just like composite numbers, can be composed from other simpler groups. To study groups, mathematicians  break them up into smaller constituent groups, which are simpler, easier to understand and reveal a lot about the structure of the original group.  
  
Normal subgroups of a group allow partioning of the group into a smaller group, called the quotient group. In this post, we shall delve into normal groups and quotient groups in a detail.

## 1. Cosets
To understand normal subgroups and quotient groups, we first need to understand the concept of *Cosets*. Cosets are one of the basic tools to study groups. Informally, if there is a subgroup $$(H,.)$$ of a group $$(G,.)$$, the subgroup $$H$$ divides the group $$G$$ into disjoint sets of cardinality equal to the size of the subgroup H.
  
More formally,      
Let there be a Group $$(G,.)$$ which contains a subgroup $$(H,.)$$. Then for every element $$g \in G$$, the left coset is defined $$g.H$$ and the right coset is desined as $$H.g$$.  
  
Note, that :
- Subgroup H is also a left coset and right coset wherein $$g.H$$ and $$H.g$$, $$g $$ is the identity element of the subgroup G.
- a coset, barring the subgroup H is not a group, as it does not contain the identity element. The identity element is a part of the subgroup H.  
- The cardinality of a coset is same as  the cardinality of the subgroup H.
  
## 2. Normal Subgroups and Quotient Groups

Let $$(N,.)$$ be a subgroup of a group $$(G,.)$$, then $$N$$ is called a ***normal subgroup*** if the cosets it creates also form a group, called the ***quotient group***, with $$N$$ being the identity element of the group. Note, that the quotient group is not a subgroup of G but an entirely different group. A quotient group is denoted as $$G/N$$. 
  
Every subgroup is not a normal group. A subgroup is normal, if and only if, it is  invariant under conjugation by members of the group of which it is a part. More formally,   
  
if $$(N,.)$$ is a subgroup of $$(G,.)$$, then  N is a normal subgroup of G, if and only if,  
$$g.N.g^{-1} \in N$$ for $$g\in G$$.  

### 2.1 Properties of a Normal Subgroup

if a subgroup $$(N,.)$$ of $$(G,.)$$ is normal, then:  
- The Left coset $$g.N$$ is equal to the right coset N.g, for $$g \in G$$
- $$(g.N)^{-1} = g^{-1}N$$

## 2. Simple Groups

Every group $$(G,.)$$ has atleast two normal subgroups, the identity element $$e$$, and the group G itself. If a group has only these two normal subgroups, then such a group is called a ***simple group***. Such groups form the building blocks of other groups.

  
    

