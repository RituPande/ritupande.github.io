---
layout: post
title: Expectation Maximization
permalink: /blog/expectation-maximization/
published: false
---

In this post we shall explore *expectation maximization*, a mathematical tool used in many generative-ai algorithms, in detail. Expectation maximization is a means to calculate the maximum likelihood estimate in presence of latent variables. 

## Background
In this section we cover the necessry definitions and notations to understand the expecation maximization algorithm:  
### Definitions
Let $X= \\{x^{(1)}, x^{(2)}, ....x^{(3)} \\}$ be samples taken from a distribution model parameterized by $\Theta$ as part of an experiment:   
* **Probability**: Chance of occurance of an event.   
* **Probability distribution**: A mathematical function that gives probabilities of all the possible outcomes of an experiment, written as  $P (x^{(i)} | \Theta )$. The sum of probabilities of all outcomes must sum to 1 .  
* **Likelihood**: If the paramter of a distribution model are represented as $\Theta$ , then the likehood function is the joint probability of all the observed data points as a function of $\Theta$ i.e. it outputs the likeliness of different values of the parameter $\Theta$ to model the distribution from which the observed data could be sampled, written as $L(\Theta| X )$.  
* **Maximum Liklihood**: Mechanism to find the value of $\Theta$ that maximizes the likelihood function given $X$.    
* **Latent variables**: Assume that each $x^{(i)}$  is dependent on another random variable $Z^{(i)} = \\{ z_1^{(i)}, z_2^{(i)},...z_k^{(i)} \\}$ that is not observed. Such a variable is called hidden or latent variable. $Z$ is called latent variable because it is not observed.
Each observation $x^{(i)} \in X$ is dependent, with some probability on all possible $K$ values of Z, called the *posterior*.    
* **Evidence**: The probability distribution of X , denoted as $P(X)$ i.e. the probability ditribution of observed data.
* **Posterior**: The probability distribution of latent variables Z given $x^{(i)} \in X$, denoted as $P(Z|x^{(i)})$ .
* **Prior**: The probability distribution of latent variables known from prior experience, denoted as $P(Z)$
* **Model**: A computational framework that maximizes the joint probability of variables X and Z parameterized by $\Theta$, denoted as $\displaystyle \sum_i^N \sum_j^K P(x^{(i)},z_j^{(i)}; \Theta)$. This , can be evaluated as:
$P(X|Z,\Theta) * P(Z)$, using Baye's rule.
* **Cordinate descent**: is a an iterative optimization algorithm. Each iteration involves two steps. In the first step the algorithm optimizes the objective by updating only a subset of parameters influencing the objective, while keeping the remaining parameters fixed. In the next step, it fixes the values of the parameter subset changed in first step and optimizes the objective by changing the remaining ones.

### Jensen's Inequality:   
* $E[f(x)] \ge f( E(x))$  , when $f$ is convex  
* **IF** *f* is stricly convex **AND**  $E[f(X)] = f( E(X) )$ **THEN**  
&nbsp;&nbsp;&nbsp;&nbsp; $X = E(X)$ with probability 1 i.e. the value of X is a constant.


## Expectation Maximization (EM)
If we are tasked with creating a computational model which maximizes the probability of observed data $X= \\{x^{(1)}, x^{(2)}, ....x^{(n)} \\}$ each of which are dependent latent variables $Z=\\{z_1, z_2, .... z_k\\}$ , it is not possible to get a closed form equation to maximize the liklihood function of the joint probability of $X$ and $Z$ . Expectation maximization, tries instead to obtain the maximum liklihood of the observed data by indirectly accounting for Z using a co-ordinate descent approach. 

### Derivation of EM Algoritm
The objective of EM algorithn is to maximize the log likelihood of the observed data in presence of latent variables:  
  
$\displaystyle L(\Theta| X ) = \sum_{i=1}^N log (P(x^{(i)}; \Theta))  $  
  
The above equation can be modified to introduce $Z$ as follows:  
$\displaystyle = \sum_{i=1}^N \sum_{j=1}^K log ( P(x^{(i)},z_j^{(i)}; \Theta ) )$  

Let us assume there is a distribution $Q$ from which $Z$ is sampled for each $x_i$. We multiply and divide the above expression by $Q(z_j)$:    
  
$\displaystyle =\sum_{i=1^N} \sum_{j=1^K} log \frac{ Q(z_j) * P(x^{(i)},z_j^{(i)}, \Theta ) }{ Q(z_j^{(i)}) }$  

By definition of Expectation:  
  
$\displaystyle = \sum_{i=1^N} log ( E_{z \sim Q(z)}\frac{P(x^{(i)},z, \Theta ) }{ Q(z) }) $   

Since $log$ is a concave function: using Jenson's inequaltity: 
    
$\displaystyle \ge \sum_{i=1^N} E_{z \sim Q(z)}log( \frac{P(x^{(i)},z, \Theta ) }{ Q(z) })$   

This expression is termed as $ELBO(X, Q, \Theta )$  or the **E**vidence **L**ower **Bo**und and based on  the above derivation, it is clear that $L(\Theta| X )$ is always greater than this value. However, Jenson's inequality also says that ELBO will be exactly equal to $L(\Theta| X )$ if:
  
$\displaystyle \frac{P(x^{(i)},z, \Theta ) }{ Q(z) } = c$, a constant 

$\displaystyle Q(z) \propto P(x^{(i)},z, \Theta )$  

Since $Q$ is a probability distribution $\sum_z Q(z)=1$. Therefore to convert proportionality to equality, we can normalize the right-hand side:
  
$\displaystyle Q(z) = \frac{P(x^{(i)},z, \Theta )}{\sum_z P(x^{(i)},z, \Theta )}$  

$\displaystyle Q(z) = \frac{P(x^{(i)},z, \Theta )}{P(x^{(i)},\Theta )}$  

$\displaystyle Q(z) = P(z|x^{(i)}) $  

Thus, the EM Algorithm can be framed as follows:

Randomly initalize  $$\Theta $$  

Loop till convergence  
E-Step:
  for each i  
      Set  $$ Q_i(z) = P(Z_j|x_i ;\Theta) $$  
M-Step:
  $$\Theta = arg max_{\Theta} $$ \sum_{i=1}^n ELBO(x_i; \Theta ) $$


### Gaussian Mixture Models

Models that make the assumption that the evidence X can be sampled from multiple gaussian distribution are called Gaussian Mixture Models i.e Q(z) is assumed to be a gausian.
