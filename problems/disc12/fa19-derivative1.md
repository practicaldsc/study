# BEGIN PROB

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


# END PROB