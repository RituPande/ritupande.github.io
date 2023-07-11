---
layout: post
title: Introduction to Lagrangian Duality
permalink: /Lagrangian-Duality/
published: true
---
As we have previously disucssed in [this](https://ritupande.github.io/Introduction-to-Statistical-Learning-Theory/) article, optimization techniques are used in machine learning to find decision function in the hypothesis set closest to the emperical risk minimizer for the problem. The decision functions for a machine learning problem could be constrained or unconstrained. In this article, we will be focussing on the *Constrained Optimization* problems and how *Lagrangian Duality* can be used to solve them. 
  
General constrained optimization problem can be defined as:      
  
**min** f(x)    
**s.t.** $$ h_i(x)  \leq 0 $$  , i = 1,2,...m    
&nbsp;&nbsp;&nbsp;&nbsp;$$ e_j(x) $$ = 0, j = 1,2,...,p  

However, equality constraints can be written in form of inequality constraints and therefore not required to be included in the problem definition.  
i.e.  $$ e_j(x) = 0 \implies   0 \geq e_j(x) \leq 0  $$  
  
The generalized constrained optimization then reduces to:  
  
**min** f(x)    
**s.t.** $$ h_i(x) \leq 0 $$ , i = 1,2,...m    

## 1. Lagrangian of Constrained Optimization Problem

The Lagrangian of the general constrained optimization problem can be defined as: 
  
$$ L(x, \lambda) = f(x) + \sum_{i=1}^m \lambda_i h_i(x) $$    
  
$$ \lambda_i 's $$  are called ***Lagrangian multipliers*** or ***dual variables***   
  
Lagrangian of a constrained optimization problem can be viewed as a means of representing the original problem with relaxed constraints, while imposing penalty to the objective function if the constraints are violated. Lagrangian multipliers can be seen as  penalties that are to be applied in case  corresponding constraints are violated.  
    
Supremum over the Lagriangian, $$ sup_{\lambda_i \ge 0} L(x, \lambda_i) $$ is equivalent to the original decision function and the constraints put together.  This can be seen in the equation below:  
    
  $$ sup_{\lambda_i \geq 0} L(x, \lambda)  =  sup_{\lambda_i \ge 0} ( f(x) + \sum_{i=1}^m \lambda_i h_i(x))  $$  
  $$ sup_{\lambda_i \geq 0} L(x, \lambda)  = f(x) $$ when $$ h_i(x) \leq 0 $$  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = $$ \infty $$ otherwise     
  
If $$ h_i(x) $$ violate the constraints and assume positive value, $$ sup_{\lambda_i \ge 0} L(x, \lambda) $$ is infinity. If however, $$ h_i(x) \leq 0 $$, then the supremum of Langrangian function can be obtained only by setting the value of $$ \lambda_i $$ to 0.  So the optimization problem is equivalent to :
  
$$ p^* =  inf_x\:sup_{\lambda_i \geq 0} L(x, \lambda) $$  
 
 This form of the optimization  problem is called the **Primal** form.   
## 2.  Lagrangian Dual Problem   
    
  The **Lagrangian Dual** of the primal form of a constrained optimization problem is defined as:    
  
$$ d^* =  sup_{\lambda_i \geq 0} \: inf_x \: L(x, \lambda) $$  
  
  The Lagrangian dual provides lower bound to the solution of the primal form of any optimization problem.i.e.  
  $$ d^* \leq p* $$   
  
  This property is called  ***weak duality*** and the difference between $$ p^*$$ and $$ d^* $$  is called ***duality gap***.   
  It is easy to prove weak duality:  
      
  For any function $$ f: W\:X\:Z \rightarrow R, w_o \in W, z_o \in Z  $$:
  
  $$ inf_{w\in W} \: f(w, z_o )  \geq f(w_o,z_o) \leq sup_{z \in Z } \: f(w_o,z ) $$    
  $$ \implies inf_{w\in W} \: f(w, z_o ) \leq sup_{z \in Z } \: f(w_o,z ) $$  
  $$ \implies sup_{z_o \in Z} \: inf_{w \in W} f(w, z_o ) \leq inf_{w_o \in W} \: sup_{z \in Z } \:f(w_o,z ) $$  
  $$ \implies d^* \leq p* $$  
      
  When $$ d^* = p* $$ , it is called ***strong duality***    
### 2.1 Lagrangian Dual Function.
  
  The *Lagrangian Dual Function* is defined as:  
    
  $$ \displaystyle g(\lambda) = inf_x L(x, \lambda) = inf_x ( f(x) + \sum_{i=1}^m \lambda_i h_i(x) ) $$  
  
  Writing Lagrangian Dual problem in terms of the Langrangian Dual function:
  
  **maximize** $$ g( \lambda ) $$    
  **s.t.** $$ \lambda \geq 0 $$  
    
  $$ \lambda $$ are called ***dual feasible*** if $$ \lambda \geq 0 $$  and $$ g( \lambda ) > - \infty $$  
  $$ \lambda^* $$ are called ***dual optimal*** if they give optimal value for Lagrangian Dual Problem    
## 3. Why Lagrangian Dual
  
  What might come to the reader's mind is; what purpose the Lagrangian dual of a primal problem serve ? Why should one bother about it?
  
  1. Lagrangian dual  greatly simplifies the primal problem. It removes all constraints from the problem making them part of the objective dunction. The dual is left with only affine constarints $$ \lambda_i \geq 0 $$   
  2. Lagrangian dual function is always concave i.e its negative is a convex function. This is so because it only has affine constraints and point-wise minimum of affine functions is always a concave function. So even if the primal problem is not convex, its dual can be solved using convex optimization techniques.  
  3. $$ d^* $$ can be used as stopping criteria while solving primal optimization problem.    
  4. If the primal problem is convex, then it almost always guarnatees strong duality.  
  5. Duality also lets us formulate optimality conditions for constrained optimisation problems.
  
## 4. KKT Conditions for Constrained Optimization Problems
  
  KKT conditions are first order necessary optimality conditions  for  non-linear optimization problems.  
  
  if p* and d* are primal and dual optimal solutions to a general constrained optimization problem such that p* = d* then the following are the KKT optimality conditions:
  
  - **Stationarity Condition:**   
  $$ 0 \in \partial L $$,  where $$ \partial L $$ is subdifferntial of L   
    
  - **Complemenatry Slackness:**   
    $$ \lambda_i h_i(x) = 0 . i = 1,2,...,m $$
  
    This can be easily proven as follows:
  
     $$ f(x^*) = g(\lambda^* ) $$   
     &nbsp;&nbsp;&nbsp;&nbsp; $$ = g(\lambda^* ) = inf_x \: L(x, \lambda^*) $$  
     &nbsp;&nbsp;&nbsp;&nbsp; $$ \leq L(x^*, \lambda^*) $$  
     &nbsp;&nbsp;&nbsp;&nbsp; $$  = f(x^*) + \sum_{i=1}^m \lambda_i^* h_i(x^*) $$   
     &nbsp;&nbsp;&nbsp;&nbsp; $$ \leq f(x^*) $$ Since, $$ \lambda_i^* h_i(x^*) \leq 0 $$  
       
     This gives us the following:  
     $$ f(x^*) \leq L(x^*, \lambda^*)  \leq f(x^*) $$  
     $$ \displaystyle \implies  \sum_{i=1}^m \lambda_i^* h_i(x^*) =0  $$  
     $$ \implies \lambda_i^* h_i(x^*) = 0 $$  i.e. each individual term in summation has to be zero
     
  
  - **Primal Feasibility:**  
     $$ h_i(x) \leq 0 $$ 
    
  - **Dual Feasibility:**  
     $$ \lambda_i \geq 0 $$     
    
### 4.1 Optimality Conditions for Convex Objective Functions
   1. For convex problems the KKT conditions are both necessary and sufficient.
   2. Conditions that guarantee strong duality for convex problems are called ***constraint qualifications***.  
   3. **Slater's constraint qualification** : is a sufficient condition, needed to prove strong duality for constrained convex optimization problem.  
      - It states that $$ p^* = d^* $$ if atleast one point in the domain of the primal function must satisfy the constarints with strict inequality i.e be **strictly feasible***.
      - For problems with only affine constraints, only feasibilty of the constraints is required.
   
  
## References
1. [Lec-9:Langrangian Duality and Convex Optimization from  Foundations of Machine Learning Bloomberg ML EDU](https://bloomberg.github.io/foml/#lecture-9-lagrangian-duality-and-convex-optimization)  
2. [Lec-12 KKT Conditions](https://www.stat.cmu.edu/~ryantibs/convexopt-F16/scribes/kkt-scribed.pdf)   
3. [Duality: Constraint Relaxation](https://www.youtube.com/watch?v=nClTjGznkTo)
