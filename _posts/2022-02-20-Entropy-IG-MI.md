---
layout: post
title: Information Theory and Machine Learning
published: false  
---

**Information theory**  is a subfield of mathematics that deals with the quantification of the information in events, random variables, and distributions and storing it in a fashion such that it is robust to errors ( channel encoding and error correction). The field was proposed and developed by Claude Shannon while working at the US telephone company Bell Labs to quantify information for communication. This post provides an introduction to basic concepts of information theory and their application to machine learning.  

## 1. Information
Information of an event can be intuitively understood as to how much surprise there is an event. Knowledge of an unlikely ( more uncertain ) event occurring is more informative  than learning that a likely event (more certain)  has occurred. This can be summarized as follows:  

Low Probability Event: High Information (surprising, more uncertain).  
High Probability Event: Low Information (unsurprising, more certain).

If an event has a probability of 0.25 i.e $$ \frac{1}{4} $$, it occurs only once in 4 possibile outcomes. Therefore, to communicate that such an event has occurred, information about which of the 4 possible outcomes has occurred has to be passed. This requires log<sub>2</sub>(4) = 2 bits of information to be trasnmitted.
    
For any event x, the information required to communicate its occurance in bits can be calculated as:    
$$ \displaystyle information(x) =  log_2( \frac{1}{p(x)} ) $$  
$$ information(x) =  -log_2(p(x)) $$    
  
### 1.1 Entropy
Calculating the information for a random variable is called information entropy. Entropy can be intuitively understood as the average or expected number of bits required to represent or transmit a random event drawn from the probability distribution for the random variable. For a discreet random variable X, which can take K possible values, with probability distribution p, information entropy can be represented as:  

$$ \displaystyle H(X) =  - \sum_1^K p(x) log_2(p(x)) $$ 

It should be noted that a skewed probability distribution has more certainity and less surprise and therefore low entropy. A uniformally distributed random variable has more uncertainity, hence potential for more suprise factor and therefore higher entropy.

### 1.2 Cross-Entropy
If P is a true distribution and Q an approximation of it, cross entropy can be intuitively understood as  average or expeceted number of bits required to represent an event in P using Q to encode it. More precisely,    
$$ \displaystyle H(P,Q) = - \sum_1^K p(x)log_2(q(x)) $$  
where p(x) is the probability of the event x in P and q(x) is the probability of the same event x in Q.  

###  1.3 KL-Divergence

KL- Divergence can be intuitively understood to be additional bits required to represent an event in true distribution, P by encoding it with its approximate distribution, Q instead of P itself.  
  
$$ D_{KL}(P \mid \mid Q ) =  H(P,Q) - H(P) $$


## 5. References  
[1]. [What is Information Entropy](https://machinelearningmastery.com/what-is-information-entropy/)    
[2]. [Information Gain and Mutual Information for Machine Learning](https://machinelearningmastery.com/information-gain-and-mutual-information/)    
