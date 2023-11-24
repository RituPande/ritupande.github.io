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
Let $X= \\{x_1, x_2, ....x_n \\}$ be samples taken from a distribution model parameterized by $\Theta$ as part of an experiment:   
* **Probability**: Chance of occurance of an event.   
* **Probability distribution**: A mathematical function that gives probabilities of all the possible outcomes of an experiment, written as  $P (x_i | \Theta )$. The sum of probabilities of all outcomes must sum to 1 .  
* **Likelihood**: If the paramter of a distribution model are represented as $\Theta$ , then the likehood function is the joint probability of all the observed data points as a function of $\Theta$ i.e. it outputs the likeliness of different values of the parameter $\Theta$ to model the distribution from which the observed data could be sampled, written as $L(\Theta| X )$.  
* **Maximum Liklihood**: Mechanism to find the value of $\Theta$ that maximizes the likelihood function given $X$.    
* **Latent variables**: Assume that $X$  is dependent on another random variable $Z = \\{ z_1, z_2,...z_k \\}$ that is not observed. Such a variable is called hidden or latent variable. $Z$ is called latent variable because they is not observed.
Each observation $x_i \in X$ is dependent, with some probability on all possible $K$ values of Z based on the *posterior*.    
* **Evidence**: The probability distribution of X , denoted as $P(X)$ i.e. the probability ditribution of observed data.
* **Posterior**: The probability distribution of latent variables Z given $x_i \in X$, denoted as $P(Z|x_i)$ .
* **Prior**: The probability distribution of latent variables known from prior experience, denoted as $P(Z)$
Each observation $x_i \in X$ is dependent on $k$ hidden variables $\\{z_1, z_2, .... z_k\\}$
* **Model**: A computational framework that maximizes the joint probability of variables X and Z parameterized by $\Theta$, denoted as $\displaystyle \sum_i^N \sum_j^K P(x_i,z_j; \Theta)$.  

### Jensen's Inequality:   
* $E[f(x)] \ge f( E(x))$  , when $f$ is convex  
* **IF** *f* is stricly convex **AND**  $E[f(X)] = f( E(X) )$ **THEN**  
&nbsp;&nbsp;&nbsp;&nbsp; $X = E(X)$ with probability 1 i.e. the value of X is a constant.


## Expectation Maximixation
If we are tasked with creating a computational model which maximizes the probability of observed data $X= \\{x_1, x_2, ....x_n \\}$ which are dependent latent variables $Z=\\{z_1, z_2, .... z_k\\}$ , it is not possible to get a closed form equation to maximize the liklihood function of the joint probability of $X$ and $Z$ . Expectation maximization, tries instead to obtain the maximum liklihood of the observed data by indirectly accounting for Z in :
  
$\displaystyle L(\Theta| X ) = \sum_{i=1}^N log P(x_i; \Theta)  $  
  
The above equation can include $Z$ by marginalizing for all values of $Z$ :
$\sum_{i=1}^N \sum_{j=1}^K log ( P(x_i,z_j; \Theta ) )$  

Let us assume there is a distribution $Q$ from which $Z$ is sampled for each $x_i$. We multiply and divide the above equation by Q(z_j):  
$\sum_i \sum_j \frac{ Q(z_j) * log (  P(x_i,z_j, \Theta ))  }{ Q(z_j) } $  
$$\ge  \sum_i E_{z~Q(z)}( \frac{log ( P(x_i,z, \Theta ) ) }{ Q(z) } $$  
This value is called Evidence Lower Bound or ELBO  

Algorithm :  

Randomly initalize  $$\Theta $$  

Loop till convergence  
E-Step:
  for each i  
      Set  $$ Q_i(z) = P(Z_j|x_i ;\Theta) $$  
M-Step:
  $$\Theta = arg max_{\Theta} $$ \sum_{i=1}^n ELBO(x_i; \Theta ) $$


### Gaussian Mixture Models

Models that make the assumption that the evidence X can be sampled from multiple gaussian distribution are called Gaussian Mixture Models i.e Q(z) is assumed to be a gausian.
