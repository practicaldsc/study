# BEGIN PROB

You have a classification data set consisting of two $(x, y)$ pairs $(1, 0)$ and $(-1, 1)$.
The covariate vector $\vec{x}$ for each pair is a two-element column vector \left[1 \quad x\right]^T$.
You run an algorithm to fit a model for the probability of $Y=1$ given $\vec{x}$:
$$\mathbb{P}({Y=1|}{\vec{x}}) = \sigma(\vec{x}^T \theta)$$

where $$\sigma(t) = \frac{1}{1 + \exp(-t)}$$

Your algorithm returns $\hat\theta = \left[-\frac{1}{2} \quad -\frac{1}{2}\right]^T$

# BEGIN SUBPROB

Calculate $\hat{\mathbb{P}}({Y=1|}{\vec{x}=\left[1 \quad   0\right]^T})$
# BEGIN SOLN
**Answer:** 
\begin{align*}
			\hat{\mathbb{P}}({Y=1|}{\vec{x}=[1 \quad 0]^T}) 
			&= \sigma\left(\begin{bmatrix}1 & 0\end{bmatrix} \begin{bmatrix}-\frac{1}{2} \\ -\frac{1}{2}\end{bmatrix}\right) \\
			&= \sigma\left(1 \cdot -\frac{1}{2} + 0 \cdot -\frac{1}{2}\right) \\
			&= \sigma\left(-\frac{1}{2}\right) \\
			&= \dfrac{1}{1 + \exp(\frac{1}{2})} \\
			&\approx 0.38
		\end{align*}
# END SOLN

# END SUBPROB

# BEGIN SUBPROB
The empirical risk using log loss (a.k.a., cross-entropy loss) is given by the following expression. Remember, whenever you see $\log$ in this course, you must assume the natural logarithm (base-$e$), unless explicitly told otherwise.
	\begin{align*}
		R(\theta) &= \dfrac{1}{n} \sum_{i=1}^{n} - \log \hat{\mathbb{P}}({Y=y_i|}{\vec{x_i}}) \\
		&= -\dfrac{1}{n} \sum_{i=1}^{n} y_i \log \hat{\mathbb{P}}({Y=1|}{\vec{x_i}}) + (1-y_i) \log  \hat{\mathbb{P}}({Y=0|}{\vec{x_i}})
	\end{align*}
	And $\hat{\mathbb{P}}({Y=1|}{\vec{x_i}}) = \sigma\left(\vec{x_i}^T\theta\right) = \frac{1}{1 + \exp\left(-\vec{x_i}^T\theta\right)} = \frac{\exp\left(\vec{x_i}^T\theta\right)}{1+\exp\left(\vec{x_i}^T\theta\right)}$ while $\hat{\mathbb{P}}({Y=0|}{\vec{x_i}}) = 1- \hat{\mathbb{P}}({Y=1|}{\vec{x_i}}) = 1 - \frac{\exp\left(\vec{x_i}^T\theta\right)}{1+\exp\left(\vec{x_i}^T\theta\right)} = \frac{1}{1+\exp\left(\vec{x_i}^T\theta\right)}$. Therefore,
	\begin{align*}
		R(\theta) &=  -\dfrac{1}{n} \sum_{i=1}^{n} y_i \log \frac{\exp\left(\vec{x_i}^T\theta\right)}{1+\exp\left(\vec{x_i}^T\theta\right)} + (1-y_i) \log \frac{1}{1+\exp\left(\vec{x_i}^T\theta\right)} \\
		&= -\dfrac{1}{n} \sum_{i=1}^{n} y_i \vec{x}_i^T\theta + \log(\sigma(-\vec{x}_i^T\theta)) \\
	\end{align*}
	Let $\theta = \left[\theta_0 \quad \theta_1 \right]$.  Explicitly write out the empirical risk for the data set $(1, 0)$ and $(-1, 1)$ as a function of $\theta_0$ and $\theta_1$.

# BEGIN SOLN
**Answer:**
$$ \vec{x_i}^T \theta 
		= \begin{bmatrix}1 & x_i\end{bmatrix} \begin{bmatrix}\theta_0 \\ \theta_1\end{bmatrix} 
		= \theta_0 + \theta_1 x_i
		$$
		For the data point $(1, 0)$, $\vec{x}_i = [1 \quad 1]^T$ and $y_i = 0$, so:
		$$y_i \vec{x}_i^T\theta = 0$$
		$$-\vec{x}_i^T\theta = -(\theta_0 + \theta_1 \cdot 1) = -\theta_0 - \theta_1 $$
		For the data point $(-1, 1)$:
		$$y_i\vec{x_i}^T\theta = 1 \cdot (\theta_0 + \theta_1 \cdot -1) = \theta_0 - \theta_1 $$
		$$-\vec{x_i}^T\theta = -(\theta_0 + \theta_1 \cdot -1) = -\theta_0 + \theta_1 $$
		We can then write the empirical risk as:
		\begin{align*}
		R(\theta) &= -\dfrac{1}{2} \left[
		\left(0 + \log\sigma(-\theta_0 - \theta_1)\right)
		+ \left(\theta_0 - \theta_1 + \log\sigma(-\theta_0 + \theta_1)\right)
		\right] \\
		&= -\frac{1}{2} \left[\theta_0 - \theta_1 + \log\sigma(-\theta_0 - \theta_1) + \log\sigma(-\theta_0 + \theta_1) \right]\\
		&= -\frac{1}{2} \left[\theta_0 - \theta_1 
		    + \log\left(\frac{1}{1 + \exp(\theta_0 + \theta_1)}\right) 
		    + \log\left(\frac{1}{1 + \exp(\theta_0 - \theta_1)}\right)\right] \\
		&= \frac{1}{2} \left[\theta_1 - \theta_0 
		    + \log\left(1 + \exp(\theta_0 + \theta_1)\right) 
		    + \log\left(1 + \exp(\theta_0 - \theta_1)\right)\right]
		\end{align*}
# END SOLN

# END SUBPROB

# BEGIN SUBPROB
Calculate the empirical risk for $\hat\theta = \left[-\frac{1}{2} \quad -\frac{1}{2}\right]^T$ and the two observations $(1, 0)$ and $(-1, 1)$.

# BEGIN SOLN
**Answer:** 
\begin{align*}
		R(\hat\theta) 
		&= \frac{1}{2} \left[\theta_1 - \theta_0 
		    + \log\left(1 + \exp(\theta_0 + \theta_1)\right) 
		    + \log\left(1 + \exp(\theta_0 - \theta_1)\right)\right] \\
		&= \frac{1}{2}\left[
		    -\frac{1}{2} - \left(-\frac{1}{2}\right)
		    + \log\left(1 + \exp(-\frac{1}{2} + -\frac{1}{2})\right) 
		    + \log\left(1 + \exp(-\frac{1}{2} - -\frac{1}{2})\right) 
		    \right] \\
	    &= \frac{1}{2}\left[
	        0
	        + \log\left(1 + \exp(-1)\right) 
	        + \log\left(1 + \exp(0)\right)
	        \right] \\
	    &= \frac{1}{2} \log(2+2e^{-1})
		\end{align*}
# END SOLN

# END SUBPROB


# END PROB
