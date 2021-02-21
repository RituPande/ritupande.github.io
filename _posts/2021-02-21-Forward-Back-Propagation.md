---
layout: post
title: Forward and Back Propagation in Computational Graphs
---
A computational graph is defined as a directed graph where the nodes correspond to mathematical operations. It is used as a way of expressing and evaluating a mathematical expression. Each node of a computational graph has one or two incoming edges carrying the inputs and one outgoing edge representing the result of the operation performed by the node on the inputs. There are two basic operations performed on a computational graph:  
**Forward Propagation:** Forward propagation involves computing the values of all nodes in the graph to arrive at the final value of the mathematical expression represented by the graph.  
**Back Propagation:** Back propagation involves calculating partial derivatives of the output of the graph w.r.t. the inputs of each node. These partial derivatives explain how the output of the graph varies w.r.t to its inputs  

## Operations on Computational Graphs
Let *f* represent a mathematical operation represented by one of the nodes in a computational graph whose final output in L, such that  *z=f(x,y)* as depicted in the diagram below.  
* **Forward propagation** (shown in green) on a computational graph calculates the output  *L* of the graph by calculating the intermediate outputs  *z* of each node in the graph and passing on the output as input to the next node.  
* **Back propagation** (shown in red) calculates the gradient of L w.r.t. inputs of each node, passing the gradients thus calculated to nodes down the graph.    
	* The **input** to the back propagation operation at every node is the partial derivation of L w.r.t. the output of that node z i.e. $$\displaystyle \frac{\partial L}{\partial z} $$   
	* The **output** of backpropagation is the partial derivatives L w.r.t. to the inputs of the node i.e.  $$ \displaystyle \frac{\partial L}{\partial x}, \frac{\partial L}{\partial y} $$  
	* Back propagation **procedure** involves the following steps:  
	  * If the output of a node is distributed to multiple nodes during forward propagation, the inputs from all of them during to backpropagation are added together i.e
	  $$ \displaystyle \partial \frac{L}{\partial z}=  \frac{\partial L}{\partial z_1 } + \frac{\partial L}{\partial z_2} $$  
	  * Calculating the partial derivative of the output of the node z, w.r.t. inputs to the node x and y  i.e.  $$ \displaystyle \frac{\partial z}{\partial x} ,\frac{\partial z}{\partial y} $$  
	  * Calculating  $$ \displaystyle \frac{∂L}{∂x},\frac{∂L}{∂y} $$  using chain rule by multiplying the partial derivates calculated in the previous two steps i.e. $$ \displaystyle \frac{∂L}{∂x}=  \frac{∂L}{∂z}.\frac{∂z}{∂x} $$ and $$ \displaystyle \frac{∂L}{∂y}=\frac{∂L}{∂z}.v\frac{∂z}{∂y} $$    
