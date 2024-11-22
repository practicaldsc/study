# BEGIN PROB

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

2. We have 6 true positive and 3 false positives, so the precision evaluates to: $$\frac{6}{6+3} = \frac{2}{3}$$

3. From the solution to (2) above, we know true positives = 6. The number of false negatives is 0 (we only predicted 0 once and the true value actually was 0). Thus the recall is: $$\frac{6}{6+0} = 1$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Consider a model (e.g. the logistic regression model) that predicts $p_i = P(y = 1 | \vec{x}_i)$, and then applies some threshold $T$ to the outputted probability. That is, the model predicts either class 1, if $p_i \geq T$, or class 0, if $p_i < T$.

In general, if we increase the threshold $T$, which of the following can happen to our precision, recall, and accuracy? Select all that apply.

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

# END PROB