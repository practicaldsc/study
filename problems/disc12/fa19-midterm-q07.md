# BEGIN PROB
Suppose we want to use logistic regression to classify whether a person survived the sinking of the Titanic. The first 5 rows of our dataset are given below.

$$\begin{array}{|c|c|c|c|}
\hline
 & \textbf{Age} & \textbf{Survived} & \textbf{Female} \\ \hline
0 & 22.0 & 0 & 0 \\ \hline
1 & 38.0 & 1 & 1 \\ \hline
2 & 26.0 & 1 & 1 \\ \hline
3 & 35.0 & 1 & 1 \\ \hline
4 & 35.0 & 0 & 0 \\ \hline
\end{array}$$

Suppose after training our logistic regression model we get $\vec{w}^* = \begin{bmatrix}
-1.2 \\ -0.005 \\ 2.5
\end{bmatrix}$, where $-1.2$ is an intercept term, $-0.005$ is the optimal parameter corresponding to passenger's age, and $2.5$ is the optimal parameter corresponding to sex (1 if female, 0 otherwise).

# BEGIN SUBPROB

Consider Sı̄lānah Iskandar Nāsı̄f Abı̄ Dāghir Yazbak, a 20 year old female. What chance did she have to survive the sinking of the Titanic according to our model? Give your answer as a probability in terms of $\sigma$. If there is not enough information, write "not enough information."
# BEGIN SOLN

**Answer**: $P(y = 1 | \text{age} = 20, \text{female} = 1) = \sigma(1.2)$

Our augmented feature vector is of the form $\text{Aug}(\vec{x}) = \begin{bmatrix} 1 \\ 20 \\ 1 \end{bmatrix}$. Then $\vec{w}^* \cdot \text{Aug}(\vec x) = 1(-1.2) + 20(-0.005) + 1(2.5) = 1.2$, so:

$$P(y = 1 | \vec{x}) = \sigma \left( \vec{w}^* \cdot \text{Aug}(\vec x) \right) = \boxed{\sigma (1.2)}$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Sı̄lānah Iskandar Nāsı̄f Abı̄ Dāghir Yazbak actually survived. What is the cross-entropy loss for our prediction in the previous part?

# BEGIN SOLN

**Answer**: $-\log (\sigma (1.2))$

Here $y_i=1$ and $p_i = \sigma (1.2)$. The formula for cross entropy loss is:

$$L_\text{ce}(y_i, p_i) = -y_i\log (p_i) - (1 - y_i)\log (1 - p_i) = \boxed{-\log (\sigma (1.2))}$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

At what age would we predict that a female passenger is more likely to have survived the Titanic than not? In other words, at what age is the probability of survival for a female passenger greater than 0.5?

_Hint: Since $\sigma(0) = 0.5$, we have that $\sigma \left( \vec{w}^* \cdot \text{Aug}(\vec x) \right) = 0.5 \implies \vec{w}^* \cdot \text{Aug}(\vec x) = 0$._

# BEGIN SOLN

**Answer**: 260 years old

The probability that a female passenger of age $a$ survives the Titanic is:

$$P(y = 1 | \text{age} = a, \text{female} = 1) = \sigma(-1.2 - 0.005 a + 2.5) = \sigma(1.3 - 0.005a)$$

In order for $\sigma(1.3 - 0.005a) = 0.5$, we need $1.3 - 0.005a = 0$. This means that:

$$0.005a = 1.3 \implies a = \frac{1.3}{0.005} = 1.3 \cdot 200 = 260$$

So, a female passenger must be at least 260 years old in order for us to predict that they are more likely to survive the Titanic than not. Note that $\text{age} = 260$ can be interpreted as a **decision boundary**; since we've fixed a value for the $\text{female}$ feature, there's only one remaining feature, which is $\text{age}$.

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

Let $m$ be the **odds** of a given non-female passenger's survival according to our logistic regression model, i.e., if the passenger had an 80\% chance of survival, $m$ would be 4, since their odds of survival are $\frac{0.8}{0.2} = 4$. 

It turns out we can compute $f$, the odds of survival for a female passenger of the same age, in terms of $m$. Give an expression for $f$ in terms of $m$.

# BEGIN SOLN

Let $p_m$ be the probability that the non-female passenger survives, and let $p_f$ be the probability that the female passenger of the same age survives. Then, we have that:

$$p_m = \sigma(-1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 0)$$

$$p_f = \sigma(-1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 1)$$

Now, recall from [Lecture 24](https://practicaldsc.org/resources/lectures/lec24/lec24-filled.html#Aside:-Odds) that:

- If $p_i$ is the probability of an event, then the odds of the event are $\frac{p_i}{1 - p_i}$.
- If $p_i = \sigma(t)$, then $t = \sigma^{-1}(p_i) = \log \left( \frac{p_i}{1 - p_i} \right)$. In other words, **the inverse of $p_i = \sigma(t)$ is the log odds of $p_i$, i.e. $\sigma^{-1}(p_i) = \log \left( \text{odds}(p_i) \right)**.

What does this all have to do with the question? Well, we can take the two equations at the start of the solution and apply $\sigma^{-1}$ to both sides, yielding:

$$\sigma^{-1}(p_m) = -1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 0$$

$$\sigma^{-1}(p_f) = -1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 1$$

But, $\sigma^{-1}(p_m) = \log \left( \text{odds}(p_m) \right) = \log(m)$ (using the definition in the problem) and $\sigma^{-1}(p_f) = \log \left( \text{odds}(p_f) \right) = \log(f)$, so we have that:

$$\log(m) = -1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 0$$

$$\log(f) = -1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 1$$

Finally, if we raise both sides to the exponent $e$, we'll be able to directly write $f$ in terms of $m$! Remember that $e^{\log(m)} = m$ and $e^{\log(f)} = f$, assuming that we're using the natural logarithm. Then:

$$m = e^{-1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 0}$$

$$f = e^{-1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 1}$$

So, $f$ in terms of $m$ is:

$$\frac{f}{m} = \frac{e^{-1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 1}}{e^{-1.2 - 0.005 \cdot \text{age} + 2.5 \cdot 0}} = e^{2.5}$$

Or, in other words:

$$\boxed{f = e^{2.5}m}$$

# END SOLN

# END SUBPROB

# END PROB
