# BEGIN PROB

Consider the function $R(h) = \sqrt{(h - 3)^2 + 1} = ((h - 3)^2 + 1)^{\frac{1}{2}}$, which is a convex and differentiable function with only one local minimum.

# BEGIN SUBPROB

Perform by hand two iterations of the gradient descent algorithm on this function, using an initial prediction of $h_0 = 2$ and a learning rate of $\alpha = 2\sqrt{2}$. Show your work and your final answers, $h_1$ and $h_2$.

# BEGIN SOLN

$$h_1 = 4, h_2 = 2$$

The updating rule for gradient descent in the one-dimensional case is:
$$h_{i+1} = h_{i} - \alpha \cdot \frac{dR}{dh}(h_i)$$

We can find $\frac{dR}{dh}$ by taking the derivative of $R(h)$:
$$\frac{d}{dh}R(h) = \frac{d}{dh}(\sqrt{(h - 3)^2 + 1}) = \dfrac{h-3}{\sqrt{\left(h-3\right)^2+1}}$$

Now we can use $\alpha = 2\sqrt{2}$ and $h_0 = 2$ to begin updating:

$$\begin{align*}
h_{1} &= h_{0} - \alpha \cdot \frac{dR}{dh}(h_0) \\
h_{1} &= 2 - 2\sqrt{2} \cdot \left(\dfrac{2-3}{\sqrt{\left(2-3\right)^2+1}}\right) \\
h_{1} &= 2 - 2\sqrt{2} \cdot (\dfrac{-1}{\sqrt{2}}) \\
h_{1} &= 4
\end{align*}$$
<br>
$$\begin{align*}
h_{2} &= h_{1} - \alpha \cdot \frac{dR}{dh}(h_1) \\
h_{2} &= 4 - 2\sqrt{2} \cdot \left(\dfrac{4-3}{\sqrt{\left(4-3\right)^2+1}}\right) \\
h_{2} &= 4 - 2\sqrt{2} \cdot (\dfrac{1}{\sqrt{2}}) \\
h_{2} &= 2
\end{align*}$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

With more iterations, will we eventually converge to the minimizer? Explain.

# BEGIN SOLN

No, this algorithm will not converge to the minimizer because if we do more iterations, we’ll keep oscillating back and forth between predictions of 2 and 4. We showed the first two iterations of the algorithm in part 1, but the next two would be exactly the same, and the two after that, and so on. This happens because the learning rate is too big, resulting in steps that are too big, and we keep jumping over
the true minimizer at $h = 3$.

# END SOLN

# END SUBPROB

# END PROB