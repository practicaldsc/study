# BEGIN PROB

Consider the function $R(h) = \sqrt{(h - 3)^2 + 1} = ((h - 3)^2 + 1)^{\frac{1}{2}}$, which is a convex and differentiable function with only one local minimum.

# BEGIN SUBPROB

Perform by hand two iterations of the gradient descent algorithm on this function, using an initial prediction of $h^{(0)} = 2$ and a learning rate of $\alpha = 2\sqrt{2}$. Show your work and your final answers, $h^{(1)}$ and $h^{(2)}$.

# BEGIN SOLN

$$h^{(1)} = 4, h^{(2)} = 2$$

The updating rule for gradient descent in the one-dimensional case is:
$$h^{(t+1)} = h^{(t)} - \alpha \cdot \frac{dR}{dh}(h^{(t)})$$

We can find $\frac{dR}{dh}$ by taking the derivative of $R(h)$:
$$\frac{d}{dh}R(h) = \frac{d}{dh}(\sqrt{(h - 3)^2 + 1}) = \dfrac{h-3}{\sqrt{\left(h-3\right)^2+1}}$$

Now we can use $\alpha = 2\sqrt{2}$ and $h^{(0)} = 2$ to begin updating:

$$\begin{align*}
h^{(1)} &= h^{(0)} - \alpha \cdot \frac{dR}{dh}(h^{(0)}) \\
h^{(1)} &= 2 - 2\sqrt{2} \cdot \left(\dfrac{2-3}{\sqrt{\left(2-3\right)^2+1}}\right) \\
h^{(1)} &= 2 - 2\sqrt{2} \cdot (\dfrac{-1}{\sqrt{2}}) \\
h^{(1)} &= 4
\end{align*}$$
<br>
$$\begin{align*}
h^{(2)} &= h^{(1)} - \alpha \cdot \frac{dR}{dh}(h^{(1)}) \\
h^{(2)} &= 4 - 2\sqrt{2} \cdot \left(\dfrac{4-3}{\sqrt{\left(4-3\right)^2+1}}\right) \\
h^{(2)} &= 4 - 2\sqrt{2} \cdot (\dfrac{1}{\sqrt{2}}) \\
h^{(2)} &= 2
\end{align*}$$

# END SOLN

# END SUBPROB

# BEGIN SUBPROB

With more iterations, will we eventually converge to the minimizer? Explain.

# BEGIN SOLN

No, this algorithm will not converge to the minimizer because if we do more iterations, we’ll keep oscillating back and forth between predictions of 2 and 4. We showed the first two iterations of the algorithm in part 1, but the next two would be exactly the same, and the two after that, and so on. This happens because the learning rate is too big, resulting in steps that are too big, and we keep jumping over
the true minimizer at $h^* = 3$.

# END SOLN

# END SUBPROB

# END PROB