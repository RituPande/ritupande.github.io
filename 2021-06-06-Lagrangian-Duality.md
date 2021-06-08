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
  
  \lamda_i 's  are called *Lagrangian multipliers* or *dual variables*   
  
  Supremum over the Lagriangian, $$ sup_{\lambda_i \ge 0} L(x, \lambda) $$ is equivalent to the original optimization problem - the decision function and the constraints.  This can be seen in the equation below:  
    
  $$ sup_{\lambda_i \ge 0} L(x, \lambda)  =  sup_{\lambda_i \ge 0}  f(x) + \sum_i=1^m \lambda_i h(x_i)  $$ 
  $$ sup_{\lambda_i \ge 0} L(x, \lambda)  = f(x), when h(x)_i \le 0 $$  
  nbsp;nbsp;nbsp;nbsp;nbsp;nbsp;nbsp;nbsp;nbsp; = $$ \infinity otherwise $$  
  
  If $$ h_i(x) $$ violate the constraints and assume positive value,  sup_{\lambda_i \ge 0} L(x, \lambda)  is infinity. If however, $$ h_i(x) \le 0 $$, then the supremum of Langrangian function can be obtained only by setting the value of \lambda_i to 0. 
  

