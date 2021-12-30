---
layout: post
title: Eigenvector Centrality
published: true  
---

Eigenvector centrality is one the most fundamental mechanism used to assign importance to a node in a graph. While Degree Centrality' assigns importance to a node based on  the number of its neighboring nodes, Eignevector Centrality assigns importance to a node in a graph based not only based on the number of its neightbors but also their importance. i.e. a node's importance is proportional to the sum of the importance of it's neighbors.

Let X(t) represent the importance vector of a graph at time-step t, then:  
  
$$ X(t+1) \propto A * X(t) $$
  
In a graph, the eigenvector centrality of node can be viewed as a measure of "steady state" of each node passing its importance to its neighbors. i.e. X(t+1) = X(t). This implies that in "steady state", the node is giving away and receving the same amount of centrality to/from the neighboring nodes. Let this "steady state" vector be denoated as v  
  
$$ v  \propto A*v $$  
$$ v  = \lambda A*v $$

By definition, v is an eigenvector of A. Hence, we can intuitively understand that eignevector of an adjacency matrix provides importance ( centrality ) of each node based on the premise that its importance is proportional to the sum of the importances of it's neighbors.  

### Mathematical Proof

As discussed, in a "steady state",  the node is giving away and receving the same amount of centrality to/from the neighboring nodes. : 

X(t) = A * X(t)  
$$ X(t) = A^t  * X(0) $$
  
Since A is a symmetric matrix, it's eigenvectors span  R<sup>n</sup>:  
$$ \displaystyle X(0) = \sum_{i=1}^n  c_i * v_i $$, where v<sub>i</sub>  are eignevectors of A. 

$$ \displaystyle X(t) =  A ^t  \sum_{i=1}^n  c_i * v_i $$  
$$ \displaystyle X(t) =  \sum_{i=1}^n   c_i * A^t * v_i $$  
$$ \displaystyle X(t) =  \sum_{i=1}^n   c_i * \lambda_i^t * v_i $$
  
Let $$ \lambda_1 $$ be the highest eignevalue:  
$$ \displaystyle X(t) =  c_1 * \lambda_1^t * v_1 + \sum_{i=2}^n   c_i * \lambda_i^t * v_i $$  
$$ \displaystyle X(t) =  c_1 * \lambda_1^t * v_1 + \sum_{i=2}^n   c_i * \lambda_i^t * v_i $$   
  
Multiplying and dividing with $$ \lambda_1^t $$   
$$ \displaystyle X(t) =  c_1 * \lambda_1^t * v_1 + \lambda_1^t \sum_{i=2}^n   c_i * \frac{\lambda_i^t}{\lambda_1^t} * v_i $$  

$$ t \to \inf , \displaystyle \frac{\lambda_i^t}{\lambda_1^t} \to 0 $$  
$$ X(t) =  c_1 * \lambda_1^t * v_1 $$  
$$ X(t) \propto v_1 $$  
  
Hence, the largest eigenvector gives the "Eignevector Centrality" for a graph.  

### References
[1]. [Eingenvector Centrality](https://www.youtube.com/watch?v=1S1mD0l9FwU&list=LL&index=1&t=176s)  



