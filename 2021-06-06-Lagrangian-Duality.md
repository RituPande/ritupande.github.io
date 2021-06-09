As we have previously disucssed in [this](https://ritupande.github.io/Introduction-to-Statistical-Learning-Theory/) article, optimization techniques are used in machine learning to find decision function in the hypothesis set closest to the emperical risk minimizer for the problem. The decision functions for a machine learning problem could be constrained or unconstrained. In this article, we will be focussing on the *Unconstrained Optimization* problems and how *Lagrangian Duality* can be used to solve them.   
  
General constrained optimization problem can be defined as:    

**min** f(x)    
**s.t.** $$ h(x_i) $$  < = 0 , i = 1,2,...m    
nbsp;nbsp;nbsp;nbsp;$$ e(x_i) $$ = 0, j = 1,2,...,p  

However, equality constraints can be written in form of inequality constraints and therefore not required to be included in the problem definition.  
i.e.  $$ e(x_i) = 0 \implies   0 \ge e(x_i) \le 0  $$  
  
The generalized constrained optimization then reduces to:  
  
**min** f(x)    
**s.t.** $$ h(x_i) $$  < = 0 , i = 1,2,...m    

## 1. Lagrangian of Constrained Optimization Problem

The Lagrangian of the general constrained optimization problem can be defined as:  
  
  $$ L(x, \lambda) = f(x) + \sum_i=1^m \lambda_i h(x_i) $$    
  
  \lamda_i 's  are called ***Lagrangian multipliers*** or ***dual variables***   
  
  Supremum over the Lagriangian, $$ sup_{\lambda_i \ge 0} L(x, \lambda) $$ is equivalent to the original the decision function and the constraints put together.  This can be seen in the equation below:  
    
  $$ sup_{\lambda_i \ge 0} L(x, \lambda)  =  sup_{\lambda_i \ge 0}  f(x) + \sum_i=1^m \lambda_i h(x_i)  $$  
  $$ sup_{\lambda_i \ge 0} L(x, \lambda)  = f(x), when h(x)_i \le 0 $$  
  nbsp;nbsp;nbsp;nbsp;nbsp;nbsp;nbsp;nbsp;nbsp; = $$ \infinity otherwise $$  
  
If $$ h_i(x) $$ violate the constraints and assume positive value,  sup_{\lambda_i \ge 0} L(x, \lambda)  is infinity. If however, $$ h_i(x) \le 0 $$, then the supremum of Langrangian function can be obtained only by setting the value of \lambda_i to 0.  So the optimization problem is equivalent to :
  
 $$ p^* =  inf_x sup_{\lambda_i \ge 0} L(x, \lambda) $$  
 
 This form of the optimization  problem is called the **Primal** form.
 
  
  ## 2.  Lagrangian Dual Problem   
    
  The **Lagrangian Dual** of the primal form of a constrained optimization problem is defined as:    
    
  $$ d^* =  sup_{\lambda_i \ge 0} inf_x L(x, \lambda) $$  
  
  The Lagrangian dual provides lower bound to the solution of the primal form of any optimization problem.i.e.  
  $$ d^* \le p* $$   
  
  This property is called  ***weak duality*** and the difference between $$ p^* and d^* $$  is called ***duality gap***.   
  It is easy to prove weak duality:  
      
  For any function $$ f: W X Z \rightarrow R and w_o \in W, z_o \in Z  $$:
  
  $$ inf_w{ \in W} f(w, z_o )  \ge f(w_o,z_o) \le sup_{z \in Z } f(w_o,z ) $$    
  $$ \implies inf_w{ \in W} f(w, z_o ) \le sup_{z \in Z } f(w_o,z ) $$  
  $$ \implies sup_{z_o \in Z} inf_{w \in W} f(w, z_o ) \le inf_{w_o \in W} sup_{z \in Z } f(w_o,z ) $$  
     
  The above result provides proof that:      
  $$ d^* \le p* $$      
      
  $$ d^* = p* $$ is called ***strong duality***  
  
  ### 2.1 Lagrangian Dual Function.
  
  The *Lagrangian Dual Function* is defined as:  
    
  $$ \displaystyle g(\lambda) = inf_x L(x, \lambda) = inf_x ( f(x) + \sum_i=1^m \lambda_i h(x_i) ) $$  
  
  Writing Lagrangian Dual problem in terms of the Langrangian Dual function:
  
  **maximize** $$ g( \labmda ) $$    
  **s.t.** $$ \lambda /ge 0 $$  
    
  $$ \lambda $$ are called ***dual feasible*** if $$ \lambda /ge 0 $$  and g( \labmda ) > - \infinity $$  
  $$ \lambda^* $$ are called ***dual optimal*** if they give optimal value for Lagrangian Dual Problem $$  
  
  ## 3. Why Lanrangian Dual
  
  What might come to mind immediately is what purpose does taking Lagrangian dual of a primal problem serve ? Why should one bother about it?
  
  1. Lagrangian dual  greatly simplifies the primal problem. It removes all constraints from the problem aside the trivial  $$ \lambda /ge 0 $$ constraint, making them part of the objective dunction.    
  2. Lagrangian dual function is always concave i.e its negative is a convex function. This is so because it only has affine constraints and point-wise minimum of affine functions is always a concave function. So even if the primal problem is not convex, its dual can be solved using convex optimization techniques.  
  3. $$ d^* $$ can be used as stopping criteria while solving primal optimization problem.    
  4. If the primal problem is convex, then it almost always guarnatees strong duality.  
  
  
  
  
  
  
 
  
 
  
## References
[Lec-9:Langrangian Duality and Convex Optimization from  Foundations of Machine Learning Bloomberg ML EDU](https://bloomberg.github.io/foml/#lecture-9-lagrangian-duality-and-convex-optimization)