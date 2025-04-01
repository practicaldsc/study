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

Let's first identify all elements of the confusion matrix by comparing predictions with true labels:

| Metric | Count | Explanation |
|--------|-------|-------------|
| True Positives (TP) | 6 | Prediction=1 and True Label=1 |
| False Positives (FP) | 3 | Prediction=1 and True Label=0 |
| True Negatives (TN) | 1 | Prediction=0 and True Label=0 |
| False Negatives (FN) | 0 | Prediction=0 and True Label=1 |
| Total | 10 | Total number of predictions |


1. **Accuracy**: The proportion of correct predictions (TP + TN) among the total number of predictions.
   $$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN} = \frac{6 + 1}{10} = \frac{7}{10} = 0.7$$

2. **Precision**: The proportion of true positives among all positive predictions.
   $$\text{Precision} = \frac{TP}{TP + FP} = \frac{6}{6 + 3} = \frac{6}{9} = \frac{2}{3} \approx 0.67$$

3. **Recall**: The proportion of true positives among all actual positives.
   $$\text{Recall} = \frac{TP}{TP + FN} = \frac{6}{6 + 0} = \frac{6}{6} = 1$$

# END SOLN

# END PROB