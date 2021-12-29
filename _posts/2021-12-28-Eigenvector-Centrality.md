---
layout: post
title: Eigenvector Centrality
published: false  
---

## Introduction  

Eigenvector centrality is one the most fundamental mechanism used to assign importance to a node in a graph. While Degree Centrality' assigns importance to a node based on  the number of its neighboring nodes, Eignevector Centrality assigns importance to a node in a graph based not only based on the number of its neightbors but also their importance. i.e. a node's importance is proportional to the sum of the importance of it's neighbors.

Let X(t) represent the importance vector of a graph at time-step t, then 
X(t+1) = A * X(t) 
  
In a graph, the eigenvector centrality of node can be viewed as a measure of "steady state" of each node passing its importance to its neighbors. i.e. X(t+1) = X(t) =v
v = A*v.   

By definition, 



