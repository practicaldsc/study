# BEGIN PROB

<!-- 
For a given classifier, suppose the first 10 predictions of our classifier and 10 true observations are as follows:
$$
\begin{array}{|c|c|c|c|c|c|c|c|c|c|c|}
\hline
\textbf{Predictions} & 1 & 1 & 1 & 1 & 1 & 0 & 1 & 1 & 1 & 1 \\ \hline
\textbf{True Label} & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 1 & 1 & 1 \\ \hline
\end{array}
$$ -->

The logistic regression model first predicts $p_i = P(y_i = 1 | \vec{x}_i)$, and then applies some threshold $T$ to the outputted probability to classify $\vec x_i$. That is, the model predicts either class 1, if $p_i \geq T$, or class 0, if $p_i < T$.

In general, if we increase the threshold $T$, which of the following can happen to our precision, recall, and accuracy? Select all that apply.

- [ ] Precision can increase.
- [ ] Precision can decrease.
- [ ] Recall can increase.
- [ ] Recall can decrease.
- [ ] Accuracy can increase.
- [ ] Accuracy can decrease.

# BEGIN SOLN

**Answer:** All except "Recall can increase" are correct.

As a refresher:

$$\begin{align*} 
\text{Precision} &= \frac{TP}{TP + FP} = \frac{TP}{\text{\# points predicted positive}} \\ 
\text{Recall} &= \frac{TP}{TP + FN} = \frac{TP}{\text{\# points actually positive}} \\ 
\text{Accuracy} &= \frac{TP + TN}{TP + TN + FP + FN} = \frac{\text{\# points correctly predicted}}{\text{\# total points}} 
\end{align*}$$

Remember that in binary classification, 1 is "positive" and 0 is "negative".

As we increase our classification threshold, the number of false positives
decreases, but the number of false negatives (i.e. undetected points) increases. 

As a result, our precision increases (more of the points we say are positive will actually be positive), but our recall decreases (there will be more points that are actually positive that we don't detect).

However, in some cases precision can also decrease, when
increasing a threshold lowers the number of true positives but keeps the number of
true negatives the same. It's impossible for recall to decrease as we increase our threshold, though – the denominator in $\text{Recall} = \frac{TP}{TP + FN}$ is just the total number of points that are actually 1, which is a constant, and as we increase the threshold, the number of true positives will only decrease or stay the same.

As seen in Lecture 23, accuracy may increase or decrease as we increase the threshold – there typically exists an optimal threshold that maximizes accuracy, and if we increase or
decrease our threshold from that point, accuracy decreases.

# END SOLN

# END PROB