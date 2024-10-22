# BEGIN PROB

<i>Source: [Spring 2023 Midterm 1](../sp23-midterm1/index.html), Problem 5</i>

Let $X$ be a design matrix with 4 columns, such that the first column is a column of all $1$s. Let $\vec{y}$ be an observation vector. Let $\vec{w}^* = (X^TX)^{-1}X^T\vec{y}.$ We'll name the components of $\vec{w}^*$ as follows:

$$\vec{w}^* = \begin{bmatrix} w_0^* \\ w_1^* \\ w_2^* \\ w_3^* \end{bmatrix}$$

In this problem, we'll consider various modifications to the design matrix and see how they affect the solution to the normal equations.

# BEGIN SUBPROB

Let $X_a$ be the design matrix that comes from **interchanging the first two columns** of $X$. Let $\vec{w_a}^* = (X_a^TX_a)^{-1}X_a^T\vec{y}$. Express the components $\vec{w_a}^*$ in terms of $w_0^*, w_1^*, w_2^*$, and $w_3^*$ (which were the components of $\vec{w}^*$).

# BEGIN SOLUTION

$$\vec{w_a}^* = \begin{bmatrix} w_1^* \\ w_0^* \\ w_2^* \\ w_3^* \end{bmatrix}$$

Suppose our original prediction rule was of the form: 
$$H(\vec{x}) = w_0 + w_1x_1+ w_2x_2+  w_3x_3.$$ 

Where: 
$$\vec{w_a}^* = \begin{bmatrix} v_0^* \\ v_1^* \\ v_2^* \\ v_3^* \end{bmatrix}$$

By swapping the first two columns of our design matrix, this changes the prediction rule to be of the form: 
$$H_2(\vec{x}) = v_1 + v_0x_1 + v_2x_2+  v_3x_3.$$ 

Therefore the optimal parameters for $H_2$ are related to the optimal parameters for $H$ by:
$$\begin{aligned} v_0^* &= w_1^* \\ v_1^* &= w_0^* \\ v_2^* &= w_2^* \\ v_3^* &= w_3^* \end{aligned}$$

Intuitively, when we interchange two columns of our design matrix, all that does is interchange the terms in the prediction rule, which interchanges those weights in the parameter vector.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Let $X_b$ be the design matrix that comes from **adding one to each entry of the first column** of $X$. Let $\vec{w_b}^* = (X_b^TX_b)^{-1}X_b^T\vec{y}$. Express the components $\vec{w_b}^*$ in terms of $w_0^*, w_1^*, w_2^*$, and $w_3^*$ (which were the components of $\vec{w}^*$).

# BEGIN SOLUTION

$$\vec{w_b}^* = \begin{bmatrix} \dfrac{w_0^*}{2}  \\ w_1^* \\ w_2^* \\ w_3^*\end{bmatrix}$$

Suppose our original prediction rule was of the form:
$$H(\vec{x}) = w_0 + w_1x_1+ w_2x_2+  w_3x_3.$$ 

Where: 
$$\vec{w_b}^* = \begin{bmatrix} v_0^* \\ v_1^* \\ v_2^* \\ v_3^* \end{bmatrix}$$

By adding one to each entry of the first column of the design matrix, we are changing the column of $1$s to be a column of $2$s. This changes the prediction rule to be of the form:
$$H_2(\vec{x}) = v_0\cdot 2+ v_1x_1 + v_2x_2+  v_3x_3.$$

In order to compensate for these changes to our coefficients, we need to "offset" any alterations made to our coefficients. 
Therefore the optimal parameters for $H_2$ are related to the optimal parameters for $H$ by: 
$$\begin{aligned} v_0^* &= \dfrac{w_0^*}{2} \\ v_1^* &= w_1^* \\ v_2^* &= w_2^* \\ v_3^* &= w_3^* \end{aligned}$$

This is saying we just halve the intercept term. For example, imagine fitting a line to data in $\mathbb{R}^2$ and finding that the best-fitting line is $y=12+3x$. If we had to write this in the form $y=v_0\cdot 2 + v_1x$, we would find that the best choice for $v_0$ is $6$ and the best choice for $v_1$ is $3$.

# END SOLUTION

# END SUBPROB 

# BEGIN SUBPROB

Let $X_c$ be the design matrix that comes from **adding one to each entry of the third column** of $X$. Let $\vec{w_c}^* = (X_c^TX_c)^{-1}X_c^T\vec{y}$. Express the components $\vec{w_c}^*$ in terms of $w_0^*, w_1^*, w_2^*$, and $w_3^*$, which were the components of $\vec{w}^*$.

# BEGIN SOLUTION

$$\vec{w_c}^* = \begin{bmatrix} w_0^* - w_2^*  \\ w_1^* \\ w_2^* \\ w_3^* \end{bmatrix}$$

Suppose our original prediction rule was of the form:
$$H(\vec{x}) = w_0 + w_1x_1+ w_2x_2+  w_3x_3.$$ 

Where: 
$$\vec{w_c}^* = \begin{bmatrix} v_0^* \\ v_1^* \\ v_2^* \\ v_3^* \end{bmatrix}$$

By adding one to each entry of the third column of the design matrix, this changes the prediction rule to be of the form: 
$$\begin{aligned} H_2(\vec{x}) &= v_0+ v_1x_1 + v_2(x_2+1)+  v_3x_3 \\ &= (v_0 + v_2) + v_1x_1 + v_2x_2+  v_3x_3 \end{aligned}$$ 

In order to compensate for these changes to our coefficients, we need to "offset" any alterations made to our coefficients. 
Therefore the optimal parameters for $H_2$ are related
to the optimal parameters for $H$ by 
$$\begin{aligned} v_0^* &= w_0^* - w_2^* \\ v_1^* &= w_1^* \\ v_2^* &= w_2^* \\ v_3^* &= w_3^* \end{aligned}$$

One way to think about this is that if we replace $x_2$ with $x_2+1$, then our predictions will increase by the coefficient of $x_2$. In order to keep our predictions the same, we would need to adjust our intercept term by subtracting this same amount.

# END SOLUTION

# END SUBPROB 

# END PROB