# BEGIN PROB
Suppose we want to build a classifier to predict whether a person survived the sinking of the Titanic. The first 5 rows of our dataset are given below.
$$\begin{array}{|c|c|c|c|}
\hline
 & \textbf{Age} & \textbf{Survived} & \textbf{Female} \\ \hline
0 & 22.0 & 0 & 0 \\ \hline
1 & 38.0 & 1 & 1 \\ \hline
2 & 26.0 & 1 & 1 \\ \hline
3 & 35.0 & 1 & 1 \\ \hline
4 & 35.0 & 0 & 0 \\ \hline
\end{array}$$
# BEGIN SUBPROB
For a given classifier, suppose the first 10 predictions of our classifier and 10 true observations are as follows:
$$
\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|}
\hline
\textbf{Predictions} & 1 & 1 & 1 & 1 & 1 & 0 & 1 & 1 & 1 & 1 \\ \hline
\textbf{True Label} & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 1 & 1 & 1 \\ \hline
\end{array}
$$
1. What is the accuracy of our classifier on these 10 predictions? 

2. What is the precision on these 10 predictions? 

3. What is the recall on these 10 predictions?
# BEGIN SOLN
**Answer:**
1. $\frac{7}{10}$

2. We have 6 true positive and 3 false positives, so the precision evaluates to $$\frac{6}{6+3} = \frac{2}{3}$$

3. From the solution to the previous part, we know true positives = 6. The number of false negatives is 0 (we only predicted 0 once and the true value actually was 0). Thus the recall is $$\frac{6}{6+0} = 1$$
# END SOLN

# END SUBPROB

# BEGIN SUBPROB
In general (not just for the Titanic model), if we increase the threshold for a classification model, which of the following can happen to our precision, recall, and accuracy? Select all that apply.

    - [ ] Precision can increase.
    - [ ] Precision can decrease.
    - [ ] Recall can increase.
    - [ ] Recall can decrease.
    - [ ] Accuracy can increase.
    - [ ] Accuracy can decrease.
# BEGIN SOLN
**Answer:**
All except "Recall can increase" are correct.

As we increase our classification threshold, the number of false positives
decreases, but the number of false negatives (i.e. undetected points) increases. As a
result, our precision increases (more of the points we say are positive will actually be
positive), but our recall decreases (there will be more points that are actually positive
that we don’t detect). However, in some cases precision can also decrease, when
increasing a threshold lowers the number of true positives but keeps the number of
true negatives the same. As seen in lecture, accuracy may increase or decrease – there
typically exists an optimal threshold that maximizes accuracy, and if we increase or
decrease our threshold from that point, accuracy decreases.
# END SOLN

# END SUBPROB

# BEGIN SUBPROB
Suppose after training our model we get $\mathbf{\beta} = \begin{bmatrix}
-1.2 & -0.005 & 2.5
\end{bmatrix}^T$, where $-1.2$ is an intercept term, $-0.005$ is the parameter corresponding to passenger's age, and $2.5$ is the parameter corresponding to sex.

1. Consider Sı̄lānah Iskandar Nāsı̄f Abı̄ Dāghir Yazbak, a 20 year old female. What chance did she have to survive the sinking of the Titanic according to our model? Give your answer as a probability in terms of $\sigma$. If there is not enough information, write "not enough information."
    $$
    P(Y = 1 | \text{age} = 20, \text{female} = 1) =
    $$


2. Sı̄lānah Iskandar Nāsı̄f Abı̄ Dāghir Yazbak actually survived. What is the cross-entropy loss for our prediction in part (i)? If there is not enough information, write "not enough information."
    $$
    \text{Cross entropy loss} =
    $$


3. Let $m$ be the odds of a given male passenger's survival according to our model, i.e., if the passenger had an 80\% chance of survival, $m$ would be 4, since their odds of survival are $0.8 / 0.2 = 4$. It turns out we can compute $f$, the odds of survival for a female of the same age, even if we don't know the age of the two people. What is this relationship? Hint: How are the odds related to $t = \mathbf{x}^T \mathbf{\beta}$ for a given observation?
    $$
    f =
    $$

# BEGIN SOLN
**Answer:** 
1. Our observation vector is of the form $\vec{x} = [1, 20, 1]^T$. Then $\vec{x}^T \vec{\beta}} = 1(-1.2) + 20(-0.005) + 1(2.5) = 1.2, so $P(Y = 1 | \vec{x}) = \sigma \vec{x}^T \vec{\beta}} = \sigma (1.2)$

2. Here $y=1$ and $\hat{y} = \sigma (1.2)$. The formula for cross entropy loss is $-y\log (\hat{y}) - (1 - y)\log (1 - \hat{y}) = -\log (\sigma (1.2))$

3. 
We start by finding a simple relationship between the odds and $\sigma(t) = \sigma(\mathbf{x}^T \boldsymbol{\beta})$.
In logistic regression $p = \sigma(\mathbf{x}^T \boldsymbol{\beta})$.  
The odds are defined as $\text{odds} = \frac{p}{1-p}$. Substituting in, we have:  
 $= \frac{\frac{1}{1+e^{-t}}}{1 - \frac{1}{1+e^{-t}}}$


 $= \frac{\frac{1}{1+e^{-t}}}{\frac{1+e^{-t}-1}{1+e^{-t}}}$


$ = \frac{\frac{1}{1+e^{-t}}}{\frac{e^{-t}}{1+e^{-t}}}$


$ \frac{1}{e^{-t}} = e^t$
Thus, we have that $\text{odds} = e^{\mathbf{x}^T \boldsymbol{\beta}}$.  
From here, the problem is relatively straightforward, as we have that  

$$\frac{f}{m} = \frac{e^{-1.2 - 0.005\text{age} + 2.5}}{e^{-1.2 - 0.005\text{age}}}$$

$$\frac{f}{m} = e^{2.5}$$
# END SOLN

# END SUBPROB


# END PROB
