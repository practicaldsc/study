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
TODO
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
TODO
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
TODO
# END SOLN

# END SUBPROB


# END PROB
