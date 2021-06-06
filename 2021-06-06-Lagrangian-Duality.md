As we have previously disucssed in [this](https://ritupande.github.io/Introduction-to-Statistical-Learning-Theory/) article, optimization techniques are used in machine learning to find decision function in the hypothesis set closest to the emperical risk minimizer for the problem. The decision functions for a machine learning problem could be constrained or unconstrained. In this article, we will be focussing on the Unconstrained Optimization Problems and how *Lagrangian Duality* can be used to solve them.   
  
A generalized constrained optimization problem can be defined as:    

**min** f(x)    
**s.t.** $$ h(x_i) $$  < = 0 , i = 1,2,...m    
nbsp;nbsp;nbsp;nbsp;$$ e(x_i) $$ = 0, j = 1,2,...,p  

However, equality constraints can be written in form of inequality constraints and therefore not required to be included in the problem definition.  
i.e.  $$ e(x_i) = 0 \implies   0 \ge e(x_i) \le 0  $$  
  
The generalized constrained optimization then reduces to:  
  
**min** f(x)    
**s.t.** $$ h(x_i) $$  < = 0 , i = 1,2,...m    


