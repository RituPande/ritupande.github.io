---
layout: post
title: Information Theory and Machine Learning
published: false  
---

**Information theory**  is a subfield of mathematics that deals with the quantification of the information in events, random variables, and distributions and storing it in a fashion such that it is robust to errors ( channel encoding and error correction). The field was proposed and developed by Claude Shannon while working at the US telephone company Bell Labs to quantify information for communication. This post provides an introduction to basic concepts of information theory and their application to machine learning.  

## 1. Information of an Event
Information of an event can be intuitively understood as to how much surprise there an is an event. Knowledge of an unlikely ( more uncertain ) event occurring is more informative  than learning that a likely event (more certain)  has occurred. This can be summarized as follows:  

Low Probability Event: High Information (surprising, more uncertain).  
High Probability Event: Low Information (unsurprising, more certain).

If an event has a probability of 0.25 i.e $$ \frac{1}{4} $$, it is true in only 1 in 4 possibile outcomes. Therefore, to communicate that such an event has occurred, information about which of the 4 possible outcomes has occurred has to be passed. This requires log<sub>2</sub>(4) = 2 bits of information to be trasnmitted.
    
For any event x, the information required to communicate its occurance in bits can be calculated as:    
$$ information(x) =  log_2( \frac{1}{p(x)} ) $$  
$$ information(x) =  -log_2(p(x)) $$    


## 5. References  
[1]. [What is Information Entropy](https://machinelearningmastery.com/what-is-information-entropy/)    
[2]. [Information Gain and Mutual Information for Machine Learning](https://machinelearningmastery.com/information-gain-and-mutual-information/)    
