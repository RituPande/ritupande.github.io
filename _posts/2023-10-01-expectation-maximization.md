---
layout: post
title: Expectation Maximization
permalink: /blog/expectation-maximization/
published: false
header-includes:
  - \usepackage[ruled,vlined,linesnumbered]{algorithm2e}
---

In this post we shall explore expectation maximization, a mathematical tool used in many generative-ai algorithms, in detail.  

Let $$ X = { x_1, x_2, ....x_n } $$ be observed samples from a distribution parameterized by $$ \theta $$.  
Probability: Chance of occurance of an event.   
Probability distribution: A mathematical function that gives probabilities of all the possible outcomes of an experiment. The sum of all outcomes must sum to 1, written as  $$ P (x_i | \Theta ) $$ .  
Likelihood: If the paramter of a distribution model are represented as $$ \Theta $$ , then the likehood function is the joint probability of all the observed data points as a function of $$ \Theta $$ i.e. it outputs the likeliness of different values of the parameter $$ \Theta $$ to model the distribution from which the observed data could be sampled, written as $$ L(\Theta| X ) $$.  
Maximum Liklihood: Mechanism to find the value of $$ \theta $$ that maximizes the likelihood function given X.  

Assume now that X has come not just from one but $ K $ probability distributions, represented by set of parameters \Theta. The probabaility of observed point $$ x_i $$ to come from one of the K distributions is ditermined by a latent variable $$ Z $$ s.t.   
$$ Z_i = \Phi $$ , where \Phi is a multinomial s.t.  
$$ \phi_j \ge 0; \sum_{j=0}^K \phi_j = 1 $$  

$$ \phi_j $$ = P( Z_i =j )  
  
This imples that the probability that an observed datapoint is sampled from a distribution from a set of K distributions is not a one-hot vector but a softmax.  

$$ P(Z) $$ = Class Prior for latent variable Z  
P(X) = Evidence  
P(Z,X; \Theta) = Model  
P(Z|X ) = Posterior  

Jensen's Inequality:   
$$ E[f(x)] \ge f( E(x) ) $$ , when $$ f $$ is convex  
IF f is stricly convex AND $$ E[f(X)] \eq f( E(X) ) $$ THEN  
&nbsp;&nbsp;&nbsp;&nbsp; $$ X = E(X) $$ with probability 1 i.e. the value of X is a constant.

Expectation Maximization : Mechanism to find the value of $$ \Theta $$ that maximizes the likelihood function that is dependent on observed values X and latent variables Z.  
Objective : max  $$ log ( \sum_Z P(X,Z, \Theta ) )  $$

Multiply and divide by a probbaility distribution $$ Q(z) $$  
$$ \frac{ Q(z) * log ( \sum_Z P(X,Z, \Theta ) ) }{ Q(z) }  $$  
$$ \ge E_{z~Q(z)}( \frac{log ( \sum_Z P(X,Z, \Theta ) ) }{ Q(z) } $$  
This value is called Evidence Lower Bound or ELBO  

Algorithm :  

Randomly initalize  $$ \Theta $$  

Loop till convergence  
E-Step:
  for each i  
      Set  $$ Q_i(z) = P(Z_i|x_i ;\Theta) $$  
M-Step:
  $$ \Theta = arg max_{\Theta} $$ \sum_{i=1}^n ELBO(x_i; \Theta ) $$

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Write here the result}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{Write here the input}
\Output{Write here the output}
\BlankLine
\While{While condition}{
    instructions\;
    \eIf{condition}{
        instructions1\;
        instructions2\;
    }{
        instructions3\;
    }
}
\caption{While loop with If/Else condition}
\end{algorithm} 
